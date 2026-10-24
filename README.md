# Air Rules

Surge 与 Loon 共用的分流规则集合，按客户端分别存放规则文件。两端同名 `.list` 文件保持一致，便于同步维护。

## 规则列表

| 规则 | 用途 |
| --- | --- |
| `Apple.list` | Apple 与 iCloud 服务 |
| `ChatGPT.list` | ChatGPT 与 OpenAI |
| `Claude.list` | Claude 与 Anthropic |
| `Copilot.list` | Microsoft Copilot 与 Bing |
| `Gemini.list` | Gemini、Antigravity、Android Studio Gemini |
| `Google.list` | Google 基础服务，不含 YouTube 视频域名 |
| `Netflix_Disney+.list` | Netflix 与 Disney+ |
| `Telegram.list` | Telegram 域名与部分 IPv4 网段 |
| `YouTube.list` | YouTube 网页、视频与静态资源 |

## 接入配置

- [规则接入说明与主配置示例](docs/规则接入说明.md)
- [Surge 规则段](Surge/Rule-Section.conf)
- [Loon 规则段](Loon/Rule-Section.conf)

示例中的 `Proxy` 是占位策略名，导入前要替换成客户端中已配置的策略。Google 通用规则包含 `DOMAIN-KEYWORD,google`，匹配范围较广，应放在 Gemini、YouTube 等具体规则之后。

## 同步维护

更新任一客户端的规则后，请将同名文件同步到另一个目录，并保持规则内容一致。个人上传脚本 `upload_rules_123.sh` 在 `.gitignore` 中，不会进入仓库。
