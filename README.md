# ssl_tls_commands

## Info about ssl/tls
``` $ echo | openssl s_client -servername karnali.com -connect karnali.com:443 | openssl x509 -noout -text | grep DNS:| tr ',' '\n' | sed 's/DNS://'

depth=2 O = Digital Signature Trust Co., CN = DST Root CA X3
verify return:1
depth=1 C = US, O = Let's Encrypt, CN = Let's Encrypt Authority X3
verify return:1
depth=0 CN = *.karnali.com
verify return:1
DONE
                *.karnali.com
 karnali.com
 
 ```
 ## Find ssl/tls expiration date
```$ echo | openssl s_client -servername karnali.com -connect karnali.com:443 2>/dev/null | openssl x509 -noout -dates
 
notBefore=Jul 21 14:39:52 2020 GMT
notAfter=Oct 19 14:39:52 2020 GMT
```
## Find ssl/tls Subject Alt Name
```$ echo | openssl s_client -servername karnali.com -connect karnali.com:443 2>/dev/null | openssl x509 -noout -text | grep DNS:| tr ',' '\n' | sed 's/DNS://'
                *.karnali.com
 karnali.com
 ```
