# 上傳已開立發票 AppendInvoice


上傳已開立發票前，需要先與業務人員**確認帳號已建立完成**，並取得**專屬加密Salt**一組，以便後續上傳作業之進行。


### 相關說明

發票以單張發票上傳方式進行，採用HttpPost方式傳送，傳送內容為JSON格式，資料說明如下：

```
{
	"CompanyID":"89430377",
	"Timestamp":"1477585655",
    "Signature":"89C480C1E4ACD1FD06C08D364404D74C014EEEDCDD8FE026EA2018B311A96D16",
	"Data":{"COMPANY_ID":"89430377","Invoice_ID":"AA12345678","Invoice_DateTime":"2016-10-27T16:27:34.7258383+08:00","BUYER_ID":"0000000000","BUYER_NAME":"Name","BUYER_ADDRESS":null,"Buyer_TelNo":"077190888","Buyer_Email":"nestor@systemlead.com","CheckNumber":null,"RelateNumber":"訂單編號","Invoice_Type":null,"CARRIER_TYPE":null,"CARRIER_ID1":null,"CARRIER_ID2":null,"PrintMark":"0","DONATE_MARK":"0","NPOBAN":null,"RandomNumber":"3716","SALES_AMOUNT":5238.0,"FreeTaxSalesAmount":0.0,"ZeroTaxSalesAmount":0.0,"TAX_TYPE":"1","TAX_RATE":0.0,"TAX_AMOUNT":262.0,"TOTAL_AMOUNT":5500.0,"InvoiceType":null,"ORDER_ID":null,"ORDER_DATE":null,"ORDER_SOURCE":null,"Details":[{"DETAIL_ID":"001","PRODUCT_ID":"P1234","PRODUCT_NAME":"產品名稱","QUANTITY":5.0,"UNIT_PRICE":100.0,"SubTotal":500.0,"Remark":null},{"DETAIL_ID":"002","PRODUCT_ID":"P2345","PRODUCT_NAME":"長度256個字","QUANTITY":2.0,"UNIT_PRICE":500.0,"SubTotal":1000.0,"Remark":null},{"DETAIL_ID":"003","PRODUCT_ID":"P3456","PRODUCT_NAME":"明細編號3碼","QUANTITY":4.0,"UNIT_PRICE":1000.0,"SubTotal":4000.0,"Remark":null}]}
}
```
* CompanyID: 請傳入使用e首發票的公司統編
* Timestamp: 請傳入 Unix Timestamp 相關轉換請參考 [[http://www.epochconverter.com/](http://www.epochconverter.com/)]
* Signature: 簽章驗證值，為SHA256加密之所產生之驗證值。產生方法可參閱[簽章驗證碼](signature.md)說明。
* Data: 發票資料。發票內容可參閱發票格式說明。

 

