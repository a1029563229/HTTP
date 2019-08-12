# URL 与资源

## 浏览因特网资源
+ URL 的三部分
    + URL 的第一部分是 URL 方案（scheme）；
    + URL 的第二部分是服务器地址；
    + URL 的第三部分是资源路径； 

## URL 的语法
大多数 URL 方案的 URL 语法都建立在这个由 9 部分构成的通用格式上
```es6
<scheme>://<user>:<password>@<host>:<port>/<path>;<param>?<query>#<frag>
```
URL 最重要的 3 个部分是方案（scheme）、主机（host）、路径（path）
+ scheme：方案
+ user：用户
+ password：密码
+ host：主机
+ port：端口号
+ path：路径
+ param：参数
+ query：查询
+ frag：片段 —— 一小片或一部分资源的名字。引用对象时，不会将 frag 字段传送给服务器；这个字段是在客户端内部使用的。

## URL 快捷方式
+ URL 分为绝对的和相对的。绝对 URL 中包含有访问资源所需的全部信息。相对 URL 是不完整的，要获取相对 URL 对应的全部信息，需要对相对 URL 进行解析。
+ 相对 URL 转换为绝对 URL 的步骤
    + 找到基础URL
        + 在资源中显式提供（例如 HTML 中的 <BASE> 标签）
        + 通过绝对 URL 计算
    + 解析相对引用
+ 自动扩展 URL
    + 主机名扩展（放弃之前尝试几种扩展形式）
    + 历史扩展（缓存用户访问过的 URL）

## 编码机制
+ 为了避开安全字符集表示法带来的限制，人们设计了一种编码机制，用来在 URL 中表示各种不安全的字符。这种编码机制就是通过一种“转义”表示法来标识不安全字符的，这种转义标识法包含一个百分号（%），后面跟着两个表示字符 ASCII 码的十六进制数。（例如空格使用 %20 来表示）

## 方案
+ http：超文本传输协议；
+ https：和 http 一致，只是使用了 SSL，完成了端到端的加密机制；
+ mailto：Email；
+ ftp：文件传输协议；
+ rtsp，rtspu：实时流传输协议（Real Time Streaming Protocol）；
+ file：标识一台主机上（本地磁盘、网络文件系统或其他一些文件共享系统）可直接访问的文件；
+ news：访问新闻；
+ telnet：远程控制协议；