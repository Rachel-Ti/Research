- [预热](#预热)
  - [CCF](#CCF)
    - [2022](#2022)
      - [1.IceBreaker: Warming Serverless Functions Better with Heterogeneity](#1icebreaker-warming-serverless-functions-better-with-heterogeneity)
      - [2.INFless: a native serverless system for low-latency, high-throughput inference](#2infless-a-native-serverless-system-for-low-latency-high-throughput-inference)
    - [2021](#2021)
       - [1.Nightcore: efficient and scalable serverless computing for latency-sensitive, interactive microservices](#1nightcore-efficient-and-scalable-serverless-computing-for-latency-sensitive-interactive-microservices)
        

# 预热

## CCF

### 2022

> 2022.2.28-3.14
>
> 有专门的关于 serverless 的会议主题

#### 1.IceBreaker: Warming Serverless Functions Better with Heterogeneity 

**摘要：**

无服务器计算是一种新兴的计算模式，它依赖于在预期执行前的 "预热 "函数，以便为用户提供更快、更经济的服务。不幸的是，**预热函数可能是不准确的，并且在预热期间会产生令人望而却步的昂贵成本（即函数保活成本）**。在本文中，**我们介绍了 IceBreaker，这是一种新颖的技术，通过用异构节点（昂贵和便宜）组成系统来减少服务时间和 "保活 "成本。IceBreaker 的做法是，根据函数的时间变化概率，动态地确定在具有成本效益类型的节点来预热函数。通过采用异构性，IceBreaker 允许在相同的成本预算下拥有更多数量的节点，因此可以保活更多数量的函数，并减少高负载时的等待时间**。我们的实际系统评估证实，IceBreaker 使用具有代表性的无服务器应用程序和行业级工作负载跟踪，将整体保持不变的成本降低了 45％，执行时间降低了 27％。IceBreaker 是第一个采用并利用昂贵和便宜节点混合的想法来改善无服务器函数的服务时间和保持成本的技术--为研究人员和从业者开辟了一条在异构服务器上进行无服务器计算的新研究途径。

### 2.INFless: a native serverless system for low-latency, high-throughput inference

**摘要：**

现代网站越来越依赖机器学习（ML）来提高其业务效率。开发和维护 ML 服务会给开发者带来高昂的成本。虽然无服务器系统是一个很有前途的降低成本的解决方案，但我们**发现目前的通用无服务器系统不能满足 ML 服务的低延迟、高吞吐量的需求。**

虽然简单地 "修补 "通用无服务器系统并不能完全解决这个问题，但我们建议这样的系统应该将推理的特点与无服务器范式天然地结合起来。我们**提出了 INFless，这是第一个针对 ML 领域的无服务器平台。它在 CPU 和加速器之间提供了一个统一的、异构的资源抽象，并利用内置的批处理和非统一的扩展机制实现了高吞吐量。**它还通过协调管理批处理排队时间、执行时间和**冷启动率**支持低延迟。我们使用本地集群测试平台和大规模模拟来评估 INFless。实验结果表明，INFless 在系统吞吐量上优于最先进的系统 2-5 倍，满足了 ML 服务的延时目标。


### 2021 

> 2021.4.19-4.23

#### 1.Nightcore: efficient and scalable serverless computing for latency-sensitive, interactive microservices 

摘要：

微服务架构是一种流行的软件工程方法，用于构建灵活的大规模在线服务。无服务器计算或者函数计算提供了一个简单的无状态函数编程模型，它是实现微服务的无状态 RPC 处理程序的自然基础，是容器化 RPC 服务器的替代方案。但是，**当前的无服务器平台具有毫秒级的运行时开销，使其无法满足现有交互式微服务所需的严格的亚毫秒级延迟目标**。 

我们展示了 **Nightcore，这是一个具有微秒级开销的无服务器函数运行时，可在函数之间提供基于容器的隔离。Nightcore 的设计仔细考虑了具有微秒级开销的各种因素，包括函数请求的调度、通信原语、I/O 的线程模型和并发函数执行。** Nightcore 目前支持用 C/C++、Go、Node.js 和 Python 编写的无服务器函数。我们的评估表明，在运行延迟敏感的交互式微服务时，Nightcore 实现了 1.36–2.93 倍更高的吞吐量和高达 69% 的尾部延迟减少。

