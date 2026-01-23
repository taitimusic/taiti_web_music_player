# Web Music Player

[English README](README.md)

## 概要
- 静止画＋音楽で動く、軽量な音楽プレイヤーです（動画は使いません）。
- 編集するのは "USER CONFIG" の部分だけでOKです。
- 新機能: シークバー / 操作パネル自動非表示 / 曲紹介文のスクロール表示。

## ファイル
- `html/taiti_music_player_demo.html`（メインの編集対象）
- 詳細ガイド: `HOW_TO_USE.ja.md`

## かんたん設定（USER CONFIG）
1) 編集したいファイルを開く  
2) `// USER CONFIG` を探す  
3) `PLAYLIST_DATA` を曲ごとに編集する  
   - `title`, `artist`
   - `audioSrc`: 音源ファイルのパス（mp3など）
   - `images`: 画像ファイルの配列（jpg/pngなど）
   - `description`: 操作パネルが隠れている間に流れる紹介文
   - `descriptionSpeed`: 1-5（1が最も遅い、未設定なら1）
   - `descriptionSize`: 1-3（1が標準サイズ）
   - `defaultPattern`, `defaultAbstract`, `imageIntervalSec`（任意）

## 新しいUIの動き
- シークバーで再生位置を移動できます。
- 操作パネルは無操作15秒で自動的に隠れます。
- パネルが隠れている間、紹介文が下部で横スクロールします。

## メモ / ヒント
- ブラウザの仕様で自動再生がブロックされることがあります。最初にPlayを1回押してください。
- iOSでは音量はWebAudio（GainNode）で制御しています。
- 画像は「contain表示＋ぼかし背景」で横長画面でも崩れにくい設計です。
- 音源や画像を軽くすると読み込みが速くなります。

## パスについて
- サーバー公開なら `./music_files/track.mp3` のような相対パスが無難です。
- ローカルで開く場合はブラウザ制限があるので、簡易サーバー経由が安全です。

## トラブルシューティング
- 音が鳴らない: Playボタンを1回押す
- 画像が出ない: パスとファイル名（大小文字）を確認
