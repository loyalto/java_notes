- Cookie：客户端保存用户信息的一种机制，服务端响应SetCookie，进行设置后续请求带上设置的Cookie 标识客户端身份
- Session：服务端标识用户信息机制，一般是唯一ID 存储在Cookie 中发送，当Cookie 禁用时，可以放在请求Url 上
- 关联与区别：都是标识客户端的一种方式，Cookie 是存储在客户端，有长度限制；Session 是存储在服务端，一般存储在缓存中

