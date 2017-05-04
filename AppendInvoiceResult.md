### Append Invoice Result

|欄位名稱|欄位說明|欄位型態|說明|
|--|
|InvoiceID|Invoice Number|String|發票字軌含流水號例如 QQ12345678|
|InvoiceDateTime|Invoice Create DateTime|DateTime|發票開立時間，請採用ISO 8601格式傳遞 例如：<br /> 2011-07-14T19:43:37+0100|
|AuthCode|Invoice Report AuthCode|String|當發票開立成功時，此欄位會回傳AuthCode，可以透過發票檢視網址加上AuthCode 即可檢視發票，發票檢視網址：<br />http://serv.youshop.com.tw/Report/GetInvoice/{AuthCode}|
|Message|Error Message|String|當發票開立發生錯誤時，此欄位有錯誤訊息，若正確則回傳空值|

### Success Result Sample
```
[
    {
        "InvoiceID":"AA12345678",
        "Invoice_DateTime":"2016-10-27T16:27:34.7258383+08:00",
        "AuthCode":"B36EB45F-F77C-4A8A-A13D-3F3B12957746",
        "Message":""
    },
    {
        "InvoiceID":"AA12345679",
        "Invoice_DateTime":"2016-10-27T16:28:34.7258383+08:00",
        "AuthCode":"2272CC24-5D2D-45ED-B837-189B9221EC5E",
        "Message":""
    }    
]
```
### Fail Result Sample
```
[
    {
        "InvoiceID":"AA12345680",
        "Invoice_DateTime":"2016-10-27T16:29:34.7258383+08:00",
        "AuthCode":"",
        "Message":"Signature Fail"
    },
    {
        "InvoiceID":"AA12345681",
        "Invoice_DateTime":"2016-10-27T16:30:34.7258383+08:00",
        "AuthCode":"4D355175-40BA-4F17-BC6E-BA38EA119014",
        "Message":""
    }

]
```





