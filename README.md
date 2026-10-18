# Rasmitra: Every Season, a Rasmitra

A single-page static site (no build step). Everything lives in `index.html`; images are in `assets/`.

Pages (hash routes, all in one file):
- `#/` Home: brands, year calendar, every product with a detail view, the Ek Garam Wish gift section, where to buy
- `#/explore` Explore: wish experiences by occasion, search, likes, "Try it" and "Make it yours", most-used board, Winter Wall
- `#/create` Creators: build an experience (theme, game, cup, words, editable JSON code), publish to get a link and QR, reward tiers and a dashboard
- `#/w/<code>` a personalised wish (game, letter, free-cup code, Trio upsell)
- `#/t/<code>` a creator's experience, opened ready to personalise

## Deploy on Vercel
1. Create a GitHub repo and upload `index.html`, `vercel.json`, `README.md` and the `assets` folder (keep the folder name).
2. On vercel.com: Add New > Project > import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty. Deploy.

## Counting visits and wishes across all devices
Wishes and templates travel inside the link, so the site needs no server. Likes, the Winter Wall and creator counts are stored on each device. To count across everyone, point `API_URL` (top of the script) to any endpoint that accepts `POST {event, tid}`, for example a Vercel serverless function writing to Vercel KV or Supabase.
