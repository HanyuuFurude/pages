---
title: Software Engineering Review
date: 2019-01-13 13:16:18
tags: SE, Software Engineering, review
---

# Chapter 00 Intorduction
* 软件工程的概念、方法和技术：
  * 软件工程基本概念（软件产品、软件过程、软件开发模型）
  * 软件工程开发方法和技术
    * 传统的软件工程方法与技术
    * 面向对象的软件工程方法与技术
  * 软件测试策略和技术
  * 软件项目管理
# Chapter 01 Software and Software Engineering
* Software's dual role
  * Software is a **product** (软件即产品（服务）)
    * Transforms information - produces, manages, acquires, modifies, displays or transmits information;
    * Delivers computing potential of hardwora and networks.
  * Software is a **vehicle(载体)** for delivering a product.
* Hardware & Software
* wear out vs. Deterioration 软件老化和变质
* ![1547359380593](/Review/SoftwareEngineering/1547359380593.png)

*   Component Based & Custom Built

    *   The software industry dose seem to be moving (slowly) toward component-based construction.\
*   Software Complexity

    *   <font color = red>**No Silver Bullet** </font>(智力密集型没有最优解不可预估bug不可避免)
*   >   Software changeability 软件可更改性
    >   *   It must be fixed to eliminate errors. 必须对其进行修复以消除错误。
    >   *   It must be enhanced to implement new functional and non-functional requirements 必须对其进行改进, 以实现新的功能和非功能要求
    >   *   Software must be adapted to meet the needs of new computing environments or technology.软件必须进行调整, 以满足新的计算环境或技术的需要。
    >   *   Software must be enhanced to implement new business requirements.必须增强软件以实现新的业务需求。
    >   *   Software must be extended to make it interoperable with other more modern systems or databases.软件必须进行扩展, 以使其可与其他更现代的系统或数据库进行互操作。
    >   *   Software must be re-architected to make it viable(切实可行的) within a network environment.必须重新构建软件, 使其在网络环境中可行。
*   >   Software Evolution[Lehman定律]（记标题就行）
    >   *   The Law of Continuing Change [持续变化规律] (1974):  E-type systems must be continually adapted else they become progressively less satisfactory.
    >   *   The Law of Increasing Complexity [复杂性增长规律] (1974):  As an E-type system evolves its complexity increases unless work is done to maintain or reduce it.
    >   *   The Law of Self Regulation [自我调控规律] (1974):  The E-type system evolution process is self-regulating with distribution of product and process measures close to normal.
    >   *   The Law of Conservation of Organizational Stability [组织稳定性守恒规律] (1980):  The average effective global activity rate in an evolving E-type system is invariant over product lifetime.
    >   *   The Law of Conservation of Familiarity [保证通晓性规律] (1980): As an E-type system evolves all associated with it, developers, sales personnel, users, for example, must maintain mastery of(熟悉) its content and behavior to achieve satisfactory evolution.
    >   *   The Law of Continuing Growth [持续增长规律] (1980):  The functional content of E-type systems must be continually increased to maintain user satisfaction over their lifetime.
    >   *   The Law of Declining Quality [质量衰减规律] (1996): The quality of E-type systems will appear to be declining unless they are rigorously maintained and adapted to operational environment changes.
    >   *   The Feedback System Law [反馈系统规律] (1996):  E-type evolution processes constitute multi-level, multi-loop, multi-agent feedback systems and must be treated as such to achieve significant improvement over any reasonable base.
*   Software **Myths** 软件谬论
    *   Software Myths affect managers, customers (and other non-technical stakeholders) and practitioners

    *   Software Myths are believable because they often have elements of truth,
        *   but …
            *   Invariably lead to bad decisions,
        *   therefore …
            *   Insist on reality as you navigate your way through software engineering

    *   If we get behind schedule, we can **add more programmers** and catch up.

    *   **A general statement about objectives** is sufficient to begin building programs.

    *   Change in project requirements can be **easily accommodated** because software is flexible.

    *   **Management Myths**

>   “We already have a book of standards and procedures for building software. It does provide my people with **everything** they need to know …”
>
>   “If my project is behind the schedule, I always can add more programmers to it and catch up …”
>
>   “If I decide to **outsource** the software project to a third party, I can just relax: Let them build it, and I will just pocket my profits …”

*   **Customer Myths**

>   “A general statement of objectives is sufficient to begin writing programs - we can fill in the details later …”
>
>   “Project requirements continually change but this change can easily be accommodated because software is flexible …”

*   **Practitioner’s Myths**

>“Let’s start coding ASAP, because once we write the program and get it to work, our job is done …”
>
>“Until I get the program running, I have no way of assessing its quality …”
>
>“The only deliverable work product for a successful project is the working program …”
>
>“Software engineering is baloney[胡扯]. It makes us create tons of paperwork, only to slow us down …”

# Chapter 02 Process 软件过程（综述）

*   Overview

*   What? 过程是什么？当开发产品或构件系统时，遵循一系列可预测的步骤（即路线图）是非常重要的，它有助于及时交付高质量的产品。

*   Who? 相关人员？管理人员、软件工程师和客户均应该参与过程的定义、建立和测试。

*   Why?重要性？提高了软件开发活动的稳定性、可控性和有组织性；否则软件活动会失控并变得混乱。

*   Steps?有哪些步骤？ 具体步骤随着所构造的软件类型不同在细节方面有所变化，但对所有过程来讲有很多活动是相同的。

*   Work product?有哪些工作产品？ 是指过程中定义的一系列活动和任务的结果，包括Programs, documents, and data.

*   Correct process?什么是正确的过程？ Assessment, quality deliverable.

*   IEEE Definition

    >Software Engineering: (1) The application of a systematic, disciplined, quantifiable[系统的、规范的和可量化的] approach to the development, operation, and maintenance of software; that is, the application of engineering to software. (2) The study of approaches as in (1).

![1547363766241](/Review/SoftwareEngineering/1547363766241.png)

*   软件过程

    *   软件过程是一个为建造高质量软件所需完成的任务的框架，即形成软件产品的一系列步骤。包括中间产品、资源、角色及过程中采取的方法、工具等范畴。

*   Software process model

    *   Attempt to organize the software life cycle by
        *   defining activities involved in software production[软件生产]
        *   defining order of activities and their relationships
    *   Goals of a software process
        *   standardization, predictability, productivity, high product quality, ability to plan time and budget requirements

*   早期做法： Code & Fix

    	>The earliest approach
    	>
    	>*   Write code
    	>
    	>*   Fix it (修复) to eliminate any errors that have been detected, to enhance existing functionality, or to add new features
    	>
    	>*   Source of difficulties and deficiencies
    	>    *   impossible to predict（不可预测性）
    	>    *   impossible to manage

*   软件危机 Symptoms of inadequacy: **the software crisis**

    *   **scheduled time and cost exceeded**

    *   **user expectations not met**

    *   **poor quality**

    The **size** and **economic value** of software applications require appropriate "**process models**"

*   Process model goals (B.Boehm 1988)

>   *   determine the order of stages involved in software development and evolution, and to establish the **transition criteria（标准尺度）** for progressing from one stage to the next.  These include completion criteria for the current stage plus choice criteria and entrance criteria for the next stage. Thus a process model addresses the following software project questions:确定软件开发和进化所涉及的阶段的顺序, 并建立从一个阶段到下一个阶段的过渡标准。 其中包括当前阶段的完成标准加上选择标准和下一阶段的标准。因此, 流程模型解决了以下软件项目问题:
>
>       *   What shall we do next?
>
>       *   How long shall we continue to do it?

*   软件过程

    *   黑盒观点

    *   ![1547365114325](/Review/SoftwareEngineering/1547365114325.png)

        *   Problems

            *   The assumption is that requirements **can be fully understood** prior to development

            *   Interaction with the customer occurs **only** at the beginning (requirements) and end (after delivery)

            *   Unfortunately the assumption almost **never holds**

    *   白盒观点

    *   ![1547365404494](/Review/SoftwareEngineering/1547365404494.png)

        *   Advantages
            *   Reduce risks by improving visibility
            *   Allow project changes as the project progresses
                *   based on feedback from the customer

    *   软件开发活动

        *   线性过程模型
        *   非线性模型

*   过程框架

    ![1547365505796](/Review/SoftwareEngineering/1547365505796.png)

*   <font color = red>**通用活动框架（非常重要）**</font>

    ![1547365900978](/Review/SoftwareEngineering/1547365900978.png)![img](/Review/SoftwareEngineering/1547367400287.png)![1547367504297](/Review/SoftwareEngineering/1547367504297.png)

    ![img](/Review/SoftwareEngineering/1039166-20170321200512502-745718093-1547367531435.png)

*   普适性活动 Umbrella Activities
    *   Software project management
    *   Formal technical reviews
    *   Software quality assurance
    *   Software configuration management
    *   Work product preparation and production
    *   Reusability management
    *   Measurement
    *   Risk management
*   能力成熟度模型集成**(CMMI)
*   过程评估 Process Assessment
    *   评估软件过程以确认满足了成功软件工程所必需的基本过程标准(basic
        process criteria**)**要求.The process should be assessed to ensure that it meets a set of basic process criteria that have been shown to be essential for a successful software engineering.
    *   ![1547367730629](/Review/SoftwareEngineering/1547367730629.png)

# Chapter 03 Process Models

![1547451466048](/Review/SoftwareEngineering/1547451466048.png)

*   Prescriptive Models[惯例模型]

    *   Prescriptive process models advocate an orderly approach to software engineering.

        *   question
            *   If prescriptive process models strive for structure and order, are they inappropriate for a software world that thrives on change? 
            *   Yet, if we reject traditional process models (and the order they imply) and replace them with something less structured, do we make it impossible to achieve coordination and coherence in software work?

    *   The waterfall Model 瀑布模型

    *   ![1547451662260](/Review/SoftwareEngineering/1547451662260.png)

    *   >   (适用于需求较为固定和明确的场景、不适应大量、频繁的更改)
        >   1.  The requirements are **knowable** in advance of implementation.
        >   2.  The requirements have **no unresolved, high-risk implications.**
        >   * risks due to COTS choices, cost, schedule, performance, safety, security, user interfaces, organizational impacts.
        >   3.  The nature of  the requirements will **not change very much.** 
        >   *   During development; during evolution.
        >
        >   4.  The requirements are **compatible with** all the key system stakeholders’ expectations. 
        >       *   e.g., users, customer, developers, maintainers, investors.
        >   5.  The **right architecture** for implementing the requirements is well understood.
        >   6.  There is **enough calendar time** to proceed sequentially.~

    *   The V Model V模型

        *   ![1547454083297](/Review/SoftwareEngineering/1547454083297.png)

    *   Incremental Models 增量模型

    *   *   ![1547454772132](/Review/SoftwareEngineering/1547454772132.png)
        *   RAD 模型
        *   ![1547454814108](/Review/SoftwareEngineering/1547454814108.png)

    *   Evolutionary Models 演化模型

       *   >   客户不确定要求 工程师对算法效率 可用性不确定
           >
           >   帮助客户和工程师了解要构建的内容快速设计和实现

       *   Prototyping 原型

       *   ![1547455509874](/Review/SoftwareEngineering/1547455509874.png)

       *   >原型范式中的问题
           >sw 工程师尝试修改原型以用作工作版本
           >一旦客户看到工作原型, 她希望很快就能得到工作产品
           >

       * The Spiral 螺旋形

           *   ![1547455726118](/Review/SoftwareEngineering/1547455726118.png)

       * Full Spiral Model 

           *   Radial dimension[按射线方向]: cumulative cost to date
           *   Angular dimension[按螺旋方向]: progress through the spiral
           *   ![1547455837090](/Review/SoftwareEngineering/1547455837090.png)

       *   UP Unified Process Model 统一过程模型

           *   用例驱动
           *   以体系结构为中心
           *   迭代和增量
           *   jia'gou
           *   ![1547455977324](/Review/SoftwareEngineering/1547455977324.png)
           *   Life cycle![1547455998301](/Review/SoftwareEngineering/1547455998301.png)
*   软件生命周期、概念、阶段

*   软件过程模型

# Chapter 04 Agile Development

*   敏捷开发 XP

# Chapter 06

*   <font color = red>系统工程中的概念</font>
*   系统建模
*   系统建模分类

# Chapter 07

*   需求工程任务
*   需求工程工作产品
*   <font color = red>需求开发方法</font>

# Chapter 08

*   分析模型的作用
*   分析模型的构建原则
*   <font color = red>方法</font>
    *   **场景建模**
        *   用况use-case
        *   部署图
        *   ……
    *   **类建模**
        *   **class图**
        *   **协作图**
        *   ……
    *   行为建模
        *   状态转换图
        *   活动图
        *   顺序图

# Chapter 09

*   抽象abstraction
*   体系结构architecture 
*   模式patterns
*   逐步求精refinement
*   模块化modularity
*   信息隐藏information hiding 
*   模块独立functional independence 
*   Refactoring（重构）

# Chapter 10

*   为何进行体系结构设计
*   **体系结构风格（style）**

# Chapter 11

*   构件
*   构建设计原则：开关、替换、依赖倒置、接口分离
*   内聚性、耦合性
*   构建设计方法：DPL、程序流程图、决策表

# Chapter 13~14

*   测试策略
    *   **单元测试**
    *   **集成测试**：big bang, top down, bottom up
    *   确认测试
    *   系统测试
*   测试用例
*   测试技术
    *   白盒、黑盒
    *   手工测试、自动化测试

# Chapter 21 

*   4P模型
*   W5HH

# Chapter 15，22

*   **McCall质量因素**
*   Measures,Metrics,Indicators
*   **度量的作用**

# Chapter 23

*   **项目计划任务和内容**
*   LOC&FP

# Chapter 24

*   任务网络、关键路径的作用
*   **里程碑**

# Chapter 25

*   被动风险和主动风险管理
*   Risk Management Paradigm（风险过程管理）
*   **RMMM**

# Chapter 26

*   **McCall软件质量模型**
*   软件质量保证活动
*   **正式技术评审**
*   软件质量的成本

# Chapter 27

*   软件配置项、版本、基线etc.
*   **软件配置管理流程**
*   