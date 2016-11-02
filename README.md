# e首發票 API 說明文件

此文件主要為e首發票 API 相關說明文件，內容以 2016-10 月矽聯科技定義之API為說明範本，程式仍以目前釋出版本為主。

**請注意**
e首發票 API 主要分為兩種，這兩種將對應到不同的站台提供服務。

* 拋入訂單由e首發票進行發票開立與後續整合作業(訂單版)

  ```
  採用SOAP的方式傳送，以 SoapHeader 認證
  訂單版e首發票 API 測試區串接位置：
  http://web.systemlead.com/EasyCartAdmin/api/invoiceService.asmx
  相關說明文件，可參閱 https://github.com/SL-PD/e-Invoice_API 說明
  ```

* 拋入已開立發票由e首發票進行後續整合作業(發票版)
```
  採用的是HTTP POST的方式傳送，以 SHA256簽章值 驗證
  發票版e首發票 API 測試區串接位置：
  http://web2.systemlead.com/EINV2API/api/einv/
  其版本與正式區相符，惟正式區網址，待測試區測通後，將由業務人員提供。
```  
 