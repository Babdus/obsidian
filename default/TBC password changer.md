#### Before changing password

1. Turn of 116 machine
2. Turn of local machine
3. comment out TBC jobs in app.py
4. restart docker
5. switch off F1 TBC jobs:
	1. Update transactions
	2. აყვანები 100-იანი
	3. არასწორი ...
#### Change password

###### IMPOTRTANT! Use below code for each user from start to finish

```
ssh bank@192.168.2.119
4QDYA2BKeK475EcCXy7
```

```
docker exec -it swissCap__app bash
python3
```

```
import requests

# CERT_PATH="/app/Docker/certification_files/cert.pem"
# PFX_FILE="/app/Docker/certification_files/JSC_MFO_SWISS_CAPITAL.pfx"
# KEY_PATH="/app/Docker/certification_files/key.pem"

CERT_PATH="Docker/certification_files/cert.pem"
PFX_FILE="Docker/certification_files/JSC_MFO_SWISS_CAPITAL.pfx"
KEY_PATH="Docker/certification_files/key.pem"

TBC_WITHIN_BANK_PAYMENT_PAYLOAD = {
	"url": "https://secdbi.tbconline.ge/dbi/dbiService",
	"headers": {
		'Content-Type': 'text/xml; charset=utf-8',
		'SOAPAction': 'http://www.mygemini.com/schemas/mygemini/ChangePassword'
	},
	"payload":
		'''
        <soapenv:Envelope
	        xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/"
			xmlns:myg="http://www.mygemini.com/schemas/mygemini"
			xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
			<soapenv:Header>
				<wsse:Security>
					<wsse:UsernameToken>
					    <wsse:Username>{}</wsse:Username>
					    <wsse:Password>{}</wsse:Password>
					    <wsse:Nonce>{}</wsse:Nonce>
				    </wsse:UsernameToken>
				</wsse:Security>
			</soapenv:Header>
			<soapenv:Body>
				<myg:ChangePasswordRequestIo>
					<myg:newPassword>{}</myg:newPassword>
				</myg:ChangePasswordRequestIo>
			</soapenv:Body>
		</soapenv:Envelope>
		'''
}

TBC_WITHIN_BANK_PAYMENT_PAYLOAD['payload'] = TBC_WITHIN_BANK_PAYMENT_PAYLOAD['payload'].format('MURVANIDZE_1', 'Givi55Random!Pass', '427376', 'Givi77Random!Pass')

url = TBC_WITHIN_BANK_PAYMENT_PAYLOAD["url"]
payload = TBC_WITHIN_BANK_PAYMENT_PAYLOAD["payload"]
headers = TBC_WITHIN_BANK_PAYMENT_PAYLOAD["headers"]

response = requests.post(url, data=payload, headers=headers, cert=(CERT_PATH, KEY_PATH), verify=True)
```
#### After changing password

1. uncomment TBC jobs in app.py
2. Change password in .env.certificates
3. restart docker
4. switch on F1 TBC jobs:
	1. Update transactions
	2. აყვანები 100-იანი
	3. არასწორი ...
5. Turn on 116 machine