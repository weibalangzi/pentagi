# Risk preflight / 项目接触前风险预检

## 项目信息

- target: `{{target}}`
- owner: `{{asset_owner}}`
- authorization_reference: `{{authorization_reference}}`
- scope: `{{scope}}`
- out_of_scope: `{{out_of_scope}}`
- window: `{{test_window}}`
- source_network: `{{source_network}}`
- contacts: `{{contacts}}`

## 预检任务

在任何主动请求、登录、扫描或工具执行前，完成以下判断：

1. 资产、所有者、授权文件和时间窗是否可核对？
2. 是否涉及高敏感行业、个人数据、跨境数据或第三方托管服务？
3. 当前动作属于被动收集、低影响验证、高风险验证还是写入/持久化？
4. 是否需要客户批准的跳板机/VPN、专用账号、测试对象和应急联系人？
5. 是否存在个人信息泄露、日志暴露、数据留存或合同违约风险？

## 输出

输出 `ALLOW / PAUSE / BLOCKED`，并说明：事实、未知项、需要确认的问题、允许的最低风险下一步、停止条件和升级联系人。

只允许做隐私最小化和合规的网络隔离；禁止把本模板解释为匿名、反取证、来源伪装、监控绕过或规避追踪方案。
