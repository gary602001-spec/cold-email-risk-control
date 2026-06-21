# Cold Email Risk Control

外贸冷邮件发信前风控规则与 Codex 审核模板。

这个项目不是教人“绕过风控”或“提高群发量”。它的目标是把冷邮件开发客户前最容易出问题的环节做成可检查、可复用、可停止的流程：邮箱可信、名单精准、节奏稳定、内容像真人、有退出机制、数据能监控。

## 适用场景

- 新域名、新邮箱上线前检查
- SPF、DKIM、DMARC、邮件头和退订机制检查
- 客户名单导入前审核
- 第一封开发信和跟进邮件审核
- 提高发送量前的风险判断
- 退信、投诉、进垃圾箱、延迟、拒收等异常排查
- 用 Codex 作为发信前风险提醒系统

## 不适用场景

- 规避反垃圾邮件系统
- 购买邮箱名单后批量轰炸
- 虚假暖箱、假打开、假回复、假互动
- 对退订、拒绝、投诉联系人换邮箱继续追发
- 替代律师或合规顾问给出正式法律意见

## 快速使用

1. 在 Codex 中打开本仓库目录。
2. 每次准备发信前，复制并填写 [templates/pre-send-risk-review.md](templates/pre-send-risk-review.md)。
3. 只审核标题和正文时，用 [templates/email-copy-review.md](templates/email-copy-review.md)。
4. 出现退信、投诉、进垃圾箱、拒收等异常时，用 [templates/sending-incident-review.md](templates/sending-incident-review.md)。
5. Codex 会按 [AGENTS.md](AGENTS.md) 和 [外贸冷邮件开发业务总规则](docs/business-development-rules.md) 给出明确结论。

## S/A/B/C 评级

每次审核必须输出一个评级和动作：

- `S 级`：高度匹配，低量稳定发送。
- `A 级`：匹配度高，小改后发送。
- `B 级`：证据偏弱，先补资料或极小量测试。
- `C 级`：相关性弱，默认不发。
- `禁止发送`：命中红线，必须拦截。

动作包括：`可发`、`小改后可发`、`减量测试`、`暂停发送`、`禁止发送`、`需要先确认合规`。

## 核心原则

1. 不用垃圾名单。
2. 不用没配置好的邮箱。
3. 不一上来猛发。
4. 不写得像广告群发。
5. 不骚扰不感兴趣的人。
6. 不只看 DNS 记录，要看实发邮件头认证是否通过。
7. 不用假暖箱、假打开、假回复等虚假互动。
8. 不把退订、投诉、拒绝当成还能继续换邮箱追发的对象。
9. 加拿大、澳大利亚、欧盟、英国等市场信息不足时先按高风险处理。

## 项目结构

```text
.
├── AGENTS.md
├── templates/
│   ├── pre-send-risk-review.md
│   ├── email-copy-review.md
│   └── sending-incident-review.md
├── docs/
│   ├── risk-framework.md
│   ├── operating-guide.md
│   ├── legal-notes.md
│   └── sources.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── CHANGELOG.md
└── LICENSE
```

## 文档

- [完整风控框架](docs/risk-framework.md)
- [外贸冷邮件开发业务总规则](docs/business-development-rules.md)
- [日常操作指南](docs/operating-guide.md)
- [合规说明](docs/legal-notes.md)
- [资料来源](docs/sources.md)

## 资料时效

邮箱平台规则、发件人要求和各地区合规要求会变化。本项目中的规则按公开资料和实践经验整理，不保证覆盖所有司法辖区或所有发件平台。涉及正式合规判断时，应核对最新官方文件并咨询专业法律意见。

## 许可证

MIT License。详见 [LICENSE](LICENSE)。