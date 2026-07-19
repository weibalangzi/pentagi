# PentAGI 初学者安全测试内容包

本目录用于导入 PentAGI 的 `Resources`，并将 `templates/*.md` 中的文本复制到 `Templates`。

## 推荐导入顺序

1. 先阅读 `01-engagement-methodology.md`，建立任务、证据和停止条件。
2. 将本目录全部上传到一个资源目录，例如 `resources/learning-pack/`。
3. 在创建 Flow 时附加相关资源文件。
4. 从 `templates/` 选择任务模板，替换其中的 `{{...}}` 变量。
5. 将最终报告中的新事实、误报和复现步骤整理后存入 Knowledge，避免把未经验证的猜测写入长期知识。

## 适用范围

默认面向本地靶场、CTF、明确授权的内部资产和书面授权的测试项目。模板中的 `scope`、`out_of_scope`、`rate_limit`、`stop_conditions` 是执行参数，不是装饰性文字。

## 目录

- `templates/`：Flow 任务模板，适合复制到 Templates。
- `knowledge/`：短知识卡片，适合逐份导入 Knowledges。
- `resources/`：参考资料、检查表和报告字段，适合上传到 Resources。

新增 `resources/knowledge-sources.yml` 和 `templates/05-knowledge-upgrade.md`，用于维护漏洞、方法论和培训来源，并按来源、版本、时效和交叉验证结果更新 Knowledge。

新增 `resources/risk-policy.yml`、`knowledge/09-risk-preflight-and-privacy.md` 和 `templates/06-risk-preflight.md`，用于在每个 Flow 开始前做授权、范围、敏感行业、数据和个人隐私预检。它支持隐私最小化，不提供匿名化攻击、反取证或规避归因能力。

`knowledge/07-official-pentagi-and-standards.md` 和 `resources/references.md` 汇总了本内容包所依据的官方 PentAGI 文档、OWASP WSTG 与 ASVS。外部标准更新时，应重新核对版本，不要无条件覆盖现有已验证知识。

## 提升低能力模型稳定性的顺序

优先导入 `knowledge/00-agent-operating-system.md` 和 `templates/00-structured-security-assessment.md`。前者提供固定的计划—行动—观察—验证—记录循环，后者把每个子任务强制约束为结构化字段。之后再导入领域知识卡片。模型回答变差时，不要只换模型，先检查它是否遵循了事实等级、证据门槛和失败恢复协议。
