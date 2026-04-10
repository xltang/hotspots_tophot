# hotspots_tophot

用于消费并展示「每日热点」数据的 OpenClaw Skill 项目。

## 功能说明

- 拉取接口：`GET /hotspots/platform/每日热点?timestamp=$TIME_STEMP`
- 使用 `web_fetch` 实际请求，禁止缓存或编造
- 按 `source_name` 分组展示热点标题
- 支持 `status` 检查（连通性与基础统计）
- **不** 持久化 `user_id`；定时任务默认仅**提示**，经用户确认后再提供 `openclaw cron add` 命令

## 接口信息

- Base URL: `https://hotspot.api4claw.com`
- Endpoint: `/hotspots/platform/每日热点`
- Query:
  - `timestamp`: 分钟级时间戳（示例：`2026-04-08T09:30`）

## 定时任务

默认任务名：

- `hotspots-tophot-scheduled-shanghai`

默认 cron（用户确认后手动或按需执行）：

- `30 9 * * *`（每天 09:30，`Asia/Shanghai`）

## 主要文件

- `SKILL.md`：Skill 规则与执行流程
- `SKILL_hotspots.md`：结构与行为参考
- `SKILL_weibo.md`：历史参考模板
