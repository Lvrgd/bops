<!-- BEGIN:nextjs-agent-rules -->

# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` (resolved from this file's directory; in monorepos the `next` package may not be visible from the repo root) before writing any code. Heed deprecation notices.

This block is written and re-added by `next dev` — verify at `node_modules/next/dist/server/lib/generate-agent-files.js`. Removing it from a diff only re-creates the uncommitted change; committing it with your work keeps the tree clean.

<!-- END:nextjs-agent-rules -->

## Cloud Agent

The Mac app (`npm run app`) is Electron on Apple silicon. On Linux, run the Bops server with `npx next dev --port 3210` and open http://127.0.0.1:3210. With `BOPS_SELF_HOSTED=1` and empty keys in `.env.local`, that server shows the sign-in screen.

In the Cloud Agent environment, boot starts PostgreSQL 18, then that dev server. Install uses `npm ci` and skips the Electron and Playwright browser downloads. Bops Cloud tests use the throwaway role from CI: `BOPS_TEST_DATABASE_URL=postgres://bops_app:bops-local@127.0.0.1:5432/orgo_core` (edge tests use `orgo_edge`). Node 22 runs the cloud's TypeScript here.
