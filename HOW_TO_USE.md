# How to Use (Easy Guide)

[日本語版はこちら](HOW_TO_USE.ja.md)

Hi!  
This Web music player creates an atmospheric experience with **static images + music**.
It is lighter than video, so it is great for personal sites and portfolios.

You only need to edit the section between:

```
// --------------------------
// USER CONFIG
// --------------------------
```

and

```
// --------------------------
// END USER CONFIG
// --------------------------
```

Everything is set inside `PLAYLIST_DATA`.

---

## Folder basics

Recommended setup:
- Put audio files in `music_files`
- Put images in `image_files`

Example paths:
```txt
./music_files/your_song.mp3
./image_files/your_image.jpg
```

---

## Edit only PLAYLIST_DATA

Each `{ ... }` block is one track.
Copy it to add more tracks.

Example:

```js
{
  id: 1,
  title: 'Track 01: Neon Letters',
  artist: 'Nova Keys',
  description: 'A bright opener with airy synths and a slow-blooming chorus.',
  descriptionSpeed: 3,
  descriptionSize: 1,
  defaultPattern: 10,
  defaultAbstract: false,
  imageIntervalSec: 38,
  audioSrc: './music_files/demo_track_01.mp3',
  images: [
    './image_files/demo_image_01.jpg'
  ]
},
```

---

## Field meanings (the ones to remember)

- `id`: Track number (1, 2, 3...)
- `title`: Track title shown on screen
- `artist`: Artist name shown on screen
- `description`: Short note that scrolls when UI is hidden
- `descriptionSpeed`: Scroll speed 1-5 (1 is slowest, default if omitted)
- `descriptionSize`: Text size 1-3 (1 is standard)
- `defaultPattern`: Background pattern number (0-15)
- `defaultAbstract`: Dark Mode default (`true` or `false`)
- `imageIntervalSec`: Image swap interval (seconds, optional)
- `audioSrc`: Path to your audio file
- `images`: List of image paths (1+ images)

Minimum required fields: `title`, `artist`, `audioSrc`, `images`.

---

## Common mistake: commas

This is JavaScript.
If you miss a comma or add an extra one, it breaks.

Example:
```js
images: [
  './image_files/a.jpg',
  './image_files/b.jpg'
]
```

---

## Quick replace steps

1. Put your audio in `music_files`
2. Put your images in `image_files`
3. Replace `audioSrc` and `images`
4. Update `title` and `artist`
5. (Optional) Add `description` for the scrolling note

That is it. Your music + images will play immediately.

---

## New features (short version)

- **Seekbar**: drag to jump in the track.
- **Auto-hide controls**: after 15 seconds of no input.
- **Scrolling description**: appears only when the UI is hidden.

For artists, the description is perfect for short thoughts or credits.
