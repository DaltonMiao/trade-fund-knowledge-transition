# Session 4｜GI onboarding session 4

## 1. Session定位
本场重点是 GI 的 Post OI 主干流程：活动如何创建、如何审批、如何生成 POA / POP、如何进入 payment、IG如何审核、最终如何对接 Optima。

## 2. 本场开场：从“钱怎么花”切入
会议先回顾：有了 funding 和 checkbook 后，需要理解 AE 如何把钱花出去。

两大方向：

- **Pro I / PR**：提前设置，客户下单时发票上直接抵扣，之后根据 actual spending 从账户扣减。
- **Post OI**：GI 中最典型的报销主流程，需要创建活动并走审批、协议、执行、报销等步骤。

## 3. Post OI活动类型
Post OI 在 GI 中主要体现为活动管理，包括：

1. **Pricing Promotion**  
   GI 中最主流、最核心的活动类型。
2. **Formal**  
   店内执行类活动，例如 shelf、display 等。
3. **Pay to Agency**  
   不是付给客户，而是付给第三方 agency，例如到家券、平台券等相关活动。

## 4. Pay to Agency初步解释
会议中解释：

- Pay to Agency 适用于 agency 提供服务或发放券的场景。
- 示例包括饿了么、美团、淘鲜达等平台券。
- 本质仍是 promotion，因为最终影响消费者到手价。
- 但资金不是直接给客户，而是给 agency。
- 该流程是独立流程，不完全走主干活动流程。

## 5. PP / Free Goods初步解释
会议中标记：

- PP = Promotion Pack。
- PP 有点类似下单时享受折扣，但与 Pro I 不完全一样。
- PP 是独立模块，不属于典型 Pre OI / Post OI 主流程。
- Free Goods 在新财年会发生变化，后续不再作为本阶段重点展开。

## 6. GI Post OI主干流程
本场明确建立主干流程：

```text
AE创建活动（PID）
→ DOA审批
→ auto POA
→ 活动执行
→ auto POP
→ Request Payment
→ IG审核
→ 发送至Optima处理后续付款
```

## 7. 活动创建（PID）
- PID 本质上就是创建活动。
- Pricing promotion / formal 类活动需要创建 PID。
- PP / Pay to Agency 等不一定有“活动”概念，属于独立流程。

## 8. DOA审批
### 8.1 DOA含义
会议中解释 DOA 可理解为 Definition of Approval：

- 定义什么情况下由谁审批。
- 与金额、角色、层级、合规规则相关。
- 可能涉及 MM / DVM 等审批人。

### 8.2 Compliance关联
活动创建和审批强关联 second line / compliance：

- 活动创建本身有很多 compliance 校验。
- DOA 规则背后有大量限制和条件。

## 9. auto POA
### 9.1 POA含义
POA = Proof of Alignment。

### 9.2 POA作用
- 代表与客户的事前 alignment。
- 可以理解为事前协议。
- 系统根据活动自动生成 POA。
- AE / 系统发送给客户确认。

## 10. 活动执行
活动执行本身在系统外发生。GI 负责活动前的设置、协议、审批与后续报销材料/金额计算。

## 11. auto POP
### 11.1 POP含义
POP = Proof of Performance。

### 11.2 POP作用
- 是报销材料 / 执行结果证明。
- Pricing 活动会基于系统中已有逻辑生成 POP。
- Formal 类活动正在结合 Golden Hand、SKU distribution 等数据实现 auto POP。

### 11.3 auto POA / auto POP核心价值
会议中特别强调：

- auto POA 和 auto POP 是 GI 报销环节的核心能力。
- 一个解决事前协议自动化，一个解决执行结果/报销材料自动化。

## 12. Request Payment与IG审核
### 12.1 Request Payment
活动执行并生成 POP 后，AE 在 GI 中发起 request payment。

### 12.2 IG审核
IG = Internal Audit Group。

- 属于 second line 相关审核机制。
- 并非所有活动都全查，而是抽查。
- 部分金额小、历史表现好的 checkbook / account 可能进入白名单，免 IG 审批。
- 系统会根据规则自动判断是否需要进入下一步。

## 13. Optima对接
GI 不承载实际资金。会议中 Haoling 复述并确认：

- Optima 负责 funding generation 和后续资金处理。
- GI 输出的数据会影响 Optima 最终支付。
- Request payment / IG 后，GI 会将相关信息发送给 Optima。

## 14. 活动创建关键字段：单套补差与Cap
在 pricing 活动中，AE 创建活动时需要：

- 选择 SKU。
- 维护每个 SKU 的价格信息。
- 设置单套补差：卖出一套/一件后补多少钱。
- 设置补差上限 cap：活动最多报销多少钱。

这些字段直接影响后续 POP 计算与最终付款金额。

## 15. AE与Finance协作
会议中 Haoling 提问：系统中看起来大部分动作由 AE 操作，但实际业务上 finance 是否参与？Dalton 确认：

- 活动前 AE 需要与 finance 对齐 master plan。
- 补差比例、报销节奏、资金规划等应在系统操作前沟通清楚。
- 系统承接的是已经对齐后的业务安排。

## 16. 关键风险点
会议中明确指出两个“最不能出错”的点：

1. **Funding generation**  
   Optima 产生 funding，如果出错就是大问题。
2. **POP / 单套补差计算**  
   GI 计算最终报销金额，如果错会直接影响付款金额。

## 17. 后续计划
- 下一步继续讲 pay to agency、PP、free goods 等边缘模块。
- 后续还需要进一步讲 compliance rules、分支规则、不同 process 的详细逻辑。
- Dalton 会把流程图发给 Haoling。

## 18. 本场结论
本场建立了 GI Post OI 主流程：

```text
Funding → Checkbook → Activity/PID → DOA → POA → Execution → POP → Payment Request → IG → Optima
```

## 19. Source
- Event: GI onboarding session 4
- Source reference: turn9search53
