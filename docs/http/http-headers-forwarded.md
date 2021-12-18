# HTTP 头|转发

> 原文:[https://www.geeksforgeeks.org/http-headers-forwarded/](https://www.geeksforgeeks.org/http-headers-forwarded/)

HTTP 头允许客户端和服务器通过 HTTP 请求或 HTTP 响应传递补充信息。标题可以根据它们的上下文进行分类。一般报头包含请求和响应的信息，但与传输的数据没有关系。请求头包含有关请求资源的客户端的信息，响应头包含有关响应或提供资源的服务器的信息。有一些实体头包含了关于资源内容或主体的信息。

*   它用于显示通过 HTTP 代理连接到网络的用户的真实信息。
*   每当代理参与请求路径时，它都包含客户端代理服务器的数据(已更改或丢失)。它属于请求标题类别。
*   该报头字段的可选版本是 X-转发-原型、X-转发-针对、X-转发-主机报头。
*   根据其设计，该报头揭示了客户端的机密信息，例如 IP 地址。因此，部署此标头时必须小心。
*   它用于制作位置相关的内容、调试和统计。

**语法**:

```
Forwarded: 
by=<identifier>;for=<identifier>;host=<host>;proto=<http | https>

```

**指令**:该表头接受五个参数，如上所述，描述如下:

*   **<标识符>**
    标识符公开了使用代理时与任何变更或丢失相关的信息。它们可以是:
    *   IP 地址(IPV4 或 IPV6)
    *   神秘的标识符(如“_ 隐藏”或“_ 秘密”)
    *   当先前实体未知时为未知
*   **by= <标识符>**
    这是一个请求进入代理服务器的地方。
*   **为= <标识符>**
    请求和以下代理已由客户端启动。
*   **主机= <主机>**
    代理接收到的请求头字段“主机”显示。
*   **proto =<http | https>**
    它解释了使用了哪种协议来发出请求(无论是 http 还是 https)

**示例**:

以分号分隔。

```
Forwarded : by=203.0.111.42;for="192.0.3.61";proto=https; 
```

不区分大小写。

```
FORWARDED: FOR="[2003:db4:cafs::17]:4731" 

```

可以使用逗号附加多个值。

```
Forwarded: for=192.0.3.41, for=198.53.103.08 

```

**支持的浏览器:**

支持的浏览器未知 **HTTP 头转发**