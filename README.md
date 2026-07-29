# EverythingBox — Add-ons

A community registry of add-ons (media sources) for **EverythingBox**. Browse and install these from
inside the app: **Settings → Browse Add-ons…**

## Use it in the app
This repo is the **default** registry in the app. Its raw `index.json` URL is:

```
https://raw.githubusercontent.com/cubman3134/everythingbox-addons/main/index.json
```

You can also add your own independent registries in **Browse Add-ons…** via **Add registry…**.

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
plus a `main.js` exposing `getCatalog`, `getDetail`, `getMeta`, `search`. See `addons/com.everythingbox.podcasts/`
for a complete, keyless example — including a custom media type with its own colour + bundled SVG icon.
