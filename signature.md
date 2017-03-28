# 開立發票簽章驗證值

簽章驗證值產生方法如下：

步驟一、組合字串
字串格式為:
```
    tt={TimeStamp},data={發票欄位字串},salt={專屬加密Salt}
```
發票欄位字串格式為:
```
{發票號碼發票}{開立日期時間(ISO8601格式 GMT)}{發票購買人ID}{檢核碼}{發票總金額}
```

範例：
發票傳入TimeStamp(GMT: Tue, 28 Mar 2017 15:14:11 GMT):1490714051<br/>
發票號碼:AA12345678<br/>
發票開立日期時間:2016-11-03T07:04:28+00:00<br/>
發票購買人ID:26039959<br/>
檢核碼:9467<br/>
發票總金額:5500<br/>
e首發票提供之加密Salt:ABCDEFGHIJKLMNOPQRSTUVWXYZ

```
    tt=1490714051,data=AA123456782016-11-03T07:04:28+00:002603995994675500,salt=ABCDEFGHIJKLMNOPQRSTUVWXY
```

步驟二、將字串使用 SHA256 Hash

步驟三、將產生的Byte[]轉成Hex String







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
    byte[] source = Encoding.ASCII.GetBytes(NonEncryptString);//將字串轉為Byte[]
    byte[] crypto = sha256.ComputeHash(source);//進行SHA256加密
    string result = BitConverter.ToString(crypto).Replace("-", string.Empty);//把加密後的字串從Byte[]轉為字串
    return result;//輸出結果
}
```

