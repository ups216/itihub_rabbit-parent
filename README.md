# rabbit-parent
[English](README_en.md) | 中文

## 概述  
该代码模块是一个综合性的分布式系统解决方案集合，主要包含以下核心功能组件：  
1. **分布式任务调度**：基于ElasticJob和Zookeeper实现定时任务的分片执行与协调。  
2. **消息队列处理**：通过RabbitMQ提供可靠的消息通信、序列化及持久化能力。  
3. **Spring Boot集成**：标准化应用启动与自动配置，支持快速扩展和部署。  

模块采用分层架构设计，涵盖任务调度、消息生产/消费、异常处理、数据持久化等完整链路，适用于高并发、分布式场景下的任务与消息管理需求。  

## 什么是rabbit-parent?  
`rabbit-parent`是一个多模块的Java项目，整合了ElasticJob分布式任务调度和RabbitMQ消息队列两大核心技术栈，主要包含以下子模块：  

1. **任务调度模块**  
   - 实现基于ElasticJob的分布式任务调度（如`rabbit-task-example`、`es-job`），支持：  
     - 简单定时任务（`SimpleJob`）与数据流任务（`DataflowJob`）  
     - 分片处理、故障转移、事件监听（如`SimpleJobListener`）  
     - Zookeeper协调与作业状态持久化  

2. **消息队列模块**  
   - 提供完整的RabbitMQ消息处理能力（如`rabbit-api`、`rabbit-core-producer`），特性包括：  
     - 多类型消息投递（迅速/确认/可靠消息）  
     - 消息序列化（JSON/Jackson）、延迟投递、失败重试  
     - 生产者端的消息落库与状态管理（`BrokerMessage`）  

3. **公共组件模块**  
   - 封装通用工具（如`rabbit-common`），涵盖：  
     - 消息转换器（`RabbitMessageConverter`）  
     - 异常体系（`MessageException`）  
     - MyBatis类型处理器（`MessageJsonTypeHandler`）  

**典型应用场景**  
- 电商订单状态同步（分布式任务+可靠消息投递）  
- 日志收集与ETL处理（数据流任务+高吞吐消息队列）  
- 定时对账报表生成（分片任务+事务消息保障）  

**技术栈**  
- 核心框架：Spring Boot, ElasticJob, RabbitMQ  
- 中间件：Zookeeper  
- 数据层：MyBatis, 关系型数据库  
- 工具库：Lombok, Jackson, Slf4j

## 快速导航

### 👨‍💻 开发者
- [开发指南](summary/dev_guide.md) - 快速上手项目开发
- [模块说明](docs/_module.md) - 项目模块详细说明