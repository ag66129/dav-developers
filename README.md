# dav-developers

Public static pages for **Dav Developers** (e.g. **AllInOne Service** privacy policy).

## Netlify deploy (ZIP drag & drop)

1. On your computer, open this repo’s **`docs`** folder.
2. Select **everything inside `docs`** (`index.html`, `allinone-privacy-policy.html`) → **Compress** to a `.zip`.  
   - Do **not** put an extra parent folder with nothing inside except `docs` unless you know what you’re doing — the zip’s **root** should be the files that must appear at `https://yoursite.netlify.app/`.
3. [Netlify](https://app.netlify.com/) → **Sites** → **Add new site** → **Deploy manually** (or **Import** → look for manual / drag-and-drop).
4. Drag the **zip** (or the unzipped folder) onto the deploy zone.
5. Open the live URL: **`/`** should open the policy (via `index.html` redirect), or open **`/allinone-privacy-policy.html`** directly.

**Google Play:** use  
`https://<your-site>.netlify.app/allinone-privacy-policy.html`  
(or the site root `https://<your-site>.netlify.app/` after upload).

---

## Netlify deploy (GitHub)

1. Push this repo to GitHub (if it is not already).
2. Sign in at [Netlify](https://app.netlify.com/) → **Add new site** → **Import an existing project**.
3. **Connect to Git provider** → pick this repository.
4. Leave **build settings** as Netlify reads from `netlify.toml`:
   - **Base directory:** *(leave empty)*
   - **Build command:** *(empty — not required)*
   - **Publish directory:** `docs` *(already set via `netlify.toml`)*  
   If the UI still asks, set **Publish directory** to `docs` manually.
5. Click **Deploy site**.
6. After deploy, open the site URL Netlify assigns (e.g. `https://random-name-123.netlify.app/`).
   - `/` redirects to **`/allinone-privacy-policy.html`** (301).
7. **Optional:** **Site configuration → Domain management** → **Options → Edit site name** to a readable subdomain (e.g. `dav-developers-privacy`).

### Google Play Console

Use the **HTTPS** URL that shows the policy in the browser, for example:

- `https://YOUR-SUBDOMAIN.netlify.app/allinone-privacy-policy.html`  
  or after the redirect is live, the root:  
- `https://YOUR-SUBDOMAIN.netlify.app/`

Use the same URL in the app if you add an in-app “Privacy policy” link.

## Files

| Path | Purpose |
|------|--------|
| `docs/index.html` | Root `/` → redirects to privacy (works for ZIP manual deploy) |
| `docs/allinone-privacy-policy.html` | Privacy policy page |
| `netlify.toml` | Git deploy: publish `docs` + root redirect |
