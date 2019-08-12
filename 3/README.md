# HTTP 报文
如果说 HTTP 是因特网的信使，那么 HTTP 报文就是它用来搬东西的包裹。

## 报文流
- HTTP 使用术语流入（inbound）和流出（outbound）来描述事务处理（transaction）的方向。报文流入源端服务器，工作完成之后，会流回用户的 Agent 代理中。

## 报文的组成部分
- HTTP 报文是简单的格式化数据块。它们由三部分组成：对报文进行描述的起始行（start line）、包含属性的首部（header）块、以及可选的包含数据的主体（body）部分。
- 起步行和首部就是由行分隔的 ASCII 文本。每行都以一个 由两个字符组成的行终止序列作为结束，其中包括一个回车符（ASCII 码 13）和一个换行符（ASCII 码 10）。这个行终止序列可以写作 CRLF。
- 猪蹄可以包含文本或二进制数据。
- 报文的语法
    - 请求报文的格式 `<method><request-URL><version> CRLF <headers> CRLF <entity-body>`
    - 响应报文的格式 `<version><status><reason-phrase> CRLF <headers> CRLF <entity-body>`
- 报文的组成部分
    - 方法（method）：客户端希望服务器对资源执行的动作。
    - 请求 URL（request-URL）：命名了所请求资源，或者 URL 路径组件的完整 URL；
    - 版本（version）：报文所使用的 HTTP 版本，其格式看起来是这样的：`HTTP/<major>.<minor>`；
    - 状态码（status-code）：这三位数字描述了请求过程中所发生的情况；
    - 原因短语（reason-phrase）：数字状态码的可读版本，包含行终止序列之前的所有文本；
    - 首部（header）：可以有零个或多个首部，每个首部都包含一个名字，后面跟着一个冒号（：），然后是一个可选的空格，接着是一个值，最后是一个 CRLF。
    - 实体的主体部分（body）：实体的主体部分包含一个由任意数据组成的数据块。