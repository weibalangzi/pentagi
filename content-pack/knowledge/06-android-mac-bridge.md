# Android/Mac bridge / 联动执行节点

Android Bridge (`http://host.docker.internal:8765`) 和 Mac Bridge (`http://host.docker.internal:8766`) 是执行工具节点，不是默认测试目标。先调用 `/health`、读取设备/系统信息，再执行最小必要动作。所有命令应写明目的、预期输出和回滚方式。

危险 shell 接口只在本地、显式 danger 模式启用；不要把端口暴露到局域网或公网。手机探测仅限用户拥有或明确授权的网络；Mac shell 仅操作工作目录和测试环境。结果中记录执行节点、命令摘要和时间。

English retrieval keywords: Android bridge, ADB, Shizuku, rish, Mac bridge, execution node, host.docker.internal, least privilege.
