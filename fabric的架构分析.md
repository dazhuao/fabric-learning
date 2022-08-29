# node节点
一个node节点仅仅是一个逻辑函数，在这个意义上，多个不同类型的node节点可以运行在同一台服务器上。
1. 客户端
客户端代表最终用户实体，必须连接到一个peer节点以便与区块链交互。客户端可以选择连接任何peer节点，创建并调用交易。
2. peer
以块的形式从排序服务（orderer）接受有序状态更新，维护状态和账本。还有一个特殊的背书角色。每个链码指定一个背书策略，引用一组背书节点。
3. orderer
排序者产生排序服务，即一个提供交付保证的通信架构。


# fabric 整体项目结构介绍

- bccsp：全称为 blockchain cryptographic service provider，提供了加密标准以及算法的实现，为整个项目提供统一的加密、签名、验签服务。
- cmd：类似于提供了一个客户端，可以通过命令和Fabric交互。
- common：提供了通用功能以及一些通用的代码实现，包括日志、错误、工具包等，主要包括项目全局的功能性代码。
- core： 核心代码模块，其中包括权限控制、chaincode模块、committer、endorser、ledger、policy等核心功能的代码实现。
- devent： 主要是历史遗留原因，早期的docker不支持Windows操作系统，使用vagrant运行Ubuntu，在启动docker，以此来构建开发环境，但是目前各大操作系统已支持docker，所以不建议采用这种方案。
- discovery：该模块旨在为客户端程序提供服务发现的功能。
- docs：基于python的sphinx进行在线文档的构建。
- example：为整个项目提供相关的操作案例。
- gossip：流言蜚语，为fabric在节点间达成最终一致性，实现信息的传播的模块。
- idemix：对IDEMIX的支持相关，和零知识证明相关，适用于开发环境。
- images：打包文件
- integration:行为驱动开发相关。
- msp：全称为 membership service provider，为fabric统一提供成员服务。
- orderer：进行全局的交易排序以及切块，并推送给peer。
- peer：包含peer节点的入口代码，以及命令行操作的相关功能。
- protos：存放Protocol buffer的消息，相关的通信协议数据处理（protobuf）以及数据结构体。
- release：发布模板。
- release-note：各版本的changelog。
- sampleconfig：相关样例配置文件。
- scripts：用于存放相关脚本文件。
- token：资产管理相关接口服务。
- unit-test：Docker环境下的单元测试。
- vendor：Golang的第三方包管理器。
- Makefile：用于编译Fabric。