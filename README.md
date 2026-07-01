# SpringBoot入职作业

## 一、项目简介
本项目实现了一个简单的下单功能，包括：
- MVC开发模式
- MySQL数据库操作
- Redis分布式锁
- RocketMQ消息队列
- AOP日志
- 拦截器登录校验
- Spring事务管理

---

## 二、技术点说明

### 1. MVC
Controller负责接收请求，Service处理业务逻辑，Mapper操作数据库。

### 2. 事务
使用@Transactional保证订单插入与消息发送的一致性。

### 3. AOP
统一打印方法执行日志。

### 4. 拦截器
模拟登录校验，通过header中的token判断。

### 5. Redis
使用setnx实现简单分布式锁，防止重复提交订单。

### 6. RocketMQ
订单创建后发送消息，由消费者进行处理。

---

## 三、运行步骤

1. 创建数据库 demo_db
2. 执行 schema.sql
3. 启动 Redis
4. 启动 RocketMQ nameserver + broker
5. 修改 application.yml
6. 启动 SpringBoot

---

## 四、接口说明

### 创建订单
POST /order/create

```json
{
  "userId": 1,
  "amount": 100
}
```
