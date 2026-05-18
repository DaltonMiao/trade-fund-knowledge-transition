# Session 2｜GI onboarding session 2｜2026-05-08

## 1. Session定位
本场是 Trade Fund 业务知识的第一场 deep dive。重点是从业务底层逻辑理解：ITT 是什么、Trade Term 如何分类、funding 怎么来、spending 怎么出去、为什么有 PR / Post OI 两种支付方式，以及数据准确性为什么对 GI 非常关键。

## 2. ITT与Trade Term整体框架
### 2.1 ITT定义
ITT 被解释为 Integrated Trade Term，是多个贸易条款的统一框架。它不是一个单一字段，而是包含不同类型的条款、折扣、补贴和付款机制。

### 2.2 Demand Term vs Supplier Term
会议中将 Trade Term 大体分为两类：

- **Demand Term**：与 Trade Fund / GI 更相关，主要用于 drive business，例如 pricing promotion、formal、shelf、display、品牌露出、分销覆盖等。
- **Supplier Term**：与供应侧相关，例如下单量、付款速度、残损、付款折扣等。

本次 onboarding 强调：GI 更关注 demand term 中与 SD / Trade Fund 投入相关的内容。

## 3. 定价与补贴的基础逻辑
### 3.1 List Price与实际成交
客户通常以统一的 list price / 出厂价体系为基础下单。不同客户、不同条款下的最终价格差异，不是简单地“直接改售价”，而是通过 Trade Term / discount / reimbursement 等机制体现。

### 3.2 为什么不是直接卖低价
会议中用“原价100，促销价60”的例子解释：

- 客户仍可能按统一价格体系下单。
- 差额通过不同补贴机制体现。
- 这样做与公平定价、合同条款、系统结算、税务处理和后续报销逻辑有关。

## 4. 两类核心支付方式：PR vs Post OI
### 4.1 PR / Pre OI
PR 是下单时直接抵扣的方式：

- 客户在 invoice 中直接享受折扣。
- 对客户现金流更友好。
- 但对于 AE 来说，会降低后续谈判和付款节奏控制力。

### 4.2 Post OI
Post OI 是事后根据 performance 进行报销：

- 活动执行后，根据实际 performance 计算补贴。
- 销售团队可以保留更多 control power。
- 能与客户谈判节奏、活动表现、执行结果绑定。

### 4.3 PR与Post OI的取舍
会议中明确讨论到：AE 不会把所有资金都通过 PR 提前给掉，因为需要保留一定 post OI 空间作为谈判筹码和客户管理手段。

## 5. Funding体系：钱从哪里来
### 5.1 Fund Type示例
会议中提到多个 fund type / bucket：

- KBD / KBC Driver：核心资金池。
- AKBD：可理解为 KBD 下的相关资金类型之一。
- TFI：临时促销基金，用于应对竞争、临时策略等。
- PP：Promotion Pack 相关资金。
- Incremental SRE、How High Is High、Contingency 等 program / incentive 类型。

### 5.2 Funding Generation两类方式
#### Rate-based
通过 GIV × fund rate 自动生成 funding。该逻辑常与 ITT form 中预设的 rate 相关。

#### Program-based
BU 设定 program 和 criteria，客户或 customer team 达成条件后 release funding。会议中用“揭榜/赏金”类比解释。

## 6. ITT Form / ITT Board / Optima
### 6.1 ITT Form
每个财年，相关团队会在 ITT form 中定义不同客户、品类下的 rate、fund type 等规则。

### 6.2 ITT Board
ITT board 参与审批这些规则。会议中提到 BU、sales、finance 等高层会参与设计和审批。

### 6.3 Optima的角色
Optima 根据配置和实际 GIV 生成 funding，并作为后续 funding / payment 处理的重要系统。GI 并不直接产生 funding。

## 7. Funding vs Spending区分
会议中特别强调：

- **Funding**：钱从哪里来，怎么生成。
- **Spending**：钱怎么花出去，如何补贴客户。

这两个概念需要分开理解。一个 AE 就像有一个“账户/钱包”，钱可能来自不同来源，但花出去时可以用于不同活动和支付方式。

## 8. Lean Forward / Lean Back资金健康度
会议中解释了资金动态管理：

- **Lean Forward**：spending 暂时超过当前 funding，但未来 funding 可能补回来。
- **Lean Back**：funding 大于 spending，钱没有充分使用。

两种状态都需要管理：

- 财年末 overspending 是严重问题。
- 财年末大量 lean back 也说明资源没有充分投入。

AE 需要结合客户未来下单量、活动计划、spending 节奏动态规划资金。

## 9. Funding调整与审批
会议中明确：AE / DVM 不能随意加钱。

- 资金追加通常需要 BU 发起。
- 需要 LT / ITT Board / Finance 等审批。
- Operation team 只承接最终已批准的 action，例如 fund adjustment。

## 10. 数据准确性与报销风险
本场对数据问题做了大量讨论：

### 10.1 数据错误的影响
如果 POS data 或其他上游数据错误，会直接影响报销金额。如果已经付款，后续善后复杂；如果尚未付款，可以暂停报销并通知用户。

### 10.2 DQE与Debug
DQE 可以发现数据异常，但定位问题需要判断：

- 是 GI 内部计算逻辑问题；还是
- 上游数据源问题。

如果是 GI 逻辑问题，GI team 需要 debug；如果是上游问题，需要催促上游并管理用户预期。

### 10.3 用户管理与Workaround
会议强调，在用户面对数据问题时，仅解释“上游问题”通常不够。更有效的方式是：

- 站在用户角度帮忙找 workaround。
- 管理 customer team / finance / sales 的期待。
- 在问题不能立即解决时，协助业务判断是否暂停报销或延期。

## 11. DPB特殊场景
本场也简要讨论了 DPB：

- 部分 DPB 业务与 LMNI 类似，也有 checkbook、AE 管钱、建活动、花钱。
- 某些 RD / DPP 模式不完全走 GI。
- VIP / 抖音 / 京东等场景可能存在复杂的 GIV 拆分、倒剪、post base / indirect base 处理。
- DTC 不在本次 Trade Fund / GI 范围内。

## 12. 本场结论
本场建立了 Trade Fund 的业务底层模型：

```text
ITT规则设计 → Funding生成 → Checkbook承载 → AE规划 → PR/Post OI等方式花钱 → GI/Optima/ICP等系统承接
```

## 13. 待展开
- FID / Checkbook / G1-G3 结构。
- GI 如何承载业务对象。
- 有了 funding 后，AE 如何在 GI 中建活动、审批、报销。

## 14. Source
- Event: GI onboarding session 2
- Source reference: turn9search57
