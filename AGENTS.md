# Repository guidance for TGV maintainers

## Scope

This repository is the TGV review fork of the upstream AGPL-3.0 OpenAlice project. Keep upstream application code easy to synchronize:

- Prefer TGV-specific policy, integration notes, and maintenance tooling in clearly named files rather than rewriting upstream modules.
- Keep behavior changes narrow, tested, and separate from fork-governance changes.
- Preserve upstream copyright, license, and attribution notices.
- Never add broker credentials, API keys, account data, generated runtime state, or trading logs.

## Safety boundary

Treat all broker and order paths as financially sensitive. Reviews and tests must not start live services, connect to broker accounts, or submit orders. Use existing mocks and fixtures unless the task explicitly authorizes a safe non-production integration.

## Quality gates

Use the package-manager version declared in `package.json` through Corepack:

```sh
corepack pnpm install --frozen-lockfile
corepack pnpm build
corepack pnpm test
```

Run the narrower documented suites when relevant:

```sh
corepack pnpm test:e2e
corepack pnpm test:bbProvider
corepack pnpm test:smoke
```

Before handoff, inspect `git diff --check`, the complete diff, and `git status --short`. Do not commit generated output, local configuration, or secrets.
