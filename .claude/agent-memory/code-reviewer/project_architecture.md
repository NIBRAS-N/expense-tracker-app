---
name: project-architecture
description: Expense tracker React 19 + Vite 7 app architecture, component relationships, and data flow
metadata:
  type: project
---

React 19 + Vite 7 expense tracker. No routing, backend, or external state management.

**Component hierarchy:** App.jsx (state owner) -> Summary.jsx, SpendingChart.jsx, TransactionForm.jsx, TransactionList.jsx

**Data flow:** App owns `transactions` array and `categories` list. Summary/SpendingChart receive transactions read-only. TransactionForm calls `onAddTransaction` callback. TransactionList calls `onDeleteTransaction` callback.

**Known intentional bug:** "Freelance Work" transaction (id: 4) has `type: "expense"` when it should be `type: "income"`.

**Why:** This is a course starter project with intentional bugs for exercises.

**How to apply:** When reviewing, distinguish between intentional bugs (documented in CLAUDE.md) and newly introduced issues. The Freelance Work bug is by design.
