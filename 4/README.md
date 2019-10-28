# 连接管理

## TCP 连接

- 对 TCP 连接进行编程所需的常见套接字接口函数
    - s = socket(<parameters>): 创建一个新的、未命名、未关联的套接字；
    - bind(s, <local IP: port>): 向套接字赋一个本地端口号和接口；
    - connect(s, <remote IP:port>): 创建一个连接本地套接字与远程主机及端口的连接；
    - listen(s, ...): 标识一个本地套接字，使其可以合法接受连接；
    - s2 = accept(s): 等待某人建立一条到本地端口的连接；
    - n = read(s, buffer, n): 尝试从套接字向缓冲区读取 n 个字节；
    - n = write(s, buffer, n): 尝试从缓冲区中向套接字写入 n 个字节；
    - close(s)：完全关闭 TCP 连接；
    - shutdown(s, <side>): 只关闭 TCP 连接的输入或输出端；
    - getsockopt(s, ...): 读取某个内部套接字配置选项的值；
    - setsockopt(s, ...): 修改某个内部套接字配置选项的值；

## 对 TCP 性能的考虑

- TCP 连接的握手时延；
- 延迟确认；（延迟以等待捎带）
- TCP 慢启动；
- Nagle 算法；（等待缓冲区接收到一定数据再发送）
- TIME_WAIT 累积与端口耗尽；

## HTTP 连接的处理

### 并行连接

- 并行连接可能会提高页面的加载速度；
- 并行连接不一定更快；
- 并行连接可能让人“感觉”更快一些；

### 持久连接
- HTTP/1.1 允许 HTTP 设备在事务处理结束之后将 TCP 连接保持在打开状态，以便为未来的 HTTP 请求重用现存的连接。在事务处理结束之后仍然保持在打开状态的 TCP 连接被称为持久连接。

- Keep-Alive
    - 实现 HTTP/1.0 keep-alive 连接的客户端可以通过包含 Connection: Keep-Alive 首部请求将一条连接保持在打开状态；
- Keep-Alive 选项
    - Keep-Alive: max=5, timeout=120;
    - timeout：响应首部。它估计了服务器希望将连接保持在活跃状态的时间；
    - max：响应首部。它估计了服务器还希望为多少个事务保持此连接的活跃状态。

- Keep-Alive 和哑代理
    - Connection 首部和盲中继
    - 代理和逐跳首部：现代的代理都绝不能转发 Connection 首部和所有名字出现在 Connection 值中的首部；
