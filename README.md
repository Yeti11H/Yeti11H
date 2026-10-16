# Hi, I'm ooohyg 👋

<p align="center">
  <a href="https://github.com/Yeti11H">
    <img src="https://img.shields.io/badge/Java-Backend-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java Backend" />
  </a>
  <a href="https://github.com/Yeti11H/ooohyg-agent">
    <img src="https://img.shields.io/badge/AI-Agent-7C3AED?style=for-the-badge&logo=openai&logoColor=white" alt="AI Agent" />
  </a>
  <a href="https://github.com/Yeti11H/ooohyg-agent">
    <img src="https://img.shields.io/badge/Harness-Engineering-0EA5E9?style=for-the-badge&logo=githubactions&logoColor=white" alt="Harness Engineering" />
  </a>
  <a href="https://github.com/Yeti11H">
    <img src="https://img.shields.io/badge/Distributed-Systems-16A34A?style=for-the-badge&logo=apachekafka&logoColor=white" alt="Distributed Systems" />
  </a>
</p>

<p align="center">
  <strong>Java Backend Developer · AI Agent Engineer</strong><br/>
  Building backend systems that are reliable under concurrency and useful in real workflows.
</p>

<p align="center">
  <a href="mailto:zeleny66picek@hotmail.com">Email</a>
  ·
  <a href="https://github.com/Yeti11H">GitHub</a>
  ·
  <a href="https://github.com/Yeti11H/ooohyg-agent">Open-source project</a>
</p>

---

## What I work on

I am a Java backend developer interested in the engineering problems behind AI applications:

- how an Agent chooses and executes tools;
- how a long-running task recovers after a timeout or process failure;
- how cache, message queues and databases remain correct under concurrency;
- how a non-deterministic model becomes a controllable backend capability.

My current focus is:

<p align="center">
  <img src="https://img.shields.io/badge/Java_/%20Spring_Backend-ED8B00?style=flat-square&logo=openjdk&logoColor=white" />
  <img src="https://img.shields.io/badge/Agent_/%20Harness-7C3AED?style=flat-square&logo=openai&logoColor=white" />
  <img src="https://img.shields.io/badge/RAG_/%20Tool_Calling-DB2777?style=flat-square&logo=probot&logoColor=white" />
  <img src="https://img.shields.io/badge/Redis_/%20Kafka_/%20RocketMQ-0891B2?style=flat-square&logo=redis&logoColor=white" />
  <img src="https://img.shields.io/badge/High_Availability-16A34A?style=flat-square&logo=apache&logoColor=white" />
</p>

## Selected work

### `ooohyg-agent` · Pluggable Java Agent Runtime

<a href="https://github.com/Yeti11H/ooohyg-agent">
  <img align="right" width="360" src="https://github-readme-stats.vercel.app/api/pin/?username=Yeti11H&repo=ooohyg-agent&theme=transparent&hide_border=true" alt="ooohyg-agent repository card" />
</a>

A Java 21 Agent execution framework designed around **composition and explicit control flow**.

- Uses one `BaseAgent` container with an injected `ExecutionStrategy`;
- Supports `ReAct`, `Plan-and-Execute` and `Reflexion`;
- Allows nested execution such as `Reflexion(Plan(ReAct))`;
- Abstracts `LlmClient`, `Tool`, `ToolRegistry` and `Evaluator`;
- Uses explicit strategy state machines and legal transition checks;
- Separates technical failures (`AgentException`) from business failures (`AgentResult.failure`);
- Keeps the core layer independent from Spring, Redis, Kafka and vendor SDKs.

> Design question: how do we keep Agent execution extensible when models, tools and execution strategies keep changing?

[View the project →](https://github.com/Yeti11H/ooohyg-agent)

<br clear="right"/>

### `hyg-cache` · Multi-level Cache Orchestration

A learning-oriented cache component inspired by the design ideas of JetCache.

```text
L1 Local Cache  →  L2 Remote Cache  →  L3 Data Source
 Caffeine          Redis               Loader
```

The project focuses on the details that usually cause production incidents:

- Cache Aside read and write paths;
- L1/L2 backfill and invalidation broadcast;
- `eventId` idempotency and `version` ordering checks;
- SingleFlight request coalescing for hot keys;
- empty-value caching and Bloom filter protection;
- TTL jitter and failure fallback;
- pluggable read/write strategies, serializers, metrics and invalidation buses.

The project is a study implementation. It does not reuse JetCache source code.

The design README will be published with the repository after the first runnable release.

### Keep · AI Training Assistant Backend

During my Java backend internship at Keep, I worked on the backend chain around an intelligent training assistant:

- designed a RAG flow from intent diagnosis and query rewriting to hybrid retrieval, RRF fusion and Cross-Encoder reranking;
- participated in RocketMQ DLedger high-availability adaptation and failure verification;
- designed a layered task scheduling approach using Redis distributed locking, local priority queues, AQS-based local coordination and MySQL optimistic locking;
- handled duplicate requests, timeout paths, missing business data, streaming interruptions and asynchronous task recovery.

The engineering lesson I took from this work is simple:

> A successful model call is not the same as a successful business result.

## How I think about backend systems

I prefer to make the correctness boundary explicit:

```text
Model output       → can be uncertain
Tool result        → must be authorized and structured
Business state     → must be validated by the backend
Database write     → must be idempotent and recoverable
Event delivery     → must tolerate retry, duplication and reordering
```

For a distributed feature, I usually ask:

1. What is the source of truth?
2. What happens if the request times out after the write has succeeded?
3. What happens if the message is delivered twice or out of order?
4. Which data may be eventually consistent?
5. How does the system recover without manual database repair?

## Technology

<p align="center">
  <img src="https://skillicons.dev/icons?i=java,spring,maven,mysql,redis,kafka,rabbitmq,docker,git,github&perline=10" alt="Technology stack" />
</p>

### Backend

`Java` · `Spring Boot` · `Spring MVC` · `Spring Security` · `MyBatis-Plus` · `Maven`

### Data and middleware

`MySQL` · `Redis` · `Caffeine` · `Kafka` · `RabbitMQ` · `RocketMQ` · `Lettuce`

### AI application engineering

`RAG` · `Tool Calling` · `Agent Runtime` · `ReAct` · `Plan-and-Execute` · `Reflexion` · `SSE` · `MCP`

### Engineering practices

`State Machines` · `Idempotency` · `Distributed Locks` · `Optimistic Locking` · `Outbox` · `Retry` · `Circuit Breaking` · `Observability`

## What I am learning now

- Reading Agent harness designs from Claude Code and Codex;
- Implementing a reliable multi-level cache with invalidation and recovery;
- Studying Raft, replication, failover, consistency and distributed time;
- Turning AI capabilities into testable, observable and recoverable backend workflows;
- Writing practical notes about Java backend and AI application engineering.

## GitHub activity

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Yeti11H&show_icons=true&hide_border=true&theme=transparent&rank_icon=github" height="165" alt="GitHub statistics" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Yeti11H&layout=compact&hide_border=true&theme=transparent" height="165" alt="Most used languages" />
</p>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Yeti11H&theme=github-compact&hide_border=true" alt="GitHub activity graph" />
</p>

## Contact

If you are interested in Java backend, Agent infrastructure, caching or distributed systems, feel free to connect.

- Email: [zeleny66picek@hotmail.com](mailto:zeleny66picek@hotmail.com)
- GitHub: [@Yeti11H](https://github.com/Yeti11H)
