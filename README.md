# My Media Vault — Add-ons

A community registry of add-ons (media sources) for **My Media Vault**. Browse and install these from
inside the app: **Settings → Browse Add-ons…**

## Use it in the app
Paste this repo's raw `index.json` URL into the "Registry" box in **Browse Add-ons…**:

```
https://raw.githubusercontent.com/<your-user>/mymediavault-addons/main/index.json
```

## Contribute an add-on
1. Put your add-on under `addons/<your.addon.id>/` (`manifest.json`, `main.js`, plus any icons/assets).
2. Add an entry to `index.json` listing every file to download:

   ```json
   {
     "id": "your.addon.id",
     "name": "Your Add-on",
     "author": "you",
     "description": "One line about what it provides.",
     "files": [
       "addons/your.addon.id/manifest.json",
       "addons/your.addon.id/main.js"
     ]
   }
   ```
   Each file is downloaded into the app's `addons/<id>/` folder.
3. Open a pull request.

### Add-on format
An add-on is a `manifest.json` (id, name, type "media-source", catalogs, optional `mediaTypes`/`accent`)
plus a `main.js` exposing `getCatalog`, `getDetail`, `getMeta`, `search`. See `addons/com.goliath.podcasts/`
for a complete, keyless example — including a custom media type with its own colour + bundled SVG icon.
