# 發票上傳格式 B2B

發票內容分為發票單頭與發票單身兩個部分：範例說明

B2B

發票單頭

* CompanyID: 賣方統扁\(必須為e首發票客戶\)
* InvoiceID: 發票號碼
* InvoiceDateTime: 發票開立時間，請採用 ISO 8601 格式傳遞 例如： `2011-07-14T19:43:37+0100`
* BuyerID: 買方統編
* BuyerName: 買方公司名稱
* BuyerTelNo: 買方電話號碼，若要傳送簡訊則此欄位填寫行動電話號碼
* BuyerEmail: 買方電子郵件帳號，此欄位與\[買方電話號碼\]兩者必填其一，否則電子發票通知無法寄送
* CheckNumber: 檢查碼 B2B 發票上必須列印四碼檢查碼\(隨機四碼\)，且檢查碼必須與上傳至整合服務平台相同
* RelateNumber: 關聯號碼，e首發票中可用來帶入關聯的訂單號碼
* InvoiceFor: 發票開立對象，在B2B中填寫B，表示採用B2B存證模式開立
* DonateMark: 是否捐贈發票，設定為 N 若設定為 Y 則需填 NPOBAN
* NPOBAN: 捐贈愛心碼，請完整填入3-7碼愛心碼。
* SalesAmount: 銷售未稅總額
* TaxAmount: 總稅額
* TotalAmount: 總金額\(銷售未稅總額+總稅額\); 型別Decimal\(12,0\)
* Details: 單身明細

發票單身

* DetailID: 三碼數字編碼，依序 001 002 不足三碼左邊補 0
* ProductID: 產品代碼
* ProductName: 產品名稱
* Quantity: 數量; 型別Decimal\(17,4\)
* UnitPrice: 單價; 型別Decimal\(17,4\)
* SubTotal: 小計; 型別Decimal\(17,4\) 

