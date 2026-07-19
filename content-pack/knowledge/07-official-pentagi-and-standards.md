# Official PentAGI and standards / 官方实现与标准索引

## PentAGI 官方实现要点

- Flow 是完整测试任务；任务会拆分为 tasks、subtasks 和 actions，适合按阶段给出清晰目标。
- Flow 级文件会自动注入代理提示：上传文件位于 `/work/uploads/`，附加资源位于 `/work/resources/`；因此资源文件应写清用途、适用范围和关键检索词。
- Templates 是可复用的自然语言起点，不要求特殊语法；每次使用仍应替换目标、范围和限制。
- PentAGI 的主记忆和向量存储可独立工作；Graphiti 是可选的时间知识图谱增强层，启用前需确认模型端点、成本和数据留存策略。
- 官方建议小范围、单目标开始，再逐步扩大，便于人工复核和调整提示。

## 推荐外部基线

- OWASP WSTG：按被动理解、主动验证和证据记录组织 Web 测试；适合转成阶段性 checklist。
- OWASP ASVS：将验证拆为架构/威胁建模、认证、会话、访问控制、输入处理、日志、数据保护、文件、API 和配置等章节；Level 1/2/3 可作为测试深度参数。
- 报告中同时记录“测试方法”和“未测试项”，不要把 Top 10 当成完整测试范围。

## 检索关键词

English: PentAGI flow, user files, resources, reusable templates, vector memory, Graphiti, OWASP WSTG, OWASP ASVS, verification level, evidence.

来源：PentAGI 官方 README/文档、OWASP Web Security Testing Guide、OWASP Application Security Verification Standard（链接见 `resources/references.md`）。
