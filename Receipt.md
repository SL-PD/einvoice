# Invoice Format
---

### 發票單頭

|欄位名稱|欄位說明|欄位型態|欄位長度|B2B|B2C|條件說明|
|--|
|CompanyID|Seller BAN|String|10|M|M|賣方統編(必須為e首發票客戶)|
|InvoiceID|Invoice Number|String|10|M|M|發票字軌含流水號例如 QQ12345678|
|InvoiceDateTime|Invoice Create DateTime|DateTime||M|M|發票開立時間，請採用ISO 8601格式傳遞 例如：<br /> 2011-07-14T19:43:37+0100|
|BuyerID|Buyer BAN|String|10|M|M|買方統編[^Ref.1]|
|BuyerName||||||買方公司名稱|
|BuyerTelNo||||||買方電話號碼，若要傳送簡訊則此欄位填寫行動電話號碼|
|BuyerEmail||||||買方電子郵件帳號，此欄位與[買方電話號碼]兩者必填其一，否則電子發票通知無法寄送|
|CheckNumber||||||檢查碼 B2B 發票上必須列印四碼檢查碼(隨機四碼)，且檢查碼必須與上傳至整合服務平台相同|
|RelateNumber||||||關聯號碼，e首發票中可用來帶入關聯的訂單號碼|
|InvoiceFor||||||發票開立對象，在B2B中填寫B，表示採用B2B存證模式開立|
|DonateMark||||||是否捐贈發票，僅能為N|
|NPOBAN||||||僅能為NULL|
|SalesAmount||||||銷售未稅總額;(明細小計總額)|
|TaxAmount||||||總稅額|
|TotalAmount||||||總金額(銷售未稅總額+總稅額); 型別Decimal(12,0)|
|Details||||||單身明細[^Detail]|

### 發票單身[^Detail]
|欄位名稱|欄位說明|欄位型態|欄位長度|B2B|B2C|條件說明|
|--|
|DetailID||||||三碼數字編碼，依序 001 002 不足三碼左邊補 0|
|ProductID||||||產品代碼|
|ProductName||||||產品名稱|
|Quantity||||||數量; 型別Decimal(17,4)|
|UnitPrice||||||未稅單價; 型別Decimal(17,4)|
|SubTotal||||||未稅小計; 型別Decimal(17,4)|

---
[^Ref.1]



