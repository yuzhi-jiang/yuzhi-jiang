### 江茂明 · yuzhi-jiang

**Java 后端工程师** ｜ 企业级平台 / 制造业数字化（MES）｜ 佛山，可接受广州 / 深圳 / 杭州

![Java](https://img.shields.io/badge/Java-21-007396?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4-6DB33F?logo=springboot&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring%20Cloud-2024-6DB33F?logo=spring&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-Client-1f6feb)
![Vue](https://img.shields.io/badge/Vue-3-4FC08D?logo=vuedotjs&logoColor=white)

---

### 现在在做什么

2023 年 2 月至今在 **广东宝特智能数字化技术有限公司**，做制造运营平台 **FastMes**（面向制造业的 MES SaaS）：

- 负责 **基础数据 / 报表 / 权限** 模块，以及自研的 **动态字段框架 starter**（注解驱动 + MyBatis 拦截器 + JSqlParser SQL 改写 + 字段级权限脱敏 + Redis 缓存），供多个业务模块接入。
- 参与计划域（MPS / MRP 与 APS 产能负载）的工单与主数据**表结构与接口**；业务规则与算法由业务侧负责。
- 大单表报表导出重构：单次 30 万行 × 40 列——原来一次性拉全量结果集再逐单元格做对象转换，内存与对象回收都压在单次请求上；改为游标式分批读取 + EasyExcel 边读边写落盘、字典批量预加载，30 分钟 → 10 秒内。
- 现任小组长，带 2 名后端 + 1 名前端：需求拆分、接口 / 表结构 / 联调任务分配、设计评审与上线检查。
- 工程侧：Docker 镜像与 JVM 参数调优、SkyWalking / Seata / Actuator / XXL-Job、GitHub Actions 自动构建。

技术栈：JDK 21 · Spring Boot 3.4 · Spring Cloud 2024 · Spring Cloud Alibaba · MyBatis-Plus · Redis · MySQL / PostgreSQL · RabbitMQ · EasyExcel · Docker · Vue 3

### 关注方向

后端架构与工程化 ｜ **AI Agent 工程**（MCP / Tool Calling / 上下文与权限边界）｜ 让 AI 安全地操作真实系统的权限模型

---

### 代表项目

| 项目 | 说明 |
|---|---|
| **[mcp_client](https://github.com/yuzhi-jiang/mcp_client)** | 基于官方 MCP SDK 独立实现的 Python **MCP 客户端**：多 Server 会话、stdio / SSE 双传输、JSON-Schema 参数校验、有界工具调用循环。**72 项测试**（含真实 stdio 端到端），67% 行覆盖，兼容 MCP SDK 1.x / 2.x。 |
| **[netdisk](https://github.com/yuzhi-jiang/netdisk)** · **[netdisk-client](https://github.com/yuzhi-jiang/netdisk-client)** | **Spring Cloud + Hadoop(HDFS)** 的分布式网盘系统：Nacos 注册发现、Redis、RabbitMQ、MySQL，前端 Vue 3 + TypeScript。 |
| **[videwoWhisper](https://github.com/yuzhi-jiang/videwoWhisper)** | 基于 Whisper 的视频字幕提取工具：自动抽音频、断句、翻译与自定义词典替换。 |
| **[lineMarkdown](https://github.com/yuzhi-jiang/lineMarkdown)** | React + TypeScript + Supabase 的在线 Markdown 编辑器：实时预览、语法高亮、流程图、数学公式。 |

### 安全工程

两个自研工具，同一条思路：**让 AI 代理能干活，但拿不到凭据**。

- **[srvctl](https://github.com/yuzhi-jiang/srvctl)（开源）** — Secure Server Controller：代理只拿到服务器编码，看不到 IP、端口、用户名、密码或 SSH Key；凭据用 AES-256-GCM 加密存于 `~/.srvctl/data.enc`（权限 600），密钥由 PBKDF2（60 万次迭代 + 随机盐）派生，解密结果只用于建立 SSH 连接。
- **KeyDock（本地工程原型，未开源）** — macOS 本机凭据代理，Swift 6 / SwiftUI，零第三方依赖：按 UID/PID + 代码签名哈希 + 应用祖先核验调用方，**身份不可核验时仅单次批准、不记忆授权**；密码不进 argv / 环境变量 / 临时文件 / 日志 / CLI 响应。

### 开源贡献

- **[rustdesk #15650](https://github.com/rustdesk/rustdesk/pull/15650)** — 修复 Android 平板触控板的输入映射（设备上报 `SOURCE_MOUSE + TOOL_TYPE_FINGER`，被当成触摸事件：单指滑动进不了鼠标路径、双指被合成左键拖拽）。已通过自动 review、与 master 无冲突，待维护者合并。
- **[MyBatis-PageHelper #837](https://github.com/pagehelper-org/Mybatis-PageHelper/pull/837)** — 修复 `countBoundSql` 复制时 `additionalParameters` 丢失，导致 foreach 等动态 SQL 条件下分页 count 统计错误（已合并）。
- **[hermes-conduit #1152](https://github.com/kaishi00/hermes-conduit/pull/1152) / [#1182](https://github.com/kaishi00/hermes-conduit/pull/1182) · [notifier #339](https://github.com/kaishi00/hermes-conduit-notifier/pull/339)** — 实时语音通道新增独立 provider（服务端签发短时凭证，永久密钥不出服务端）；修复后台任务结果不投递并补回归测试（均由维护者合并）。

---

### 联系

📧 [yuzhi.jiang@foxmail.com](mailto:yuzhi.jiang@foxmail.com) ｜ 📝 博客 [blog.anml.cn](https://blog.anml.cn) ｜ 💼 求职方向：Java 后端 / AI 应用开发
