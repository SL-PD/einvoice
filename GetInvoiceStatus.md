# 查詢發票上傳狀態

此處查詢上傳狀態指的是由e首發票加值中心將發票上傳至整合服務平台的狀態

查詢單筆發票上傳狀態 (使用 Http Get)
```
http://tserv.youshop.com.tw/api/einv/GetInvoiceStatus?InvoiceID={發票號碼}
```
如果回傳為NULL則表示尚未進行上傳動作。(測試區皆會回傳NULL)

查詢多筆發票上傳狀態 (使用 Http Post) <br />
**注意：名稱差異單筆為Invoice 多筆為Invoices

```
http://tserv.youshop.com.tw/api/einv/GetInvoicesStatus
```
Post Json值
```
[{"InvoiceID":"{發票號碼1}"},{"InvoiceID":"{發票號碼2}"}]
```

傳回值內容為：中斷、處理中、上傳失敗、待確認、上傳完成 五種，當發票上傳至e首發票後1個小時後若查詢結果非為上傳完成，可主動通知e首發票協助處理。若發票上傳失敗，e首發票會將通知更正發票內容後重新上傳。
