# 第二章 事件驱动架构


mine the order of the steps and which ones can be done serially and in parallel.


![2-1](2-1.png)










The event channels contained within the broker component can be message queues, message topics, or a combination of both.

![2-2](2-2.png)


￼￼￼￼￼Figure 2-3. Event-driven architecture broker topology

￼￼￼￼￼Figure 2-4. Broker topology example


One consideration to take into account when choosing this architec‐ ture pattern is the lack of atomic transactions for a single business process. Because event processor components are highly decoupled and distributed, it is very difficult to maintain a transactional unit of work across them. For this reason, when designing your application using this pattern, you must continuously think about which events can and can’t run independently and plan the granu‐ larity of your event processors accordingly. If you find that you need to split a single unit of work across event processors—that is, if you are using separate processors for something that should be an undivided transaction—this is probably not the right pattern for your application.


### Ease of deployment