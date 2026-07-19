# Web/API 基线评估

## 任务描述

对 `{{target}}` 进行一次低影响的 Web/API 基线评估。目标是建立资产清单、识别明显的配置与输入处理问题，并形成可复核的证据链。

## 执行参数

- scope: `{{scope}}`
- out_of_scope: `{{out_of_scope}}`
- authorization_reference: `{{authorization_reference}}`
- test_window: `{{test_window}}`
- rate_limit: 不超过 `{{rate_limit}}` 请求/秒；发现限流或告警时立即降速。
- stop_conditions: 服务异常、数据写入风险、越权迹象、超出 scope、无法区分测试数据与真实数据。

## 阶段

1. 被动收集：域名、解析、证书、公开技术栈和公开文档。
2. 低影响探测：HTTP 方法、状态码、重定向、Cookie/Security Headers、公开路径和 API schema。
3. 认证边界：仅使用提供的测试账号；验证未认证、普通用户、管理员三种角色的访问差异。
4. 输入处理：使用无副作用标记值，验证反射、错误处理、类型校验、分页和资源 ID 的访问控制。
5. 证据与复核：每个发现记录请求、响应、时间、账号角色、影响和最小复现步骤。

## 禁止默认执行

不得默认进行破坏性 payload、批量猜解、真实数据导出、持久化、绕过 MFA、拒绝服务或对第三方资产扩展扫描。需要时先把理由、风险和回滚方案写入计划并等待授权。

## 输出

按 `resources/report-fields.md` 输出：摘要、范围、方法、发现（含置信度）、证据、影响、修复建议、残余风险和未测试项。
