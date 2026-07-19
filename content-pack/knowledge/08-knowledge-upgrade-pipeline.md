# Knowledge upgrade pipeline / 知识升级流水线

目标不是把网页全文堆进向量库，而是把新信息转成可验证、可追溯、可复用的知识记录。

## Pipeline

`discover → fetch → normalize → cross-check → classify → redact → embed → review → expire/revise`

1. **Discover**：从 `resources/knowledge-sources.yml` 按主题和更新时间检索，不进行无目标的宽泛搜索。
2. **Fetch**：保存 canonical URL、标题、来源、发布时间、修改时间、抓取时间和版本。
3. **Normalize**：提取漏洞 ID、受影响版本、前置条件、修复、检测线索、实验室复现条件和参考链接。
4. **Cross-check**：NVD/OSV/GitHub Advisory 与厂商公告交叉核对；KEV 只表示已知在野利用，不等于所有环境都可利用。
5. **Classify**：标记 `fact / inference / hypothesis`、`primary / secondary`、`lab-safe / high-risk`、`fresh / stale`。
6. **Redact**：删除密钥、Cookie、个人信息、内部地址和不必要的真实数据；不要把可直接用于未授权入侵的完整武器化内容写入共享 Knowledge。
7. **Embed**：按“摘要、事实、方法论、证据、来源”分块；中英文关键词并存；变更记录保留旧版本。
8. **Review**：由较强的 Adviser 或人工复核；未复核记录只能作为线索，不能直接驱动高风险动作。
9. **Expire/revise**：按 `modified_at` 和产品生命周期复查；过期记录降低检索权重而不是直接删除。

## Knowledge record minimum

`id, title, kind, source_url, source_version, published_at, modified_at, fetched_at, affected_scope, prerequisites, facts, verification, remediation, confidence, freshness, sensitivity, related_ids`。

English retrieval keywords: vulnerability intelligence, advisory ingestion, source provenance, cross-check, freshness, fact inference hypothesis, deduplication, re-embedding, review gate.
