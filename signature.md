# 簽章驗證值

簽章驗證值產生方法如下：
1. 組成字串：字串格式為```tt={TimeStamp},data={發票的JSON},salt={專屬加密Salt}```
2. 將字串以 SHA256 加密

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

