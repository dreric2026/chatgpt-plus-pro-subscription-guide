# [ChatGPT Plus / Pro 充值与 Codex 中文指南](https://gptupcn.com)

# ChatGPT 充值到 Codex 可用：工程化排障 Runbook

本仓库面向需要进行 ChatGPT Plus 充值、ChatGPT Pro 充值、续费并使用 Codex / AI Agent 的中文用户。目标是用可验证步骤区分账号、订单、套餐权益、Codex Usage 和 API 计费。

> 第三方中文教程，不是 OpenAI 官方项目。价格、功能和额度以账户当前页面为准。

## 决策树

```text
ChatGPT 是否显示目标套餐？
├─ 否 -> 检查登录账号、购买渠道、订单状态、恢复购买
└─ 是 -> Codex 是否使用同一账号？
        ├─ 否 -> 重新登录并核对工作区
        └─ 是 -> 检查 Usage、任务规模、仓库环境

API 是否提示余额不足？
└─ 单独检查 API 项目、Key、预算和账单
```

## 充值前检查

- [ ] 登录的是本人长期使用账号
- [ ] 已确认网页、Apple、Google Play 是否存在订阅
- [ ] Plus / Pro 套餐和周期明确
- [ ] 保存订单号、时间和付款凭证
- [ ] 了解订单查询、退款与售后规则
- [ ] 不提供密码、恢复码、Cookie 或 API Key

## 支付失败

常见原因包括银行卡不支持境外周期交易、账单资料不一致、余额不足、银行风控和短时间重复尝试。一次只调整一个条件；确认上一笔订单最终失败后再重试。

## 扣款后套餐未更新

1. 区分正式扣款、预授权和待处理。
2. 核对当前登录邮箱。
3. 回到原购买渠道检查订单。
4. 重新登录并查看套餐名称和续费日。
5. 状态不明时不要重复购买。

## Codex 额度与环境

Plus 或 Pro 有效并不代表任何规模的 Codex 任务都无限使用。大型仓库扫描、多轮测试和 Agent 长任务消耗更高。推荐：

- 指定允许读取与修改的目录；
- 提供架构说明和相关测试；
- 任务拆成 Inspect、Plan、Implement、Validate；
- 保存检查点，避免中断后重复分析；
- 使用分支和 CI 验证变更。

## ChatGPT 与 API 分开

ChatGPT Plus / Pro 是产品订阅；OpenAI API 用于程序调用，通常独立计费。Plus 充值后 API 仍提示 `insufficient_quota`，应检查 API 平台中的项目、预算、付款方式和 Key。

## 安全响应

如果密码、Cookie 或 API Key 曾被公开，立即撤销会话、轮换凭证并检查异常订单。公开 Issue 只能提交脱敏错误信息，不要粘贴付款资料和身份信息。

## 最小故障记录

```yaml
time: 2026-08-11T10:30:00+08:00
channel: web | apple | google-play | other
order_status: pending | paid | failed | refunded
plan_visible: free | plus | pro
codex_status: available | limited | login-error | env-error
api_status: not-used | active | billing-error
```

## License

Documentation released under CC BY 4.0.
