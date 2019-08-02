# 概述
Web 浏览器、服务器和相关的 Web 应用程序都是通过 HTTP 相互通信的。HTTP 是现代全球因特网中使用的公共语言。

+ Web 内容都是存储在 Web 服务器上的。Web 服务器所使用的都是 HTTP 协议，因此经常会被称为 HTTP 服务器。客户端向服务器发送 HTTP 请求，服务器会在 HTTP 响应中回送所请求的数据。
+ Web 服务器是 Web 资源（Web resource）的宿主。Web 资源是 Web 内容的源头。
+ Web 服务器会为所有 HTTP 对象数据附加一个 MIME 类型；MIME 类型是一种文本标记，表示一种主要的对象类型和一种特定的子类型，中间用一道斜杠来分割。（例如 image/jpeg text/html application/json）
+ 每个 Web 服务器资源都有一个名字，被称为统一资源标识符（Uniform Resource Idenifier, URI）。
+ 统一资源定位符（Uniform Resource Location）是资源标识符最常见的形式。