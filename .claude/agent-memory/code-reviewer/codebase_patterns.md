---
name: codebase-patterns
description: Recurring code patterns, quality issues, and style conventions found across components
metadata:
  type: project
---

**Amount handling:** `amount` is stored as a string from form input but treated as a number elsewhere. Multiple components call `parseFloat(t.amount)` independently. This is a recurring type inconsistency.

**Category capitalization:** Three separate components duplicate `cat.charAt(0).toUpperCase() + cat.slice(1)` for capitalizing category names (TransactionForm, TransactionList, SpendingChart).

**Formatting:** Both Summary.jsx and TransactionList.jsx define their own `fmt()` function for number formatting with slight differences.

**Accessibility gaps:** Form labels lack `htmlFor`/`id` pairing. Delete buttons lack descriptive aria-labels. Table Actions header was removed (now empty `<th>`). Filter selects have no labels.

**Why:** These patterns indicate areas where shared utilities and consistent practices would reduce bugs and maintenance burden.

**How to apply:** Flag DRY violations and a11y gaps in reviews. Suggest extracting shared helpers (capitalize, formatCurrency) and consistent type handling for amounts.
