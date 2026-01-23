# Web Music Player

[日本語版はこちら](README.ja.md)

## Overview
- Lightweight music player with reactive visuals and static images (no video).
- Customize by editing the "USER CONFIG" section only.
- New features: seekbar, auto-hide controls, scrolling track descriptions.

## Files
- `taiti_web_music_player.html` (main working file)
- Detailed guide: `HOW_TO_USE.md`

## Quick setup (USER CONFIG)
1) Open the file you want to edit.
2) Find: `// USER CONFIG`
3) Edit `PLAYLIST_DATA` for each track:
   - `title`, `artist`
   - `audioSrc`: path to your audio file (mp3, etc.)
   - `images`: list of image paths (jpg/png, etc.)
   - `description`: track note shown when UI is hidden
   - `descriptionSpeed`: 1-5 (1 is slowest, default if omitted)
   - `descriptionSize`: 1-3 (1 is current size)
   - `defaultPattern`, `defaultAbstract`, `imageIntervalSec` (optional)

## How the new UI works
- Seekbar lets listeners jump within a track.
- Controls auto-hide after 15 seconds of no input.
- When hidden, the description scrolls at the bottom with a short delay between loops.

## Notes / tips
- Autoplay with sound is often blocked by browsers. Users may need to tap Play once.
- On iOS, audio volume is controlled via WebAudio (GainNode), not the audio element.
- Images are displayed with a foreground "contain" + blurred "cover" background to avoid stretching.
- Smaller audio/image files reduce load time and are good for personal sites.

## File paths
- If you host on a web server, use relative paths like `./music_files/track.mp3`
- If opening locally, some browsers may restrict file access; use a simple local server if needed.

## Troubleshooting
- Audio does not play on load: click the Play button once.
- Images do not show: check file paths and case-sensitive filenames.
