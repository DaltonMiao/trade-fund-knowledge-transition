# GI / Trade Fund Onboarding 超级详细知识沉淀

> 对象：Haoling GI Onboarding  
> 术语规范：全文统一使用 **Trade Fund**，不使用任何音译写法。  
> 内容来源：基于已检索到的 Session 1-6 会议转写/纪要整理。本文是知识沉淀版，不是逐字稿；所有超出会议明确内容的推导均避免写入。  
> 适用场景：新人 onboarding、后续复盘、知识库沉淀、培训材料升级。

---

# 0. 使用说明

本文档按“全局知识地图 + 逐场 Session 记录 + 术语表 + 流程图 + Gap/Backlog”组织。

建议使用方式：

1. 新人先阅读第 1-3 章，建立 Trade Fund 领域全景。
2. 再按 Session 1-6 顺序阅读第 4 章，理解知识是如何逐步展开的。
3. 遇到具体项目/需求时，查第 5-7 章的术语、流程与 backlog。
4. 后续每场新增 onboarding 后，按第 8 章模板追加。

---

# 1. 全局知识地图：Trade Fund 在 GI 中的完整闭环

从目前 6 场 onboarding 来看，整体知识主线可以总结为：

```text
组织与角色
→ ITT / Trade Term 业务基础
→ Funding Generation
→ FID / Checkbook 系统承载
→ PR / Post OI / PP / Pay to Agency 等支付路径
→ GI 主流程与边缘模块
→ Optima / SAP / ICP 等上下游系统
→ 数据准确性、合规、资金健康度管理
```

## 1.1 组织与治理层
Trade Fund 不是一个单纯 IT 系统问题，它涉及多个 stakeholder：

- Corporate MSP / GET team：销售中台，参与政策、流程、ITT design、operation原则、需求过滤。
- Corporate Finance：参与 ITT design、资金健康度、overspending 监控、财务 guidance。
- Second Line / Compliance：负责流程合规、事中/事后监控、异常发现和合规需求。
- IG / Internal Audit Group：负责部分报销材料审核。
- AE / CTFM：核心用户群体，负责客户、活动、资金使用、对账、报销与资金健康。
- IT / GI team：负责用系统承载业务流程，并通过 GI / Optima / SAP / ICP 等系统握手实现数字化闭环。

## 1.2 业务规则层
Trade Fund 的业务规则核心来自 ITT / Trade Term：

- ITT 可理解为 Integrated Trade Term。
- Trade Term 可以区分 demand term 与 supplier term。
- GI 更关注 demand term 中与 promotion、formal、pricing、reimbursement 相关的内容。
- Funding 和 Spending 必须分开理解：
  - Funding 是钱怎么来。
  - Spending 是钱怎么花出去。

## 1.3 系统对象层
GI 中承载 Trade Fund 的核心对象包括：

- FID / Fund Account：客户或 banner 层面的资金账户。
- Checkbook：FID 下更细的资金管理容器。
- Payment AE：每个 checkbook 只能有一个 payment AE。
- Fund Type / Fund Bucket：例如 KBD、PP funding 等。
- Activity / PID：Post OI 主流程中的活动对象。
- POA / POP / Request Payment：报销链路中的关键单据/材料/动作。

## 1.4 支付路径层
目前 onboarding 中已覆盖或提及的路径包括：

1. **PR / Pre OI / Pro I**
   - 下单时客户直接享受折扣。
   - 包括 Category PR 和 SKU PR。
   - Category PR 通常财年初由 central team 维护。
   - SKU PR 可由 AE 基于业务需求维护，O&O 场景正在自动化。

2. **Post OI**
   - 事后报销。
   - 需要建活动、审批、POA、执行、POP、request payment、IG审核、Optima付款。

3. **PP / Promotion Pack**
   - 促销装相关，客户下单时享受价格优惠。
   - 有实际 spending 数据回流。
   - 可能涉及 PP funding、KBD 扣减、switching factor、借还 KBD 等复杂逻辑。

4. **Free Goods**
   - 旧财年逻辑中与 LSR / PP 类似，但新财年会从当前 SD/LSR 逻辑中移出。
   - 后续走向在会议中未完全确认。

5. **Pay to Agency**
   - 用于第三方平台/agency 发券等场景。
   - 已被多次提及，但尚未在已整理的 6 场中完整展开。

---

# 2. 核心术语表

## 2.1 Trade Fund
Trade Fund 是本文档的统一术语，指围绕贸易基金、Trade Spend、SD/TT 相关资金设计、生成、使用、报销、监控的一整套业务与系统域。

## 2.2 ITT / Integrated Trade Term
ITT 是 Trade Term 的集成框架，承载客户下单价格、折扣、补贴、付款方式、事后报销等相关条款。

## 2.3 Demand Term / Supplier Term
- Demand Term：与促销、价格、执行、分销、品牌露出等业务驱动相关。
- Supplier Term：与供应、付款速度、订单量、残损、付款折扣等供应侧条款相关。

## 2.4 Funding / Spending
- Funding：钱的来源与生成。
- Spending：钱的实际使用和支付。

这两个概念必须分开，否则会混淆“赚到的钱”和“花出去的钱”。

## 2.5 FID / Fund Account
系统中的资金账户，通常与客户 / banner 相关。

## 2.6 Checkbook
FID 下的资金容器，用于承载不同客户维度/品类维度/sector维度的资金管理。

## 2.7 KBD
核心资金池。会议中多次将其比作 AE 的主要“钱包”。很多历史 fund bucket 简化后都归入 KBD。

## 2.8 PR / Pro I / Pre OI
下单时直接抵扣的补贴方式。

## 2.9 Post OI
事后基于实际 performance 报销的补贴方式。

## 2.10 DOA
Definition of Approval，用于定义不同条件下由谁审批。

## 2.11 POA
Proof of Alignment，事前协议/客户 alignment。

## 2.12 POP
Proof of Performance，报销材料/执行证明。

## 2.13 IG
Internal Audit Group，负责部分报销材料审核。

## 2.14 LSR
价格表中的临时降价/折扣属性。在 PP、Free Goods on invest 等场景中被讨论。

## 2.15 PP / Promotion Pack
促销装。客户下单时通过价格机制享受优惠，后续产生 actual spending，并需要在相关 funding / KBD 中扣减。

---

# 3. 总体流程图

## 3.1 Trade Fund 总闭环

```text
ITT Form / ITT Board
        ↓
设定 Fund Rate / Fund Type / Program Criteria
        ↓
Optima 根据 GIV / Program 等生成 Funding
        ↓
Funding 汇入 FID / Checkbook / KBD 等系统对象
        ↓
AE / Customer Team 规划如何使用资金
        ↓
不同支付路径：
  - PR / Pre OI
  - Post OI
  - PP
  - Free Goods
  - Pay to Agency
        ↓
GI / SAP / ICP / Optima 协同处理 spending、审批、报销、扣减与付款
        ↓
资金健康度监控：Lean Forward / Lean Back / Overspending
```

## 3.2 Post OI 主干流程

```text
AE 创建活动 / PID
        ↓
DOA 审批
        ↓
auto POA / Proof of Alignment
        ↓
活动执行
        ↓
auto POP / Proof of Performance
        ↓
Request Payment
        ↓
IG 审核 / 抽查 / 白名单分支
        ↓
发送至 Optima
        ↓
Optima 处理后续付款
```

## 3.3 PR / SKU PR 自动化流程

```text
AE 在 GI 配置 SKU PR
        ↓
设置 SKU / PR rate / 生效时间
        ↓
GI 发送 alignment
        ↓
客户确认 + AE确认
        ↓
RPA 发送给 ICP / SAP
        ↓
SAP/ICP 生效
        ↓
客户下单享受折扣
        ↓
Spending 回流 GI
        ↓
Optima 扣减对应 funding
```

## 3.4 PP 流程简图

```text
客户下 PP 订单
        ↓
SAP / ICP 产生 PP spending
        ↓
数据回流 GI
        ↓
GI 判断 CCC 是否有 PP funding
        ↓
类型一：无 PP funding → 按 factor 扣 KBD
类型二：有 PP funding → 先扣 PP，不足借 KBD，后续有盈余再还
类型三：有 PP funding 但不借 KBD → 新财年新增可能类型，具体由 BU 决定
        ↓
GI 生成 draft / 指令
        ↓
Central team 审核
        ↓
Optima 执行扣减
```

---

# 4. 逐场 Session 超详细记录

---

# Session 1｜GI onboarding session｜2026-05-06

## 4.1.1 本场定位
这是 onboarding 的启动场，主要目标是建立整体框架、组织认知、后续学习路径，而不是深入某一个业务流程。

## 4.1.2 岗位交接与业务背景
会议开始讨论了 Haoling 当前岗位与新岗位交接的现实情况：

- Haoling 可能需要在 5-7 月期间同时兼顾原岗位与新岗位交接。
- 当前团队存在人员变动、岗位交接、resource 紧张等背景。
- 由于 Trade Fund 领域涉及实际资金、系统、流程和合规，因此需要较长的 onboarding 时间，而不能只靠一次知识转移。

## 4.1.3 Onboarding 六大板块
Dalton 提出完整 onboarding curriculum：

### 1. 组织架构与 stakeholder
这一块帮助 Haoling 先理解：

- 谁是核心合作方。
- 谁是用户。
- 谁负责规则。
- 谁负责审批和合规。
- IT 在中间扮演什么角色。

### 2. Business Knowledge
这是最核心模块，包含：

- Trade Fund。
- ITT。
- SD / TT。
- Funding / Spending。
- PR / Post OI。
- PP / Pay to Agency / Formal 等。

### 3. 系统生态
GI 不是孤立系统，需要讲清：

- GI 上游是什么。
- GI 下游是什么。
- GI 如何和 Optima / SAP / ICP 等系统握手。
- 哪些逻辑在 GI，哪些逻辑在其他系统。

### 4. 产品团队日常任务
包括：

- PPO / PM 日常做什么。
- 如何接需求。
- 如何判断需求优先级。
- 如何和 business / IT / vendor 协作。

### 5. 当前项目与未来规划
包括：

- 当前 GI 正在做什么。
- 各项目在业务和系统生态中的位置。
- 后续 roadmap 中可能的机会点。

### 6. 经验教训
Dalton 会把历史踩坑、处理原则、用户管理经验、问题定位方法等逐步沉淀。

## 4.1.4 中台IT与前台IT
Dalton 介绍了 GI / Trade Fund IT 属于中台 IT：

- 前台 IT 更多服务具体 customer team 或 BU。
- 中台 IT 服务的是跨业务的 central process / governance / system capability。
- GI 的定位不是只服务某个 customer team，而是承载 Trade Fund 相关的中台能力。

## 4.1.5 Corporate MSP / GET team
Corporate MSP / GET team 是核心 business partner：

- 负责销售中台政策、bulletin、guidance、promotion相关原则。
- 对来自 AE / CTFM / customer team 的需求做初步过滤。
- 与 IT 协作，将业务原则转化为系统功能。

会议中提到 Lucas 是 GET team 的负责人，Echo Wang 负责 operation，Carol 负责 ITT design，Miya 张转向 SEO/Golden Hand 相关对接。

## 4.1.6 Corporate Finance
Corporate Finance 的角色包括：

- 参与 ITT design。
- 监控 funding / spending 健康度。
- 关注是否 overspending。
- 给 CTFM / AE / customer team 提供财务 guidance。

## 4.1.7 Second Line与IG
Second line 的角色包括：

- 代表 compliance 视角参与流程设计。
- 对系统逻辑、审批、监控、异常识别有强话语权。
- 相关需求优先级通常较高。

IG / Internal Audit Group 是 second line 下负责报销材料审核的团队。

## 4.1.8 AE / CTFM / User定义
会议中讨论 customer、stakeholder、user 的区别：

- Stakeholder / customer：Corporate MSP、Corporate Finance、Second Line 等 central team。
- User：AE、CTFM，以及部分 central team user。
- AE / CTFM 代表前线 customer team / MO 的实际使用和资金管理需求。

## 4.1.9 需求来源
需求来源不止一条：

1. AE / CTFM 直接反馈痛点。
2. Corporate MSP / Finance 过滤后提出需求。
3. Second Line 从 compliance / monitoring 角度提出需求。

产品团队需要听用户声音，但也要经过 central team 的政策和合规过滤。

## 4.1.10 ITT初步概念
Dalton 初步解释 ITT：

- ITT 包含不同 trade term 元素。
- 有些在下单时体现为折扣。
- 有些在事后通过 GI 报销。
- ITT design 通常涉及 BU、Finance、Sales central team。

## 4.1.11 本场沉淀结论
- Onboarding 要做成系统课程。
- Trade Fund 是业务、系统、组织、合规四者交织的复杂域。
- 第一阶段先建立组织和 stakeholder 图谱。
- 后续重点进入业务知识和系统生态。

## 4.1.12 待跟进
- 将组织架构和关键 stakeholder 整理成图。
- 后续展开 ITT、funding、system flow。

---

# Session 2｜GI onboarding session 2｜2026-05-08

## 4.2.1 本场定位
这是 Trade Fund 业务基础的主干场，重点讲 ITT、Trade Term、funding、spending、PR/Post OI、资金健康度和数据风险。

## 4.2.2 ITT整体结构
ITT 被解释为 Integrated Trade Term。它整合了多个贸易条款，用于定义客户下单、折扣、补贴、后续报销等机制。

## 4.2.3 Demand Term与Supplier Term
### Demand Term
Demand Term 是 GI 更关注的部分，包括：

- Pricing promotion。
- Formal。
- Shelf / Display。
- Ecom brand exposure。
- Distribution coverage。

这些都是 drive business 的投入。

### Supplier Term
Supplier Term 更偏供应侧，例如：

- 下单量 tier。
- 付款速度。
- 残损。
- Payment term。

## 4.2.4 List Price与补贴逻辑
会议中解释为什么不是直接降低售价：

- 公司需要统一价格体系。
- 价格差异通过不同 trade term / discount / reimbursement 实现。
- 既能保持公平性，也能支持不同客户、不同业务策略。

## 4.2.5 PR与Post OI
### PR
- 下单时直接折扣。
- invoice 中体现。
- 客户享受更快。
- 对客户现金流和 CVE 更有利。

### Post OI
- 事后按 performance 报销。
- AE 保留 control power。
- 可根据客户表现、促销价达成、活动结果来决定最终补贴。

## 4.2.6 Promotion Performance与Passing Through
会议中讨论了 pricing 活动可能关注实际成交价是否达到建议促销价：

- 如果目的是改善客户 CVE，可能不严格绑定消费者成交价。
- 如果目的是让产品在市场中有竞争力，则可能更关注 passing through。
- 如果客户实际卖价高于建议促销价，最终补贴可能按实际情况调整。

## 4.2.7 Fund Type
本场提到的 fund type 包括：

- KBD / KBC Driver。
- AKBD。
- TFI。
- PP。
- Incremental SRE。
- How High Is High。
- Contingency。

## 4.2.8 KBD Consumer Fund
KBD consumer fund 是主流资金来源之一。会议中提到它通常占比很大，并通过 GIV × rate 生成。

## 4.2.9 Rate-based Funding
Rate-based funding 的逻辑是：

```text
实际 GIV × Fund Rate = Funding
```

这是自动生成 funding 的核心方式之一。

## 4.2.10 Program-based Funding
Program-based funding 的逻辑是：

```text
BU设定Program + Criteria
→ Customer Team达标
→ Release funding
```

Dalton 用“揭榜/赏金”解释这个模式。

## 4.2.11 Incremental SRE与How High Is High
二者模式类似，都是 program-based：

- Incremental SRE：条件相对容易达成。
- How High Is High：条件更高、更严苛，激励也更强。

## 4.2.12 Contingency Fund
Contingency fund 被解释为应对市场不确定性、潜在威胁、临时变化的缓冲资金。

## 4.2.13 Funding与Spending的区分
本场反复强调：

```text
Funding = 赚到/生成的钱
Spending = 花出去/补贴给客户的钱
```

不要把“钱从哪来”和“钱怎么花”混在一起。

## 4.2.14 ITT Form与ITT Board
每个财年会有 ITT form：

- 定义每个客户、品类下的 fund rate / fund type。
- 经 ITT Board / LT 等审批。
- 上传或配置到 Optima。
- Optima 根据实际 GIV 生成 funding。

## 4.2.15 Funding调整
资金调整不是 AE 想加就能加：

- AE / DVM 没有直接加 funding 的权限。
- BU 通常是发起方。
- 需要 LT / ITT Board / Finance 审批。
- 审批后 Operation team 才执行系统动作。

## 4.2.16 Lean Forward与Lean Back
### Lean Forward
spending 暂时超过 funding，但未来可能通过后续 GIV 追回。

### Lean Back
funding 大于 spending，说明钱还没花出去。

### 管理原则
- 财年末不能 overspend。
- 也不能长期大量 lean back。
- AE 需要动态管理资金计划。

## 4.2.17 Payment方式与边界
会议中提到不同 payment 方式：

- PR / Pro I。
- Post OI。
- 红票。
- 蓝票。
- Service invoice。

GI 的边界不是从客户下单到最终付款的全部链路，而是其中一段。后续还会涉及 Optima、ICP、税组、AR team 等。

## 4.2.18 数据准确性
### 数据错误的影响
如果 POS data 或上游数据错误，会影响报销金额。

### 未付款前
可以暂停报销、通知用户、等待修复。

### 已付款后
需要与 customer team、客户协商后续调整，善后复杂。

## 4.2.19 Debug责任判断
- 如果上游数据和 GI 收到的数据不一致，可能是上游问题。
- 如果上游数据正确但 GI 计算结果错误，是 GI 逻辑问题。
- GI 逻辑问题由 GI team debug。
- 上游问题需要催上游，同时安抚用户、找 workaround。

## 4.2.20 用户管理经验
Dalton 强调：不要只告诉用户“上游问题”。更好的方式是：

- 先帮用户想 workaround。
- 帮用户和客户管理预期。
- 解释复杂链路时尽量用业务能理解的语言。

## 4.2.21 DPB特殊场景
会议讨论 DPB：

- 部分 DPB 与 LMNI 类似，通过 GI 有账户、AE 管钱、建活动。
- 部分 RD 模式不上 GI，没有 checkbook。
- VIP、抖音、京东等有倒剪、post base GIV、indirect GIV 等复杂数据处理。
- DTC 不属于当前 Trade Fund / GI 范围。

## 4.2.22 本场结论
本场建立了 Trade Fund 的业务底层模型：

```text
ITT Design
→ Funding Generation
→ KBD / Checkbook
→ AE Plan
→ PR / Post OI / PP 等 Spending
→ GI / Optima / ICP 等系统承接
```

---

# Session 3｜GI onboarding session 3

## 4.3.1 本场定位
本场从业务逻辑进入 GI 系统对象模型，重点讲 FID、Checkbook、客户分级、权限、组织变更 SOP，以及 KBD 简化和 PR 维护。

## 4.3.2 GI权限申请
会议讨论了 Haoling 的系统权限：

- 先开 QA project team 权限。
- 正式 announce 后再开 production 权限。
- 需要邮件给 GIIO / GI Support，并抄送 Dalton。

## 4.3.3 FID / Fund Account
FID 是 fund account，可以理解为客户/banner 资金账户。

用户进入 GI 后，通常基于权限看到自己负责的 FID。

## 4.3.4 FID / Banner / Checkbook层级
系统层级可以理解为：

```text
FID / Fund Account
→ Banner
→ Checkbook
```

Checkbook 是更细粒度的资金承载容器。

## 4.3.5 Checkbook权限
每个 checkbook：

- 只有一个 Payment AE。
- 可以有其他 assistant / AE 协助建活动。
- Payment 权限不能多人同时拥有。

## 4.3.6 G1客户
G1 客户生意体量大，通常按 category 切 checkbook。

```text
Category A → Checkbook A
Category B → Checkbook B
Category C → Checkbook C
```

## 4.3.7 G2客户
G2 客户按 sector 切分，多个 category 合并成一个 sector。

```text
Category A + B + C → Sector → Checkbook
```

## 4.3.8 G3客户
G3 客户体量较小，可能所有 category 合并成一个 corp / cop checkbook。

## 4.3.9 G2/G3的Payment AE问题
Haoling 提问：如果多个 category 合并成一个 sector，到底谁做 payment？

会议中讨论到：这类客户通常不会为每个 category 配 dedicated AE，而是由一个 AE 管多个 category 或 sector。

该问题在 loop 中也被记录为待澄清点：G2/G3 客户 payment AE 分配方式需进一步澄清。

## 4.3.10 组织变更与客户升降级
会议用客户降级例子说明：

- G1 降 G2。
- G2 降 G3。
- 由生意体量与 SOP 决定。
- customer hierarchy 进来后，后台配置生效。

## 4.3.11 SOP化支持
过去组织变更需要开发，现在常见变更可由 operation team 配置支持：

- 新增 FID。
- 更换 FID。
- 改名。
- 常见 customer hierarchy / J级变化。

复杂场景仍需 case by case。

## 4.3.12 DPB Scope
会议中明确：不是所有 DPB / RD 都在 GI scope。

GI 只覆盖特定类别，例如 PUPU、JDJXT、ICP 等类似模式。很多 RD 不在 GI 中建活动。

## 4.3.13 KBD简化
历史上可能有很多 fund bucket。

当前简化后：

- 很多 funding release 后归入 KBD。
- AE request payment 时主要选择 KBD。
- 对 AE 来说，先理解为“所有钱都在 KBD 大池子里”。

## 4.3.14 KBD包含的fund来源
KBD 可能包含：

- KBD consumer。
- AKBD。
- Incremental SRE。
- How High Is High。
- Contingency。
- PP / Free Goods 相关 rate 也可能进入 KBD 逻辑中被讨论。

## 4.3.15 Pre OI / Post OI
会议中将 KBD 使用分成：

- Pre / PR：提前设置，下单抵扣。
- Post / Reimbursement：事后报销。

## 4.3.16 Category PR
Category PR：

- 财年初由 central team 维护。
- 写入 ITT form。
- 按 category level 生效。
- 客户下单时自动享受折扣。

## 4.3.17 SKU PR
SKU PR：

- 由 AE 根据业务需求维护。
- 可用于在 category PR 基础上对特定 SKU 增加额外点数。
- 需要审批。
- 需要与客户 alignment。
- 后续通过 SAP / ICP 生效。

## 4.3.18 PR与Post OI的组合
会议中 Haoling 追问：如果 category PR 已经给了折扣，为什么还会有 Post OI？

Dalton 解释：AE 不会把所有补贴都提前通过 PR 给掉，因为要保留谈判空间和 control power。PR + Post OI 合起来才是客户最终享受的补贴组合。

## 4.3.19 Loop中形成的决策
- 通过 operation team 配置支持 checkbook J级变更。
- 常见组织结构变更由 operation team 通过 SOP 支持。
- 为 Haoling 分配 GI 系统 QA 和生产权限。
- Category Pro I 由 central team 统一维护。

## 4.3.20 Loop中记录的Gap
- G2/G3 降级后系统权限和管控自动调整流程未完全明确。
- 复杂组织变更是否能走 SOP 需 case by case 判断。
- G2/G3 客户 payment AE 分配方式需进一步澄清。
- 非 end to end banner 客户 reporting line 设置需后续确认。
- KBD 以外 fund bucket 类型保留与否需后续确认。
- SKU PR 维护审批流程标准化需单独梳理。
- Post / Pre OI 资金分配比例标准需进一步明确。

## 4.3.21 本场结论
```text
FID / Banner / Checkbook 是 GI 承载 Trade Fund 的核心系统结构。
客户分级决定 Checkbook 粒度。
Payment AE 权限围绕 Checkbook 配置。
常规组织变化已基本 SOP 化。
KBD 是当前 AE 使用资金的主要简化池。
```

---

# Session 4｜GI onboarding session 4

## 4.4.1 本场定位
本场建立 Post OI 主干流程，讲清 AE 如何在 GI 中创建活动、审批、生成 POA/POP、request payment、IG审核并进入 Optima。

## 4.4.2 从钱的使用角度分类
会议开头先将资金使用分为几类：

- Pro I / PR：下单时直接抵扣。
- Post OI：GI 中创建活动并报销。
- PP：独立模块。
- Pay to Agency：独立流程。

本场重点是 Post OI。

## 4.4.3 Post OI活动类型
Post OI 主要包括：

- Pricing Promotion。
- Formal。
- 部分与 Pay to Agency 区分的活动类型。

## 4.4.4 Pay to Agency概念
Pay to Agency 用于 third-party agency 发券、平台活动等。

例子包括：

- 饿了么券。
- 美团券。
- 淘鲜达相关券。

核心区别：钱不是直接付给客户，而是付给 agency。

## 4.4.5 PP与Free Goods概念
PP 是 Promotion Pack，客户下单时已经享受某种折扣或优惠。PP 不属于典型 Post OI 活动流程。

Free Goods 新财年会有变化，本场只是标记，后续展开。

## 4.4.6 Post OI主干流程
完整主干流程：

```text
AE 创建 PID / 活动
→ DOA审批
→ auto POA
→ 活动执行
→ auto POP
→ Request Payment
→ IG审核
→ Optima付款处理
```

## 4.4.7 PID
PID 就是活动。Pricing promotion 和 formal 类活动需要创建 PID。

## 4.4.8 DOA
DOA = Definition of Approval。

它规定：

- 什么情况下需要审批。
- 谁审批。
- 审批路径是什么。
- 和金额、角色、层级、合规条件有关。

## 4.4.9 POA
POA = Proof of Alignment。

- 表示与客户事前对齐。
- 系统根据活动自动生成。
- 发送给客户确认。

## 4.4.10 活动执行
活动执行发生在系统外。系统中记录活动、协议、审批和后续报销计算。

## 4.4.11 POP
POP = Proof of Performance。

- 是报销材料或执行证明。
- Pricing 使用既有 auto POP 能力。
- Formal 未来会更多使用 Golden Hand / distribution 数据自动生成。

## 4.4.12 auto POA / auto POP核心价值
Dalton 强调这是 GI 报销环节的核心能力：

- auto POA：自动实现事前协议。
- auto POP：自动生成报销材料。

## 4.4.13 IG审核
IG = Internal Audit Group。

- 属于 second line 审核机制。
- 不是所有活动都全查。
- 部分小金额、历史表现好的活动可免 IG。
- 系统规则会自动判断是否需要 IG。

## 4.4.14 Request Payment
AE 在 GI 中 request payment，IG 审核也在 GI 中完成。完成后系统将 payment 信息发送至 Optima。

## 4.4.15 Optima
Optima 负责后续付款处理。GI 本身不承载实际钱，但 GI 输出的数据会影响 Optima 支付。

## 4.4.16 活动创建关键字段
Pricing 活动创建时，AE 需要设置：

- SKU。
- Customer Promotion Price / CPP。
- 单套补差。
- 补差上限 cap。
- 活动范围与相关参数。

## 4.4.17 单套补差
单套补差表示每卖出一套/一件，P&G 补给客户多少钱。它是 pricing promotion 中非常核心的字段。

## 4.4.18 Cap
Cap 表示活动最大补贴上限。不论销量如何，活动最多报销到 cap。

## 4.4.19 AE与Finance
系统中看起来 AE 操作很多，但实际业务上 AE 需要提前与 finance 对齐：

- master plan。
- 报销计划。
- 补差比例。
- 资金分配节奏。

## 4.4.20 最关键风险点
Dalton 强调两个关键风险：

1. Optima 的 funding generation 不能错。
2. GI 的单套补差 / auto POP 计算不能错。

这两个直接影响最终报销金额。

## 4.4.21 Formal后续项目
Formal 类活动会与 Golden Hand、SKU distribution 等数据对接，实现 auto POP。后续 phase 仍会继续做，Haoling 可能会参与。

## 4.4.22 本场结论
Post OI 主干流程已经建立。Haoling 应能理解：

```text
Funding 如何来
→ Checkbook 如何承载
→ AE 如何建活动
→ 系统如何审批、生成协议和报销材料
→ 如何进入 Optima付款
```

## 4.4.23 待展开
- Pay to Agency。
- PP / Free Goods。
- 更细的 compliance rules。
- Formal 项目详细逻辑。

---

# Session 5｜GI onboarding session 5

## 4.5.1 本场定位
本场深挖 PR / Pre OI，尤其是 SKU PR、O&O 自动化、ecom RPC/GT 复杂性，以及 Post OI 单套补差如何与 Pro I 联动。

## 4.5.2 Haoling复盘
Haoling 复盘出三类流程：

- Pro I：category 与 SKU。
- PP / Free Goods：独立流程。
- Post OI：pricing promotion / formal 主干流程。
- Pay to Agency：独立支付路径。

Dalton 确认复盘准确。

## 4.5.3 本场三条非主干流程
本场计划讲：

- SKU Pro I。
- PP / Free Goods。
- Pay to Agency。

实际主要深入 SKU PR / Pro I。

## 4.5.4 Pro I分类
Pro I 可按不同方式拆分：

- Category PR vs SKU PR。
- ecom PR vs O&O PR。

## 4.5.5 Category PR
Category PR：

- 财年初根据 ITT form 维护。
- 由 central team / Corporate MSP 统一处理。
- Rate 给到 SAP / Optima / GI。
- 客户下单时直接享受折扣。

## 4.5.6 SKU PR
SKU PR：

- 针对具体 SKU 设置额外 PR。
- AE 可根据业务需要发起。
- O&O 有新自动化能力。
- ecom 仍复杂，很多场景暂未自动化。

## 4.5.7 ecom复杂性：RPC vs GT
### 业务视角
AE 可能更习惯用 RPC 管理。

### 系统视角
SAP 下单并没有 RPC 概念，而是 GT / JT / 8位码。

### 复杂点
- 一个 RPC 可能对应多个 GT。
- GT 与 RPC 的 mapping 可能变化。
- 历史关系需要拉链。
- 如果 rate 设在 RPC，要落到 SAP 生效就需要分摊到 GT。

## 4.5.8 为什么先做O&O
O&O 的 SKU PR 更适合先做自动化：

- 业务场景相对更清晰。
- SKU PR 量大，人工维护 effort 高。
- 自动化价值明确。

## 4.5.9 O&O SKU PR自动化
流程：

```text
AE在GI中配置SKU PR
→ 填SKU、rate、生效时间
→ GI发送alignment
→ 客户确认
→ AE确认客户已确认
→ RPA发送到ICP/SAP
→ 次日可能生效
```

## 4.5.10 自动化价值
三个价值：

1. 降低 operation effort。
2. 让 alignment 可追溯，提升 compliance。
3. 从人工约 5 working days 缩短到极限 T+1。

## 4.5.11 Post OI单套补差与Pro I联动
### 两种维护方式
1. AE 直接输入单套补差。
2. AE 输入目标 margin，系统倒推单套补差。

### 关键公式思想
客户总补贴由 PR + Post OI 组成。

因此 Post OI 计算时必须减掉客户已享受的 Pro I，否则 double pay。

```text
Post OI 单套补差计算时：
需要扣除已享受的 Category PR / SKU PR investment
```

### 负数处理
如果倒推后单套补差为负，则置为 0。

## 4.5.12 CPP与Margin
会议中澄清：CPP 是消费者促销价 / customer promotion price 相关概念，不是客户进货价。Margin 计算涉及 CPP、list price、Pro I、Post OI 等因素。

## 4.5.13 ecom manual流程
ecom SKU PR：

- Customer team 给 Corporate MSP。
- Corporate MSP 给 Master Data team。
- Master Data team 维护到 SAP。
- 目前主要是 manual SOP。

## 4.5.14 PR数据回流
所有 PR 数据最终仍需要在 GI 中呈现：

- 无论 manual 还是 auto。
- Spending 需要回流 GI。
- GI 需要用这些数据做展示、计算、扣减逻辑。

## 4.5.15 Knowledge Base工具讨论
会议最后讨论：

- 使用 ghub / GitHub 做知识库。
- 希望与 VS Code Copilot / GitHub Copilot 结合。
- 相比 SharePoint，GitHub 更适合与代码/开发资料/Markdown知识库打通。

## 4.5.16 本场结论
```text
PR不是简单折扣，而是与SAP、Optima、GI、Post OI公式联动的系统化链路。
O&O SKU PR自动化是新能力，ecom因RPC/GT复杂性暂缓。
Post OI补差必须扣掉已享受Pro I，避免double pay。
```

---

# Session 6｜GI onboarding 6

## 4.6.1 本场定位
本场主要讲 PP、Free Goods、LSR、PP funding、KBD借还、switching factor、新财年类型变化，以及后续 Pay to Agency 铺垫。

## 4.6.2 开场：GitHub权限与知识库维护
会议开头讨论 Haoling 对 ghub 的访问问题：

- 可以下载和查看。
- 无法上传和 fork。
- 访问不稳定。
- 未来可能将个人知识库合并到 GI 官方 knowledge base。

## 4.6.3 回顾上一场PR
Haoling 回顾：

- O&O SKU PR 是新 automation。
- ecom 走 manual process。
- 后续需要系统 demo。

Dalton 确认先讲业务，再进入系统。

## 4.6.4 PP定义
PP = Promotion Pack。

- 可理解为促销装。
- 客户下单时享受价格优惠。
- 折扣可能通过 LSR 实现。
- 实际 spending 来自 SAP / ICP 下单数据。

## 4.6.5 Free Goods定义
会议中提到：

- Free goods on invoice。
- Free goods on invest。
- NRO。

Dalton 对 NRO 背后 WISE 系统不完全熟悉，因此未展开。

## 4.6.6 LSR定义
LSR 是价格表中的一种临时降价/折扣属性。

- PP 可通过 LSR 降低价格。
- 旧逻辑下 Free Goods on invest 也可通过 LSR 实现。
- 新财年 Free Goods 会从 LSR / SD 逻辑中移出。

## 4.6.7 PP Spending
PP spending 示例：

```text
原价100
PP价格90
PP spending = 10
```

Free Goods spending 可理解为赠品本身对应的价值。

## 4.6.8 PP数据来源
```text
SAP / ICP下单数据
→ CDL / DPO抓取LSR / fact data
→ GI接收PP / Free Goods spending
→ GI计算扣减逻辑
→ Optima执行扣减
```

## 4.6.9 PP Funding类型
Dalton 将 PP 场景分为不同类型。

### 类型一：无PP Funding
- 没有独立 PP funding。
- GI 用 PP spending × switching factor 计算需要扣多少 KBD。
- 发给 Optima 扣 KBD。

### 类型二：有PP Funding，可借KBD
- 先扣 PP funding。
- 不够时借 KBD。
- 借 KBD 时使用 switching factor。
- 后续 PP funding 有盈余时再还 KBD。

### 类型三：有PP Funding，但不借KBD
- 新财年可能新增。
- 不够扣时不再借 KBD。
- 具体由 BU / business side 在财年初决定。

## 4.6.10 Switching Factor
Switching factor 类似汇率：

```text
PP spending × switching factor = KBD扣减金额
```

例如：PP spending 100，factor 0.8，则扣 KBD 80。

Factor 每个财年可在 ITT form / setup 中设置。

## 4.6.11 为什么会PP不够扣
原因包括：

- 客户实际下 PP 单可能超过原先 PP funding 预估。
- AE 不能完全阻止客户下单。
- PP allocation 与 GI funding / spending 管理不完全打通。
- BU 设置 PP funding 时可能偏保守。

## 4.6.12 PP Allocation与Spending脱节
会议中明确：

- PP quota / allocation 可能在 sales / SAP 流程中管理。
- GI 中看到的是实际 spending 与 funding 扣减。
- 两者目前未完全闭环。
- 未来是否打通需要评估 value。

## 4.6.13 借KBD与还KBD
类型二中最复杂的逻辑是：

```text
PP funding不足
→ 借KBD
→ 后续PP funding有盈余
→ 按factor折算后还KBD
```

这一逻辑会持续 rolling，是 PP 模块最复杂的部分。

## 4.6.14 Central Team审核
PP draft payment：

- GI 自动生成草稿。
- Central team / Corporate MSP 审核计算是否正确。
- 审核后 submit。
- AE 不直接决定借还逻辑。

## 4.6.15 Free Goods新财年变化
会议中明确：

- 新财年 Free Goods 从当前 SD / LSR 逻辑中移出。
- LSR 下主要剩 PP。
- Free Goods 不再通过原有 SD / Trade Fund 方式处理。
- 后续可能走 MSE 或其他 TT term，但未确认。

## 4.6.16 Free Goods旧逻辑
旧逻辑：

- 类似 PP。
- 但没有 PP 那么复杂的 switching factor、借还KBD。
- 有 free goods funding 则扣该 funding，没有则可能扣 KBD。

## 4.6.17 Funding / Spending可见性
GI 中 AE 可以看到：

- total funding。
- total spending。
- forecast / actual。
- KBD 与其他组成。
- 不同月份数据。

这是 AE 管理资金的核心能力。

## 4.6.18 PR链路历史遗留
会议也讨论到为什么有些 PR 链路仍通过 Optima：

- Category PR 历史上最早通过 Optima 与 SAP 打通。
- 旧链路体量大，改动成本高。
- O&O SKU PR 新能力则优先尝试 GI 与 SAP 直接握手。

## 4.6.19 本场结论
PP 的本质不是简单“促销装”，而是涉及：

```text
LSR / SAP下单
→ actual spending
→ PP funding判断
→ KBD折算
→ 借还rolling
→ Optima扣减
```

## 4.6.20 待展开
- Pay to Agency。
- 系统 demo。
- 类型三新财年规则的业务背景与具体判断。
- Free Goods 移出 SD 后的新流程归属。

---

# 5. Open Questions / Backlog 汇总

## 5.1 来自Session 3的Gap
- G2/G3 降级后系统权限和管控自动调整流程未完全明确。
- 复杂组织变更是否能走 SOP 需 case by case 判断。
- G2/G3 客户 payment AE 分配方式需进一步澄清。
- 非 end to end banner 客户 reporting line 设置需后续确认。
- KBD 以外 fund bucket 类型保留与否需后续确认。
- SKU PR 维护审批流程标准化需单独梳理。
- Post / Pre OI 资金分配比例标准需进一步明确。

## 5.2 来自Session 5的Gap
- ecom SKU PR 自动化如何处理 RPC / GT mapping。
- RPC / GT 历史关系变化如何拉链。
- 如果多个 GT 对应一个 RPC，rate 如何分配。
- ecom 场景是否值得做自动化，需要进一步评估。

## 5.3 来自Session 6的Gap
- NRO / WISE 系统细节未展开。
- Free Goods 移出 SD 后的后续流程未确认。
- PP 类型三的业务规则需要进一步与 BU / business side 学习。
- PP allocation 与 PP spending 是否打通，value 未评估。
- Pay to Agency 尚未系统讲解。

---

# 6. 后续建议的知识库结构

建议在 GitHub / SharePoint / Confluence 中按以下结构维护：

```text
GI-Trade-Fund-Onboarding/
├── 00_README_Index.md
├── 01_Knowledge_Map.md
├── 02_Glossary.md
├── 03_System_Architecture.md
├── 04_Process_Flows/
│   ├── Post_OI_Core_Flow.md
│   ├── PR_SKU_Automation.md
│   ├── PP_Free_Goods.md
│   └── Pay_to_Agency.md
├── 05_Session_Records/
│   ├── Session_01.md
│   ├── Session_02.md
│   ├── Session_03.md
│   ├── Session_04.md
│   ├── Session_05.md
│   └── Session_06.md
└── 99_Backlog_and_Open_Questions.md
```

---

# 7. 可持续更新模板

```markdown
# Session X｜标题｜日期

## 1. Session定位

## 2. 上场回顾

## 3. 本场新增概念

## 4. 详细业务逻辑

## 5. 系统承载方式

## 6. 流程图

## 7. 关键例子

## 8. Haoling追问与澄清

## 9. Gap / Open Questions

## 10. Follow-up

## 11. Source
```

---

# 8. 本文档Source索引

- Session 1: `GI onboarding session` / source ref: `turn9search60`
- Session 2: `GI onboarding session 2` / source ref: `turn9search57`
- Session 3: `GI onboarding session 3` / source ref: `turn9search56` + `GI onboarding session 3.loop`
- Session 4: `GI onboarding session 4` / source ref: `turn9search53`
- Session 5: `GI onboarding session 5` / source ref: `turn9search54`
- Session 6: `GI onboarding 6` / source ref: `turn9search55`

---

# 9. 一句话总结

这 6 场 onboarding 已经形成一套完整的 Trade Fund 入门到进阶路径：

```text
先理解组织与角色，
再理解 ITT 和 funding，
再理解 GI 如何通过 FID / Checkbook 承载资金，
再理解 Post OI 主干流程，
再深入 PR / PP / Free Goods 等非主干但关键模块，
最后进入系统 demo 与实际项目承接。
```
