## HTTP 与 HTTPS 有哪些区别？
1.http数据传输是未加密的，安全性较差；https数据传输是加密的，安全性较好
2.建立连接的方式不一样，http默认是80端口，https默认是443端口
3.https需要数字认证机构申请证书
4.http比https快，因为https比http的三次握手，多了ssl协商过程
## 从输入 URL 到展现页面的全过程
1.DNS解析：用户输入的URL一般是域名，而我们需要的是ip地址，需要从域名服务器获取域名对应ip地址
2.TCP连接：获取到服务器ip地址后，发起TCP连接请求，三次握手后建立连接，就可以将http请求数据发送给服务器
3.HTTP请求：按照HTTP协议标准发送页面与后端请求
4.处理请求并返回：服务器接受到请求，返回客户端请求返回相应数据
5.浏览器渲染：浏览器根据返回的数据渲染到屏幕上
6.断开连接：客户端和服务器经过4次挥手终止TCP连接
## 简述 HTTP 1.0，1.1，2.0 的主要区别
### 1.1与1.0比
1.缓存控制：1.1缓存控制方式比1.0更灵活，如If-Match, If-None-Match等
2.更多的状态码：如410资源已永久删除，414客户端请求地址太长
3.range域：1.1支持在请求头中加入range头域，请求部分资源
4.长连接：1.0默认是短连接，每次请求，TCP都要重新握手，想保持长连接，需要指定Keep-Alive；1.1默认是短连接
### 2.0与1.1比
1.传输方式：1.1为字符串传输，2.0变为二进制传输，有流ID和优先级
2.多路复用：1个http请求，可以传输多个http请求的内容，通过流ID区分是属于哪一个http请求
3.头部压缩：2.0通过gzip和compress压缩头部发送，通信双方维持头部信息表，传输时头部字段在表中的索引就可以，减少重传次数与数据量
4.支持服务器推送：服务器端可以在客户端未经允许的情况下，预先向客户推送需要的内容，客户端退出时可发送复位取消服务端推送

## HTTP 的方法有哪些？
- GET：获取数据
- POST：提交数据处理请求，导致资源的新建或修改
- PUT：替换指定资源，没有的化新增
- DELETE：删除标识的资源
- PATCH：对资源的局部更新
- OPTIONS：返回对指定资源支持的方法
- HEAD：获取报头
- CONNECT：让服务作为代理代替访问
- TRACE：服务器返回自己收到的数据，用于测试和诊断

