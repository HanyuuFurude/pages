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
* ![1547359380593](/SoftwareEngineering/1547359380593.png)

*   Component Based & Custom Built

    *   The software industry dose seem to be moving (slowly) toward component-based construction.\
*   Software Complexity

    *   **No Silver Bullet** (智力密集型没有最优解不可预估bug不可避免)
*   Software changeability 软件可更改性
    *   It must be fixed to eliminate errors. 必须对其进行修复以消除错误。
    *   It must be enhanced to implement new functional and non-functional requirements 必须对其进行改进, 以实现新的功能和非功能要求
    *   Software must be adapted to meet the needs of new computing environments or technology.软件必须进行调整, 以满足新的计算环境或技术的需要。
    *   Software must be enhanced to implement new business requirements.必须增强软件以实现新的业务需求。
    *   Software must be extended to make it interoperable with other more modern systems or databases.软件必须进行扩展, 以使其可与其他更现代的系统或数据库进行互操作。
    *   Software must be re-architected to make it viable(切实可行的) within a network environment.必须重新构建软件, 使其在网络环境中可行。
*   Software Evolution[Lehman定律]（记标题就行）
    *   The Law of Continuing Change [持续变化规律] (1974):  E-type systems must be continually adapted else they become progressively less satisfactory.
    *   The Law of Increasing Complexity [复杂性增长规律] (1974):  As an E-type system evolves its complexity increases unless work is done to maintain or reduce it.
    *   The Law of Self Regulation [自我调控规律] (1974):  The E-type system evolution process is self-regulating with distribution of product and process measures close to normal.
    *   The Law of Conservation of Organizational Stability [组织稳定性守恒规律] (1980):  The average effective global activity rate in an evolving E-type system is invariant over product lifetime.
    *   The Law of Conservation of Familiarity [保证通晓性规律] (1980): As an E-type system evolves all associated with it, developers, sales personnel, users, for example, must maintain mastery of(熟悉) its content and behavior to achieve satisfactory evolution. 
    *   The Law of Continuing Growth [持续增长规律] (1980):  The functional content of E-type systems must be continually increased to maintain user satisfaction over their lifetime.
    *   The Law of Declining Quality [质量衰减规律] (1996): The quality of E-type systems will appear to be declining unless they are rigorously maintained and adapted to operational environment changes.
    *   The Feedback System Law [反馈系统规律] (1996):  E-type evolution processes constitute multi-level, multi-loop, multi-agent feedback systems and must be treated as such to achieve significant improvement over any reasonable base.
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

![1547363766241](/SoftwareEngineering/1547363766241.png)

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

*   软件危机 

*   Symptoms of inadequacy: **the software crisis**

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

    *   ![1547365114325](/SoftwareEngineering/1547365114325.png)

        *   Problems

            *   The assumption is that requirements **can be fully understood** prior to development

            *   Interaction with the customer occurs **only** at the beginning (requirements) and end (after delivery)

            *   Unfortunately the assumption almost **never holds**

    *   白盒观点

    *   ![1547365404494](/SoftwareEngineering/1547365404494.png)

        *   Advantages
            *   Reduce risks by improving visibility
            *   Allow project changes as the project progresses
                *   based on feedback from the customer

    *   软件开发活动

        *   线性过程模型
        *   非线性模型

*   过程框架

    ![1547365505796](/SoftwareEngineering/1547365505796.png)

*   <font color = red>**通用活动框架（非常重要）**</font>

    ![1547365900978](/SoftwareEngineering/1547365900978.png)![img](/SoftwareEngineering/1547367400287.png)![1547367504297](/SoftwareEngineering/1547367504297.png)

    ![img](/SoftwareEngineering/1039166-20170321200512502-745718093-1547367531435.png)

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
    *   ![1547367730629](/SoftwareEngineering/1547367730629.png)