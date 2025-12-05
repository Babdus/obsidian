# TBC API connection
## Things to ask TBC to give you
1. Certificate file in CERT.pfx format
2. Password for that certificate
3. Registered user with the GET permission from API (`username`)
4. Password for that user (`password`)
## Setup
### Certificate
Replace CERT.pfx and PASSWORD with your actual certificate and it's password
```bash
openssl pkcs12 -in CERT.pfx -nocerts -out key.pem -nodes -password pass:PASSWORD
openssl pkcs12 -in CERT.pfx -nokeys -out cert.pem -password pass:PASSWORD
openssl rsa -in key.pem -out key_unencrypted.pem
openssl x509 -in cert.pem -out server_cert.pem
```
You will get `server_cert.pem` and `key_unencrypted.pem` which you'll use afterwards
### Data
You will need to have these things saved somewhere:
#### username
```python
username = 
```
#### password
```python
password = 
```
#### url
```python
url = "https://secdbi.tbconline.ge/dbi/dbiService"  
```
#### headers
```python
headers = {  
    'Content-Type': 'text/xml; charset=utf-8',  
    'SOAPAction': 'http://www.mygemini.com/schemas/mygemini/GetAccountMovements'  
}
```
#### default payload
```python
default_payload = '''
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:myg="http://www.mygemini.com/schemas/mygemini" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <soapenv:Header>
	    <wsse:Security>
		    <wsse:UsernameToken>
			    <wsse:Username>{username}</wsse:Username>
			    <wsse:Password>{password}</wsse:Password>
			    <wsse:Nonce>{digipass}</wsse:Nonce>
			</wsse:UsernameToken>
		</wsse:Security>
	</soapenv:Header>
	<soapenv:Body>
		<myg:GetAccountMovementsRequestIo>
			<myg:accountMovementFilterIo>
				<myg:accountNumber>{account_number}</myg:accountNumber>
				<myg:accountCurrencyCode>{currency}</myg:accountCurrencyCode>
				<myg:periodFrom>{start_datetime}</myg:periodFrom>
				<myg:periodTo>{end_datetime}</myg:periodTo>
			</myg:accountMovementFilterIo>
		</myg:GetAccountMovementsRequestIo>
	</soapenv:Body>
</soapenv:Envelope>
'''
```
#### namespaces
```python
namespaces = {
	'ns2': 'http://www.mygemini.com/schemas/mygemini'
}
```
## API call
```python
import requests
import xml.etree.ElementTree as Et
import xmltodict
import json


def remove_namespaces(data):
	if isinstance(data, dict):
		return {key.split(':')[-1]: remove_namespaces(value) for key, value in data.items()}
	elif isinstance(data, list):
		return [remove_namespaces(item) for item in data]
	else:
		return data


def get_transactions(
	account_number: str,
	currency: str,       # format: 'GEL'
	start_datetime: str, # format: 2025-04-21T00:00:00.000
	end_datetime: str    # format: 2025-04-21T23:59:59.999
):
	payload = default_payload.format(
        username=username,
        password=password,
        digipass=1111, # Don't know why it works with constant value
        account_number=account_number,
        currency=currency,
        start_datetime=start_datetime,
        start_datetime=start_datetime
    )
    
    response = requests.post(
	    url,
	    data=payload,
	    headers=headers,
	    cert=('server_cert.pem', 'key_unencripted'),
	    verify=True
	)
	
	xml_response = response.content.decode('utf-8')
	
	root_node = Et.fromstring(xml_response)
	
	parent_node = root_node.find(
		'.//ns2:result',
		namespaces=namespaces
	)
	
	account_movements = list(
		parent_node.findall(
			'.//ns2:accountMovement',
			namespaces=namespaces
		)
	)
	
	string_xml = Et.tostring(
		root_node,
		encoding='unicode'
	)
	
	data = xmltodict.parse(string_xml)
	
	cleaned_data = remove_namespaces(data)
	
	json_data = json.dumps(
		cleaned_data,
		indent=4,
		ensure_ascii=False
	)
	
	return json_data
```