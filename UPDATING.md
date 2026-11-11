# How to update this page

Public page: https://ustazkedir.github.io/growth-playbook/

`index.html` is the shell with three tabs. Never edit it. Each scheduled task owns ONE file:

| Task | File | Tab link |
|---|---|---|
| Growth playbook | `tabs/growth.html` | `#growth` (default) |
| Pre-market catalyst screen | `tabs/premarket.html` | `#premarket` |
| Daily AI news brief | `tabs/ai-news.html` | `#ai-news` |

A tab file is an HTML fragment (no `<html>`, `<head>`, `<body>`, `<style>` or `<script>`):

- Line 1 is always one status line: `<p class="sub">Last report: <Day Mon D> · <HH:MM> ET / <HH:MM> EAT</p>`
- Below it: `<article class="report">` blocks, newest first.

To publish a report:

1. Replace line 1 with the new status line.
2. Insert one new `<article class="report">` block directly below line 1.
3. Keep at most 60 `<article class="report">` blocks. Delete the oldest beyond that.
4. Touch only your own tab file.
5. Commit, then `git pull --rebase origin main`, then `git push origin HEAD:main`. If the push is rejected, pull --rebase and push once more.

Report block shape:

```html
<article class="report">
  <h2>Short headline</h2>
  <p class="time">Wed Nov 11 · 10:00 ET / 18:00 EAT</p>
  <p class="lead">The conclusion in one sentence.</p>
  <h3>Section name</h3>
  <ul><li>Bullet</li></ul>
  <h4>Sub-item heading, such as a ticker or a story</h4>
  <ul><li>Detail line</li></ul>
  <div class="tablewrap"><table>
    <thead><tr><th>Col</th></tr></thead>
    <tbody><tr><td>...</td></tr></tbody>
  </table></div>
</article>
```

Use `<span class="ok">`, `<span class="warn">` and `<span class="stop">` for confirmed, caution and stop items.
Links: `<a href="https://...">source name</a>`. Escape `&`, `<` and `>` in text. Plain HTML only.
