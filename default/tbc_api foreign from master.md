def transfer_within_bank_account_foreign(self, data: ForeignTransactionTBC):  
  
    # db = SessionLocal()  
    # db_item = Transaction(**kwargs)    # db.add(db_item)    # db.commit()    # db.refresh(db_item)  
    try:  
        url, headers, payload = TBC_WITHIN_BANK_PAYMENT_FOREIGN_PAYLOAD.values()  
  
        formatted_payload = payload.format(  
            TBC_ACCOUNTS_DATA.get(data.sc_account_number),  
            self.__password,  
            1111,  
            data.partner_account_number,  
            data.sc_account_number,  
            data.currency_code,  
            data.amount,  
            data.currency,  
            data.additional_description,  
            data.description,  
            data.beneficiary_name,  
            data.beneficiary_tax_code  
        )  
  
        logger.info(f'\033[35;1mSending payload \033[0;95m{formatted_payload}\033[35;1m to \033[0;95m{url}\033[0m')  
  
        response = requests.post(  
            url, data=formatted_payload.encode('utf-8'), headers=headers,  
            cert=(self.cert_path, self.key_path), verify=True  
        )  
  
        # print("TBC KWARGS - ", data)  
        # print("TBC TRANSFERING - ", response)        # print("TBC RESPONSE CONTENT - ", response.content)        # print("FORMATTED PAYLOAD - ", formatted_payload)  
        logger.info(  
            f"\033[34;1mTBC foreign transaction successfully created! \033[0;34m{response.content}\033[0m",  
        )  
  
        xml_data = response.content.decode('utf-8')  
  
        root = Et.fromstring(xml_data)  
  
        if root.find(".//faultcode") is not None or root.find(".//faultstring") is not None:  
            fault_code = root.find(".//faultcode")  
            fault_code = fault_code.text if fault_code is not None else ""  
  
            fault_string = root.find(".//faultstring")  
            fault_string = fault_string.text if fault_string is not None else ""  
  
            return {"message": f"{fault_code} {fault_string}"}  
  
        response_content = {  
            "message": "სერთიფიკატის მოლოდინში",  
            "payment_id": root.find(self.headset + "paymentId").text  
        }  
  
        return response_content  
  
    except requests.HTTPError as e:  
        logger.error(f"HTTP error: {e.response.status_code} - {e.response.text}")  
        return {"message": f"HTTP error: {e.response.status_code} - {e.response.text}"}  
    except requests.RequestException as e:  
        logger.error(f"Request error: {e}")  
        return {"message": f"Request error: {e}"}  
    except Exception as e:  
        logger.error(f"Unexpected error: {e}")  
        return {"message": f"Unexpected error: {e}"}