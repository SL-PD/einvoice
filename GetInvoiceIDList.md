# 查詢發票字軌與期號

查詢e首發票下載之發票字軌與期號(使用 Http Post) 
此功能僅提供查詢客戶授權e首發票下載之發票字軌及期號

```
http://web2.systemlead.com/EINV2API/api/einv/GetInvoiceIDList
```
Post Json值
```
查詢單一期別
{"CompanyID":"公司統編","StageYear":"查詢年度","StageMonth":"查詢期別(偶數月)"}

查詢一整年度
{"CompanyID":"公司統編","StageYear":"查詢年度"}
```