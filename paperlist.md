# Papers

Here are some useful papers about serverless computing.And we look forward to your discussion and exploration with us!

We have simply divided the papers into the following categories for easy selective reading.


## Review（综述型）
综述型论文是对某一专题、某一领域的历史背景、前人工作、争论焦点、研究现状与发展前景等方面，以作者自己的观点写成的严谨而系统的评论性、资料性的论文。会引用某个领域50～100篇（甚至更多）文献参考资料，来辨明其中的关系、矛盾、差距及不一致性，并建议解决问题的后续步骤。该类型论文不要求作者对其研究发现进行阐述，因此这类论文一般在项目初期通过大量的文献资料研究进行撰写。


**Cloud Programming Simplified: A Berkeley View on Serverless Computing**
  
  > [本文](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2019/EECS-2019-3.pdf)是Berkeley于2019年发表在 _Journal Computing Research Repository (CoRR)_ 上的一篇文章。
  
  论文首先简要回顾了云计算的历史，包括 2009 年伯克利云计算观点论文的预测，然后解释了无服务器计算的动机，描述了一些挑战当前无服务器计算的应用，最后列出了无服务器计算实现其全部潜力的必要障碍和研究机会。正如 2009 年的论文指出了云计算的挑战并预测它们将被解决，云应用将加速，我们预测这些问题是可以解决的，无服务器计算将增长到主导未来云计算的发展。
  
**Serverless Computing: State-of-the-Art, Challenges and Opportunities**
  
  > IEEE Transactions on Services Computing（2022）
  
  [本文](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9756233)的研究机构：Cloud Center | Center for Cloud Computing | Center for Cloud Computing Research | Faculty of Science and Technology
  
  - 摘要  
  
  $\qquad$ 无服务器计算正因其轻量级和简单的管理而越来越受欢迎。它通过将计算单元的粒度降低到函数级别来实现这些优点。具体来说，无服务器计算允许用户专注于函数本身，而将其他繁琐的管理和调度问题留给平台提供商，后者负责在高性能调度和低资源成本之间取得平衡。在本文中，我们对无服务器计算进行了全面的调查，特别关注其基础架构特性。通过这种方式，我们确定了一些现有挑战，并分析了相关的尖端解决方案。利用这些结果，我们进一步研究了一些典型的开源框架，并研究了它们如何解决确定的挑战。鉴于无服务器计算的巨大优势，预计其部署将主导未来的云平台。因此，我们还看到了一些有待未来进一步探索的有前景的研究机会。我们希望本文的工作能够激发那些从事相关领域的研究人员和实践者，让他们认识到无服务器计算的重要性，从而涉足这个有前景的领域，为它的发展做出巨大贡献。
  
## Analytic（分析型）
分析型论文主要由分析构成，可以是分析数据，或者分析模型等等。

**Let's Trace It: Fine-Grained Serverless Benchmarking using Synchronous and Asynchronous Orchestrated Applications**
  
  > [本文](https://arxiv.org/pdf/2205.07696.pdf)是存储在 _arXiv_ · Distributed, Parallel, and Cluster Computing（2022）上的一篇文章。
  
  **摘要**：要使无服务器计算广泛适用，需要详细了解性能。尽管现有的基准测试方法存在，但它们仅报告粗略的结果，不使用分布式跟踪，不考虑异步应用程序，并且对（根本原因）分析的能力有限。为解决这个差距，我们设计并实现了 ServiBench，一个无服务器基准测试套件。我们对 AWS 环境中的服务器端应用性能进行了全面的**白盒分析**。ServiBench (i) 利用同步和异步的无服务器应用程序，代表生产使用情况，(ii) 扩展云提供商数据以生成现实的负载，(iii) 进行全面的端到端实验，以捕获应用程序级别的性能，(iv) 使用基于（分布式）无服务器跟踪的新颖方法分析结果，(v) 支持全面的无服务器性能分析。通过 ServiBench，我们对 AWS 进行了全面的实验，涵盖了五个常见的性能因素：**中位数延迟、冷启动、尾延迟、可扩展性和动态工作负载**。我们发现，无服务器应用程序的中位数端到端延迟通常不是由函数计算而是由外部服务调用、编排或基于触发器的协调所主导。我们根据公平原则发布收集的实验数据，并将 ServiBench 作为一个经过测试的可扩展的**开源**工具发布。
  
**Serverless in the Wild: Characterizing and Optimizing the Serverless Workload at a Large Cloud Provide**

> 本文是Microsoft Azure and Microsoft Research发表在ATC(International Conference on Autonomic and Trusted Computing) 2020上的一篇文章


- serverless中的特点
  对于云提供商而言，目标是以最小的资源开销来提供最高的执行性能。
  函数执行的速度和消耗的资源主要取决于三个方面：
  1.需要预先将代码加载到内存中(例如，用户代码、语言运行库)
  2.将所有函数所需的资源始终保存在内存中可能非常昂贵，特别是在函数执行时间短且执行频率不高的情况下。
  3.可能有多种多样的资源需求和多触发器的调用频率，这些特征使得通过预测来减少资源使用变得非常复杂。

- 对Azure真实生产环境下Serverless负载特征的观察以及总结
  1.对于函数和应用程序，每天的调用数量横跨了8个数量级，展示serverless调用的高度差异性(highly variable)，这使得提供者必须专门用于每个应用程序的资源也变化很大。
  2.绝大多数的function或者application的调用频率都非常低：45%的应用程序平均每小时调用一次或更少，81%的应用程序平均每分钟调用一次或更少。
  3.function或者application的流行度：受欢迎的Application占所有Application的18.6%，这些App平均每分钟至少被调用一次，却创造了99.6%的函数调用量。50%的调度源于 0.1% 的函数。说明总请求数是源于少数的 top 函数，而绝大部分函数调用是较少的。
  4.函数的执行时间：50%的函数平均执行时间小于1秒，50%的函数最大执行时间小于3秒；90%的函数的平均时间最多为60s, 96%的函数的平均时间小于60s。与其他云工作负载相比，这个FaaS工作负载中的函数非常短。例如，Azure[12]的数据显示，63%的虚拟机分配持续时间超过15分钟，只有不到8%的虚拟机持续时间小于或等于5分钟。这意味着FaaS对提供者施加了更严格的要求，以快速地准备好资源。
  5.与内存的关系：调用频率和内存分配之间以及内存分配和函数执行时间之间**没有**很强的相关性。
  6.其他特征：
    Queue和Event类型虽然在Function中占比较小，但在Invocation中占比很大，因为这些触发器是自动化地频繁地被触发。而Timer则相反，虽然在Function中占比较大，但是在Invocation中占比很小，说明Timer的定时时长都很高。
    白天调用量高于晚上，工作日的调用量高于周末。

**预热以及保活机制**

![policy](https://github.com/Rachel-Ti/Research/blob/main/img/alive.png)

[data](https://github.com/Azure/AzurePublicDataset)

[参考文章](https://zhuanlan.zhihu.com/p/566802605)

## Methods（方法型）
方法型论文旨在展示一种新的实验方法、测试方法或者流程，对结果不做过多阐述。其架构和篇幅与研究型论文相似。尽管结果不是这类论文的核心部分，但大部分期刊仍会要求提供结果相关的数据样本。

**Ditto: Efficient Serverless Analytics with Elastic Parallelism**

> 本文是北京大学发表在SIGCOMM 2023(A)上的一篇文章

- 核心
  本文主要通过合适的资源配置和任务放置以优化完成作业的时间(JCT)和成本（考虑执行成本）。提出了一个基于步进的时间模型来捕捉执行时间和并行度之间的关系；设计了一种DoP比率计算算法，在给定的函数布局方案下，有效地计算出各阶段之间的最佳DoP比率；提出了一种启发式贪婪分组算法，该算法将各个阶段按降序分组。


- Motivation
  1.传统的服务器提供的资源：
  要求用户提供固定的资源池。作业在其整个生命周期内都依附于这个资源池，而不考虑每个阶段的不同特征和不同的资源需求。

  2.无服务器计算定价模型：
  用户只对函数执行期间消耗的资源收费，这使其非常适合数据分析工作。

  3.已有的相关研究：
  最先进的解决方案NIMBLE根据每个阶段处理的数据量来调整DoP（每个阶段的并行数），一个阶段的输入数据量与其资源需求相关。

  4.已有研究存在的问题：
  一个阶段的输入数据量不能准确反映其实际的资源消耗，这忽略了DAG中不同阶段之间的关系。
  未考虑由于不同的函数放置而导致的阶段之间数据通信的影响

- Implementation
  1.任务启动时间：任务启动时间影响任务性能。启动任务太早会导致等待上游任务的不必要成本，而启动任务太晚则会增加JCT。NIMBLE[51]侧重于估算启动任务的合适时间，我们采用Ditto中的NIMBLE算法来确定任务的启动时间。确定并行配置和任务放置后触发NIMBLE算法，Ditto使用计时器在计算的任务启动时间发送执行请求。
  2.框架：用c++语言用~ 3000行代码实现了Ditto的系统原型。我们的实现基于SPRIGHT[46]，这是一个无服务器框架，允许通过共享内存进行高性能数据通信。在SPRIGHT之上实现了一个数据分析执行引擎。该引擎集成了一组用于分析查询的SQL操作符(例如，join和groupby)。它还提供了数据通信api(例如shuffle和broadcast)，根据上游和下游任务的共存位置，透明地将I/O请求分派到共享内存或外部存储。
  3.Benchmark：TPC-DS分析基准[17](https://www.tpc.org/tpcds/.)，为零售产品供应商提供具有代表性的工作负载。它对决策支持系统的几个普遍适用的方面(包括查询和数据维护)进行建模。作为通用决策支持系统，基准测试提供了具有代表性的性能评估。基准测试结果测量单用户模式下的查询响应时间、多用户模式下的查询吞吐量以及受控的、复杂的、多用户决策支持工作负载下给定硬件、操作系统和数据处理系统配置的数据维护性能。TPC基准测试的目的是为行业用户提供相关的、客观的性能数据。TPC-DS使大数据系统等新兴技术能够执行基准测试。

  4.评估指标：将JCT和成本作为评估Ditto的指标。对于给定的查询，JCT定义为从提交查询到完成最后一个任务的持续时间。成本定义为内存占用乘以每个任务的执行时间的总和，这与主要云提供商的计费策略一致[5,10,13]。为了保证所有任务都顺利执行，我们使用最大理论内存占用来表示其实际内存占用。我们考虑了共享内存和Redis中数据持久化的成本，而忽略了S3中的成本[7]。这是因为内存成本在无服务器计算中占主导地位。

[code](https://github.com/chaojin0310/Ditto)




## Problems（问题型）

**Modeling and Optimization of Performance and Cost of Serverless Applications**


> 本文是发表在 IEEE Transactions on Parallel and Distributed Systems 2021上的一篇文章。

- Motivation
  由于serverless中的工作流不能够表达所有类型的应用程序，许多研究工作已经证明，基于有向无环图(DAG)和Petri网的工作流对于并行、分布式和科学计算系统的性能和成本建模是有效的[25]，[26]，[27]。然而，它们都不适合无服务器范例，因为dag中不允许循环和循环，并且在Petri网中没有有效的解决方案会导致状态爆炸问题。Petri网的缺点还在于其高复杂性和对云计算中非功能需求的有限支持[28]。因此，本文对serverless application进行建模，包括4种类型的结构：并行、分支、循环和自循环。
  ![workflow](https://github.com/Rachel-Ti/Research/blob/main/img/workflow.png)

- Solution
  本文在上述结构的基础上采用一些方法简化结构，将复杂的结构转化为概率DAG，并且设计性能模型和成本模型，模型的目标是在预算或者延迟的约束下优化延迟或者成本，本质是一个分组背包问题（MCKP），由于MCKP已被证明是一个NP完全问题，除非P=NP[35]，否则在多项式时间内没有任何解，因此必须采用启发式算法。作者基于关键路径采用3种贪心策略找到合适的内存配置以实现目标。

- 商业工作流结构：
  对AWS和Azure官方存储库进行了实证分析[30]，[31]。该存储库中由Amazon Step functions或Microsoft Azure functions编排的无服务器应用程序中的平均函数数少于5个；在存储库中没有发现任何类似于最坏情况拓扑的无服务器应用程序。最常见的类型学似乎是顺序的、平行的和分支的。

- Conclusion
  提出了一个分析模型来获得无服务器应用程序的平均端到端响应时间和成本，以及一个性能/成本权衡的优化算法。无服务器应用程序工作流中的结构(即并行、分支、循环和自循环)在有向图上定义。该分析模型利用图算法来处理无服务器应用中的结构，并将工作流转换为加权有向无环图(DAG)。然后，分析模型计算DAG中路径的加权平均响应时间和函数的平均调用次数，由此得出模型的输出，即端到端响应时间和成本的平均值。
  在此基础上，提出了概率优化关键路径算法(PRCP)，该算法是一种基于关键路径方法的启发式算法，旨在给出在预算/性能下，实现最佳性能/成本的最优内存配置

- Limitation 
  虽然提出的模型和算法首次尝试解决无服务器应用程序的性能和成本建模和优化问题，但它有几个局限性:
  1)分析模型只能预测端到端平均响应时间和成本。然而，平均值可能不是一个很好的性能/成本指标[14]。例如，开发人员可能会关注应用程序的退出状态、尾部延迟和高百分比成本(例如，响应时间的90百分比)，以满足细粒度的服务级别协议。
  2)同样，优化算法基于平均端到端响应时间和成本来解决性能/成本的权衡，这对于细粒度的权衡分析可能不是有效的优化约束。
  3)性能模型不适用于由映射状态引入的动态并行性应用程序或具有多个出口点的应用程序。此外，分析模型不能很好地扩展，不能在具有嵌套周期和无条件跳转（nested cycles and unconditional jumps）的APP上工作，从而限制了可以建模和优化的FaaS APP的类型。
  4)前期工作所依据的计费模式发生了变化。AWS引入了一个粒度为1ms和1MB的计费模型[15]，在我们之前的工作中，该模型可以显著提高功能的成本效益，但会降低模型的准确性。

- Attention:
  FineGrained_Performance_and_Cost_Modeling_and_Optimization_for_FaaS_Applications是该文的后续工作，于2023年发表在TPDS上的文章。
  [code](https://github.com/pacslab/SLApp-PerfCost-MdlOpt)


**On the Joint Optimization of Function Assignment and Communication Scheduling toward Performance Efficient Serverless Edge Computing**


> 发表在2022 IEEE/ACM 30th International Symposium on Quality of Service (IWQoS)，CCF B

- 核心
本文主要研究边缘环境下的serverless函数分配的问题，该问题通常被视为虚拟网络嵌入(Virtual Network Embedding, VNE)问题[10]-[12]，其中计算资源和通信资源是联合分配的。并且关注serverless中的数据传输，考虑不同的**通信方式**优化数据传输时延。提出启发式算法，优先分配占用资源大的函数，为了优化性能选择远程数据传输或者服务器之间直接数据传输。

- Motivation
基于通信方式
1.对于扇出程度较高的function，传统的端到端数据传输通信方式(如定义为直传)很容易成为性能瓶颈，因为需要并行传输的数据太多，会竞争有限的网络带宽 [13]。
为了解决这个问题，利用远程存储集群(如Amazon S3、ElastiCache-Redis等云存储)作为转发即时数据的中继，已经作为实践状态技术广泛应用于几个无服务器计算基础设施(如Amazon Lambda、OpenLambda)。远程存储具有较高的带宽和可扩展性，可以提供相对稳定的传输速率，并且可以很好地适应高扇出度的无服务器功能[14]-[16]。

2.对于扇出度较低的功能，远程存储的传输效果不如直传，主要有两个原因:
  1)远程存储需要更多的传输轮数(往返于远程存储集群)
  2)为了保证并行传输的稳定性和公平性，远程存储只能为每条传输链路提供较低的带宽。
  因此，不同的方式各有利弊，没有通用全面的解决方案。

- Conclusion
  在本文中，研究了如何通过适当的函数分配和通信风格选择来加速边缘云中无服务器应用程序的性能。我们将最小应用完成时间的联合优化问题形式化化为非线性整数规划形式，并证明了它是np困难的。我们进一步提出了一种叫做PASS的启发式算法，并从理论上分析了其近似比。通过跟踪驱动的仿真，我们广泛地验证了PASS算法的效率，因为它确实显著优于现有的最先进的函数分配策略。作为第一个考虑通信风格选择的工作，我们的工作显著地证明了通信风格选择对整个应用程序性能的重要性。



