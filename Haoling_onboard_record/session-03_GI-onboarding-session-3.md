# Session 3｜GI onboarding session 3

## 1. Session定位
本场重点从系统对象模型解释 Trade Fund 如何在 GI 中被承载，核心是 FID / Checkbook / G1-G3 客户分级 / 权限 / KBD 简化 / PR基础逻辑。

## 2. GI权限申请
会议中讨论 Haoling 的 GI 权限申请：

- 先申请 QA / project team 权限。
- 等正式 announce 后再申请 production 权限。
- 相关邮件需要发给 GIIO / GI Support，并抄送 Dalton。

## 3. Fund Account / FID
### 3.1 FID定义
FID 是 fund account，可以理解为客户或 banner 级别的资金账户对象。用户进入 GI 后，会基于其权限看到对应的 FID / banner 范围。

### 3.2 FID与Banner
FID 与 banner 强相关。对于 AE 来说，进入系统后通常看到自己管理范围下的客户/banner。

## 4. Checkbook结构
### 4.1 Checkbook定义
Checkbook 是 FID 下更细的资金容器。可以理解为“账户下的账本”。

### 4.2 Checkbook权限
会议中明确：

- 每个 Checkbook 只能有一个 Payment AE。
- 可以有其他 AE / assistant 协助建活动或处理部分操作。
- Payment 权限是唯一的。

## 5. 客户分级：G1 / G2 / G3
### 5.1 G1客户
G1 是生意体量较大的客户，通常可以做到每个 category 一个 checkbook。

### 5.2 G2客户
G2 客户会将多个 category 合并成 sector，一个 sector 对应一个 checkbook。

### 5.3 G3客户
G3 客户体量较小，可能所有 category 合并成一个 corp / cop 级别的 checkbook。

### 5.4 业务影响
客户分级影响：

- Checkbook颗粒度。
- Payment AE归属。
- 权限控制。
- 报销和资金管理方式。

## 6. 客户升降级与组织变更
会议中举例讨论客户因生意体量变化在新财年升降级：

- G1 → G2。
- G2 → G3。
- 这些变化会影响系统中 checkbook 粒度和 payment AE 配置。

### 6.1 SOP化支持
过去此类组织变化需要开发支持，但现在常见场景已经抽象成 SOP：

- Operation team 通过后台配置表支持。
- 配置随 customer hierarchy 生效。
- 配置后需要测试。

### 6.2 复杂组织变化
复杂变更仍需 case by case：

- 新增 channel。
- 非标准 organization change。
- 不能走现有 SOP 的场景。

## 7. DPB Scope说明
会议中说明 GI 并不覆盖所有 DPB / RD 场景。当前只覆盖部分特定类型，例如与 PUPU、JDJXT、ICP 等类似的业务流程。很多 RD 的 business process 不在 GI 中创建活动，因此对 GI 影响有限。

## 8. KBD资金池与Fund Bucket简化
### 8.1 历史情况
历史上，报销时可能需要选择多个 fund bucket。

### 8.2 当前简化
当前系统做了很多 simplification：

- 很多 fund bucket release 后都归入 KBD 大池子。
- AE request payment 时基本只能选择 KBD。
- 对 AE 来说，可以先理解为“一个主要口袋：KBD”。

### 8.3 KBD包含的内容
KBD 可能包括 consumer fund、AKBD、Incremental SRE、How High Is High、Contingency 等不同来源，但对 AE 花钱时通常表现为一个 KBD 池。

## 9. Pre OI / Post OI初步承接
会议中从 KBD 后自然引出两种花钱方式：

- Pre OI / PR：下单时抵扣。
- Post OI：事后报销。

## 10. Category PR与SKU PR
### 10.1 Category PR
- 财年初由 central team / GET team 根据 ITT form 统一维护。
- 客户下单时按 category 自动享受折扣。
- AE 无法随意更改。

### 10.2 SKU PR
- AE 可根据生意需求选择具体 SKU 设置额外 PR。
- 需要审批。
- 需要与客户 alignment。
- 生效后会通过 SAP / ICP 承接。

## 11. PR与Post OI组合逻辑
会议中讨论：即使 category 已有 PR，也不代表不需要 Post OI。AE 可能保留部分资源做 Post OI，以维持客户谈判空间和 control power。

## 12. 本场形成的决策/结论
来自 Session 3 loop 纪要的决策包括：

- 通过 operation team 配置支持 checkbook J级变更。
- 常见组织结构变更由 operation team 通过 SOP 支持。
- 为 Haoling 分配 GI 系统 QA 和生产权限。
- Category Pro I 由 central team 统一维护。

## 13. 待解决问题 / Gap
来自 Session 3 loop 的待解决问题：

- G2/G3 降级后系统权限和管控自动调整流程未完全明确。
- 复杂组织变更是否能走 SOP 需 case by case 判断。
- G2/G3 客户 payment AE 分配方式需进一步澄清。
- 非 end to end banner 客户 reporting line 设置需后续确认。
- KBD 以外 fund bucket 类型保留与否需后续确认。
- SKU PR 维护审批流程标准化需单独梳理。
- Post / Pre OI 资金分配比例标准需进一步明确。

## 14. 本场结论
本场完成了从业务 funding 到 GI 系统对象的映射：

```text
Customer / Banner → FID → Checkbook → Payment AE → KBD → PR / Post OI
```

## 15. Source
- Event: GI onboarding session 3
- Source reference: turn9search56
- File: GI onboarding session 3.loop
