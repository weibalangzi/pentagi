# Cloud and secrets / 云与凭据暴露

检查重点：身份权限最小化、公开存储桶/对象、过宽网络规则、日志与审计、密钥轮换、CI/CD secret、实例元数据访问边界。只验证是否存在暴露和权限差异，不下载不必要的数据，不使用或扩散真实密钥。

发现凭据时：停止扩大访问，记录位置和权限范围，建议所有者立即轮换，并在报告中脱敏。凭据是否可用、可访问什么资源、是否已被使用，必须分别表述。

English retrieval keywords: IAM, least privilege, secret exposure, object storage, bucket, metadata, CI/CD, key rotation.
