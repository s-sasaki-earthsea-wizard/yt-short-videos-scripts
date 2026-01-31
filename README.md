# yt-short-videos-scripts

YouTubeの科学技術解説チャンネル向け**短尺動画（3分前後）の脚本**を制作するプロジェクトです。

## 概要

通常の長尺動画（15分前後）とは別シリーズとして、コンパクトで視聴しやすいコンテンツを制作します。

## ディレクトリ構成

```text
yt-short-videos-scripts/
├── instructions/             # シリーズ全体のインストラクション
│   ├── youtube_script_guidelines.md  # TTS変換ガイドライン
│   └── video_concept.md      # 動画コンセプト
├── 001_linus-outburst/       # 動画エピソード
│   ├── outline.md            # 内容のアウトライン
│   ├── yt_script.md          # 脚本本文
│   ├── yt_script_tts.md      # ElevenLabs TTS用スクリプト
│   ├── descriptions/         # 概要欄
│   └── subtitles/            # 字幕ファイル
└── slides-jp/                # 過去のスライド資料（参考用）
```

## エピソード一覧

| No. | タイトル | ステータス |
|-----|----------|------------|
| 001 | linus-outburst | 制作中 |

## ワークフロー

1. **アウトライン作成** (`outline.md`)
   - 動画の構成・流れを設計

2. **脚本執筆** (`yt_script.md`)
   - 話し言葉で自然に聴こえる文章を作成

3. **TTS変換** (`yt_script_tts.md`)
   - ElevenLabs Audio Tags を付与
   - 数値・単位を読み上げ形式に変換

4. **概要欄・字幕作成**
   - YouTube概要欄の作成
   - 必要に応じて字幕ファイルを生成

## 関連ドキュメント

- [TTS変換ガイドライン](instructions/youtube_script_guidelines.md)
