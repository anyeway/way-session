# way-session

标签（空格分隔）： session

传统session和现代的趋势是微服务以及可水平扩展的原生云应用（cloud native application）所需要的session对比。

---

##Features

> * API and implementations for managing a user's session
> * **HttpSession** - allows replacing the HttpSession in an application container (i.e. Tomcat) neutral way
>> * **Clustered Sessions** - Spring Session makes it trivial to support clustered sessions without being tied to an application container specific solution.
>> * **Multiple Browser Sessions** - Spring Session supports managing multiple users' sessions in a single browser instance (i.e. multiple authenticated accounts similar to Google).
>> * **RESTful APIs** - Spring Session allows providing session ids in headers to work with RESTful APIs

> * **WebSocket** - provides the ability to keep the HttpSession alive when receiving WebSocket messages

新的需求

> *构建可水平扩展的原生云应用
> *每个用户有多个账号
> *多级别的安全预览
> *当使用Web Socket的时候保持登录状态
> *非Web请求访问Session数据
