# PentAGI agent operating system / 低能力模型增强协议

本卡片是执行任何安全测试任务前的固定协议。它不是目标规则，而是帮助模型稳定思考、减少遗漏和幻觉的“外部工作记忆”。

## 1. 五段式循环

对每个阶段都执行：`plan → act → observe → verify → record`。

- **plan**：写出目的、前置条件、最小动作、预期结果和停止条件。
- **act**：只执行一个可解释的动作，避免把发现、利用和清理混在同一条命令中。
- **observe**：记录原始结果、时间、身份、资产和错误。
- **verify**：用第二种证据或重复测试确认；工具告警只能作为线索。
- **record**：把事实、推断、未知项和下一步分别写入日志。

## 2. 事实等级

每条结论标记为 `FACT`（直接观察）、`INFERENCE`（有证据支持的推断）、`HYPOTHESIS`（待验证假设）或 `BLOCKED`（受条件阻塞）。低能力模型不得把 `INFERENCE/HYPOTHESIS` 自动升级为漏洞。

## 3. 工具选择决策

先问“需要什么证据”，再选工具：资产事实用枚举/读取；行为差异用最小化请求；影响判断用测试对象；历史问题用 Knowledge；外部资料用官方文档或可信数据库。若一个工具连续两次失败，记录错误并切换路径，不要无限重试。

## 4. 任务拆解格式

每个子任务必须有：`objective, scope, inputs, action, expected_observation, evidence, risk, rollback, done_when`。若缺少输入或完成条件，先补全计划，不直接猜测。

## 5. 失败恢复

失败后依次检查：参数/路径 → 权限/身份 → 网络/依赖 → 目标状态 → 是否超出范围。每次只改变一个变量；保留最后一次成功状态，避免盲目重启或扩大扫描。

## 6. 记忆写入

只将可复用且已验证的内容写入 Knowledge：环境前置条件、成功步骤、失败原因、证据特征和回滚方式。不要保存密钥、Cookie、个人信息或未经验证的利用猜想。

English retrieval keywords: agent operating system, plan act observe verify record, evidence ladder, fact inference hypothesis, task decomposition, failure recovery, memory hygiene.
