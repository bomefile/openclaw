# OpenClaw 系统诊断报告

> 诊断时间：2026-06-16 13:46 (Asia/Shanghai)

---

## 1️⃣ 健康快照 (openclaw status)

```
状态: running ✓
Gateway: local · ws://127.0.0.1:18789 · reachable 57ms · auth token
Gateway service: systemd running (pid 15382)
Dashboard: http://172.23.218.150:18789/
渠道: openclaw-weixin → ON ✓
Agent: main → 正常 · 4 sessions
内存: 已启用
Tasks: 0 active · 0 queued · 0 running · 16 tracked
Heartbeat: 30m (main)
```

## 2️⃣ 深度诊断 (openclaw doctor)

### 发现的非阻塞性问题（均为建议性质）：

| 问题 | 说明 | 建议 |
|------|------|------|
| NODE_COMPILE_CACHE 未设置 | 小机器上 CLI 启动会慢 | 建议设置环境变量 |
| 消息工具未显式加入 agent allowlist | 微信渠道的消息工具可用性告警 | 非阻塞，不影响当前运行 |
| 命令所有者未配置 | 无 owner 账号运行特权命令 | 操作前需先配置 |
| OAuth 目录不存在 | 无 WhatsApp/pairing 渠道，不影响 | 可忽略 |
| Session lock | 1个活动锁，进程存活，正常 | 正常 |
| 安全警告 | Gateway 绑定 0.0.0.0（lan），token 明文 | 生产环境建议走 Tailscale |
| Memory search | OpenAI key 未设置，语义搜索不可用 | 非必须，可配置或关闭 |

**Skills: 14 eligible · Plugin: 68 loaded · 0 errors ✅**

## 3️⃣ 网关状态 (openclaw gateway status)

```
Runtime: running (pid 15382, state active)
Connectivity probe: ok ✓
Service: systemd user (enabled)
Gateway version: 2026.6.1
Listening: *:18789
```

## 4️⃣ 完整报告 (openclaw status --all)

```
渠道: openclaw-weixin → ON · credential available ✓
Agent: main · 4 sessions · 1 active recently
Gateway connection: ws://127.0.0.1:18789 · 54ms
Config: /root/.openclaw/openclaw.json ✓
Secret diagnostics: 0 issues ✓
Port check: port 18789 正常 ✓
Inbound delivery: 0 received · 4 dispatched · 3 processed
Channel issues: none ✓
```

## 结论

系统运行正常 ✅
- 无致命错误
- 所有渠道连接正常
- 网关服务稳定运行
- 发现的问题均为建议性优化项，非阻塞性问题

