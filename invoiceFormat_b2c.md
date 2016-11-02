# 發票上傳格式 B2C

發票內容分為發票單頭與發票單身兩個部分：範例說明

B2C

發票單頭

* CompanyID: 賣方統編\(必須為e首發票客戶\)
* InvoiceID: 發票號碼
* InvoiceDateTime: 發票開立時間，請採用 ISO 8601 格式傳遞 例如： `2011-07-14T19:43:37+0100`
* BuyerID: 買方統編(一般使用者請傳 `0000000000` 10個0) 
* BuyerName: 買方名稱
* BuyerTelNo: 買方電話號碼，若要傳送簡訊則此欄位填寫行動電話號碼
* BuyerEmail: 買方電子郵件帳號，此欄位與\[買方電話號碼\]兩者必填其一，否則電子發票通知無法寄送
* RandomNumber: 檢查碼 B2C 發票上必須列印四碼隨機碼，且隨機碼必須與上傳至整合服務平台相同
* RelateNumber: 關聯號碼，e首發票中可用來帶入關聯的訂單號碼
* InvoiceFor: 發票開立對象，在B2C中填寫C，表示採用B2C存證模式開立
* PrintMark: 如果有列印發票，請填 Y 否則填 N
* DonateMark: 是否捐贈發票，設定為 N 若設定為 Y 則需填 NPOBAN
* NPOBAN: 捐贈愛心碼，請完整填入3-7碼愛心碼。
* SalesAmount: 銷售含稅總額\(明細小計總額\)
* TaxAmount: 總稅額為0
* TotalAmount: 總金額\(銷售含稅總額+總稅額\); 型別Decimal\(12,0\)
* Details: 單身明細

發票單身

* DetailID: 三碼數字編碼，依序 001 002 不足三碼左邊補 0
* ProductID: 產品代碼
* ProductName: 產品名稱
* Quantity: 數量; 型別Decimal\(17,4\)
* UnitPrice: 含稅單價; 型別Decimal\(17,4\)
* SubTotal: 含稅小計; 型別Decimal\(17,4\) 