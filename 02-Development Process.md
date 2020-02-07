# 开发过程Development Process

* **可以通过不同的过程来使用UML，按需抉择**

## 一、迭代和瀑布过程Iterative and Waterfall Processes

本质区别在于如何将一个项目划分为较小的块

### 1.1、瀑布式开发（过时）

* 基于活动activity分解项目，如将一个项目分解为需求分析、设计、代码、测试等多个阶段
* 应当尽量减少回流backflows，如在代码阶段修改需求分析和设计
* 缺点：无法确切跟踪项目进展状况

### 1.2、迭代式开发

* 基于功能子集subsets of functionality分解项目，每个功能子集都需完成完整的软件生命周期（需求分析、设计、代码、测试等） - 每次迭代都是一个小的瀑布开发
* 在迭代开始前会有探索活动exploration activity，从而对需求有个高层次的理解，并将需求划分成后续的迭代，也可能会在探索活动中产生高层次的设计决策
* 每次迭代后会有一段稳定期stabilization period，用于修改bug，从而提供produced-ready integrated software（迭代式开发的每次迭代都需要提供接近生产质量的可测试、可集成的代码 -> 即任何一次迭代的结果都可以在不需要进行大量额外工作的情况下发布）
* 时间盒time boxing：每次迭代的时间都必须是固定的，若无法在规定时间内完成本次迭代，只能减少本次迭代的功能点，而不能让本次迭代延期
* 注重rework，常用以下一种技术
  * 自动化回归测试Automated regression tests
  * 重构Refactoring
  * 持续集成Continuous integration
* 每次迭代后可以进行迭代回顾iteration retrospective，可列出以下三个列表：
  * 保留Keep：已经达到的目标，并希望在下次迭代中继续保持
  * 问题Problems：没有达到目标的地方
  * 尝试Try：对过程process做出的修改



## 二、预测性计划和适应性计划Predictive and Adaptive Planning

### 2.1、预测性计划Predictive Planning

* **针对未来进行计划**（偏向于预测未来的新需求）
* 将项目分为两个阶段
  * 第一阶段：提出计划，难以预测
  * 第二阶段：由于有可参照的计划，所以可预测性比第一阶段高
* 需求流失requirements churn会导致计划赶不上变化
* 建议
  * 在无法得到确切、具体、稳定的需求前，不要制定预测性计划
  * 如果无法获得确切、具体、稳定的需求，请使用适应性计划

### 2.2、适应性计划Adaptive Planning

* **针对变更进行计划**
* 将变更视为软件项目中的常量
* 需要使用迭代式开发



## 三、敏捷过程Agile Processes

* 更加人性化，适应性强
* 强调项目人员水平和团队协作关系
* 迭代周期/时间盒通常很短（一个月以内）
* 文档的重要性不高，通常只将UML作为草图使用
* 轻量级，没有繁琐的仪式 -> 以人为本



## 四、统一软件开发过程Rational Unified Process

* 是一个开发过程的框架
* 使用时需要提供开发案例development case，即指明将在项目中使用什么过程，开发案例各不相同，需要为一个项目量身定制
* **是一个迭代过程**，分为四个阶段
  * 开端Inception：对项目进行初步评估，决定是否在elaboration阶段投入足够资金
  * 细化Elaboration：明确项目的主要用例，并以迭代的方式构建软件。细化过程后，需要对需求有较好的理解，并提供后续开发的工作系统骨架。同时，需要发现并解决项目的主要风险
  * 建设Construction：继续构建过程，开发足够的功能并发布
  * 过渡Transition：包括不需要参与迭代的后期过程，如部署、用户培训等



## 五、将UML运用到开发过程中Fitting the UML into a Process

### 5.1、需求分析阶段Requirements Analysis

* 最重要的是与用户和客户沟通，不要引入过多符号表示notation
* **不要涉及软件实现的细节**
* **当某个UML规则限制了和用户、客户的交流时，一定要打破该规则**
* 可能用到的UML图类型
  * 用例图Use cases：介绍人如何与系统交互
  * 概念角度的类图class diagrams from a conceptual perspective：是一种建立严格的领域词汇的方法
  * 活动图activity diagrams：显示用例的上下文，以及复杂用例的工作细节
  * 状态图state diagrams：帮助展示概念，该概念拥有生命周期、多个状态和能够改变状态的事件

### 5.2、设计阶段Design

* 可以使用更多的符号表示notation，并且需要精确地使用这些符号表示
* 瀑布式开发&迭代式开发
  * 瀑布式开发：以蓝图的方式使用UML
  * 迭代式开发：以草图或蓝图的方式使用UML
    * 草图方式：更加随意、流畅，可随时修改（更推荐，难以保证蓝图的正确性）
      * 可以在迭代开始前花几天以草图的方式进行设计，也可以在迭代中随时召开会议
    * 蓝图方式：更加确定，不能随便修改
      * 在迭代早期进行，先于功能的构建
      * 每次迭代不再是从头开始，而是修改现有文档的主体，突出当前迭代做出的修改
* 可能用到的UML图类型
  * 软件角度的类图class diagrams from a software perspective：描述软件中的类以及他们直接如何交互
  * 序列图sequence diagrams：使用CRC card(Class-responsibility-collaboration card)或序列图描述用例中的重要场景或特殊场景，展示软件内部的情况
  * 包图package diagrams：展示软件的大规模组织
  * 复杂生命周期类的状态图state diagrams for classes with complex life histories
  * 部署图deployment diagrams：展示软件的物理部署

### 5.3、文档化阶段Documentation

* **UML图无法代替详细的文档**
* 可能用到的UML图类型：注意权衡全面性和可理解性
  * 包图package diagram：提供系统的逻辑路线图
  * 部署图deployment diagram
  * 类图class diagram：只需提供重要特征即可
  * 交互图interaction diagram：显示重要的交互
  * 状态机图state machine diagram：用于描述具有复杂生命周期的类（行为十分复杂）
  * 活动图activity diagram：用于帮助理解复杂算法

### 5.4、理解旧代码Understanding Legacy Code

* 使用草图帮助理解关键类和类之间的交互
* 使用工具生成关键部分的图，如生成序列图帮助理解多个对象如何协作处理复杂方法