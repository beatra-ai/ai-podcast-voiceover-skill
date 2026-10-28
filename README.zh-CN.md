# AI Podcast Voiceover Skill

[English](./README.md) | 简体中文 | [日本語](./README.ja.md)

> 👉 也看看 [AI Audiobook Generator Skill](https://github.com/beatra-ai/ai-audiobook-generator-skill)

把文章、公众号长文、笔记或定稿做成自然流畅的单人播客口播，固定主播音色，交付可用于发布的 MP3 单集音频，在 Claude Code、Cursor、Codex、Windsurf、Cline 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-podcast-voiceover-skill) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 把文章、公众号长文、笔记或定稿整理成自然流畅的单人播客口播，固定主播音色，交付可用于发布的MP3单集音频。 |
| **底层模型** | MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、Suno 6、MiniMax Music 3.0 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构的单人播客《The Small Studio Show》的封面，节目主题是把业余项目做完上线。由 Beatra AI 生成。"></p>

*虚构的单人播客《The Small Studio Show》的封面，节目主题是把业余项目做完上线。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-podcast-voiceover`](skills/ai-podcast-voiceover) | [SKILL.md](skills/ai-podcast-voiceover/SKILL.md) | 0.2.8 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-podcast-voiceover) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-podcast-voiceover-skill
```

作为 Claude Code 插件：

```bash
claude plugin marketplace add beatra-ai/ai-podcast-voiceover-skill
claude plugin install ai-podcast-voiceover@ai-podcast-voiceover-skill
```

作为 Codex 插件：

```bash
codex plugin marketplace add beatra-ai/ai-podcast-voiceover-skill
codex plugin add ai-podcast-voiceover@ai-podcast-voiceover-skill
```

作为 GitHub Copilot CLI 插件：

```bash
copilot plugin marketplace add beatra-ai/ai-podcast-voiceover-skill
copilot plugin install ai-podcast-voiceover@ai-podcast-voiceover-skill
```

作为 Gemini CLI 扩展：

```bash
gemini extensions install https://github.com/beatra-ai/ai-podcast-voiceover-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-podcast-voiceover-skill ai-podcast-voiceover
```

也可以克隆本仓库，把 `skills/ai-podcast-voiceover` 复制到 `~/.claude/skills/`（Claude Code）、`~/.cursor/skills/`（Cursor）、`~/.agents/skills/`（Codex）、`~/.codeium/windsurf/skills/`（Windsurf）、`~/.cline/skills/`（Cline）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-podcast-voiceover-skill 安装 ai-podcast-voiceover skill（目录 skills/ai-podcast-voiceover），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构的单人播客《The Small Studio Show》的封面，节目主题是把业余项目做完上线。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*《The Small Studio Show》第 12 集，一位主持人用 50 秒讲为什么业余项目需要一个周五截止日，脚本改写自一份简短笔记。由 Beatra AI 生成。*

在你的 Agent 里这样说：

```text
把 ./episode-12-script.md 做成 The Small Studio Show 的第 12 期：用同一个主持人声音，语速自然像聊天，给我一个可以直接发布的 MP3。
```

提示词：

```text
Welcome to The Small Studio Show. This is Episode twelve: why your side project needs a Friday deadline.

Most side projects don't die from bad ideas. They die from "someday."

So here's my point. Pick one small, shippable piece, and give it a deadline: this Friday, five p.m. Not a launch. Just one thing a real person can see. A landing page. A demo video. A working sign-up form.

Why Friday? A week is short enough to feel urgent, and long enough to finish something real. When Friday comes, ship what you have, even if it's rough.

Your takeaway: next Monday, write down one Friday deliverable, and tell one friend.

That's it for today. Keep it small, keep it shipping. See you next week.
```

## 技术规格与输出限制

截至 2026-10-18。实时列表：https://docs.beatra.ai/zh/docs/models

- **上传** — 单个文件最大 100 MB；同时适用下方各模型的输入限制
- **语音合成** — 2 个模型（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）；FLAC、MP3、OPUS、PCM、WAV；40 种语言；采样率 8、16、22.05、24、32、44.1 kHz；单次最多 50000 字符
  - 语言（ISO 639 代码）：zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **文生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；MP3
  - Suno 6：提示词最多 500、歌词最多 5000、标题最多 80 字符
  - MiniMax Music 3.0：提示词最多 2000、歌词最多 3500、标题最多 100 字符
- **参考音频生音乐** — 2 个模型（Suno 6、MiniMax Music 3.0）；MP3
  - Suno 6：提示词最多 500、歌词最多 5000、标题最多 80 字符；参考音频 6–480 秒（FLAC、MP3、WAV）
  - MiniMax Music 3.0：提示词最多 300、歌词最多 1000、标题最多 100 字符；参考音频 6–360 秒，最大 50 MB（FLAC、MP3、WAV）

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 语音合成 2；文生音乐 2；参考音频生音乐 2（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、Suno 6、MiniMax Music 3.0）（截至 2026-10-18），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw。

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

- 官网 — https://www.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-podcast-voiceover-skill
- 文档 — https://docs.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-podcast-voiceover-skill
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt （索引）· https://www.beatra.cn/llms-full.txt （全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
