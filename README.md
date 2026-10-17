# AI Podcast Voiceover Skill

English | [简体中文](./README.zh-CN.md)

Turn an article, notes, or a finished script into a solo podcast episode with a consistent host voice, natural pacing, pronunciation control, and an MP3 you can publish, from inside Claude Code, Codex, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Turn an article, notes, or finished script into a listenable solo podcast episode with a consistent host voice, natural pacing, pronunciation control, and MP3 delivery. |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Codex, OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="Cover art for The Small Studio Show, a fictional solo podcast about shipping side projects. AI-generated with Beatra."></p>

*Cover art for The Small Studio Show, a fictional solo podcast about shipping side projects. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-podcast-voiceover`](skills/ai-podcast-voiceover) | [SKILL.md](skills/ai-podcast-voiceover/SKILL.md) | 0.2.4 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-podcast-voiceover). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-podcast-voiceover-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-podcast-voiceover-skill ai-podcast-voiceover
```

Or clone this repository and copy `skills/ai-podcast-voiceover` into `~/.claude/skills/` for Claude Code,
`~/.agents/skills/` for Codex, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the ai-podcast-voiceover skill from https://github.com/beatra-ai/ai-podcast-voiceover-skill (folder skills/ai-podcast-voiceover), then follow its SKILL.md to connect my Beatra account.
```

## Examples

<p align="center"><img src="assets/cover.webp" width="800" alt="Cover art for The Small Studio Show, a fictional solo podcast about shipping side projects. AI-generated with Beatra."></p>

[▶ Listen (MP3)](assets/sample.mp3)

*Episode 12 of The Small Studio Show, a 50-second solo episode read by one host voice from a short script about giving side projects a Friday deadline. AI-generated with Beatra.*

Prompt:

```text
Welcome to The Small Studio Show. This is Episode twelve: why your side project needs a Friday deadline.

Most side projects don't die from bad ideas. They die from "someday."

So here's my point. Pick one small, shippable piece, and give it a deadline: this Friday, five p.m. Not a launch. Just one thing a real person can see. A landing page. A demo video. A working sign-up form.

Why Friday? A week is short enough to feel urgent, and long enough to finish something real. When Friday comes, ship what you have, even if it's rough.

Your takeaway: next Monday, write down one Friday deliverable, and tell one friend.

That's it for today. Keep it small, keep it shipping. See you next week.
```

## Technical Specifications & Output Limits

As of 2026-10-16. Live list: https://docs.beatra.ai/en/docs/models

- **Uploads** — up to 100 MB per file; the per-model input limits below also apply
- **Text to speech** — 2 models (MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo); FLAC, MP3, OPUS, PCM, WAV; 40 languages; sample rates 8, 16, 22.05, 24, 32, 44.1 kHz; up to 50000 characters per request
  - Languages (ISO 639 codes): zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **Text to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters
  - MiniMax Music 3.0: prompt up to 2000, lyrics up to 3500, title up to 100 characters
- **Reference audio to music** — 2 models (Suno 6, MiniMax Music 3.0); MP3
  - Suno 6: prompt up to 500, lyrics up to 5000, title up to 80 characters; reference audio 6–480 s (FLAC, MP3, WAV)
  - MiniMax Music 3.0: prompt up to 300, lyrics up to 1000, title up to 100 characters; reference audio 6–360 s, up to 50 MB (FLAC, MP3, WAV)

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Text to speech 2; Text to music 2; Reference audio to music 2 (as of 2026-10-16), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Codex, OpenClaw.

## What you get

- **Make source material easy to hear** — Turn articles, notes, and finished writing into a spoken episode with clear transitions, natural rhythm, and listener-friendly structure.
- **Keep the host direction consistent** — Choose a fitting current voice, keep names and specialist terms clear, and reuse the show direction as new episodes take shape.
- **Shape each episode with clarity** — Bring the script, host direction, pronunciation notes, and episode focus together in one listener-ready production brief.

## Use cases

- **Article-to-podcast audio** — Turn an article, newsletter, or research note into a focused episode that listeners can follow from the opening through the close.
- **News and expert commentary** — Give explainers, analysis, and knowledge shows a steady host voice with clear names, numbers, and technical terms.
- **Branded solo series** — Build a familiar host direction for recurring insight, education, and founder-led podcast episodes.
- **Podcast trailers and show introductions** — Create concise trailer, opener, and recurring sign-off audio that helps a show sound cohesive across episodes.

## FAQ

### What can AI Podcast Voiceover create?

It turns supplied articles, notes, outlines, and finished scripts into listener-friendly solo podcast episodes, with a selected host voice, natural pacing, clear pronunciation, and MP3 episode audio.

### Can I keep one host voice across a series?

Yes. Choose a host direction for the show and reuse its voice, language, delivery settings, opener, closer, and pronunciation notes as later episodes are prepared.

### What material works well for a podcast episode?

Articles, newsletters, research notes, expert commentary, show outlines, and final scripts all provide strong starting points for an episode tailored to listeners.

## Updates and security

Since the 2026-10 release, this skill contains no self-updater: it runs only the
files you installed and never replaces them on its own. Update it with the tool
you installed it with — `npx skills update ai-podcast-voiceover` or `gh skill update ai-podcast-voiceover`.
Details: `references/updates-and-security.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.

## Links

- Website — https://beatra.ai
- Docs — https://docs.beatra.ai
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
