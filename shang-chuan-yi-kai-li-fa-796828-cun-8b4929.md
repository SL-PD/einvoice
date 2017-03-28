# 上傳已開立與作廢發票 AppendInvoice or CancelInvoice


上傳已開立發票前，需要先與業務人員**確認帳號已建立完成**，並取得**專屬加密Salt**一組，以便後續上傳作業之進行。


### 相關說明

```
[{
    "CompanyID":"89430377",
    "Timestamp":"1477585655",
    "Signature":"89C480C1E4ACD1FD06C08D364404D74C014EEEDCDD8FE026EA2018B311A96D16",
    "Data": {發票資料}
}]
```
* CompanyID: 請傳入使用e首發票的公司統編
* Timestamp: 請傳入 Unix Timestamp 相關轉換請參考 [[http://www.epochconverter.com/](http://www.epochconverter.com/)]
* Signature: 簽章驗證值，為SHA256加密之所產生之驗證值。產生方法可參閱[簽章驗證碼](signature.md)說明。
* Data: 發票資料。發票內容可參閱發票格式說明。

發票資料範本
* B2B發票範例
* B2C發票範例

