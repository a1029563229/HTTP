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