
## Mind your Ps and Qs
Method 1.
```
> ./RsaCtfTool.py -n 1422450808944701344261903748621562998784243662042303391362692043823716783771691667 -e 65537 --uncipher 843044897663847841476319711639772861390329326681532977209935413827620909782846667
```

Method 2.
```
import gmpy2
# Get P,Q of N from http://factordb.com 
r = 2159947535959146091116171018558446546178* 658558036833541874645521278345168572231472
d = gmpy2.invert(e, r)
print(f"d is {d}")

msg = pow(c, d, n)
msg = bytearray.fromhex(hex(msg)[2:]) # https://stackoverflow.com/questions/13141787/convert-decimal-int-to-little-endian-string-x-x
print(msg)
```

Reference
- [RsaCtfTool](https://github.com/RsaCtfTool/RsaCtfTool/tree/master)
- [CTF-Crypto-RSA整理](https://blog.csdn.net/q20010619/article/details/121023558)
