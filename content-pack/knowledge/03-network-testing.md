# Network testing / 网络资产与服务评估

采用“被动 → 低影响存活 → 少量端口 → 服务识别 → 定向复核”的顺序。记录扫描源、时间、速率和排除项。将网络事实与漏洞判断分开：`open port`、`service exposure`、`version hint`、`confirmed weakness` 使用不同证据等级。

高敏感系统（生产数据库、OT/ICS、医疗、身份基础设施）优先人工确认，避免高并发、默认口令尝试、爆破、写入和拒绝服务测试。

English retrieval keywords: asset inventory, CIDR, service enumeration, banner, exposure, rate limit, OT/ICS, database.
