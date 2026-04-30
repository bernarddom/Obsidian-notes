### Encoding
#### SHA512
```
var hmac = new HMACSHA512();

var password = hmac.ComputeHash(Encoding.UTF8.GetBytes(password));
```
