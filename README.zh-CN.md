# AI Podcast Voiceover Skill

[English](./README.md) | 简体中文

把文章、公众号长文、笔记或定稿做成自然流畅的单人播客口播，固定主播音色，交付可用于发布的 MP3 单集音频，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 把文章、公众号长文、笔记或定稿整理成自然流畅的单人播客口播，固定主播音色，交付可用于发布的MP3单集音频。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构的单人播客《The Small Studio Show》的封面，节目主题是把业余项目做完上线。由 Beatra AI 生成。"></p>

*虚构的单人播客《The Small Studio Show》的封面，节目主题是把业余项目做完上线。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-podcast-voiceover`](skills/ai-podcast-voiceover) | [SKILL.md](skills/ai-podcast-voiceover/SKILL.md) | 0.2.4 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-podcast-voiceover) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-podcast-voiceover-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-podcast-voiceover-skill ai-podcast-voiceover
```

也可以克隆本仓库，把 `skills/ai-podcast-voiceover` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-podcast-voiceover-skill 安装 ai-podcast-voiceover skill（目录 skills/ai-podcast-voiceover），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构的单人播客《The Small Studio Show》的封面，节目主题是把业余项目做完上线。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*《The Small Studio Show》第 12 集，一位主持人用 50 秒讲为什么业余项目需要一个周五截止日，脚本改写自一份简短笔记。由 Beatra AI 生成。*

提示词：

```text
Welcome to The Small Studio Show. This is Episode twelve: why your side project needs a Friday deadline.

Most side projects don't die from bad ideas. They die from "someday."

So here's my point. Pick one small, shippable piece, and give it a deadline: this Friday, five p.m. Not a launch. Just one thing a real person can see. A landing page. A demo video. A working sign-up form.

Why Friday? A week is short enough to feel urgent, and long enough to finish something real. When Friday comes, ship what you have, even if it's rough.

Your takeaway: next Monday, write down one Friday deliverable, and tell one friend.

That's it for today. Keep it small, keep it shipping. See you next week.
```

## 规格

截至 2026-10-16。实时列表：https://docs.beatra.ai/zh/docs/models

- **语音合成** — 2 个模型（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）；FLAC、MP3、OPUS、PCM、WAV；40 种语言；最高 44.1 kHz；单次最多 50000 字符
- **文生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；歌词最多 5000 字符
- **参考音频生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；歌词最多 5000 字符

## 你能得到什么

- **让文字更适合听** — 把文章、笔记和定稿整理为带有清晰过渡、自然节奏和听众友好结构的播客脚本。
- **延续节目主播感** — 选择适合栏目的当前音色，处理人名和术语读法，并把节目方向延续到后续单集。
- **清楚整理每一集** — 把脚本、主播方向、读音记录和单集重点整理为一份适合听众的播客制作简报。

## 适用场景

- **文章转播客音频** — 把文章、公众号长文或研究笔记整理为从开场到收尾都便于聆听的播客单集。
- **新闻与知识解说** — 为新闻评论、专业分析和知识栏目选择稳定的主播声音，清楚呈现人名、数字和专业术语。
- **个人与品牌系列** — 为持续更新的观点、教育和创始人栏目建立熟悉的主播方向，让每一集保持节目感。
- **节目预告和开场** — 制作简洁的预告、开场和固定收尾音频，让栏目在不同单集之间拥有连贯的声音。

## 常见问题

### AI播客配音可以制作什么？

它把已有文章、笔记、大纲和定稿整理成适合聆听的单人播客单集，包含主播音色、自然节奏、清晰读音和MP3单集音频。

### 系列节目可以延续同一主播音色吗？

可以。先为节目选择主播方向，后续单集可以沿用音色、语言、表达设置、开场、收尾和读音记录。

### 哪些内容适合做成播客单集？

文章、公众号长文、研究笔记、专业解说、节目大纲和定稿都适合作为整理成播客单集的起点。

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update ai-podcast-voiceover` 或 `gh skill update ai-podcast-voiceover`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn
- 文档 — https://docs.beatra.cn
- 控制台 — https://console.beatra.cn

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
