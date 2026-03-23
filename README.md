# 🐄 Dairy Teaching Apps

A set of interactive HTML tools for teaching dairy cattle nutrition and reproduction, built for embedding in Moodle and other LMS platforms. This repo was built using Claude, following instructions inspired by my old, basic Shiny apps of simple calculators and tools for teaching.

These apps are built as self-contained HTML files — no server, no framework, no build step. Each one can be hosted on GitHub Pages and embedded directly into a Moodle course page via an `<iframe>`.


## Apps

### [Dairy Lactation Timeline Visualiser](./dairy_repro_timeline_app.html)

An interactive horizontal bar chart that lets students explore the components of the dairy cow reproductive cycle. Students adjust four parameters using sliders and see the timeline update in real time.

**Parameters:**
- Voluntary Waiting Period (days)
- Dry Period Length (days)
- Gestation Length (days)
- Days Open / calving-to-conception (days)

**Outputs shown:**
- Lactation length
- Breeding period length
- DIM to start breeding by
- Calving interval


## Embedding in Moodle

These apps are hosted via [GitHub Pages](https://pages.github.com/) and can be embedded into any Moodle page using an `<iframe>`.

### Step-by-step

1. **Add a Page or Label resource** to your Moodle course
2. In the text editor, switch to **HTML/source view** (the `</>` button in Atto, or "Source code" in TinyMCE)
3. Paste the iframe code below, replacing the URL with the specific app you want:

```html
<iframe
  src="https://YOUR-USERNAME.github.io/dairy-teaching-apps/dairy_repro_timeline_app.html"
  width="100%"
  height="580"
  style="border:none;"
  scrolling="no">
</iframe>
```

4. Save the resource — the app will render inline on the course page

### Notes on Moodle compatibility

- **Script blocking:** Moodle will block `<script>` tags if you try to paste raw HTML directly into a text editor. Using an iframe pointing to GitHub Pages bypasses this entirely.
- **Height:** A height of `580px` works well for the timeline app at typical screen widths. Adjust if content is cut off.
- **HTTPS:** GitHub Pages serves over HTTPS, which is required for Moodle to allow iframe embedding without mixed-content warnings.
- **Mobile:** The apps are responsive but work best on tablet/desktop width. Consider adding a note for students on mobile.



## Adding a New App

Each app is a single `.html` file — all CSS, JavaScript, and markup in one place. To add a new one:

1. Create your `.html` file locally (or in Claude/another tool)
2. Upload it to this repository via **Add file → Upload files** on GitHub
3. GitHub Pages will deploy it automatically within a minute or two
4. The URL will be: `https://YOUR-USERNAME.github.io/dairy-teaching-apps/your-file-name.html`
5. Embed it in Moodle using the iframe template above

### Design principles for new apps

- **Self-contained:** No external dependencies except CDN-hosted libraries (Chart.js, etc.)
- **No scrollbars:** Set `overflow: hidden` on `body` so the iframe fits cleanly
- **Neutral background:** Use `#faf8f4` or similar — avoids the jarring white box look in Moodle themes
- **Accessible labels:** Avoid relying on colour alone to convey information


## Licence

Feel free to adapt these tools for your own teaching. If you build something useful, a mention or link back is appreciated.
