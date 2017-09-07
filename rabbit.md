#Rabbit note

rabbitmq是AMQP的一种实现。

rabbitmq 具有３个主要的部件
１．队列(queue)
２．交换器(exchange)
３．绑定(bind)

rabbitmq的消息有两部分组成：payload与label

rabbitmq提供了发送方确认来确保消息的投递。

消费者会绑定到队列，并获取到达队列的消息

生产者向指定交换器发送消息，rabbit根据路由键与交换器类型来决定将消息发送到哪些队列。
交换器将发送者、队列、消费者解耦。


交换器分４种类型：
---
	direct 　路由键与绑定完全匹配的队列
    fanout　　广播到所有绑定的队列
    topic　　　特殊模式，灵活匹配
    headers　通过header信息来决定如何路由，不常用


vhost:　虚拟主机
	虚拟主机类似mini版的rabbit，它有自己的队列、交换器、绑定，以及权限控制。
    rabbit服务器默认会创建一个"/"的vhost。

