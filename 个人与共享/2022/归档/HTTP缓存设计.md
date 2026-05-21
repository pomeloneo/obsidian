# HTTP缓存设计

\#interview

# 无需验证

假设有一个脚本50年没有改动 那么就可以在文件的返回头中设置Cache-Control Cache-Control: max-age=3153600

# 需要验证

如何验证文件已经发生改变了呢 在服务器第一次返回给浏览器的http响应头中, 有一个名为Eatg的字段

这个字段代表这个请求的token, 这个token没有统一的规则, 主要看服务端是如何实现这个Eatg值的, 总之就是辨别这个请求返回的唯一性

当资源过期时, 浏览器再次请求该资源时, 浏览器会添加一个If-None-Match的http请求头信息, 这个值就是这个过期资源的Etag, 用于服务器告诉浏览器当前的资源版本, 服务器也是通过对比Etag来判断资源是否更新

[![](https://www.notion.soHTTP%E7%BC%93%E5%AD%98%E8%AE%BE%E8%AE%A1/D404C372-4735-472D-9D7F-964A5C785739.png)](https://www.notion.soHTTP%E7%BC%93%E5%AD%98%E8%AE%BE%E8%AE%A1/D404C372-4735-472D-9D7F-964A5C785739.png)

# 技术细节

1. Cache-Control 字段不仅仅可以设置max-age的存储时间 还可以填写其他的值:

- no-cache: 字面意思是不要缓存, 实际的机制是仍对资源缓存, 但是每一次使用缓存之前必须向服务器对缓存资源进行验证

- no-store: 不适用任何缓存

- must-revalidate: 如果你配置了max-age信息，当缓存资源仍然新鲜（小于max-age）时使用缓存，否则需要对资源进行验证。所以must-revalidate可以和max-age组合使用Cache-Control: must-revalidate, max-age=60

1. Expires VS max-age expires和max-age都是用于控制缓存的生命周期的, 不同的是expires指的是过期的具体时间 而max-age指的是生命的时长

1. Etag VS Last-Modified Etag和Last-Modified都可以对资源进行验证 Last-Modified顾名思义便是资源最后更新的时间

我们把这两者都当成验证器, 不同的是Etag属于强验证, 因为它期望资源字节级别的一致 Last-Modified属于弱验证, 只要资源的内容一致即可

1. max-age = 0 VS no-cache max-age是在告诉浏览器资源过期了, 应该重新验证了 no-cache告诉浏览器使用缓存之前必须验证

1. public VS private 要知道服务器到浏览器并非只有浏览器对资源进行缓存, 服务器的返回会经过一些中间服务器 如果一些资源不想被中间浏览器缓存只需要将Cache-Control设置为private

# 强制缓存

强制缓存就是向浏览器缓存查找该请求结果，并根据该结果的缓存规则来决定是否使用该缓存结果的过程，强制缓存的情况主要有三种(暂不分析协商缓存过程)，如下： 1. 不存在该缓存结果和缓存标识，强制缓存失效，则直接向服务器发起请求（跟第一次发起请求一致） 2. 存在该缓存结果和缓存标识，但该结果已失效，强制缓存失效，则使用协商缓存(暂不分析) 3. 存在该缓存结果和缓存标识，且该结果尚未失效，强制缓存生效，直接返回该结果

强制缓存的规则: 当浏览器向服务器发起请求时，服务器会将缓存规则放入HTTP响应报文的HTTP头中和请求结果一起返回给浏览器，控制强制缓存的字段分别是Expires和Cache-Control，其中Cache-Control优先级比Expires高

# 协商缓存

协商缓存就是强制缓存失效后，浏览器携带缓存标识向服务器发起请求，由服务器根据缓存标识决定是否使用缓存的过程，主要有以下两种情况： 1. 协商缓存生效 304 not-modifiy 2. 协商缓存失效，返回200和请求结果结果

协商缓存的标识也是在响应报文的HTTP头中和请求结果一起返回给浏览器的，控制协商缓存的字段分为两组 * Last-Modified / If-Modified-Since * Etag / If-None-Match

其中Etag / If-None-Match的优先级比Last-Modified / If-Modified-Since高。

**Last-Modified / If-Modified-Since**

Last-Modified是服务器返回给浏览器时写在响应头的字段 表示该资源最后的修改时间 If-Modified-Since则是客户端再次发起该请求时，携带上次请求返回的Last-Modified值，通过此字段值告诉服务器该资源上次请求返回的最后被修改时间。服务器收到该请求，发现请求头含有If-Modified-Since字段，则会根据If-Modified-Since的字段值与该资源在服务器的最后被修改时间做对比，若服务器的资源最后被修改时间大于If-Modified-Since的字段值，则重新返回资源，状态码为200；否则则返回304，代表资源无更新，可继续使用缓存文件

**但是 Last-Modified 存在一些弊端：** * 如果本地打开缓存文件，即使没有对文件进行修改，但还是会造成 Last-Modified 被修改，服务端不能命中缓存导致发送相同的资源 * 因为 Last-Modified 只能以秒计时，如果在不可感知的时间内修改完成文件，那么服务端会认为资源还是命中了，不会返回正确的资源

**Etag / If-None-Match** Etag是服务器响应请求时，返回当前资源文件的一个唯一标识(由服务器生成) f-None-Match是客户端再次发起该请求时，携带上次请求返回的唯一标识Etag值，通过此字段值告诉服务器该资源上次请求返回的唯一标识值。服务器收到该请求后，发现该请求头中含有If-None-Match，则会根据If-None-Match的字段值与该资源在服务器的Etag值做对比，一致则返回304，代表资源无更新，继续使用缓存文件；不一致则重新返回资源文件，状态码为200

# 强制缓存优先于协商缓存