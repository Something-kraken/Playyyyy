# MY SOUNDTRACK
Node 20.6+ required.

## Setup
1. https://developer.spotify.com/dashboard → Create app. Tick "Web API".
2. Add Redirect URI exactly: `http://127.0.0.1:3000/callback` (Spotify no longer accepts `localhost`).
3. In the app's User Management, add your own Spotify account email while the app is in Development mode.
4. `cp .env.example .env` and paste Client ID + Client Secret.
5. `npm install && npm start`, then open **http://127.0.0.1:3000** (not localhost) and click Connect Spotify.

## Notes
- Tokens live only on the server (in-memory sessions, HttpOnly cookie). Secrets never reach the browser. For production: HTTPS, NODE_ENV=production, a real session store, and your real redirect URI.
- Optional hero photo: save it as `public/hero.jpg`.
- Playback controls (play/pause/next/shuffle/volume) need Spotify Premium and an active device; playlist embeds work for everyone.
- Spotify doesn't expose playlist creation dates, so sorting is Library order / Name / Track count.
- Spotify's Development-mode rules limit which playlists' tracks the API returns (generally ones you own or collaborate on). Other playlists still show with covers and the embed player.
- Moods are grouped from your playlist names and descriptions (Spotify's audio-features API is no longer available to new apps).
