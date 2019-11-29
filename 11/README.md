# 客户端识别与 cookie 机制

现代的 Web 站点希望能够提供个性化的接触。它们希望对连接另一端的用户有更多的了解，并且能在用户浏览页面时对其进行跟踪。

## HTTP 首部

- 承载用户相关信息的 HTTP 首部
    - From：用户的 Email 地址；
    - User-Agent：用户的浏览器软件；
    - Referer：用户是从这个页面上依照链接跳转过来的；
    - Authorization：用户名与密码；
    - Client-IP：客户端的 IP 地址；
    - X-Forwarded-For：客户端的 IP 地址；
    - Cookie：服务器函数的 ID 标签；

## 客户端 IP 地址

- 通常在 HTTP 首部并不提供客户端的 IP 地址，但 Web 服务器可以找到承载 HTTP 请求的 TCP 连接另一端的 IP 地址。
- 使用客户端 IP 地址来识别用户存在着很多缺点，限制了将其作为用户识别技术的效能：
    - 客户端 IP 地址描述的是所用的机器，而不是用户；
    - 很多因特网服务器提供商都会在用户登录时会其动态分配 IP 地址；
    - 为了提高安全性，并对稀缺的地址资源进行管理，很多用户都是通过网络地址转换（NAT）防火墙来浏览网络内容的；
    - HTTP 代理和网关通常会打开一些新的、到原始服务器的 TCP 连接；Web 服务器看到的将是代理服务器的 IP 地址，而不是客户端的；

## 用户登录

- Web 服务器无需被动地根据用户的 IP 地址来猜测他的身份，它可以要求用户通过用户名和密码来进行认证（登录）来显式地询问用户是谁。
- 为了使 Web 站点的登录更加简便，HTTP 中包含了一种内建机制，可以用 WWW-Authenticate 首部和 Authorization 首部向 Web 站点传送用户的相关信息。

## Cookie

cookie 是当前识别用户，实现持久会话的最好方式。

- 可以笼统的将 cookie 分为两类：会话 cookie 和持久 cookie。会话 cookie 是一种临时 cookie，它记录了用户访问站点时的设置和偏好。用户退出浏览器时，会话 cookie 就被删除了。持久 cookie 的生存时间更长一些；它们存储在硬盘上，浏览器退出，计算机重启时它们仍然存在。会话 cookie 和持久 cookie 之间唯一的区别就是它们的过期时间。

- 浏览器会记住从服务器返回的 Set-Cookie 或 Set-Cookie2 首部中的 cookie 内容，并将 cookie 集存储在浏览器的 cookie 数据库中。将来用户返回同一站点时，浏览器会挑中那个服务器铁道用户上的哪些 cookie，并在一个 cookie 请求首部中将其传出去。