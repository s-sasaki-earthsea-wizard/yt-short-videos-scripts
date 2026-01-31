# yt-short-videos-scripts

## プロジェクト概要

YouTubeの科学技術解説チャンネル向けの**短尺動画（3分前後）の脚本**を制作するプロジェクト。
通常の長尺動画（15分前後）とは別シリーズとして、コンパクトで視聴しやすいコンテンツを制作する。

## ディレクトリ構造

```text
yt-short-videos-scripts/
├── CLAUDE.md                 # プロジェクト設定・開発ルール
├── README.md                 # プロジェクト概要
├── Makefile                  # ビルドコマンド
├── organizer.yaml            # プロジェクト設定
├── instructions/             # シリーズ全体のインストラクション
│   ├── youtube_script_guidelines.md  # TTS変換ガイドライン
│   └── video_concept.md      # 動画コンセプト
├── 001_linus-outburst/       # 動画エピソード（番号_タイトル形式）
│   ├── outline.md            # 内容のアウトライン
│   ├── yt_script.md          # 脚本本文
│   ├── yt_script_tts.md      # ElevenLabs TTS用スクリプト
│   ├── descriptions/         # 概要欄
│   │   └── youtube_description-jp.md
│   └── subtitles/            # 字幕ファイル
├── slides-jp/                # 過去のスライド資料（参考用）
└── .github/                  # GitHubテンプレート
```

## 動画エピソードの構成

各エピソードディレクトリ（`NNN_タイトル/`）には以下のファイルを配置：

| ファイル | 説明 |
|----------|------|
| `outline.md` | 動画の構成・アウトライン |
| `yt_script.md` | 脚本本文（編集用） |
| `yt_script_tts.md` | ElevenLabs TTS用スクリプト（Audio Tags付き） |
| `descriptions/` | YouTube概要欄（日本語・英語） |
| `subtitles/` | 字幕ファイル（SRT/VTT） |

## 言語設定

このプロジェクトでは**日本語**での応答を行ってください。コード内のコメント、ログメッセージ、エラーメッセージ、ドキュメンテーション文字列なども日本語で記述してください。

## 制作ルール

### 脚本作成

- 詳細なガイドラインは `instructions/youtube_script_guidelines.md` を参照
- 話し言葉として自然に聴こえる文章を心がける
- 一文は20〜30文字程度を目安に
- 専門用語には補足説明を付ける

### TTS変換（ElevenLabs）

- Audio Tags（`[excited]`, `[curious]` など）を適切に使用
- 数値・単位は読み上げ形式に変換
- 間（ポーズ）のコントロールには句読点やタグを活用

### コーディング規約

- Python: PEP 8準拠
- 関数名: snake_case
- クラス名: PascalCase
- 定数: UPPER_SNAKE_CASE
- Docstring: Google Style

### Manimアニメーション

- アニメーション内のテキスト・ラベルは**日英併記**とする
- 国際的な視聴者にも理解できるよう、日本語と英語を併記する

## Git運用

- ブランチ戦略: feature/*, fix/*, refactor/*
- コミットメッセージ: 英文を使用、動詞から始める
- PRはmainブランチへ

## 開発ガイドライン

### ドキュメント更新プロセス

機能追加やPhase完了時には、以下のドキュメントを同期更新する：

1. **CLAUDE.md**: プロジェクト全体状況、Phase完了記録、技術仕様
2. **README.md**: ユーザー向け機能概要、実装状況、使用方法
3. **Makefile**: コマンドヘルプテキスト（## コメント）の更新
4. **makefiles/**: コマンドヘルプテキスト（## コメント）の更新

### コミットメッセージ規約

#### コミット粒度

- **1コミット = 1つの主要な変更**: 複数の独立した機能や修正を1つのコミットにまとめない
- **論理的な単位でコミット**: 関連する変更は1つのコミットにまとめる
- **段階的コミット**: 大きな変更は段階的に分割してコミット

#### プレフィックスと絵文字

- ✨ feat: 新機能
- 🐞 fix: バグ修正
- 📚 docs: ドキュメント
- 🎨 style: コードスタイル修正
- 🛠️ refactor: リファクタリング
- ⚡ perf: パフォーマンス改善
- ✅ test: テスト追加・修正
- 🏗️ chore: ビルド・補助ツール
- 🚀 deploy: デプロイ
- 🔒 security: セキュリティ修正
- 📝 update: 更新・改善
- 🗑️ remove: 削除

**重要**: Claude Codeを使用してコミットする場合は、必ず以下の署名を含める：

```text
🤖 Generated with [Claude Code](https://claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>
```
