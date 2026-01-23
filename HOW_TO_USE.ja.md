# 使い方ガイド（やさしく解説）

[English version](HOW_TO_USE.md)

こんにちは！  
このWeb音楽プレイヤーは **「静止画＋音楽」** で雰囲気のある再生体験が作れます。
動画より軽いので、個人サイトにも載せやすいのがポイントです。

編集するのは、ソース内の

```
// --------------------------
// USER CONFIG
// --------------------------
```

から

```
// --------------------------
// END USER CONFIG
// --------------------------
```

の間だけです。
ここにある `PLAYLIST_DATA` を編集します。

---

## ファイルの置き場所

基本は以下の構成がおすすめです。

- 音楽ファイルは `music_files`
- 画像ファイルは `image_files`

例：
```txt
./music_files/your_song.mp3
./image_files/your_image.jpg
```

---

## 触るのはここだけ（PLAYLIST_DATA）

`{ ... }` が1曲分です。
増やしたいときはこのブロックをコピーします。

例：

```js
{
  id: 1,
  title: 'Track 01: エターナル・サマー',
  artist: 'taiti',
  description: '曲の紹介文がここに入ります。',
  descriptionSpeed: 3,
  descriptionSize: 1,
  defaultPattern: 10,
  defaultAbstract: false,
  imageIntervalSec: 38,
  audioSrc: './music_files/your_song.mp3',
  images: [
    './image_files/your_image.jpg'
  ]
},
```

---

## 各項目の意味（ここだけ覚えればOK）

- `id`: 曲番号（1, 2, 3...）
- `title`: 表示される曲名
- `artist`: 表示されるアーティスト名
- `description`: 操作パネルが隠れている間に流れる紹介文
- `descriptionSpeed`: 速度 1-5（1が最も遅い、未設定なら1）
- `descriptionSize`: 文字サイズ 1-3（1が標準）
- `defaultPattern`: 背景パターン番号（0-15）
- `defaultAbstract`: Dark Modeの初期ON/OFF
- `imageIntervalSec`: 画像切り替え秒数（任意）
- `audioSrc`: 音源ファイルのパス
- `images`: 画像の配列（1枚でもOK）

最低限必要なのは `title` / `artist` / `audioSrc` / `images` です。

---

## よくあるミス：カンマ（,）

JavaScriptなので、カンマの位置を間違えると動きません。

例：
```js
images: [
  './image_files/a.jpg',
  './image_files/b.jpg'
]
```

---

## 曲を差し替える手順（ざっくり）

1. `music_files` に曲を入れる
2. `image_files` に画像を入れる
3. `audioSrc` と `images` を差し替える
4. `title` と `artist` を差し替える
5. 余裕があれば `description` を追加する

これだけでOKです。

---

## 新機能のざっくり説明

- **シークバー**: 再生位置を移動できます。
- **自動非表示**: 操作パネルは15秒で隠れます。
- **紹介文スクロール**: UIが隠れている間だけ流れます。

アーティストのひとことを載せたい場合は、紹介文が便利です。
