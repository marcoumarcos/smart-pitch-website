# smart-pitch website

Live site: https://marcoumarcos.github.io/smart-pitch-website/
Greek version directly: https://marcoumarcos.github.io/smart-pitch-website/?lang=el

| File | What it contains |
|---|---|
| `index.html` | The whole website: layout, colours and all **English** text |
| `i18n.js` | The **Greek** translations and the EN / ΕΛ language switch |
| `README.md` | This guide |

---

## Before you start: how to edit a file on GitHub

1. Open the repository and click the file (`index.html` or `i18n.js`).
2. Click the **pencil icon** (Edit this file) at the top right of the file.
3. Click inside the editor and press **Ctrl+F** to find the text you want to change (the search words are listed below).
4. Make your change, then click **Commit changes…** → keep **Commit directly to the main branch** → **Commit changes**.
5. Wait 1–2 minutes, then open the live site and press **Ctrl+F5** to see the update.

### Rules for the two languages

- The **English** text is in `index.html`. The **Greek** text is in `i18n.js`, one line per phrase:
  ```
  "English text exactly as on the site": "Το ελληνικό κείμενο",
  ```
- If you change an English sentence in `index.html`, also change the **left side** of its line in `i18n.js` so it matches **exactly** (same words, same punctuation). Otherwise that sentence will stay in English on the Greek version.
- To add a Greek translation for new text, add a new line in the same format anywhere inside the list in `i18n.js`.
- Keep the quotes `"` and the comma `,` at the end of each line in `i18n.js`.
- In `index.html` the `&` sign is written as `&amp;`. In `i18n.js` write a normal `&`.
- **After every change to `i18n.js`**, open `index.html`, search for `i18n.js?v=` and increase the number by one (for example `v=5` → `v=6`). This makes visitors' browsers load the new translations immediately.

### If something goes wrong

Open the file, click **History**, open the last version that worked, click the **…** menu → **View file**, copy everything, and paste it back into the editor as a new commit.

---

## Section 1: Pending items (placeholders still to fill in)

### 1. Product video (YouTube)
- In `index.html` search for `data-youtube-id="YOUR_VIDEO_ID"` (change only this one; leave other mentions of `YOUR_VIDEO_ID` as they are).
- Replace `YOUR_VIDEO_ID` there with the ID from your YouTube link. For `https://www.youtube.com/watch?v=abc123XYZ` the ID is `abc123XYZ`.
- The video appears automatically. No Greek change needed.

### 2. Contact form → your email
- Go to https://web3forms.com, enter the email address that should receive messages, and copy the **Access Key** they email you.
- In `index.html` search for `value="YOUR_ACCESS_KEY"` and replace `YOUR_ACCESS_KEY` there with that key (leave other mentions of `YOUR_ACCESS_KEY` as they are).
- Test it: send a message from the live site and check your inbox (and spam folder).
- Optional: the email subject line is `New enquiry from the smart-pitch website` (search for it to change it).

### 3. Venues map
- Go to https://www.google.com/mymaps → **Create a new map** → search for each venue and click **Add to map**.
- Click **Share** → turn on **Anyone with this link can view** → copy the link. The link contains `mid=XXXXXXXX`.
- In `index.html` search for `data-mymaps-id="YOUR_MAP_ID"` and replace `YOUR_MAP_ID` there with the `XXXXXXXX` part (leave other mentions of `YOUR_MAP_ID` as they are).
- After that, venues you add in My Maps appear on the website automatically.

**Venue list next to the map:**
- Search for `<strong>Venue name</strong><span>City, Country</span>` and type the real venue name and city.
- To add a venue, copy one whole line that starts with `<li><div class="pin">` and paste it below. To remove one, delete its line.
- Greek: in `i18n.js` add lines such as `"Arena Sports Club": "Arena Sports Club",` and `"Athens, Greece": "Αθήνα, Ελλάδα",`.

### 4. Team photos
- Use portrait photos (about 4:5 shape), preferably under 500 KB each.
- On the repository's main page click **Add file → Upload files**, drag the photos in, and click **Commit changes**. Use simple names without spaces, e.g. `konstantinos.jpg`, `christos.jpg`, `markos.jpg` (names are case-sensitive).
- In `index.html` search for `<div class="photo">Photo 1</div>` and replace it with:
  ```html
  <div class="photo"><img src="konstantinos.jpg" alt="Konstantinos Lambrou"></div>
  ```
  Do the same for `Photo 2` and `Photo 3`.

### 5. Testimonials
- In `index.html` search for `Client name`. Each testimonial is a block that starts with `<div class="slide"` and contains:
  - the quote inside `<blockquote>…</blockquote>`
  - the initials inside `<div class="avatar">AB</div>`
  - the person's name inside `<strong>…</strong>`
  - their role and venue inside `<span>…</span>`
- To add a testimonial, copy a whole `<div class="slide" …> … </div>` block and paste it after the last one (the dots under the slider update themselves). To remove one, delete its whole block.
- Greek: in `i18n.js` update or add a line for each quote and each role/venue (search for `// Testimonials`).

### 6. Company details (Contact section)
In `index.html` search for and replace:
- `Company legal name · VAT 000000000` → legal name and VAT number
- `Street address 00` and `City, Postcode, Country` → address
- `info@smart-pitch.com` → your email (it appears **twice** on the same line: inside `mailto:` and as the visible text; change both)
- `+300000000000` (the phone link) and `+30 000 000 0000` (the visible number)

Greek: update the matching lines under `// Contact` in `i18n.js` (for example the `ΑΦΜ` line and the address lines).

### 7. Statistics (About section)
- Search for `00+` (venues equipped) and `00k` (matches recorded) and enter your real numbers. Numbers don't need translating.

### 8. Your own domain (when you buy one)
- Repository **Settings → Pages → Custom domain**, type your domain and click **Save**.
- At your domain provider, add the DNS records GitHub shows you, then tick **Enforce HTTPS** once it becomes available.

---

## Section 2: Editing existing content

Each item shows what to search for in `index.html` (English). Remember to update the matching Greek line in `i18n.js`.

| What | Search for in `index.html` | Notes |
|---|---|---|
| Browser tab title | `<title>` | Greek: first line in `i18n.js` |
| Google search description | `<meta name="description"` | Greek: second line in `i18n.js` |
| Menu items | `<nav id="nav">` | Change only the visible text. The part after `href="#…"` must stay as is |
| Small green line above the headline | `<span class="eyebrow">` | Each section has one |
| Main headline | `<h1>` | The part inside `<em>…</em>` is shown in green |
| Intro paragraph | `<p class="lead">` | Each section has one under its title |
| Offering cards (4) | `<div class="feature">` | Title in `<h3>`, text in `<p>`. To remove a card delete the whole `<div class="feature"> … </div>` block. Leave the `<svg …>` icon code untouched |
| Section titles | `<h2>` | |
| Team members | `<div class="member">` | Name in `<h3>`, role in `<p>` |
| About us paragraphs | `<div class="about-text">` | Two paragraphs, each in `<p>` |
| Statistics labels | `<div class="stat">` | Number in `<strong>`, label in `<span>` |
| Testimonials | `<div class="slide"` | See Pending item 5 |
| Venues section | `id="venues"` | See Pending item 3 |
| Contact details | `<ul class="info-list">` | See Pending item 6 |
| Contact form labels and button | `<form id="contact-form"` | Labels are the text before each input, e.g. `Venue / company` |
| Contact form messages (sending, thanks, error) | `status.textContent` | Text is inside `t('…')`. Greek versions are at the end of the `// Contact` part of `i18n.js` |
| Footer | `<footer>` | Copyright text and "Back to top" link |

### Look and feel
- **Colours:** at the top of `index.html`, under `:root {`:
  `--pitch` (dark green background), `--pitch-deep` (darker green), `--turf` (green accents), `--lime` (bright highlight), `--chalk` (light background), `--ink` (text colour). Replace the colour code, e.g. `#c6f432`.
- **Fonts:** search for `fonts.googleapis.com` (font loading) and `font-family` (where they are used). Any new font must support Greek letters.
- **Map starting area (before your My Maps map is added):** search for `q=Greece&amp;z=6`. Change `Greece` to another place, and `z=6` for the zoom (higher number = closer).
