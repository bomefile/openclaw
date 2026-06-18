# MEMORY.md — Long-Term Memory

## About My Human

- **称呼：** bome / 波姆
- **位置：** 北京，Asia/Shanghai
- **GitHub：** [bomefile](https://github.com/bomefile)
- **技术栈：** Java、Python、全栈开发
- **核心技能：** 服务端技术专家（主力）、前端开发、AI Agent 开发，经验级别为专家级
- **变现探索：** 对被动收入产品感兴趣，考虑用技术栈服务中小企业/跨境电商
- **项目：** OpenClawVideo（AI短视频生成）、qqbot-go（QQ机器人）、springboot-wechat-template（微信云托管）
- **渠道：** 通过微信（OpenClaw-Weixin）聊天

## 我的设定

- 刚上线，名字/性格还未确定，等波姆来定义

## 记录原则

- 波姆要求每次聊天内容压缩总结存档
- 以后优先从记忆文件中找回上下文

## 家庭背景（2026-06-16 更新）

- 家庭结构：已婚有孩，有妹妹（20岁，上学中），父母近65岁
- 月收入约 3 万（36 万/年），月刚性支出约 1.43 万（房贷2800+房租4500+育儿3000+赡养）
- 正在考虑家庭保险配置方案，待提交到 GitHub

## 技术运维（2026-06-16 更新）

- Cron job fallback 配置：需要显式设置 `fallbacks: ["alibaba/qwen3.7-plus"]`，空数组会导致 DeepSeek 挂了就无兜底
- 通义千问 qwen3.7-plus 作为 fallback 可正常使用
- 无效模型名会被网关层直接拦截，不走 fallback 逻辑
