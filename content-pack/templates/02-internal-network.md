# 内网资产与服务暴露评估

## 任务描述

在 `{{cidr_or_hosts}}` 范围内进行低影响的资产发现与服务暴露评估，重点回答“有哪些资产、哪些服务、哪些版本需要人工复核”。

## 执行参数

- scope: `{{cidr_or_hosts}}`
- exclusions: `{{exclusions}}`
- source_network: `{{source_network}}`
- rate_limit: `{{rate_limit}}`
- stop_conditions: 大量丢包、业务延迟、设备告警、发现生产数据库/控制系统、超出授权网段。

## 方法

1. 先记录本机接口、路由、DNS 和时间，确认扫描源。
2. 采用分阶段探测：存活性 → 少量常见端口 → 服务识别 → 针对性验证。
3. 将“端口开放”“服务可访问”“存在漏洞”严格区分，版本信息必须注明来源和时间。
4. 对高风险服务（管理面、数据库、文件共享、远程管理）只做 banner/配置级验证，不进行口令喷洒或数据读取。
5. 结果去重，保存资产、端口、协议、证据和复核建议。

## 输出

生成资产表：`ip, hostname, owner, exposure, port, protocol, service, version, evidence, confidence, next_check`；另附异常资产和未覆盖范围。
