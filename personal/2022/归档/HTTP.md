# HTTP

\#interview

1. 状态码

100 continue 200 ok 201 204 created

300 301 永久重定向 302 临时重定向 303 304 Not Modify

400 bad request 401 权限问题 403 禁止访问 404 not found 405 请求方法不被允许 414 请求过长

500 server error 502 内部错误

1. http缓存

- Etag: MD5

- Expire: 日期

- Cache-Control: max-age=1000 Expire和Cache-Control区别 Expire可能有bug 如果用户修改了本地时间, 会导致资源更新有问题

Etag和Cache-Control区别 Etag还是会发请求 可能会得到304 Cache-Contorl不会发请求了

浏览器缓存顺序

1. GET POST区别 **错误答案** POST安全 GTE不安全 GET 有长度限制 POST没有长度限制 GET参数是放在URL, POST是放在消息体里面的 GET只需要一个报文, POST需要两个及以上 GET 幂等 POST不幂等

**正确答案** GET 是获取数据 POST 提交数据

1. Cookie, LocalStorage, SessionStorage, Session区别

Cookie和Session的区别 Cookie 服务器发给浏览器的一段数据, 浏览器每次访问对应的网站会带上这个数据 Session 浏览器和服务器一段时间的回话 Session是在服务器上的 Cookie是在浏览器上的 Session基于Cookie实现, SessionId放到Cookie里面

Cookie和LoalStorage区别 Cookie 4K LocalStorage 5M Cookie存用户信息 LocalStorage不重要信息 Cookie发送到服务器 LocalStorage存在本地