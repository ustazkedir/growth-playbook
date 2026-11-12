# How to update this page

Public page: https://ustazkedir.github.io/growth-playbook/

`index.html` is the shell with four tabs. Never edit it. Each scheduled task owns ONE file:

| Task | File | Tab link |
|---|---|---|
| Growth playbook | `tabs/growth.html` | `#growth` (default) |
| Market headlines | `tabs/headlines.html` | `#headlines` |
| Pre-market catalyst screen | `tabs/premarket.html` | `#premarket` |
| Daily AI news brief | `tabs/ai-news.html` | `#ai-news` |

NO HISTORY: each run REPLACES the previous content of its tab file. Overwrite the whole file.

A tab file is an HTML fragment (no `<html>`, `<head>`, `<body>`, `<style>` or `<script>`).

## Report tabs (growth, premarket, ai-news)

The file holds exactly two parts:

- Line 1, one status line: `<p class="sub">Last report: <Day Mon D> · <HH:MM> ET / <HH:MM> EAT</p>`
- Then exactly ONE `<article class="report">` block: the current report. Never keep earlier reports.

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

## Market headlines tab

`tabs/headlines.html` holds only the entries found by the current run:

- Line 1: `<p class="sub">Last checked: <Day Mon D> · <HH:MM> ET / <HH:MM> EAT · <N> new</p>`
- Then this run's `<article class="hl">` entries, newest first. Add `major` to the class for market-moving items.
- Delete every entry from earlier runs. Exception: if this run found 0 new entries, change only line 1 and leave the entries as they are.

```html
<article class="hl major">
  <p class="hl-time">Wed Nov 11 · 09:14 ET / 17:14 EAT</p>
  <p class="hl-text"><span class="tag">Earnings</span><strong>TICKER</strong> One-sentence headline. <span class="ok">✓</span> <a href="https://...">Reuters</a></p>
</article>
```

Tags: Macro, Fed, Trump, Earnings, Guidance, M&A, Analyst, Rumor, Geopolitics, Commodities, Crypto, Other.

## All tabs

- Use `<span class="ok">`, `<span class="warn">` and `<span class="stop">` for confirmed, caution and stop items.
- Links: `<a href="https://...">source name</a>`. Escape `&`, `<` and `>` in text. Plain HTML only. No em-dashes.
- Touch only your own tab file.
- Commit, then `git pull --rebase origin main`, then `git push origin HEAD:main`. If the push is rejected, pull --rebase and push once more. Never force push.
