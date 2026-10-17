# Roadmap — Memory, Output Control, Artifacts & Activity Tracking

## Current request — Backend-only Cloudflare setup
- [x] Existing standalone auth-gateway covers OAuth/mail/AI/runtime only, not chat memory, XLSX jobs or attachment APIs; both configs target vision, so deploying that gateway would remove required APIs.
- [ ] Configure/deploy only the backend — requires separating the full API entrypoint from the combined app server; awaiting user choice before changing that architecture. No live service replaced.

## Current request — Existing preview backend verification
- [ ] Inventory preview routing, required resources, bindings and configured credential access without exposing secrets.
- [ ] Repair only demonstrated development setup issues; preserve existing data, exact preview URL, and production resources. No production deployment or new pipeline.
- [ ] Verify signed-in authentication, persistence, memory and actual Excel job/download in the existing preview; record concrete failure and server-side cause when blocked.

## Current request — Resume deployment and prove live Excel delivery
- [x] Deployment audit: dist is ignored/generated, not source; harness output is not available in this sandbox. README/package scripts describe local Vite build then root Wrangler deploy; manual builds and external Cloudflare hosting deployment from this environment are unsupported.
- [ ] Deploy latest verified code — external blocker: GitHub vision-v9 main lacks both current workbook branch and delivery guard; GitHub Actions API reports zero app workflows. GitHub PAT authentication returns 200 (CLI absent), so authentication is not the blocker. Runtime workflows are separate and cannot deploy app source under project rules.
- [ ] Authenticated live chat/download validation — waits on supported external build/deployment of current source. No new submission or download claimed.
- [x] Demonstrated blocker and checked production: Cloudflare deployment API confirms version d74f493f-b746-4086-9da6-175fd37a2f6d at 100%, created 2026-10-17T07:22:54Z; source read HTTP 200, SHA256 f0d2c7172212540832f2def92db81065e7f4b097f96f1edbc064808c7efbd960, lacks updated business-runner validation marker and Business_Performance_Analysis.xlsx filename. No deployment/mutation or blind retry performed.

## Current request — Fix and verify in-chat Excel delivery
- [x] Reproduced twice with authenticated browser evidence: sign-in/API connection works; deployed catalog path incorrectly generates 10 records; both jobs interrupted. First upload reservation reached verified, but no job_artifacts row exists.
- [x] Preserved workbook writer; repaired false delivery announcement on restored tasks, required completed status plus artifacts, restored fallback Retry control, kept expired workbook contents private. Full suite: 1428 passed, 1 skipped; automatic build OK; authenticated browser confirms Retry available and no false delivery sentence.
- [ ] Generate the original workbook through chat and validate its download — blocked by older live service; two attempts failed. Local writer independently verified: 500 rows, five worksheets, three charts, 1745 recalculated formulas, zero errors, 2025 month coverage, source/summary reconciliation, rankings, freeze panes and filters. This is not a chat-download pass.
- [ ] Deploy fresh version and repeat live check — no dist/server or dist/client artifacts exist in this sandbox; hosted preview validation does not expose a deployable bundle. Manual builds are prohibited and the supported Publish tool does not update the existing external Worker. Active version remains d74f493f-b746-4086-9da6-175fd37a2f6d; no deployment made.
- [x] Reported evidence and blocker; retries bounded to two real generation attempts, no background retry remains.

## Current request — Repair memory and Excel generation
- [x] Review latest app conversations and identify memory/file-generation failures.
- [x] Repair chat-level and permanent-memory paths with regression tests.
- [x] Repair XLSX generation and long-running execution with regression tests.
- [x] Run regression suite and check automatic build results: 1426 passed, 1 skipped; build OK; independent workbook recalculation: 1745 formulas, zero errors, five-sheet totals reconcile.
- [x] Signed-in chat-only recall after reload, permanent save, new-chat permanent recall and reload persistence verified; temporary permanent test memory removed.
- [ ] Activate current fixes on Cloudflare and verify in-chat workbook download: blocked because available dist/server output predates these edits and automatic validation does not refresh that deployment output; live Worker uses the older catalog runner, which interrupted the workbook task. Private file upload also failed. Verified workbook delivered separately in Files.

## Current request — vision-sandbox D1 + long-context generation
- [x] Created "vision-sandbox" D1 (id 4d8098d8-e148-46ea-9e79-b4d35c148c8f), SANDBOX_DB binding in wrangler.toml; schema applied local + remote (6 tables verified live).
- [x] Schema in db/migrations/0001_vision_sandbox.sql: generation_jobs/plans/chunks/context/events/outputs with PKs, FKs, indexes, UNIQUE(job_id, seq), status checks.
- [x] Pipeline in src/lib/sandbox/ (pure generation.ts, store.server.ts, runner.server.ts): outline plan → parallel independent chunks / sequential dependencies → retry failed only → resume from checkpoints → assemble → validate (gaps/order/duplication) → output.
- [x] Endpoints /api/sandbox-generations (+ /$jobId with status/chunks/output/events views and retry/resume/cancel), owner-scoped, same proxy/auth/CSRF conventions as existing routes.
- [x] 17 new tests in src/test/sandbox-generation.test.ts; full suite 1392 passed | 1 skipped; typecheck clean; automatic build OK.
- [x] Verified live Worker has SANDBOX_DB binding; long-context chat jobs use it. Standalone sandbox screen is not requested.

# Roadmap — Memory, Output Control, Artifacts & Activity Tracking

## Current request — Private Google Drive storage
- [x] Audit output capabilities and storage paths; reconcile 115 canonical writable formats.
- [x] Replace final-file D1 fallback with private Drive; preserve bounded runtime staging and legacy downloads; integrate browser exports.
- [x] Add folder/upload reservations, metadata recovery, authenticated downloads, and bounded legacy migration.
- [x] Automated regressions: 1375 passed, 1 skipped; automatic validation build OK.
- [ ] Deploy updated service, initialize Drive folders, migrate legacy finals and verify signed-in downloads — blocked pending deployment authorization; existing Cloudflare Drive settings confirmed present, not changed.

## Current request — Cloudflare-only AI routing
- [x] Audit AI paths; all three live providers responded through Cloudflare (reported outage not reproduced).
- [x] Unify off-Worker text/tools relay with API_ORIGIN; prioritize Worker settings; document Cloudflare-only execution in AGENTS.md.
- [x] Routing regressions: 56 passed; full suite: 1334 passed, 1 skipped; automatic build OK; signed-in preview chat returned 4 and completed in 2s.

## Current request — File-only delivery
- [x] Default all file creation/transformation replies to file delivery without in-file content.
- [x] Show requested contents underneath the delivered file only on explicit opt-in.
- [x] Run delivery regression tests and full suite; verify file/download rendering through automated tests.
- [x] Signed-in preview file-generation check executed twice; both failed on the old live runner, with no attachment registered. Full delivery remains blocked under the current Excel task above.

Spec: user-uploaded VISION memory/output/artifact/activity integration doc (5 tasks, sequential gates).

- [x] Task 1 — Memory integration (chat / permanent / project scopes) + tests
- [x] Task 2 — Output control & response discipline + tests
- [x] Task 3 — Artifact execution & delivery + tests
- [x] Task 4 — Deep-task status & activity history (Title Case labels, collapsed "Worked for Ns") + tests
- [x] Task 5 — Integrated regression suite + real-user E2E with screenshots (completed in earlier turns)
- [x] Final report (completed in earlier turns)

## Task 5 — Real-user verification (final report)
- Login, signup + email verification (MAIL_TOKEN fixed both sides): OK.
- Title Case statuses ("Thinking", "Reasoning"): OK visually.
- PDF of existing story → story.pdf chip, no fake "Writing" status: OK.
- Simple Q&A end-to-end: OK — "2+2" → "Four", with "Worked for 1s" activity row shown.
- BUG (reproducible): "Remember that my favorite color is teal." hangs at "Reasoning" in the UI and never completes; after reload the stuck spinner persists and the reply is missing from chat_messages. Direct fetch of /api/chat with the same payload (mode default, requestId, conversationId) streams fine and fast — so the hang is in the UI/client path for this request kind, not the provider. Not yet fixed.
- Memory recall: unverified because the remember turn never completes (earlier "recall works" was a false positive from composer text).

## Fix: memory chat hang (root cause)
- Root cause: the deployed "vision" Worker predated the permanent-memory feature; the code only existed in the repo. Deployed current code (`bun run build` + `npx wrangler deploy`, version e7780a89).
- Verified E2E: "Remember that my favorite color is teal." completes ("Worked for 5s", no hang), row saved in D1 user_memories, no stuck spinner after reload, recall in a brand-new chat answers "Your favorite color is teal." from memory.
- Added fail-soft test: DB unreachable -> savePermanentMemory null, load [] (11/11 pass).
- Full suite: 1263 passed | 1 skipped; production build OK.
- Remaining known limitation (pre-existing, separate from memory): if the page is reloaded mid-generation, the preview proxy aborts the upstream Worker request, so that reply isn't saved; the reload poll then waits up to 15 min. Memory itself is still saved. On the Worker itself (no proxy) replies run detached and survive reloads.

## Reload during generation — done
- [x] Server records generation stage/outcome (chat_generations); /api/chat-status for reconnect
- [x] Preview proxy keeps generation alive after reload; first message of a new chat now carries its chat id (answer was previously never saved server-side)
- [x] Verified: reload mid-answer → live "Writing" status restored → answer appears once; provider failure → clear note, no spinner

## Current request — Autonomous user-level QA for Long Context Generation (500-record Excel)
- [x] New job type `long_context` routed from chat, driving the vision-sandbox pipeline (plan/chunks in D1, resume on retry)
- [x] Real .xlsx output stage with catalog validation and native business workbook formulas/charts.
- [x] Tests: pure helpers + pipeline with in-memory sandbox double + request routing + xlsx options + invalid-record automatic retries.
- [ ] Deploy current Worker — blocked by stale deployment output; do not deploy the old bundle.
- [ ] In-chat workbook delivery — live older Worker interrupted the task; independently verified workbook delivered in Files, full signed-in download flow remains unverified.
