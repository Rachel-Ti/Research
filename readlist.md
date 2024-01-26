- Papers
  -[edge and multi](#edge-and-multi)
  -[scheduler](#scheduler)
  -[scaler](#scaler)
  -[scale and schedule](#scale-and-schedule)
  -[review](#review)
  -[benchmark](#benchmark)
  -[dataset](#dataset)




## edge and multi 

**A Decentralized Framework for Serverless Edge Computing in the Internet of Things**

> 2021 CCF C

- 结论

  在本文中，我们提出了一种在边缘网络中实现无服务器计算的架构，这对物联网应用越来越感兴趣。客户端向电子路由器发送lambda函数请求，电子路由器将请求转发给当前认为最合适的电子计算机。整体解决方案非常轻量级，可以在资源受限的设备上实现，例如物联网网关，特别是当使用两层覆盖选项来减少本地状态的大小时。我们设计了三种算法来选择来自客户端的lambda请求的目的地，其中一种称为RR的算法被证明可以保证短期和长期的公平性。

  我们通过仿真实验在不同的场景中广泛地验证了我们的贡献，还集成了一个广泛使用的开源无服务器框架(OpenWhisk)。

  结果表明，我们的架构可以有效地处理快速变化的负载和网络条件，特别是延迟可以与分布式架构的无服务器平台的乐观情况相媲美。此外，两层覆盖可以有效地减少计算需求，同时实现与平面覆盖相同或更好的性能。

[code](https://github.com/ccicconetti/serverlessonedge)


## scheduler

**A Declarative Approach to Topology-Aware Serverless Function-Execution Scheduling**
  
> 2021 ICWS CCF B

- 摘要  

  最先进的无服务器平台使用不知道功能可能的拓扑约束的硬编码调度策略。在调度函数时考虑这些约束会带来明显的性能改进，例如，最小化加载时间或数据访问延迟。当考虑到新兴的多云和边缘云连续系统时，这个问题变得更加紧迫，因为只有特定的节点才能访问专门的本地资源。为了解决这个问题，我们提出了一种声明性语言，用于定义无服务器调度策略，以表达对调度程序和执行节点拓扑的约束。我们将我们的方法作为**OpenWhisk**平台的扩展来实现。

- Attention

  Allocation Priority Policies for Serverless Function-Execution Scheduling Optimisation也是同类型的文章


**Container lifecycle-aware scheduling for serverless computing**

> Software - Practice and Experience (Software)（2022）CCF B

- CONCLUSION  

  冷启动会妨碍无服务器计算的弹性。减少冷启动的主要策略是依赖调度器来**重用暂停的容器**。我们分析了现有调度器如何以及为什么不能很好地工作，提出了一种容器生命周期感知调度策略CAS。调度请求时，CAS首选承载可用容器或不需要容器驱逐的工作线程，以避免当前请求和即将到来的请求的冷启动。在一个worker上，CAS使用第一个可用容器来处理请求。因此，许多请求可以由可用的容器或即将可用的容器提供服务，而不必忍受冷启动的痛苦。CAS在OpenWhisk上实现。实验结果表明，当工作负载之间存在worker争用时，与OpenWhisk中的本机调度策略相比，CAS减少了81%的冷启动，因此在95百分位延迟上减少了63%，并且没有增加明显的性能开销。


**Caerus: Nimble Task Scheduling for Serverless Analytics**

> Symposium on Networked Systems Design and Implementation (NSDI)（2021）CCF A

我们介绍了Caerus，一个无服务器分析的任务调度程序，它使用了一种新的灵活调度算法。NIMBLE在无服务器分析工作的**各个阶段有效地执行流水线任务**，NIMBLE对各种执行参数(**可管道化和不可管道化的数据依赖关系**、数据生成、消耗和处理率等)进行建模（一个新的步骤依赖关系模型），以确定理想的任务启动时间，以确保成本和JCT之间的成本最优和paretooptimal。我们表明，对于广泛的分析工作负载，NIMBLE通常在这两个维度上都是最佳的。这使得Caerus在JCT上的性能比现有的惰性调度方法高1.08 - 2.2倍，在这些工作负载上的成本比现有的惰性调度方法高1.21 - 1.57倍。

## load balancing

**A Greedy Load Balancing Algorithm for FaaS Platforms**

> 2021 ICCBDC

- CONCLUSION  

  为了激活FaaS计算，应该实现最大化局部性和负载平衡的负载平衡算法。在本文中，我们通过在公共和私有FaaS平台中采用三种不同的缓存配置来模拟实际工作负载，从而评估了FaaS负载平衡算法的效果。为了提高FaaS性能，我们进一步提出了一种新的负载均衡算法GRAF，该算法采用表格数据结构和贪婪方法。我们证明，与现有方案相比，GRAF在局部性、负载平衡和整体性能方面可以取得更好的结果。此外，我们的评估显示，根据负载平衡算法的不同，相同的缓存技术可能产生不同的结果。总之，我们探讨了FaaS平台中使用各种**缓存**技术的局部性和性能之间的关系，希望能进一步深入了解云计算领域。

## scaler

**AI-based Resource Allocation: Reinforcement Learning for Adaptive Auto-scaling in Serverless Environments**

> 2021 IEEE/ACM 21st International Symposium on Cluster, Cloud and Internet Computing (CCGrid) CCF C

- Conclusion

  为了灵活调整自动缩放设置以满足特定需求，我们设计了一个基于Q-learning的强化学习模型，并评估了其在运行时学习有效缩放策略的适用性。基于不同的工作负载，我们证明了所提出的模型可以在有限的时间内在没有先验知识的情况下适当地调整并发性，并且与Knative的默认设置相比，其平均吞吐量优于平均吞吐量。

  •除了之前对无服务器平台的扩展能力的研究之外，我们还提供了详细的分析，以揭示并发配置变化对性能的影响。

  •用我们提出的模型证明了基于q学习的自动缩放在无服务器应用领域的适用性。

  •研究结果有助于Knative社区项目的自动缩放系统的持续开发。

  然而，我们在实验中发现了该方法的一些局限性。首先，第V节的结果基于一个应用程序模拟的具有不同参数的合成工作负载，因此不能将其解释为关于实际应用程序影响的普遍有效结论。其次，由于关注Q-learning的一般适用性，该方法使用了一个相当简单的奖励函数，只测量与参考值的接近程度。进一步改进奖励函数可以提高模型的效率。同样，RL环境的系统状态描述可以通过额外的参数(如内存分配和时间约束)进行扩展，以提高模型的准确性。

  虽然在这项工作中已经开发了一种RL方法，主要通过测试不同的并发状态来学习每个工作负载的特定扩展策略，但仍然需要分析单个组件的资源使用比例在多大程度上可能影响性能。因此，可以进行全面的研究，以确定可能在所有工作负载中实现最佳性能的利用率水平组合。因此，并发配置只能作为将系统带入这种特定状态的工具。


**Algorithms for scheduling scientific workflows on serverless architecture**

> 2021 IEEE/ACM 21st International Symposium on Cluster, Cloud and Internet Computing (CCGrid) CCF C

- Conclusion

  在本文中，我们提出了两种新的调度算法SMOHEFT(MOHEFT的改编)和SML，这两种算法旨在为在无服务器基础设施上执行科学工作流创建时间和成本限制的调度。我们通过执行实验来评估提出的算法，其中我们计划执行三个应用程序。以SDBWS和SDBCS算法为基准，SML在执行Ellipsoids工作流时取得了最好的效果，成功率在80%以上，而其他算法的成功率在60%以下。在Vina案例中，除了SDBWS之外，所有算法的成功率都在87.5%以上，而在蒙太奇案例中，所有算法的成功率都差不多，都在87.5%以上。该算法的成功率与其他已研究的解决方案相当或更好。

## scale and schedule

**A scalable clustering-based task scheduler for homogeneous processors using DAG partitioning**

> 2019 IEEE International Parallel and Distributed Processing Symposium(IPDPS) CCF B

- Abstract  

  在计算平台上调度具有通信开销的任务的有向无环图(DAG)时，需要在负载平衡和数据局部性之间进行良好的权衡。基于列表的调度技术是解决此问题的常用贪婪方法。列表调度启发式的缺点是，它们不能为调度的全局效率做出短期牺牲。在本工作中，我们描述了在现实双工单端口通信模型下，基于聚类的同构平台的新的基于列表的调度启发式算法。我们的方法使用dag的无循环分区器进行聚类。聚类通过图的全局视图增强了调度器的数据局部性。

  此外，由于分区是无循环的，一旦每个部分的输入任务准备好执行，我们就可以完全调度每个部分。提出了一个广泛的实验评估，显示了集群粒度和并行性之间的权衡，以及这如何影响调度。此外，将我们的启发式方法与最先进的列表调度和聚类启发式方法进行了比较，并在具有许多通信的情况下获得了三倍以上的最大完成时间。

- Conclusion

  基于dag的非循环划分，提出了三种新的分区辅助列表调度技术(或元启发式):*-PART、*-BUSY和*-MACRO。分区的非循环性确保我们可以在其输入节点可用时立即调度整个部分。

  因此，我们已经能够设计特定的列表调度技术，这在没有非循环分区的情况下是不可能实现的。据我们所知，这是第一个在集群阶段使用多级定向DAG分区器的分区辅助列表调度器。非周期性非常适合于识别DAG中的数据局部性，并且它允许设计特定的分配策略，例如*-MACRO。

  所提出的元启发式算法具有通用性，可以与任何经典的列表调度启发式算法相结合，并可用于任何非循环分区。

  我们将我们的调度技术与广泛使用的BL-EST、ETF和DSC-GLB-ETF启发式方法进行了比较，这些启发式方法适用于实际的双工单端口通信模型。结果是惊人的，新的启发式不断提高完工时间。尽管*-MACRO似乎不能很好地随处理器数量的增加而扩展，但它在一些情况下提供了最好的结果，而*-PART和*-BUSY一直都很好。例如，提议的*-PART(参见第1部分)。

  *-BUSY和*-MACRO算法实现的最大跨度为2.6。3.1和3.3)比BL-EST小1倍，当考虑到CCR = 20的大数据集时，对所有处理器数量进行平均。此外，如果我们为每个实例选择三种启发式中最好的，那么它的效果会提高四倍。

  在未来的工作中，我们计划考虑凸分区而不是非循环分区，后者限制较少，因此暴露了更多的并行性。据我们所知，目前还没有自上而下的凸分区技术，我们计划对此进行研究。此外，提出的启发式适应异构处理系统可以进行。


**Atoll: A Scalable Low-Latency Serverless Platform**

> ACM Symposium on Cloud Computing (SoCC)（2021）CCF B

- Abstract

  随着面向用户的应用采用无服务器计算，无服务器平台良好的延迟性能已经成为一个强有力的基本要求。然而，由于其底层控制和数据平面的设计特别不适合具有不可预测到达模式的短期功能，因此在当今的平台上实现这一点是非常困难的。我们介绍了Atoll，一个无服务器平台，它通过对控制和数据平面的重新设计来克服这些挑战。在Atoll中，每个应用程序都与延迟截止日期相关联。Atoll通过以下方式实现其每个应用程序请求延迟目标:(a)将集群划分为(半全局调度器，工作池)对，(b)执行截止日期感知调度和主动沙盒分配，以及(c)使用负载平衡层进行沙盒感知路由，并自动扩展每个应用程序的半全局调度器。我们的结果表明，与不同的scale方法相比，Atoll减少了**错失的截止日期以及尾延迟**。

  本文主要是提出了一个框架，关注于**sandbox的管理**。通过管理sandbox实现proactive（主动）sandbox allocation和placement，通过scale sandbox来满足负载均衡；使用剩余空闲时间最短方法进行优先级排序和调度以满足延迟截止日期，假设函数不能被抢占。

## Resource Management and Configuration


**AMPS-Inf: Automatic Model Partitioning for Serverless Inference with Cost Efficiency**

> International Conference on Parallel Processing (ICPP)（2021）CCF B

- Conclusion and Architecture

  近年来，无服务器计算显示出巨大的前景，吸引了将机器学习工作负载迁移到无服务器平台的研究关注。在无服务器平台上对部署规模的限制以及神经网络模型的复杂性使得在单个无服务器功能中部署大型模型变得困难。为了解决分割模型和协调分区的挑战，并向用户隐藏这些复杂性，我们设计并实现了AMPS-Inf，这是一个用于无服务器机器学习推理的自动化框架，旨在实现成本效益和及时响应。

  Optimizer为预训练模型(以YAML/JSON格式)找到最佳执行计划和资源分配作为用户输入。从模型分区和lambda内存分配的不同组合中选择，以最小的成本生成最佳配置。Coordinator组件创建由每个分区的函数和权重文件组成的压缩部署包，并将它们部署到AWS Lambda平台上。给定Optimizer的分区点解决方案，AMPS-Inf将YAML文件划分为分区的文件，添加输入和输出层，并将它们(及其依赖项)上传到lambda。推理首先调用与第一个分区对应的lambda，然后依次调用其他lambda。每个过程的中间输出存储在AWS S3中。最终的预测结果将被发送回用户。

  AMPSInf解决了模型划分和资源分配的混合整数二次规划问题，以成本最小化为目标，同时满足响应时间服务水平要求(SLO)。部署在AWS Lambda中，AMPS-Inf使用四个预训练模型进行评估，与Amazon SageMaker和三个不同的基线进行比较。结果表明，AMPS-Inf通过找到lambda资源类型和模型分区的最佳配置，可以在不降低响应时间性能的情况下节省高达98%的成本。



**AQUATOPE: QoS-and-Uncertainty-Aware Resource Management for Multi-stage Serverless Workflows**

> International Conference on Architectural Support for Programming Languages and Operating Systems (ASPLOS)（2023）CCF A

- Abstract

  我们介绍了Aquatope，一个qos和不确定性感知资源管理器，用于多阶段无服务器工作流程。Aquatope共同应对冷启动和资源管理的挑战;前者通过使用混合贝叶斯神经网络，后者使用定制贝叶斯优化。Aquatope使用一组可扩展且经过验证的贝叶斯模型，在函数调用之前创建预热的容器，并在函数粒度上分配适当的资源，以满足复杂工作流的端到端QoS，同时最大限度地降低资源成本。在各种分析和交互式多阶段无服务器工作负载中，Aquatope显著优于先前的系统，与其他QoS会议方法相比，将QoS违反减少了5倍，平均成本降低了34%，最高可达52%。

**Astrea: Auto-Serverless Analytics Towards Cost-Efficiency and QoS-Awareness**

> IEEE TRANSACTIONS ON PARALLEL AND DISTRIBUTED SYSTEMS(TPDS)（2022） CCF A
or Astra: Autonomous Serverless Analytics withCost-Efficiency and QoS-Awareness

- Conclusion

  本文提出了一个优化框架Astrea，用于导航无服务器分析工作的成本性能权衡。Astrea依靠对完井时间性能和作业货币成本的建模来制定针对用户指定目标的优化问题。Astrea根据图论确定了资源配置和Lambda函数编排的最佳解决方案，以最小化预算限制下的作业完成时间，或最小化性能阈值下的货币成本。我们已经在AWS Lambda中实现并部署了Astrea。我们的三个代表性基准的实验结果证明了Astrea在最优资源配置方面的有效性:Astrea在不超出预算约束的情况下实现了21%至60%的性能提升，在不违反QoS目标的情况下实现了20%至80%的成本降低。Astrea的最优性也在与Apache Spark的比较中得到了证明:在无服务器数据分析基准测试中，Astrea的成本降低了近92%，而性能却没有下降。对于机器学习分析，Astrea实现了高达98%的成本降低和至少37%的性能提升。我们扩展的多轮设计和实现Astrea的性能也比Apache Spark好，成本降低了92%。

**COSE: Configuring Serverless Functions using Statistical Learning**

> IEEE Conference on Computer Communications (INFOCOM)（2020）CCF A

- Conclusion

  运行无服务器函数**需要用户配置多个参数**，如内存、CPU、云提供商等。
  虽然相对简单，但正确配置这些参数，同时最小化成本并满足延迟约束并非易事。在本文中，我们提出了COSE，这是一个使用贝叶斯优化来找到无服务器功能的最佳配置的框架。COSE使用统计学习技术来智能地收集样本，并在不可见的配置值中预测无服务器功能的成本和执行时间。我们的框架使用预测的成本和执行时间，在满足客户目标的同时，为运行单个或一系列功能选择“最佳”配置参数。COSE支持函数链，并且能够适应无服务器函数执行时间的变化。我们不仅在商业云提供商上评估了COSE，在那里我们成功地在五个样本中找到了最优/接近最优的配置，而且还在广泛的模拟分布式云环境中评估了COSE，这些环境证实了我们方法的有效性。

  未来的工作包括在更大规模的多云提供商上部署COSE作为服务。这将支持研究广泛的工作负载、应用程序需求以及云资源供应和定价策略。我们打算扩展我们的COSE模拟器，以适应更复杂的场景，比如服务图。请注意，尽管我们没有对输入工作负载变化很大的函数测试COSE，但我们相信，如果输入工作负载可以分类(例如，基于大小)，并且COSE是为每个类单独训练的，那么COSE可以用于这样的场景。


**Deadline-aware Dynamic Resource Management in Serverless Computing Environments**

> 2021 IEEE/ACM 21st International Symposium on Cluster, Cloud and Internet Computing (CCGrid) CCF C





## review

**Auto-scaling techniques in container-based cloud and edge/fog computing: Taxonomy and survey**

关于自动扩缩容的综述。

## benchmark

**BBServerless: A Bursty Traffic Benchmark for Serverless**

- Abstract

  为4种主流云工作负载设计了流量生成算法(基于泊松分布)，即大数据，流处理(Stream)， Web应用程序(WebApps)和机器学习推理(MaLI)。我们在私有云环境中进行跟踪驱动模拟实验。通过从评估中收集的数据，我们观察到时间本地化组件(如CPU迁移、分支预测和缓存)的性能与端到端工作负载性能高度相关。

  [code](https://github.com/whoszus/BurstyServerlessBenchmark)

**Characterizing Serverless Platforms with ServerlessBench**

## dataset

**Characterizing Microservice Dependency and Performance: Alibaba Trace Analysis**


## Other

**Automated Verification of Idempotence for Stateful Serverless Applications**
本文介绍了Flux，这是第一个可以自动验证和帮助确保无服务器应用程序的幂等一致性的工具包。它通过日志保证幂等一致性，同时减少不必要的日志开销。
