# Walkthrough

`index.html` is a self-contained guided tour of every tool in Pillar — 53 screens
across 16 chapters, captured from the running app on the demo workspace in
`../demo-data.json`.

Open it by double-clicking. Nothing loads from the network: the screenshots are
embedded, so it works offline and can be emailed or shared as a single file.

It plays itself. <kbd>K</kbd> pauses and resumes, <kbd>←</kbd> and <kbd>→</kbd>
step through, and the chapter list at the bottom jumps straight to a tool.

## Regenerating it

The frames are captured by driving a real browser through the running dev
server, so the walkthrough can never drift from the app.

One-off prerequisites — Google Chrome, plus:

```bash
npm install --no-save puppeteer-core && pip3 install pillow
```

Then, with the dev server running (`npm run dev`):

```bash
./scripts/walkthrough.sh
```

- `scripts/capture-walkthrough.mjs` — which screens to visit, and what to click
  on each one. Add a scene here.
- `scripts/build-walkthrough.py` — the narration script and the page itself.
  Edit the wording here, never in the generated HTML, which is overwritten.
