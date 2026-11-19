# Browser-testing application: Caribbean Merchant

**[Game project](https://github.com/KonstantinOreshnikov/KonstantinOreshnikov/tree/main/projects/caribbean-merchant)** · **[QA evidence](https://github.com/KonstantinOreshnikov/KonstantinOreshnikov/blob/main/projects/caribbean-merchant/testing/original-qa-report.md)**

A downloadable offline game is a richer test subject than a static form. It has event handlers, responsive layouts, language switching, save state and trade workflows. The owner directly playtested early releases; automated release tests checked selected behaviors.

## Useful practice scenarios

1. Render the app, switch Russian → English → Azerbaijani and verify selected texts/local state.
2. Set a known starting budget and test one-click bulk buying without spending beyond available funds.
3. Scroll the market and confirm treasury / hold usage remains visible.
4. Choose a voyage and check the pirate-risk panel updates with the route.
5. Verify failed contract acceptance does not modify gold, stock or active contracts.
6. Export/import saves and confirm idempotent awards and business state.
7. Capture desktop and mobile widths, watch label intersections and text overflow.

The actual v1.0 automated report describes **26 passing local browser scenarios** based on Chromium + Playwright `page.set_content`; it does **not** prove tests on the user's Windows machine or remote GitHub Pages.

Use semantic selectors, explicit assertions, controlled localStorage fixtures and a game-state reconciliation oracle. See [Quality Engineering Lab](https://github.com/KonstantinOreshnikov/web-testing-page-object) for deeper test architecture.

**RU:** прикладной пример QA веб-игры. Не путать реальный результат проверок v1.0 с историческими учебными тестами этого репозитория.

[Back to browser practice](browser-testing-practice.md)
