# Race Morning

A one-page guide to eating before an early cross country race. Built for a high school runner whose bus leaves at 5 AM for an 8:30 gun.

No framework, no build step. One HTML file with inline CSS and vanilla JS.

## What's here

```
index.html          the page
og-image.png        1200x630 social preview
favicon.svg         battery icon (default)
favicon.ico
apple-touch-icon.png
icon-192.png
icon-512.png
head-snippet.html   meta tags to paste into <head>
icon-shoe-option/   alternate running shoe icon set
```

## Deploy

Static hosting, anywhere.

```
npx vercel
```

or drag the folder onto Netlify Drop, or push to GitHub and enable Pages.

After the first deploy, open `head-snippet.html`, replace `YOUR_URL` with the live URL, and paste the block into `<head>` in `index.html` so link previews work.

## Using the shoe icon

Move the files out of `icon-shoe-option/` to the root and drop the `shoe-` prefix. Filenames will then match the head snippet.

## Editing content

Everything is in `index.html`.

- Schedule and swaps are in `<section id="plan">`
- Tappable term definitions are in the `TERMS` object at the bottom of the file. To add one, add an entry there and wrap the word in `<button class="t" data-term="key">`
- Colors are CSS variables at the top of `<style>`

Fonts load from Google Fonts (Barlow Condensed, Source Sans 3).
