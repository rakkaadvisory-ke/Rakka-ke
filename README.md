# Rakka Advisory (GitHub Pages)

This folder contains an updated static website ready for GitHub Pages, plus a simple API option for login.

## What's updated
- The login now calls an external API URL (Cloudflare Worker) instead of `/api/login` (GitHub Pages can't host backend routes).
- Redirect after login uses a **relative path**: `client/dashboard.html` (works on GitHub Pages).
- Added placeholder dashboard page: `client/dashboard.html`.

## 1) Deploy the website (GitHub Pages)
Upload the contents of this folder to your GitHub repo (root). Ensure `index.html` is in the root.

## 2) Deploy the login API (Cloudflare Worker)
1. Create a Cloudflare account → Workers & Pages → Create Worker
2. Paste `cloudflare-worker.js`
3. Deploy, copy your Worker URL (example: https://rakka-login.yourname.workers.dev)

## 3) Connect the website to the API
Open `index.html` and set:

```js
const API_BASE = "https://YOUR-WORKER-URL.workers.dev";
```

## Demo logins (for testing)
- client@rakkaadvisory.com / 123456
- admin@rakkaadvisory.com / admin123

## Next upgrade (real accounts)
We can replace demo users with Supabase Auth or a database (Cloudflare D1 / KV).
