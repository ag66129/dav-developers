# dav-developers

Public static pages for **Dav Developers** (e.g. **AllInOne Service** privacy policy).

## Netlify deploy (ZIP drag & drop)

1. On your computer, open this repo’s **`docs`** folder.
2. **Easiest (recommended):** select **`index.html` only** → compress to `.zip` → upload to Netlify.  
   The live site **`/`** will show the full privacy policy (no redirect).
3. **Or** select both `index.html` and `allinone-privacy-policy.html` → zip → upload.  
   Then **`/allinone-privacy-policy.html`** also works.
4. **Do not** zip the whole repo unless you know Netlify’s folder layout: if the zip opens as `dav-developers/docs/...`, the site root may be wrong and you get **404** or a blank site. The files that must be at the **site root** are the HTML files (not buried inside an extra empty folder).

### If it still “does not work”

| Problem | Fix |
|--------|-----|
| **404** on `/` | Upload a zip whose **root** contains `index.html` (open the zip and check: you should see `index.html` immediately, not only a folder name). |
| **Page not found** | Netlify → **Deploys** → open latest deploy → check **Published files** list for `index.html`. |
| **Wrong / old page** | After upload, use **Deploys → Trigger deploy → Clear cache and deploy site** (or upload a new zip with a changed file). |
| **Play rejects URL** | Use **`https://yoursite.netlify.app/`** or **`https://yoursite.netlify.app/index.html`** — must be **https** and open in a normal browser tab. |

5. [Netlify](https://app.netlify.com/) → **Sites** → **Add new site** → **Deploy manually** → drag the **zip** (or folder).
6. Open the live URL and confirm the policy text appears.

**Google Play:** use  
`https://<your-site>.netlify.app/`  
or  
`https://<your-site>.netlify.app/allinone-privacy-policy.html`

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
