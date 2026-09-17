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

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-podcast-voiceover`](skills/ai-podcast-voiceover) | [SKILL.md](skills/ai-podcast-voiceover/SKILL.md) | 0.1.6 |

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

## Updates

Each installed skill checks for a new version at most once a day, verifies the
official archive before replacing itself, and leaves your installation untouched
if anything fails. Turn it off at any time — see
`references/automatic-updates-and-safety.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.
