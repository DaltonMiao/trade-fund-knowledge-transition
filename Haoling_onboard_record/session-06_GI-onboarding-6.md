# Session 6｜GI onboarding 6

## 1. Session定位
本场继续围绕非 Post OI 主干流程展开，重点是 PP、Free Goods、LSR、PP funding、KBD扣减、借还逻辑、新财年变化，以及后续 Pay to Agency 的铺垫。

> 日期说明：会议源中返回的时间为“today at 5 PM”，未在当前导出中固化绝对日期，因此本文档不写具体日期。

## 2. 开场：知识库与GitHub访问问题
会议开头讨论了 ghub / GitHub 知识库访问与编辑问题：

- Haoling 可以下载和查看内容，但无法上传或创建文件。
- 尝试 fork / create new file 时出现 unexpected error。
- Dalton 说明 GI 已有自己的 GitHub knowledge base，当前个人材料后续可能并入 GI knowledge base。
- GitHub 在公司网络下访问不稳定，可能需要备用方式分享资料。

这部分对知识沉淀方式很重要：说明 onboarding 资料未来计划以 GitHub / Markdown 方式持续维护。

## 3. 回顾上一场：Pre OI / PR
Haoling 回顾上一场内容：

- Pro I / PR 分为 ecom 与 O&O 不同路径。
- O&O 有新的自动化能力。
- ecom 仍多走 manual process。
- 后续还需要结合 GI QA 环境做系统 demo。

Dalton 确认：先讲清业务，再做系统演示。

## 4. 本场重点：PP与Free Goods
Dalton 本场开始讲 PP / Free Goods。

### 4.1 PP定义
PP = Promotion Pack，可以理解为促销装。

- PP 在下单时通过价格机制让客户享受优惠。
- 其折扣可以通过 LSR 等价格属性体现。
- PP 的实际 spending 来自客户下单后的事实数据。

### 4.2 Free Goods定义与分类
会议中提到 free goods 相关类型：

- Free goods on invoice。
- NRO。
- Free goods on invest。

Dalton 明确表示对 NRO 背后的 WISE 系统不完全熟悉，因此本场主要聚焦 free goods on invest 与 PP 的关系。

## 5. LSR概念
### 5.1 LSR是什么
会议中解释：LSR 是价格表中的一种临时降价/折扣属性，可用于 PP 或 free goods on invest 等场景。

### 5.2 LSR与PP
PP 的折扣可以通过 LSR 在价格表中体现，使客户下单时价格降低。

### 5.3 LSR与Free Goods
在旧财年逻辑中，free goods on invest 也可能通过 LSR 实现，使发票中体现为价格为0或类似折扣处理。

## 6. PP spending数据来源
会议中明确：

- PP spending / Free Goods spending 的事实数据来自 SAP / ICP 侧下单数据。
- CDL / DPO 会从 SAP 抓取相关 LSR / fact data。
- GI 接收这些 spending 数据，用于后续计算和扣减。

示例：

- 如果原价100，PP价格90，则 spending 为10。
- 如果 free goods 本身无金额，spending 可理解为其对应价值。

## 7. PP与KBD的关系
PP 与普通 KBD spending 不完全一样。

Dalton 将 KBD 类比为一张主银行卡，PP 类比为另一张专款专用卡：

- KBD 是 AE 主要可管理的资金池。
- PP 可能有独立 PP funding。
- PP 与 KBD 之间可能存在转换系数 / switching factor。

## 8. PP客户类型 / CCC类型
会议中将 PP 场景分为几类。

### 8.1 类型一：没有 PP Funding
如果某个 customer + category / CCC 没有 PP funding：

- GI 根据实际 PP spending 计算需要扣多少 KBD。
- 计算时可能要乘以预设 switching factor。
- 之后发送给 Optima 扣减 KBD。

### 8.2 类型二：有 PP Funding，且可借 KBD
如果有 PP funding：

- 先从 PP funding 中扣。
- 如果 PP funding 足够，则有多少扣多少，剩余 PP funding 累积到下月。
- 如果 PP funding 不够，则不足部分向 KBD 借。
- 借 KBD 时需要按 switching factor 折算。
- 后续月份如果 PP funding 有盈余，则需要还 KBD。

这也是本场强调的 PP 最复杂点：借钱、还钱、rolling 计算。

### 8.3 类型三：有 PP Funding，但不借 KBD
新财年可能新增类型三：

- 有 PP funding。
- 但不借 KBD。
- 如果不够扣，可能先记账或由业务侧自行 manage。
- 具体规则由 BU / business side 在财年初决定。

## 9. Switching Factor / 折算系数
会议中解释 switching factor 类似“汇率”：

- PP spending 与 KBD 扣减金额之间不一定 1:1。
- 例如 PP spending 100，factor 0.8，则可能扣 KBD 80。
- Factor 每个财年可由 BU 在 ITT form / setup 中设定。

## 10. 为什么PP可能不够扣
Haoling 提出：如果有 quota / allocation，为什么还会不够扣？Dalton 解释：

- 客户下 PP 订单是业务行为，AE 不能完全阻止客户下单。
- PP allocation / quota 与实际 spending 不是完全同步闭环。
- BU 财年初设置的 PP funding 可能偏保守。
- 客户实际 PP 下单量可能超过 PP funding。
- AE 需要结合 business need 与 funding 健康度平衡管理。

## 11. PP Allocation与Spending的脱节
会议中明确提到：

- PP allocation 在 sales / SAP 流程里管理。
- PP spending 在实际下单后产生。
- 当前 PP allocation 与 GI 中 PP spending / funding 管理存在一定脱节。
- 未来可能有机会打通，但 value 和 priority 尚未评估。

## 12. Central Team审核
对于 PP 相关 draft payment：

- GI 自动生成 draft payment。
- Central team / Corporate MSP 相关人员审核计算是否正确。
- 审核后 submit。
- AE 本身不能直接参与借还钱规则判断，更多是系统规则自动计算。

## 13. Free Goods新财年变化
会议中明确：

- 新财年 Free Goods 会从当前 SD / LSR 逻辑中移出。
- LSR 下主要剩 PP。
- Free Goods 后续不再通过原有 Trade Fund / SD 逻辑处理。
- Dalton 对其后续是否走 MSE 或其他 TT term 不完全确定。

## 14. Free Goods旧逻辑
旧财年中：

- Free Goods 逻辑类似 PP。
- 但比 PP 简单，没有 PP 那么复杂的 switching factor、借 KBD、还 KBD rolling 逻辑。
- 有 free goods funding 就扣 free goods funding；没有则可能扣 KBD。

## 15. GI中的可见性
会议中说明 GI 对 AE 提供 funding / spending visibility：

- AE 可以在 monitor / funding forecast 中看到自己的 funding 与 spending。
- 可区分 forecast 与 actual。
- Funding 表示赚了多少钱，spending 表示实际花了多少钱。
- 这些 visibility 是 AE 管理 checkbook 的核心能力。

## 16. 历史链路与系统边界
本场也讨论到 PR / PP / KBD 相关数据链路中，SAP、Optima、GI 的历史演变：

- Category PR 历史上通过 Optima 与 SAP 打通。
- O&O SKU PR 自动化则尝试建立 GI 与 SAP 更直接的路径。
- PP / Free Goods 相关 spending 也需要通过 SAP/ICP事实数据回流。

## 17. 本场结论
PP 是一个比表面复杂得多的模块。核心要点：

```text
客户下PP订单
→ SAP/ICP产生PP spending
→ 数据回流GI
→ GI判断CCC是否有PP funding
→ 有则先扣PP funding
→ 不足时视类型决定是否借KBD
→ 后续若PP funding盈余则还KBD
→ Optima执行扣减/付款相关动作
```

## 18. 后续计划
- 下次继续讲 Pay to Agency。
- Pay to Agency 流程可能比 PP 更复杂，但理解上会更直观。
- 讲完 Pay to Agency 后，大的业务场景基本可以覆盖七七八八，随后进入系统 demo / QA 环境讲解。

## 19. Source
- Event: GI onboarding 6
- Source reference: turn9search55
