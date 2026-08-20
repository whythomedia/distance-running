# Race Morning

A one-page guide to eating before an early cross country race. Built for a high school runner whose bus leaves at 5 AM for an 8:30 gun.

No framework, no build step. One HTML file with inline CSS and vanilla JS.

Live at <https://whythomedia.github.io/distance-running/>.

## What's here

```
index.html                    the page (all content, styles, and JS)
site.webmanifest              name, colors, and app icons
.nojekyll                     serve the files as-is on GitHub Pages
assets/
  og-image.png                1200x630 social preview
  favicon.svg                 battery icon (default)
  favicon.ico
  apple-touch-icon.png        180x180
  icon-192.png
  icon-512.png
  icon-shoe-option/           alternate running shoe icon set, same filenames
```

## Deploy

Static hosting, anywhere. It's already wired for GitHub Pages: push to `main` and enable Pages
(Settings → Pages → deploy from branch `main`, folder `/`).

For any other host — `npx vercel`, Netlify Drop, whatever — the only thing to change is the
absolute URL in the social tags. Icons and the manifest use relative paths and follow the files.

```
sed -i '' 's|https://whythomedia.github.io/distance-running|https://your-url.example|g' index.html
```

Those tags have to be absolute: crawlers fetch `og:image` without a page to resolve it against,
which is why a relative path there is the usual reason a link preview comes up blank.

## Using the shoe icon

The alternate set uses the same filenames as the default one, so swapping is a copy:

```
cp assets/icon-shoe-option/* assets/
```

## Editing content

Everything is in `index.html`.

- Schedule and swaps are in `<section id="plan">`
- Tappable term definitions are in the `TERMS` object at the bottom of the file. To add one, add an entry there and wrap the word in `<button class="t" data-term="key">`
- Colors are CSS variables at the top of `<style>`

Fonts load from Google Fonts (Barlow Condensed, Source Sans 3).
