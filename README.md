# NADIR

An ASCII roguelike in one HTML file. No install, no build, no dependencies, no network.

Current version: **v0.5** (share levels by code).

## Play

**From the site** (GitHub Pages): see "Host it" below, then open your site's address.

**Locally:** double-click `index.html`. It opens in any modern browser.

**Locally, served** (some browsers limit saving on `file://`):

    cd Nadir
    python3 -m http.server 8000     # then open http://localhost:8000

Works on desktop and phone. Saves (your depth editor dungeon) live in the browser.

## Host it (GitHub Pages, free)

1. Put this folder's files in a GitHub repo (`index.html` at the repo root).
2. Repo > Settings > Pages > Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. The game is live at `https://<user>.github.io/<repo>/` within a minute or two.

Any static host works the same way (Netlify, Cloudflare Pages, your own server): upload `index.html`.

## Custom domain

1. Buy a domain from any registrar (this is the part only you can do).
2. Repo > Settings > Pages > Custom domain: enter it (for example `nadir.example`). GitHub creates a `CNAME` file in the repo for you. Tick "Enforce HTTPS" once the certificate is ready.
3. At the registrar's DNS settings:
   - subdomain (`play.example.com`): a `CNAME` record pointing to `<user>.github.io`
   - apex (`example.com`): four `A` records pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
4. DNS can take from minutes to a few hours.

## Sharing levels

- **CODE tab** (community screen): paste a level code and press PLAY, or press MY CODE then COPY to send yours. Works everywhere, including this offline/hosted copy.
- **COMMUNITY / MINE / MOD** (shared level browser with moderation) need the Claude app version, which provides the shared database. In this copy those tabs say so and the CODE tab is the way to share.

## Files

- `index.html` the game (open this one)
- `versions/Nadir_v0.5.html` the same file, kept by version number. Put older versions here as `Nadir_vX.Y.html`.

## Modding

The top of the script holds the tuning tables: `MOBS` (mob stats), `mobPool` (what spawns where), `SFX` (sounds), `GEAR`, `ICON`, `PICKUP` (items), `DOOR_COUNT` and `LOCK_RATE`. Comments in the code explain each one.
