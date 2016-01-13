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

> * 构建可水平扩展的原生云应用
> * 每个用户有多个账号
> * 多级别的安全预览
> * 当使用Web Socket的时候保持登录状态
> * 非Web请求访问Session数据

---

##Setup

###与httpSession结合

[多账号切换][1]

---
###与boot结合的例子

 - Updating Dependencies

```
<dependencies>
        <!-- ... -->

        <dependency>
                <groupId>org.springframework.session</groupId>
                <artifactId>spring-session</artifactId>
                <version>1.0.2.RELEASE</version>
        </dependency>
        <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-starter-redis</artifactId>
        </dependency>
</dependencies>
```
 - Spring Configuration
```
@EnableRedisHttpSession 
public class HttpSessionConfig { }

The @EnableRedisHttpSession annotation creates a Spring Bean with the name of springSessionRepositoryFilter that implements Filter. The filter is what is in charge of replacing the HttpSession implementation to be backed by Spring Session. In this instance Spring Session is backed by Redis.
```
 - Configuring the Redis Connection

src/main/resources/application.properties
```
spring.redis.host=192.168.230.53
spring.redis.password=
spring.redis.port=6379
spring.redis.database=159
```
 - Servlet Container Initialization


 - boot Sample Application
 >*  Running the boot Sample Application
 >* Exploring the security Sample Application
 >* How does it work?


  [1]: http://docs.spring.io/spring-session/docs/current/reference/html5/guides/users.html