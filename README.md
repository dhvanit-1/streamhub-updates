# streamhub-updates

Update files for **StreamHub**, a personal-use Android TV app. Only this update repository is public;
the app's code is private.

## Disclaimer

StreamHub hosts nothing, stores no media and holds no rights to any film, series or channel. It is
only a front end: it reads public catalogue data from TMDB and runs community plugins that look up
links on publicly available websites. Nothing in this repository is media. It is made for personal
use. If you use it, you do so **at your own risk**, and you are responsible for following the laws
where you live.

## Requirements

- **TV app:** an Android TV, Android 8.0 or newer.
- **Phone app:** an Android phone or tablet, Android 8.0 or newer (quality is picked to match the screen; no 4K).
- **PC app:** Windows 10/11 (x64 or ARM64) with Chrome or Edge installed.
- Your own free **TMDB API key** (themoviedb.org → Settings → API). StreamHub asks for it on first
  launch and keeps it on that TV only.

## Files

| File | What it is |
|---|---|
| `streamhub-tv.apk` | The TV app. TVs offer it as an update when it's newer than theirs. |
| `streamhub-mobile.apk` | The phone app (`com.streamhub.mobile`). Phones offer it as an update the same way. |
| `providers.json` + `providers.json.sig` | The plugin setup every TV and phone follows, and the current version of each app, signed. Apps ignore unsigned or changed files. |
| `plugins/` | Plugin files that aren't in any public repository (pinned by SHA-256 in the signed file). |

TVs check `providers.json` 15 seconds after StreamHub starts and every 6 hours. They add the listed
plugin repositories, install the listed plugins, keep every installed plugin on its newest version
from its own repository, and apply removals, switched-off providers and priority order when the
version number goes up. Plugins added by hand on a TV stay unless the list names them under `remove`.

## Credits

Film and series data from [TMDB](https://www.themoviedb.org) (this product uses the TMDB API but is
not endorsed or certified by TMDB). Plugin support built on [CloudStream](https://github.com/recloudstream/cloudstream)'s
plugin library; the plugins are made by their own authors and come from their own repositories.
Trailers through [NewPipe Extractor](https://github.com/TeamNewPipe/NewPipeExtractor); trailer fallback in
[SmartTube](https://github.com/yuliskov/SmartTube).
