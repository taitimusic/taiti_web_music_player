for_github contents

- taiti_web_music_player.html: main page
- music_files/placeholder.wav: dummy audio (replace with your own)
- image_files/placeholder.png: dummy image (replace with your own)

Author
- taitimusic (https://taitimusic.com)

How to replace media
- Edit PLAYLIST_DATA in taiti_web_music_player.html
- Set audioSrc to your audio file path (mp3/wav/ogg etc.)
- Set images to your image file path(s)

Local viewing note
- This page uses ES modules and external CDN files (three.js, es-module-shims, Google Fonts).
- Some browsers block these when opening the file directly (file://).
- Use a local web server (Apache, or: python3 -m http.server) for reliable viewing.
