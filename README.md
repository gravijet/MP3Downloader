# MP3Downloader

Browser interface for audio and playlist downloads. A Python API runs yt-dlp, spotDL and ffmpeg as background jobs. Individual tracks are returned as media files; playlists and albums are ZIP archives.

Spotify supplies metadata; audio is matched on YouTube Music, so the recording may differ from the requested release. Downloads can fail when a provider restricts access.

## Development

```sh
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/python -m unittest discover -s tests -v
node --check app/static/app.js
```

Requires ffmpeg. Set `YTDLWEB_DATA_DIR` to a writable directory and configure authentication through environment variables. Start the API with `.venv/bin/uvicorn app.main:app`. Browser sessions require HTTPS because their cookies use the `Secure` flag.
