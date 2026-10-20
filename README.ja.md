# AI Podcast Voiceover Skill

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

> 👉 こちらもどうぞ [AI Audiobook Generator Skill](https://github.com/beatra-ai/ai-audiobook-generator-skill)

記事、メモ、完成台本を、一貫したホストの声、自然なテンポ、発音の指定で、そのまま公開できる MP3 の一人語りポッドキャストに。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-podcast-voiceover-skill) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | 記事・メモ・完成台本を、同じホストの声で続けられる、聴きやすい一人語りポッドキャスト音声に仕上げます。 |
| **モデル** | MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、Suno 6、MiniMax Music 3.0 |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="サイドプロジェクトを世に出す話をする架空の一人語りポッドキャスト The Small Studio Show のカバーアート。Beatra AI で生成。"></p>

*サイドプロジェクトを世に出す話をする架空の一人語りポッドキャスト The Small Studio Show のカバーアート。Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-podcast-voiceover`](skills/ai-podcast-voiceover) | [SKILL.md](skills/ai-podcast-voiceover/SKILL.md) | 0.2.6 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-podcast-voiceover) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/ai-podcast-voiceover-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/ai-podcast-voiceover-skill ai-podcast-voiceover
```

または、このリポジトリをクローンして `skills/ai-podcast-voiceover` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/ai-podcast-voiceover-skill から ai-podcast-voiceover スキル（フォルダ skills/ai-podcast-voiceover）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 作例

<p align="center"><img src="assets/cover.webp" width="800" alt="サイドプロジェクトを世に出す話をする架空の一人語りポッドキャスト The Small Studio Show のカバーアート。Beatra AI で生成。"></p>

[▶ 試聴する（MP3）](assets/sample.mp3)

*The Small Studio Show の第 12 回。サイドプロジェクトに金曜の締め切りを設ける話の短い台本を、1 つのホストの声で読んだ 50 秒のエピソード。Beatra AI で生成。*

エージェントへの依頼例：

```text
./episode-12-script.md を The Small Studio Show の第 12 回にして：ホストの声は 1 人分に統一し、話し言葉のテンポで、そのまま公開できる MP3 を作って。
```

プロンプト：

```text
Welcome to The Small Studio Show. This is Episode twelve: why your side project needs a Friday deadline.

Most side projects don't die from bad ideas. They die from "someday."

So here's my point. Pick one small, shippable piece, and give it a deadline: this Friday, five p.m. Not a launch. Just one thing a real person can see. A landing page. A demo video. A working sign-up form.

Why Friday? A week is short enough to feel urgent, and long enough to finish something real. When Friday comes, ship what you have, even if it's rough.

Your takeaway: next Monday, write down one Friday deliverable, and tell one friend.

That's it for today. Keep it small, keep it shipping. See you next week.
```

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **アップロード** — 1 ファイルあたり最大 100 MB。下記の各モデルの入力制限も適用されます
- **音声合成** — 2 モデル（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）／FLAC、MP3、OPUS、PCM、WAV／40 言語／サンプルレート 8、16、22.05、24、32、44.1 kHz／1 リクエストあたり最大 50000 文字
  - 言語（ISO 639 コード）：zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **テキストから音楽** — 2 モデル（Suno 6、MiniMax Music 3.0）／MP3
  - Suno 6：プロンプトは最大 500、歌詞は最大 5000、タイトルは最大 80 文字
  - MiniMax Music 3.0：プロンプトは最大 2000、歌詞は最大 3500、タイトルは最大 100 文字
- **参照音声から音楽** — 2 モデル（Suno 6、MiniMax Music 3.0）／MP3
  - Suno 6：プロンプトは最大 500、歌詞は最大 5000、タイトルは最大 80 文字／参照音声 6〜480 秒（FLAC、MP3、WAV）
  - MiniMax Music 3.0：プロンプトは最大 300、歌詞は最大 1000、タイトルは最大 100 文字／参照音声 6〜360 秒、最大 50 MB（FLAC、MP3、WAV）

## 得られるもの

- **文章を耳で追いやすく整える** — 記事、メモ、完成原稿を、自然な流れ、明快なつなぎ、聴き手に伝わる構成を備えた話し言葉の台本に整えます。
- **番組らしいホストの方向性を育てる** — 番組に合う現在の声を選び、固有名詞や専門用語の読み方を整え、次のエピソードへ同じ方向性を生かせます。
- **一話ずつ分かりやすく整える** — 台本、ホストの方向性、読み方の記録、エピソードの焦点を、聴き手に届く一話のためにまとめます。

## 活用シーン

- **記事をポッドキャスト音声へ** — 記事、ニュースレター、調査メモを、導入から締めまで聴き手が追いやすい一話に整えます。
- **ニュースと専門解説** — ニュース解説、専門的な分析、知識番組に安定したホストの声を添え、名前、数字、用語を聞き取りやすくします。
- **個人番組とブランドシリーズ** — 継続する知見、教育、創業者による番組に親しみやすいホストの方向性をつくり、各話へつなげます。
- **番組予告とオープニング** — 短い予告、オープニング、定番の締めの音声をつくり、複数のエピソードにまとまりのある印象を与えます。

## よくある質問

### AIポッドキャスト音声制作では何を作れますか？

手元の記事、メモ、構成、完成台本を、選んだホストの声、自然な話す速さ、明快な読み方、MP3エピソード音声を備えた一人語りポッドキャストに仕上げます。

### シリーズで同じホストの声を生かせますか？

はい。番組のホスト方向を選び、後続のエピソードでも声、言語、話し方の設定、導入、締め、読み方の記録を生かせます。

### どのような材料がエピソード作りに向いていますか？

記事、ニュースレター、調査メモ、専門解説、番組構成、完成台本は、聴き手に届くエピソードを作る良い出発点です。

## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update ai-podcast-voiceover` または
`gh skill update ai-podcast-voiceover`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

[MIT-0](LICENSE)：商用を含め、自由に使用・改変・再配布できます。クレジット表記は不要です。ClawHub 上のこれらのスキルと同じ条件です。

## リンク

- ウェブサイト — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-podcast-voiceover-skill
- ドキュメント — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-podcast-voiceover-skill
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt（インデックス）· https://beatra.ai/llms-full.txt（全スキルを 1 ファイルに）
