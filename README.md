# dav-developers

Public static pages for **Dav Developers** (e.g. **AllInOne Service** privacy policy).

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
| `docs/allinone-privacy-policy.html` | Privacy policy page |
| `netlify.toml` | Publish folder + root redirect |
