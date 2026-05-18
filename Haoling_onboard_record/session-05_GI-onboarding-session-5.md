# Session 5｜GI onboarding session 5

## 1. Session定位
本场是对 PR / Pre OI 机制的深入讲解，重点包括：Pro I 分类、ecom vs O&O 差异、SKU PR 自动化、RPC vs GT 的复杂性、Post OI 单套补差公式如何扣除已享受的 Pro I，以及知识库沉淀方式。

## 2. 开场复盘：三类主流程
会议开始时，Dalton 让 Haoling 先复盘之前的理解。Haoling 复述了三类流程：

1. Pro I / PR：包含 category PR 和 AE 补充的 SKU PR。
2. PP / Free Goods：独立流程。
3. Post OI：包括 pricing promotion 和 formal，走活动创建、审批、POA、POP、IG、Optima 等流程。
4. Pay to Agency：用于券类、到家等 agency 相关活动。

Dalton 确认 Haoling 对前几场内容已经基本消化。

## 3. 本场聚焦：三个非主干但重要流程
Dalton 指出本场主要围绕三个“粉色流程”展开：

- SKU Pro I。
- PP / Free Goods。
- Pay to Agency。

这些流程不在 Post OI 主干活动报销流程中，但在 Trade Fund 管理中非常重要。

## 4. Pro I / PR分类：Category vs SKU
### 4.1 Category PR
- 财年初通过 ITT form 定义。
- 由 central / corporate MSP / GET team 维护。
- 按 category 生效。
- 客户下单时直接享受折扣。

### 4.2 SKU PR
- 针对某些 SKU 做额外补贴。
- AE 可基于具体生意需要发起或维护。
- 通常需要审批、客户 alignment，并最终在 SAP / ICP 生效。

## 5. ecom vs O&O 的差异
### 5.1 O&O
O&O 是本次新能力优先覆盖的对象。原因包括：

- O&O SKU PR 数量多。
- 以往人工维护 effort 大。
- 自动化可以降低 operation 压力。

### 5.2 ecom
ecom 场景更复杂，尤其是 RPC 与 GT 之间的 mapping。

会议中讨论：

- ecom AE 业务上更习惯以 RPC 维度管理。
- SAP 下单生效时并没有 RPC 概念，更多是 GT / JT / 8位码等维度。
- 一个 RPC 可能映射多个 GT。
- RPC 与 GT 的 mapping 可能发生变化。
- 如果用 RPC 作为业务输入，再要落到 SAP 生效，就涉及复杂分摊、映射、历史拉链和变更处理。

因此 ecom SKU PR 自动化暂时没有优先做，而是先聚焦 O&O。

## 6. Category PR数据链路
会议中解释 Category PR 的链路：

```text
ITT Form / Central Team
→ Optima / SAP相关配置
→ 客户下单享受折扣
→ 实际 spending 回流
→ GI展示/计算
→ Optima扣减对应资金
```

需要注意：历史上部分 PR 链路先通过 Optima 与 SAP 打通，因此 category PR 仍保留原有路径。

## 7. SKU PR自动化链路
O&O 的 SKU PR 新能力被描述为新财年将使用的 automation：

```text
AE在GI中配置SKU PR
→ 设置SKU、PR rate、生效时间
→ GI发送alignment
→ 客户确认 + AE确认
→ RPA发送给ICP / SAP
→ 次日可能生效
→ 实际spending回流GI
→ Optima扣减资金
```

## 8. SKU PR自动化的价值
会议中总结了三个主要 benefit：

1. **降低 operation effort**  
   过去人工维护压力大，尤其 O&O SKU PR 数量多。
2. **提升合规与可追溯性**  
   所有 alignment 可以在系统中发送并追溯。
3. **提升时效**  
   过去人工流程可能需要至少 5 working days；自动化后在理想情况下可做到 T+1 生效。

## 9. Post OI单套补差与PR联动
### 9.1 两种输入方式
在 pricing promotion 中，单套补差可有两种方式：

1. AE 直接输入每个 SKU 的单套补差。
2. AE 输入目标 margin，系统倒推每个 SKU 的单套补差。

### 9.2 Margin与单套补差
会议中通过 CPP、list price、Pro I investment、Post OI investment 等概念解释 margin 公式。核心逻辑是：

- 客户最终可获得的总补贴由 PR + Post OI 共同构成。
- 如果客户已经通过 Pro I / PR 享受过折扣，在计算 Post OI 单套补差时必须减掉已享受的 Pro I investment。
- 不能 double pay。
- 如果倒推结果为负，则置为 0，不会让客户倒付。

### 9.3 关键原则
```text
Post OI补差 = 总目标补贴逻辑中扣除已享受的Pro I部分
```

## 10. ecom手工维护流程
会议中提到 ecom 的 SKU PR 目前仍可能通过 manual 流程：

- Customer team 提供信息。
- Corporate MSP / Master Data team 执行维护。
- 维护到 SAP。
- 维护维度更多是 JT / GT level。

## 11. DPB与SKU PR
会议中提到 DPB 并非所有 RD 都在 GI 有 checkbook。当前场景有限，因此暂未单独扩展 SKU PR 自动化能力到 DPB。

## 12. 知识库与文档管理
会议最后讨论知识沉淀工具：

- Dalton 将培训材料放入 GitHub / ghub。
- 希望与 VS Code Copilot / GitHub Copilot 结合，方便后续引用知识库。
- Haoling 尝试访问 GitHub，并讨论与 SharePoint / Confluence 类工具的差异。
- 目标是可持续保存 training 资料，后续同步更新。

## 13. 本场结论
本场将 PR 从“概念”讲到“系统实现与公式联动”：

```text
Category PR：财年初central维护
SKU PR：AE基于SKU维护，O&O优先自动化
ecom SKU PR：因RPC/GT mapping复杂，暂未完全自动化
Post OI单套补差：必须扣除已享受的Pro I，避免double pay
```

## 14. 待展开
- PP / Free Goods 更详细流程。
- Pay to Agency。
- 系统 demo：在 QA 环境中对照功能模块讲解。

## 15. Source
- Event: GI onboarding session 5
- Source reference: turn9search54
