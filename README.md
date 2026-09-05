# Cochela — portfolio

A single-page site (`index.html`) with no dependencies besides two Google Fonts. No build step, no server, nothing to install: just open the file, or upload it to any host.

## How to open it

- **Locally:** double-click `index.html` and it opens in your browser.
- **Publish for free:** upload the folder to [GitHub Pages](https://pages.github.com/), [Netlify](https://www.netlify.com/), or [Vercel](https://vercel.com/) — drag the folder in, no configuration needed.

## What's already in place

- The name **Cochela** in the nav and hero.
- A 2x2 grid with 4 video slots (collapses to 1 column on mobile).
- A contact section with Discord, Email, and Twitter already filled in, each with a copy button.
- Orange-and-black palette, no colorful gradients, no glitch effects, no controller icons — just the wordmark, one blurred glow (the only blur on the whole site), and orange borders on hover.
- A light site: no external libraries, no continuous animation, no heavy autoplaying video — just HTML, CSS, and a bit of JavaScript for the copy button.

## What to swap before publishing

### 1. The 4 videos ("Recent cuts" section)

Each card is a block like this inside `index.html`:

```html
<a class="card" href="#" target="_blank" rel="noopener">
  <div class="thumb bg-1">
    <span class="thumb-tag mono">clip 01</span>
    ...
  </div>
  <div class="card-body">
    <h3>Valorant — 1v3 clutch</h3>
    <p>Decisive round cut on the beat, no fat before the final kill.</p>
    <span class="watch mono">watch on youtube</span>
  </div>
</a>
```

For each of the 4 cards, replace:
- `href="#"` with the real video link (YouTube, TikTok, Twitch, wherever it's published).
- The text inside `<h3>` with the real title/game.
- The text inside `<p>` with the real description.

The backgrounds (`bg-1`, `bg-2`, `bg-3`, `bg-4`) are just gradients so the thumbnail isn't empty — if you want a real cover image instead, replace `<div class="thumb bg-1">` with one that has `style="background-image: url('your-image.jpg')"`.

### 2. Contacts

Already filled in with the details you gave:
- Discord: `801895540995653692`
- Email: `pedrooluuuuucas2020@gmail.com`
- Twitter: `@ETanjerina`

If any of these change, search the file for the old value and update it everywhere it appears (both the visible text and the `data-copy` or `href` attribute).

### 3. Colors

Everything lives at the top of the file, inside `:root`:

```css
--bg: #0d0c0b;        /* background black */
--orange: #ff6a1a;     /* main orange */
--orange-deep: #c7440a; /* darker orange */
--text: #f3eee7;       /* light text */
--text-muted: #a79c8e; /* secondary text */
```

Changing these values updates the color everywhere at once.

## Why it looks this way

Instead of the generic "gamer" look (neon green, controller icons, glitch text), the visual language comes from editing itself: viewfinder-style corner frames on the thumbnails, a "clip 01/02/03/04" tag like a timeline marker, and a monospace font for technical labels — the same kind of font used for video timecodes. The only blur effect is the orange glow behind the name; everything else is flat, with no generic drop shadow or default rounded card, so it loads fast and doesn't lag on any device.
