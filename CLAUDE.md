# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Expense tracker app built with React 19 and Vite 7. This is a course starter project that intentionally contains bugs, poor UI, and messy code meant to be fixed as exercises.

## Commands

- `npm run dev` — Start dev server (http://localhost:5173)
- `npm run build` — Production build to `dist/`
- `npm run preview` — Preview production build
- `npm run lint` — ESLint (flat config, React Hooks + React Refresh plugins)

No test framework is configured.

## Architecture

Single-component app — all state and UI live in `src/App.jsx`. There is no routing, no backend, and no external state management. Transaction data is hardcoded in component state (not persisted).

## Known Issues (by design)

- Transaction amounts are stored as strings, causing arithmetic bugs in summary totals (string concatenation instead of addition)
- "Freelance Work" is typed as `"expense"` instead of `"income"`
- No delete functionality for transactions

## ESLint

Uses flat config (`eslint.config.js`). The `no-unused-vars` rule ignores variables starting with uppercase or underscore (`varsIgnorePattern: '^[A-Z_]'`).
