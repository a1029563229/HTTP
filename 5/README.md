# Web 服务器

## Web 服务器的工作
- 接受客户端连接
    - 处理新连接；
    - 客户端主机名识别；
- 接受请求报文
    - 解析请求行，查找请求方法、指定的资源标识符（URI）；
    - 读取以 CRLF 结尾的报文首部；
- 处理请求
- 对资源的映射及访问
- 构建响应
    - 响应实体：Content-Type、Content-Length、实体内容；
        - MIME 类型：Web 服务器会为每个资源扫描一个包含了所有扩展名的 MIME 类型文件，以确定其 MIME 类型；
        - 重定向
            - 301：资源可能已经被移动到了新的位置；
            - 303 307：临时搬离的资源、URL 增强、负载均衡、服务器关联；
- 发送响应 
- 记录日志