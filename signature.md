# 簽章驗證值

簽章驗證值產生方法如下：
1. 組成字串：字串格式為 <br />
```tt={TimeStamp},data={發票相關欄位字串},salt={專屬加密Salt}```
2. 發票相關欄位字串為:<br />
```發票號碼+發票開立日期時間(ISO8601格式)+發票購買人ID+檢核碼+發票總金額```

```
例如：
發票號碼:AA12345678
發票開立日期時間:2016-11-03T15:04:28+08:00
發票購買人ID:26039959
檢核碼:9467
發票總金額:5500
則發票相關欄位字串為: AA123456782016-11-03T15:04:28+08:002603995994675500
```
3. 將字串以 SHA256 加密

以C#為範例
```cshap
// 取得簽章驗證值
public string GetInvoiceSignature(string TimeStamp, string Data, string HashSalt)
{
      string _hashString = string.Format("tt={0},data={1},salt={2}", TimeStamp, Data, HashSalt);
      return SHA256Encrypt(_hashString);
}

// 採用SHA256加密
public string SHA256Encrypt(string NonEncryptString)
{
    SHA256 sha256 = new SHA256CryptoServiceProvider();//建立一個SHA256
    byte[] source = Encoding.Default.GetBytes(NonEncryptString);//將字串轉為Byte[]
    byte[] crypto = sha256.ComputeHash(source);//進行SHA256加密
    string result = BitConverter.ToString(crypto).Replace("-", string.Empty);//把加密後的字串從Byte[]轉為字串
    return result;//輸出結果
}
```

