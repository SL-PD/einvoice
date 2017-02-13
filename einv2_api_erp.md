# 發票版e首發票 API

發票版e首發票，提供[e首發票用戶上傳發票](einv2_api_erp)、作廢發票、查詢發票傳送狀態等API串接功能。並且配合整合服務提供：

* 主動發送電子郵件或簡訊通知信給予買受人\(須提供買受人之電子郵件或行動電話號碼\)
* 提供線上檢閱電子發票明細
* 提供商業客戶自行下載與列印發票憑證
* 提供e首發票用戶於即時列印發票\(選購\)
* 協助e首發票用戶寄送客戶中獎發票服務\(選購\) 

### 發票API說明：

**範本類**：

開立B2C存證發票內容範本 (使用 Http Get)

```
http://tserv.youshop.com.tw/api/einv/B2CSample
```

開立B2B存證發票內容範本 (使用 Http Get)

```
http://tserv.youshop.com.tw/api/einv/B2BSample
```

發票上傳範本 (使用 Http Get)

```
http://tserv.youshop.com.tw/api/einv/AppendInvoiceSample
```

發票作廢上傳範本 (使用 Http Get)

```
http://tserv.youshop.com.tw/api/einv/CancelInvoiceSample
```

**功能類**：

發票上傳 (使用 Http Post)

```
http://tserv.youshop.com.tw/api/einv/AppendInvoice
```

發票作廢上傳 (使用 Http Post)

```
http://tserv.youshop.com.tw/api/einv/CancelInvoice
```

查詢單筆發票上傳狀態 (使用 Http Get)

```
http://tserv.youshop.com.tw/api/einv/GetInvoiceStatus
```

查詢多筆發票上傳狀態 (使用 Http Post) <br />
**注意：名稱差異單筆為Invoice 多筆為Invoices

```
http://tserv.youshop.com.tw/api/einv/GetInvoicesStatus
```

查詢e首發票下載之發票字軌與期號 (使用 Http Post)

```
http://tserv.youshop.com.tw/api/einv/GetInvoiceIDList
```

更新空白發票 (使用 Http Post)

```
http://tserv.youshop.com.tw/api/eInv/SetBlankInvoiceID
```


**驗證類**：

測試發票簽章是否正確 (使用 Http Post)

```
http://tserv.youshop.com.tw/api/eInv/AppendInvoiceTest
```

