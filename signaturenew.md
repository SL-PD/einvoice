# 開立發票簽章驗證值

簽章驗證值產生方法如下：

步驟一、組合字串
字串格式為:
```
    {TimeStamp}{專屬加密Salt}
```
範例：
發票傳入TimeStamp:1490714051
(Tue, 28 Mar 2017 15:14:11 GMT)
e首發票提供之加密Salt: ABCDEFGHIJKLMNOPQRSTUVWXYZ

```
    1490714051ABCDEFGHIJKLMNOPQRSTUVWXYZ
```
步驟二、將字串使用 SHA256 Hash

步驟三、將產生的Byte[]轉成Hex String

範例結果：
將會取得
```
    42AFE0433C4EB08B9266E3B50C72A9D11D4946DC79B7AFD4B73AE9175185644B
```


---

簽章產生程式以C#為範例
```cshap
// 取得簽章驗證值
public string GetInvoiceSignature(string TimeStamp, string Data, string HashSalt)
{
      string _hashString = string.Format("{0}{2}", TimeStamp, HashSalt);
      return SHA256Encrypt(_hashString);
}

// 採用SHA256加密
public string SHA256Encrypt(string NonEncryptString)
{
    SHA256 sha256 = new SHA256CryptoServiceProvider();//建立一個SHA256
    byte[] source = Encoding.ASCII.GetBytes(NonEncryptString);//將字串轉為Byte[]
    byte[] crypto = sha256.ComputeHash(source);//進行SHA256加密
    string result = BitConverter.ToString(crypto).Replace("-", string.Empty);//把加密後的字串從Byte[]轉為字串
    return result;//輸出結果
}
```

