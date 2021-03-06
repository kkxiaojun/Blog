# TCP
## TCP的3次握手和四次挥手、TCP与UDP的区别
## 拥塞控制和流量控制都是什么 ？两者的区别 ？
## Http位于TCP/IP模型中的第几层 ？ 为什么说Http是可靠的数据传输协议 ？

## 播放视频用TCP还是UDP ？ 为什么 ？

# HTTP

## 了解HTTP协议吗 ？HTTP报文结构
## HTTP的状态码，常见的请求头，HTTP缓存协议
## HTTP1.0与2.0的区别
## HTTPS是如何保证安全的，证书如何校验，如何加密
## HTTP与HTTPS区别 ？
## HTTP与Socket的区别 ？

# TCP与UDP
## TCP和UDP的优缺点
TCP
缺点： 
1. 三次握手四次挥手，传输更多包，浪费一些带宽
2. 为了进行可靠通信，双方都要维持在线，通信过程中服务器server可能出现非常大的并发连接，浪费了系统资源，甚至会出现宕机
3. 确认重传也会浪费一些带宽，且在不好的网络中，会不断的断开和连接，降低了传输效率

UDP

优点： 
1. 没有握手，起步快延时小
2. 不需要维持双方在线，server不用维护巨量并发连接，节省了系统资源
3. 没有重传机制，在不影响使用的情况下，能更高效的利用网络带宽

## TCP相比UDP为什么是可靠的
1. 确认和重传机制
建立连接时三次握手同步双方的“序列号 + 确认号 + 窗口大小信息”，是确认重传、流控的基础
传输过程中，如果Checksum校验失败、丢包或延时，发送端重传

2. 数据排序

TCP有专门的序列号SN字段，可提供数据re-order

3. 流量控制

窗口和计时器的使用。TCP窗口中会指明双方能够发送接收的最大数据量

4. 拥塞控制

TCP的拥塞控制由4个核心算法组成。

“慢启动”（Slow Start）

“拥塞避免”（Congestion avoidance）

“快速重传 ”（Fast Retransmit）

“快速恢复”（Fast Recovery）