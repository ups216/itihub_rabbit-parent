# rabbit-parent
[中文](README.md) | English

## Overview
This code module is a comprehensive distributed system solution collection, mainly including the following core functional components:
1. **Distributed Task Scheduling**: Implements sharded execution and coordination of timed tasks based on ElasticJob and Zookeeper.
2. **Message Queue Processing**: Provides reliable message communication, serialization, and persistence capabilities through RabbitMQ.
3. **Spring Boot Integration**: Standardized application startup and auto-configuration, supporting rapid extension and deployment.

The module adopts a layered architecture design, covering complete chains of task scheduling, message production/consumption, exception handling, data persistence, etc., suitable for task and message management requirements in high-concurrency, distributed scenarios.

## What is rabbit-parent?
`rabbit-parent` is a multi-module Java project that integrates two core technology stacks: ElasticJob distributed task scheduling and RabbitMQ message queue, mainly containing the following sub-modules:

1. **Task Scheduling Module**
   - Implements distributed task scheduling based on ElasticJob (such as `rabbit-task-example`, `es-job`), supporting:
     - Simple timed tasks (`SimpleJob`) and data flow tasks (`DataflowJob`)
     - Sharding processing, failover, event listening (like `SimpleJobListener`)
     - Zookeeper coordination and job status persistence

2. **Message Queue Module**
   - Provides complete RabbitMQ message processing capabilities (such as `rabbit-api`, `rabbit-core-producer`), features include:
     - Multi-type message delivery (rapid/confirmed/reliable messages)
     - Message serialization (JSON/Jackson), delayed delivery, failure retry
     - Producer-side message storage and status management (`BrokerMessage`)

3. **Common Component Module**
   - Encapsulates common utilities (such as `rabbit-common`), covering:
     - Message converters (`RabbitMessageConverter`)
     - Exception system (`MessageException`)
     - MyBatis type handlers (`MessageJsonTypeHandler`)

**Typical Application Scenarios**
- E-commerce order status synchronization (distributed tasks + reliable message delivery)
- Log collection and ETL processing (data flow tasks + high-throughput message queue)
- Scheduled reconciliation report generation (sharding tasks + transactional message guarantee)

**Technology Stack**
- Core Frameworks: Spring Boot, ElasticJob, RabbitMQ
- Middleware: Zookeeper
- Data Layer: MyBatis, Relational Databases
- Tool Libraries: Lombok, Jackson, Slf4j

## Quick Navigation

### 👨‍💻 Developers
- [Development Guide](summary/dev_guide.md) - Quick start for project development
- [Module Description](docs/_module.md) - Detailed explanation of project modules