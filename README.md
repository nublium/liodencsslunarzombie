# LunarZombie Den — Editing Guide

Welcome! This guide will help you customize your den layout after you've installed it. Don't worry if you're new to HTML — the instructions below are written for beginners, and you'll only need to edit a few simple text sections.

---

## What You've Received

You have two main files:

1. **lunarzombie-den.html** — This is the HTML file. It contains the structure and all the text that appears on your den page (titles, descriptions, player info, goals, etc.).

2. **lunarzombie-den.css** — This is the CSS file. It controls all the colors, fonts, animations, and styling. You probably **won't need to edit this** unless you want to change colors or do advanced customization.

The CSS file lives on GitHub and is linked to your HTML automatically, so you don't need to download it separately.

---

## Installation: First Time Setup

When you receive your den layout, here's how to install it on Lioden:

### Step 1: Copy the HTML
Open the `lunarzombie-den.html` file in a text editor (Notepad, VS Code, or any plain text editor will work).

Select **all the content** inside the file (Ctrl+A), then copy it (Ctrl+C).

### Step 2: Paste into Lioden
Go to your Lioden territory settings page and find the text box labeled **"Territory description"** or **"Custom HTML"**.

Clear any existing content, then paste the HTML code (Ctrl+V).

### Step 3: Save and Check
Click "Save" on Lioden. Then visit your den page to see it live!

The styling should load automatically from GitHub. If something looks broken, make sure you're using the exact HTML file — don't change the link tag at the top.

---

## What You Can Edit

Below are all the sections you can safely customize. Look for the text between the `<!-- -->` markers and change it to match your information.

### 1. **Den Title**

Your den's title comes from Lioden's own page heading at the top — whatever you set as your territory name on Lioden is what will appear. There is no title line in this HTML to edit.

### 2. **Subtitle**

Find this line:
```html
<div class="lz-subtitle">Blooming Spring</div>
```

Change `Blooming Spring` to describe your den's season or theme.

### 3. **Tagline**

Find this line:
```html
<div class="lz-tagline">— under the cherry blossoms, time stands still —</div>
```

Change the text inside the dashes to your favorite quote or motto. The dashes (—) are optional.

### 4. **King Image**

Find this section:
```html
<a href="https://www.lioden.com/lion.php?mid=587720">
  <span class="lz-king-frame">
    <img class="lz-king-img" src="https://nublium.github.io/liodencsslunarzombie/placeholder-king-avatar.svg" alt="The Blossom that Stained Snow">
```

**To change the king/queen image:**
- Replace the number `587720` in the first link with your lion's Lioden ID (find it in your lion's profile URL).
- Replace the `src=` URL with a link to your own image. You can host images on Imgur, Dropbox, or any image host, and paste the direct image URL here.
- Change the `alt=` text to your lion's name (this is for accessibility and displays if the image fails).

**Important:** The king image should be roughly square. If your image is very wide or tall, it may get cropped inside the circular frame.

**The other placeholder images** (the cave and beetle-mound covers) live in the CSS file instead, grouped together under the `/* CAVE & MOUND COVERS */` heading. Each one is a single line like this:

```css
.cave-grid {
background-image: url('https://nublium.github.io/liodencsslunarzombie/placeholder-cave.svg') !important; }
```

To use your own artwork, swap the link inside `url(' ')` and leave the rest of the line alone. The covers display at 260x140, so images around that shape look best. The blocks you can swap are: the general cave cover, the beetle mound cover, unsorted lions, pride overview, and the nesting bundle.

**The image behind your featured lion** is one more line in the CSS, a little further down under the heading `/* the image behind your featured lion */`:

```css
img[src*="cave/default"] {
content: url('https://nublium.github.io/liodencsslunarzombie/placeholder-cave.svg') !important;}
```

It works the same way — swap the link inside `url(' ')` for a link to your own image and leave the rest of the line alone.

**Don't want to touch the CSS at all?** You don't have to. Just send me the picture you'd like and tell me where it goes — "behind my featured lion", "the cave covers", and so on. PM nub (#166079 on Lioden), or send the file however we've been talking. I'll host it and put it into the CSS for you.

Because your HTML links to the CSS file on GitHub, the new picture shows up on your den on its own — you don't need to re-paste your code or change anything on your side. PNG or JPG both work. Around 260x140 suits the cave and mound covers, and anything roughly that shape looks good behind your featured lion. Please only send art you own or have permission to use.

### 5. **Player Tags (The Colored Chips)**

Find this section:
```html
<div class="lz-tags-row">
  <span class="lz-tag-bright">LunarZombie · #587720</span>
  <span class="lz-tag-petal">❀ baker by trade ❀</span>
  <span class="lz-tag-sage">7h ahead of lioden time</span>
  <span class="lz-tag">side · <a href="https://www.lioden.com/territory.php?id=589548">#589548</a></span>
</div>
```

You can edit:
- **First chip:** Replace `LunarZombie · #587720` with your username and Lioden ID.
- **Second chip:** Replace `❀ baker by trade ❀` with your occupation or a short description. (The ❀ symbols are optional.)
- **Third chip:** Replace `7h ahead of lioden time` with your timezone.
- **Fourth chip:** Replace `#589548` with the ID of your side account, or delete this entire `<span>` line if you don't have a side account.

### 6. **"Player Information" Box (Left Side)**

Find the section starting with:
```html
<div class="lz-section-label">— Part the First —</div>
```

Then find the large box with `<span class="lz-sym">❀</span> Player Information <span class="lz-sym">❀</span>`.

**You can edit:**
- The intro text: "My name is..." — change `<span class="lz-text-bright">Amy-Louise</span>` to your name.
- Any of the **info rows** below that (Pronouns, Age, Lioden time, Trade, Side account). For example:
  ```html
  <div class="lz-info-row">
    <span class="lz-info-label">Pronouns</span>
    <span class="lz-info-value">she / her</span>
  </div>
  ```
  Change `she / her` to your pronouns. You can add or remove rows as needed.
- The companion names at the bottom: Change `Luna · Rin · Ella` to your actual companions' names.

### 7. **"Goals" Box (Right Side) — Checklist + Pill Links**

Find the box with `<span class="lz-sym">✿</span> Goals <span class="lz-sym">✿</span>`.

**The intro text:** "Small dreams I'm tending..." — change to your own intro.

**The checklist:**
```html
<ul>
  <li class="lz-check-done"><span class="lz-check-box"></span><span class="lz-check-text"><span class="lz-text-bright">Turn the den into a soft pink theme</span></span></li>
  <li><span class="lz-check-box"></span><span class="lz-check-text">Breed a <span class="lz-text-petal">Cherry Blossom Piebald</span></span></li>
  <li><span class="lz-check-box"></span><span class="lz-check-text">Obtain a Leopon</span></li>
  ...
</ul>
```

How the checklist works:

Every goal is one `<li>` line, and each line is made of three parts that always come in this order:

1. The `<li>` itself — this is the row.
2. `<span class="lz-check-box"></span>` — this draws the little pink box. It stays empty; don't type anything inside it.
3. `<span class="lz-check-text">...</span>` — this holds your goal. Type your wording in here.

To **add** a goal, copy a whole `<li>...</li>` line, paste it on a new line, and change the words inside `lz-check-text`. To **remove** a goal, delete the whole `<li>...</li>` line.

**How to mark a goal as done**

A goal starts off unticked. To tick it off you add one thing to that goal's `<li>` — nothing else on the line changes.

Not done yet:
```html
<li><span class="lz-check-box"></span><span class="lz-check-text">Obtain a Tigon</span></li>
```

Done — the only difference is `class="lz-check-done"` added right after `<li`:
```html
<li class="lz-check-done"><span class="lz-check-box"></span><span class="lz-check-text">Obtain a Tigon</span></li>
```

Save the page, and that row now shows a filled pink box with a ✓ in it, and the text gets a soft line through it.

Three things to watch out for:
- Type it exactly as `class="lz-check-done"` — the space after `<li`, the `=`, and both quote marks all have to be there.
- It goes on the `<li>`, **not** on the spans inside it. Putting it on `lz-check-box` or `lz-check-text` does nothing at all.
- To untick a goal later, just delete `class="lz-check-done"` from that line and leave everything else as it is.

**The banner links** (wishlist / trade thread / breeding plans) live below the checklist:
```html
<div class="lz-banner-row">
  <a href="#"><span class="lz-banner-fold lz-banner-fold--lhs"></span><span class="lz-banner-glyph">❀</span><span>wishlist</span><span class="lz-banner-fold lz-banner-fold--rhs"></span></a>
  ...
</div>
```

- Replace the `#` in each `href="#"` with the real URL.
- Change the label in the plain `<span>` to your own (e.g. "art shop", "sales thread").
- Keep the `lz-banner-glyph` and `lz-banner-fold` spans — those are the blossom icon and the little ribbon ends.
- Add or remove whole `<a>` blocks if you want more or fewer banners.
- Don't put a `class` on the `<a>` itself — Lioden strips it. The styling comes from the `lz-banner-row` wrapper.

### 8. **Quote/Motto Box**

Find the section with `<span class="lz-sym">❦</span> Quote <span class="lz-sym">❦</span>`.

**You can edit:**
```html
<div class="lz-pullquote">
  <span class="lz-dropcap">U</span>nder the Cherry Blossom Tree, I find sanctuary...
  <span class="lz-attrib">— Amy-Louise · The Blossom that Stained Snow —</span>
</div>
```

- Change the main quote text (starting after the first `<span>` and before the `<span class="lz-attrib">`).
- The first letter (the big `U`) will be styled as a **drop cap** (fancy oversized first letter). If your quote doesn't start with U, replace it with your actual first letter.
- Change the attribution line to credit the quote to you, your lion, or whoever.

---

## Things You Should **NOT** Edit

These parts are important for the styling to work. If you change them, things might break:

- **The link tag at the very top:** `<link rel="stylesheet" href="...">` — This loads the CSS from GitHub.
- **All the `class=` attributes** — These tell the CSS which parts to style.
- **The template credit** — the CSS prints "css template by katie (#106445) & jester (#187561)" next to the breadcrumb. The template this layout is built on asks that it stays, so please leave it in.
- **The decorative `<span>` elements** with symbols (❀, ✿, ✦, etc.) — These are just decorations. You can remove them if you want a cleaner look, but don't change their text.
- **The king display ornaments** — the four `<span class="lz-king-flower ...">` spans are the cherry blossoms that circle the king portrait. Leave them as they are.
- **The section dividers** — `<div class="lz-section-branch">...</div>` is the decorative cherry-branch line between sections. You can change the `lz-section-label` text below it (e.g. "beneath the blossoms" → "into the spring"), but don't edit the branch itself.

---

## Common Mistakes to Avoid

**1. Breaking HTML tags by accident**

Always keep opening and closing tags together. For example:
```html
✅ CORRECT: <div class="lz-text-bright">Amy-Louise</div>
❌ WRONG:   <div class="lz-text-bright">Amy-Louise
```

If you see a red squiggly line in your text editor, it usually means you've broken a tag.

**2. Forgetting to save after editing**

After you paste new HTML into Lioden, always click "Save" to confirm your changes.

**3. Changing the CSS file**

Don't try to edit the CSS unless you know what you're doing. The CSS controls all the colors and animations, and one typo will break everything. If you want to change colors, ask the layout designer for help.

**4. Using special characters incorrectly**

If you have a character like `&` (ampersand) in your text, it needs to be written as `&amp;` in HTML. Same for `<` (use `&lt;`) and `>` (use `&gt;`). Quotes inside text can also cause problems — if you need to use a quote, use the fancy Unicode quote `"` and `"` instead of straight `"` if possible.

---

## Helpful Tips

- **Line breaks:** HTML automatically ignores extra spaces and line breaks in the source code. If you want a visual line break in your text, use `<br>` or put content in separate `<div>` tags.

- **Links:** To add a link, use this format:
  ```html
  <a href="https://example.com">Click here</a>
  ```
  Replace `https://example.com` with the actual URL, and `Click here` with your link text.

- **Testing:** After you save, wait a few seconds and refresh your den page (F5). If something looks wrong, you can copy the original HTML file again and start over.

- **Undo:** Lioden usually saves to your browser's history, so you can often undo changes. But to be safe, always keep a backup copy of the HTML before making big changes.

---

## About Lioden's HTML Sanitizer

Lioden runs code through a "sanitizer" that removes certain HTML elements for security reasons. This is why the layout uses only simple tags like `<div>`, `<span>`, `<img>`, and `<a>`. Tags like `<details>`, `<form>`, or `<script>` are automatically removed.

This shouldn't affect you as a user — just know that if you try to add advanced HTML, some of it might disappear when you save.

---

## Need Help?

If something breaks or you get stuck:

1. **Check for typos** — Make sure all `<` and `>` symbols are present and tags are spelled correctly.
2. **Compare to the original** — Open the original HTML file and find the section you're editing. Make sure your edits follow the same pattern.
3. **Ask the layout designer** — If you're not sure what to change, reach out to nub (#166079 on Lioden) for help.

---

## Quick Cheat Sheet

| What to change | Find this | Change this | Keep this |
|---|---|---|---|
| Den title | Lioden's own `<h1>` | Rename your den in settings | styled by the CSS |
| Subtitle | `<div class="lz-subtitle">` | Text inside | `<div>` tags |
| Tagline | `<div class="lz-tagline">` | Text inside | `<div>` tags |
| King image | `<img class="lz-king-img"` | `src=` URL | `class=` attribute |
| King link | `<a href="https://www.lioden.com...` | The URL | `<a>` tag |
| Username/tags | `<span class="lz-tag-...">` | Text inside | `class=` names |
| Player info text | `<div class="lz-text">` | Text inside | `<div>` tags |
| Goal item | `<li>` in the Goals `<ul>` | Text in `lz-check-text` | both inner spans |
| Mark goal done | `<li>` in the Goals `<ul>` | Add `class="lz-check-done"` | rest of the line |
| Banner label | plain `<span>` inside the `<a>` | Text inside | `href`, `lz-banner-glyph` |
| Banner URL | `<a href="#">` in `lz-banner-row` | The `#` | The `<a>` tag itself |
| Quote | `<div class="lz-pullquote">` | Quote text | `<span>` tags |
| Section label | `<div class="lz-section-label">` | Text inside | `lz-section-branch` above |

---

**Congratulations!** You now have everything you need to customize your den. Happy editing! ❀
