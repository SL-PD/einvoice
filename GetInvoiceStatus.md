# 查詢發票上傳狀態

此處查詢上傳狀態指的是由e首發票加值中心將發票上傳至整合服務平台的狀態

單筆查詢 
```
http://web2.systemlead.com/EINV2API/api/einv/GetInvoiceStatus?InvoiceID={發票號碼}
```
如果回傳為NULL則表示尚未進行上傳動作。(測試區皆會回傳NULL)

多筆查詢