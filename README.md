# Encore

A personal music guide for your phone. Four tabs:

- **Ask**: questions in plain language ("a Bob Dylan song connected to the Vietnam war"), answered by Claude, with every song playable.
- **World**: what people are listening to, globally, by genre and by country, with what is new since your last visit.
- **Mine**: your most played songs and artists on Spotify, grouped by genre, plus real play counts that build up over time.
- **Search**: songs and playlists on Spotify.

Tap any song to play it in Spotify. The three-dot button adds it to a playlist, explains it, or opens it in Spotify.

Encore is a single web page with no server. All keys and history stay on your phone.

## 1. Put it on GitHub Pages

1. Create a new **public** repository called `encore` on GitHub.
2. Upload every file in this folder to the repository root: `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `README.md`.
3. In the repository, open Settings, then Pages. Under "Build and deployment", choose "Deploy from a branch", branch `main`, folder `/ (root)`, and save.
4. After a minute the app is live at `https://ldenicola.github.io/encore/`.

The World tab works straight away, with nothing else set up.

## 2. Connect Spotify

1. Go to https://developer.spotify.com/dashboard and sign in with your Premium account.
2. Create an app. For "Which API/SDKs are you planning to use?", choose **Web API**.
3. Under Redirect URIs, add exactly: `https://ldenicola.github.io/encore/` (the app's Settings screen shows this address with a Copy button).
4. Copy the **Client ID**.
5. In Encore, open Settings (top right), paste the Client ID, and press "Save and connect Spotify".

Spotify signs you out of personal apps after six months. When that happens, press connect again.

## 3. Add the two keys

- **Last.fm** (charts by country): create a free API account at https://www.last.fm/api/account/create and paste the "API key" into Settings. Any name and description will do; leave the callback URL empty.
- **Anthropic** (the Ask tab): paste an API key from https://console.anthropic.com into Settings. Each question costs roughly a cent.

## 4. Install it on your phone

Open `https://ldenicola.github.io/encore/` in Chrome on your phone, open the menu, and choose "Add to Home screen", then "Install".

## Good to know

- **Charts are not Spotify's.** Spotify does not share chart data with personal apps. Global and genre charts come from Deezer, and country charts come from Last.fm. Every song still plays in Spotify.
- **"New" and the up and down arrows** compare a chart with the last day you opened it, so they appear from your second day of use.
- **Counted** (in Mine) saves your last 50 plays each time you open the app. If you play more than 50 songs between opens, the extra ones are missed.
- **Playback** uses whichever Spotify device is active. If none is, Encore opens the song in the Spotify app.
- **Genres** come from each song's main artist, first from Spotify and then from Last.fm when Spotify has none.
- **Updating the app**: replace `index.html` in the repository. The phone picks up the new version the next time it opens online.
