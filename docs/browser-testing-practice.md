# Web Testing with Python — A Practical Learning Guide

Browser automation is valuable for journeys that truly require a browser: navigation, form behavior, responsive layout, language switches and complete end-to-end flows. Arithmetic and schema validation should usually remain unit/data tests.

## From requirement to assertion

1. Choose a **synthetic, local** webpage and one user-visible requirement.
2. Define the precondition (known data and initial UI state).
3. Choose a stable semantic locator.
4. Perform the user action.
5. Assert a **visible behavior or state**, not just that a click did not throw.
6. Record evidence; classify failure as code, test data, environment or flakiness.

```python
# Illustrative Playwright API; not an executable file in this repository.
def test_demo_language_switch(page):
    page.goto("http://127.0.0.1:8000")
    page.get_by_role("button", name="Русский").click()
    assert page.get_by_role("heading", name="Демо-отчёт").is_visible()
```

This code assumes that an independently created **local fictional** site exposes the shown controls. It does not target an existing private application.

## Selenium and Playwright

| Tool | Useful for | Key rule |
|---|---|---|
| Selenium | Existing WebDriver-based stacks and broad browser support | Explicit waits and reliable locators |
| Playwright | Auto-waiting, browser contexts and modern E2E workflows | Semantic locators, isolated fixtures |
| pytest | Parametrization, assertions and fixtures | Keep tests deterministic |
| Page Object | Reusable page-specific actions | Keep assertions primarily in test cases |

## Test matrix

Check login-invalid, form-validation, navigation, language-switch, no-data state, active filters, reset and accessibility basics **only in a permitted test environment**. For reporting UIs, compare shown totals with the exact synthetic fixture; screenshots are not reconciliation.

## Legacy status

The original Selenium lesson files are historical and have **not** been revalidated by this documentation update. Do not run their old URLs or test data against external systems automatically.

**RU:** Selenium/Playwright применяются для проверки реальных пользовательских сценариев, но на учебном сайте нужны отдельные безопасные фикстуры и явные assertions.

Official: [Selenium](https://www.selenium.dev/documentation/), [Playwright](https://playwright.dev/docs/intro), [pytest](https://docs.pytest.org/en/stable/).
