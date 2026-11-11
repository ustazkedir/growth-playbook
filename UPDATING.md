# How to update this page

`index.html` is a public page served at https://ustazkedir.github.io/growth-playbook/

To publish a report:

1. Replace everything between `<!-- UPDATED:START -->` and `<!-- UPDATED:END -->` with
   `<p class="sub">Last report: <Day Mon D> · <HH:MM> ET / <HH:MM> EAT</p>`.
2. Insert one new `<article class="report">` block directly after `<!-- REPORTS:START -->`
   (newest first). Delete the `<p id="empty">` line if it is still there.
3. Keep at most 60 `<article class="report">` blocks. Delete the oldest beyond that.
4. Change nothing else in the file: not the `<head>`, the styles, or the markers.

Report block shape:

```html
<article class="report">
  <h2>Short headline</h2>
  <p class="time">Wed Nov 11 · 10:00 ET / 18:00 EAT</p>
  <p class="lead">The conclusion in one sentence.</p>
  <h3>Section name</h3>
  <ul><li>Bullet</li></ul>
  <h3>Analyst actions</h3>
  <div class="tablewrap"><table>
    <thead><tr><th>Time</th><th>Ticker</th><th>Firm</th><th>Action</th><th>Previous</th><th>New</th><th>Flag</th></tr></thead>
    <tbody><tr><td>...</td></tr></tbody>
  </table></div>
</article>
```

Use `<span class="ok">`, `<span class="warn">` and `<span class="stop">` for confirmed, caution and stop items.
Escape `&`, `<` and `>` in text. Plain HTML only: no scripts, no external files.
