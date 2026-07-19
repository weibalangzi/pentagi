# Report fields / 报告字段检查表

## Engagement

`engagement_id`, `authorization_reference`, `scope`, `out_of_scope`, `window`, `source_network`, `test_accounts`, `rate_limit`, `stop_conditions`。

## Finding

`id`, `title`, `asset`, `component`, `preconditions`, `steps`, `expected`, `actual`, `evidence`, `impact`, `likelihood`, `severity`, `confidence`, `root_cause`, `remediation`, `retest`, `status`。

## Evidence hygiene

脱敏 token、密码、Cookie、个人信息和内部密钥；保留时间、角色、请求方法、路径、状态码、关键响应字段和哈希。原始材料应存放在受控位置，报告只引用必要片段。
