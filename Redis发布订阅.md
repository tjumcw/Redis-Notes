# Redis发布订阅

- Redis发布订阅（pub/sub）是一种==消息通信模式==：发送者（pub）发送消息，接受者（sub）接收消息。
- Redis客户端可以订阅任意数量的频道。

订阅/发布消息图：

第一个：消息发送者，第二个：频道，第三个：消息订阅者

![image-20220726215504070](C:\Users\tjumc\AppData\Roaming\Typora\typora-user-images\image-20220726215504070.png)



#### 发布订阅相关命令

![image-20220726220103905](C:\Users\tjumc\AppData\Roaming\Typora\typora-user-images\image-20220726220103905.png)



#### 测试

- 订阅端

```bash
127.0.0.1:6379> SUBSCRIBE kuangshenshuo			#订阅一个频道 kuangshenshuo
Reading messages... (press Ctrl-C to quit)
1) "subscribe"
2) "kuangshenshuo"
3) (integer) 1
#等待读取推送的信息
1) "message"		#消息
2) "kuangshenshuo"	#消息来自的频段
3) "hello"			#具体的消息
1) "message"
2) "kuangshenshuo"
3) "redis"
```



#### 发送端

```bash
127.0.0.1:6379> PUBLISH kuangshenshuo "hello"
(integer) 1
127.0.0.1:6379> PUBLISH kuangshenshuo redis
(integer) 1
```



#### 原理

![image-20220726220720946](C:\Users\tjumc\AppData\Roaming\Typora\typora-user-images\image-20220726220720946.png)