# deploy

Deploy the application to the staging environment.

## Steps

Follow these steps in order. Stop immediately if any step fails.

### 1. Run lint checks

Run `npm run lint` to catch any code quality issues. If linting fails, report the errors and stop.

### 2. Run tests

Run `npm test` to execute the full test suite. If any test fails, report the failures and stop. If no test script is configured, warn the user and ask whether to proceed without tests.

### 3. Build the production bundle

Run `npm run build` to create an optimized production build in the `dist/` directory. If the build fails, report the errors and stop.

### 4. Push to staging

Push the current branch to the `staging` remote branch:

```
git push origin HEAD:staging
```

If the push fails (e.g., due to conflicts), report the issue and stop. Do NOT force-push unless the user explicitly confirms.

### 5. Report

Summarize what was deployed: the branch name, the commit hash, and whether all steps passed.
