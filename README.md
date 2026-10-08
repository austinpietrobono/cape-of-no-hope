# Cape of No Hope

Invite page for the Cape of No Hope Halloween hunt, 31 October.

A single static page with no build step. Guests watch the intro, answer the summons, and get a postcard to post in the WhatsApp group.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole page, with fonts, stamps, music and logic built in |
| `intro.mp4` | Intro video |
| `poster.jpg` | First frame, shown while the video loads |
| `logo-black-bg.svg`, `logo-red-bg.svg` | Logos |
| `og-image.jpg` | Preview image for WhatsApp and other link previews |
| `favicon.png`, `apple-touch-icon.png` | Browser tab and home-screen icons |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Put it live on GitHub Pages

1. **Create a repo.** On github.com click **New repository** and name it, for example `cape-of-no-hope`. Make it **Public**, because Pages on a free account needs a public repo.
2. **Upload the files.** In the new repo click **uploading an existing file**. Drag in everything in this folder, including `.nojekyll`, then click **Commit changes**.
   - Hidden files: on a Mac, press Cmd+Shift+. in Finder to show `.nojekyll`.
   - If it still won't upload, skip it. The site works without it.
3. **Turn on Pages.** Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**, then click **Save**.
4. **Wait a minute or two.** Your link shows at the top of the Pages screen. It looks like:
   `https://YOUR-USERNAME.github.io/cape-of-no-hope/`

## Fix the WhatsApp preview image (one line)

WhatsApp needs the full web address of the preview image. When you know your link:

1. In the repo, open `index.html` and click the pencil icon to edit.
2. Find this line, near the top:
   ```html
   <meta property="og:image" content="__SITE_URL__/og-image.jpg">
   ```
3. Replace `__SITE_URL__` with your link, without a trailing slash:
   ```html
   <meta property="og:image" content="https://YOUR-USERNAME.github.io/cape-of-no-hope/og-image.jpg">
   ```
4. Click **Commit changes**.

WhatsApp caches previews. If you already pasted the link somewhere, the old preview may stick for a while. A fresh chat usually shows the new one.

## Notes

- **Sound** starts after the guest taps SUMMON, because browsers block audio until someone taps.
- **Copy postcard** works in Chrome and Safari.
- **WhatsApp's built-in browser** may block copy and save. The page then tells guests to press and hold the postcard to save it. Opening the link in Safari or Chrome avoids this.
- **Text changes:** to edit titles, notes or wording, search `index.html` for `TITLES`, `ARRIVALS` or `REGRETS`.
