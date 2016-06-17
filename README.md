#   (已弃坑)如何编写一台Web服务器程序——WorkerMan源码剖析

>   我之前看过很多代码,这是第一份让我没法改的程序
>
>   ——题记

WorkerMan是一款很酷炫的高性能PHP Socket服务器框架, 但更炫酷的是, 这套框架的代码, 只有5600行。

#   从WebServer说起

WorkerMan的源码中提供了一个基础的Web服务器示例, 我们的源码分析, 也从这个服务器程序开始。

#   WebServer需要什么

*   run方法
*   监听方法
*   响应方法

#   实现

大部分方法都在WorkerMan的Worker类里实现了,WebServer只重载了onWorkerStart和onMessage这两个方法。

程序启动后执行run. 注册onWorkerStart和onMessage两个方法, onWorkerStart主要是注册一个常量类, 用于返回200,404这种状态信息, 然后在记下mimeType。主要的代码都在onMessage里。

当服务器收到消息时, 调用onMessage方法。

5000行代码分析个毛线。。。直接看就好了。。。


