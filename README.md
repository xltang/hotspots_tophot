# hotspots_tophot

用于消费并展示「每日热点」数据的 OpenClaw Skill 项目。

## 功能说明

- 拉取接口：`GET /hotspots/platform/每日热点?userId=$USER_ID&&timestamp=$TIME_STEMP`
- 按 `source_name` 分组展示热点标题
- 支持 `status` 检查（连通性与基础统计）
- 安装或首次启用时可自动注册定时任务（Asia/Shanghai）

## 接口信息

- Base URL: `https://hotspot.api4claw.com`
- Endpoint: `/hotspots/platform/每日热点`
- Query:
  - `userId`: 用户唯一标识
  - `timestamp`: 分钟级时间戳（示例：`2026-04-08T09:30`）

## userId 存放位置

`userId` 持久化在本地 OpenClaw 目录：

- `~/.openclaw/hotspots_tophot/user_id`

若文件不存在，`SKILL.md` 中的初始化脚本会自动生成并复用。

## 定时任务

默认任务名：

- `hotspots-tophot-scheduled-shanghai`

默认 cron：

- `30 9 * * *`（每天 09:30，`Asia/Shanghai`）

## 主要文件

- `SKILL.md`：Skill 规则与执行流程
- `SKILL_weibo.md`：参考模板

