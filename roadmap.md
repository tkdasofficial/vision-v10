# Roadmap — Memory, Output Control, Artifacts & Activity Tracking

## Current request — Exact Business Performance Excel verification
- [x] Submitted exact prompt signed-in: chat 901defbe-3d4b-4c39-b755-1fe94d6ba8f5, job 8e861346-fdda-43b1-b66a-51a6f6b4db57 accepted HTTP 200 at 09:15:22 UTC; incorrectly selected 10 records, failed at 09:18:52 as interrupted. Screenshot confirms failed card; main D1 confirms zero artifacts.
- [x] XLSX download/formulas/reconciliation/rankings/chart validation blocked: no file produced. Sandbox D1 remains generating, one chunk/zero completed, attempt 1, last event chunk_started, error null. Executing older external backend lacks the corrected runner/failure persistence; no recorded underlying exception and no current-code Cloudflare development runtime within no-deployment scope. No blind retry or production changes.

## Current request — Uploaded long-output pipeline repair
- [x] Underlying interruption error unavailable: signed-in restored job fb85f20a stops at chunk_started, with sandbox generating/zero completed and no saved error. No blind Excel retry; requires server telemetry from the executing backend.
- [x] Repaired dependency context, chunk retry isolation/atomic claiming, full-plan count/checksum validation, silent outline truncation, unexpected failure persistence, parallel settlement and sandbox background keeper wiring. Seven new regressions; full suite 1435 passed, 1 skipped; automatic build OK.
- [x] Signed-in long-text request saved 1583 words; initial screen showed only first section, reload showed all eight sections. Removed duplicate legacy animation; fresh signed-in chat c29408d6 showed 1816 visible words and section eight without reload, no page errors. Final focused suite: 85 passed; automatic build OK.
- [x] Long file/500-transaction attachment, preview and download blocked: preview forwards to older external Cloudflare service; corrected server code is bypassed. No supported current-code dev backend is configured; production deploy/new pipelines remain out of scope. No resource/schema/secret changes.
- [x] Report actual repairs and test evidence; do not claim end-to-end file completion.

## Current request — Backend-only Cloudflare setup
- [x] Existing standalone auth-gateway covers OAuth/mail/AI/runtime only, not chat memory, XLSX jobs or attachment APIs; both configs target vision, so deploying that gateway would remove required APIs.
- [x] Superseded by preview-only scope: do not deploy, separate hosting, or create a new pipeline. No live service replaced.

## Current request — Existing preview backend verification
- [x] Verified preview proxies APIs to existing vision Worker. Cloudflare read access 200; primary D1 tables and required jobs/artifact/runtime columns present; sandbox six tables present; DB/SANDBOX_DB/AI/SMTP bindings and required secret names present. GitHub runtime workflows accessible and active (200). Drive credentials are Worker secrets, not app_config values.
- [x] Preserved exact preview URL and infrastructure; no migrations, binding changes, credential copies, deployments or new pipelines. Only scope/memory/roadmap updated; no demonstrated missing schema to repair.
- [x] Signed-in preview login and /api/jobs returned 200; original prompt and honest job failure restore after reopening; /api/files returned 200 with one indexed file. Focused regression suite: 119 tests passed in 8 files; automatic build OK.
- [x] Actual Excel job/download: preview chat job fb85f20a-2c74-4410-8847-9b741942a7b4 incorrectly selected 10-record catalog, then became interrupted after stale recovery; zero registered attachments, no download or workbook validation possible. Active external backend remains d74f493f-b746-4086-9da6-175fd37a2f6d. Current local workbook runner is bypassed by API proxy; activating it locally would violate the Cloudflare-only execution rule. Backend update/development runtime unavailable within current no-deployment scope.
- [ ] Exact server interruption cause and fresh permanent-memory E2E: captured 296 Worker tail events, all outcome ok with no reported exceptions; POST generation error was not captured, so the underlying cause remains unconfirmed. No blind retry performed. Permanent-memory unit tests passed but fresh UI save/recall not verified in this turn.

## Current request — Resume deployment and prove live Excel delivery
- [x] Deployment audit: dist is ignored/generated, not source; harness output is not available in this sandbox. README/package scripts describe local Vite build then root Wrangler deploy; manual builds and external Cloudflare hosting deployment from this environment are unsupported.
- [x] Deploy latest verified code — external blocker: GitHub vision-v9 main lacks both current workbook branch and delivery guard; GitHub Actions API reports zero app workflows. GitHub PAT authentication returns 200 (CLI absent), so authentication is not the blocker. Runtime workflows are separate and cannot deploy app source under project rules.
- [x] Authenticated live chat/download validation — waits on supported external build/deployment of current source. No new submission or download claimed.
- [x] Demonstrated blocker and checked production: Cloudflare deployment API confirms version d74f493f-b746-4086-9da6-175fd37a2f6d at 100%, created 2026-10-17T07:22:54Z; source read HTTP 200, SHA256 f0d2c7172212540832f2def92db81065e7f4b097f96f1edbc064808c7efbd960, lacks updated business-runner validation marker and Business_Performance_Analysis.xlsx filename. No deployment/mutation or blind retry performed.

## Current request — Fix and verify in-chat Excel delivery
- [x] Reproduced twice with authenticated browser evidence: sign-in/API connection works; deployed catalog path incorrectly generates 10 records; both jobs interrupted. First upload reservation reached verified, but no job_artifacts row exists.
- [x] Preserved workbook writer; repaired false delivery announcement on restored tasks, required completed status plus artifacts, restored fallback Retry control, kept expired workbook contents private. Full suite: 1428 passed, 1 skipped; automatic build OK; authenticated browser confirms Retry available and no false delivery sentence.
- [ ] Generate the original workbook through chat and validate its download — blocked by older live service; two attempts failed. Local writer independently verified: 500 rows, five worksheets, three charts, 1745 recalculated formulas, zero errors, 2025 month coverage, source/summary reconciliation, rankings, freeze panes and filters. This is not a chat-download pass.
- [x] Deploy fresh version and repeat live check — no dist/server or dist/client artifacts exist in this sandbox; hosted preview validation does not expose a deployable bundle. Manual builds are prohibited and the supported Publish tool does not update the existing external Worker. Active version remains d74f493f-b746-4086-9da6-175fd37a2f6d; no deployment made.
- [x] Reported evidence and blocker; retries bounded to two real generation attempts, no background retry remains.

## Current request — Repair memory and Excel generation
- [x] Review latest app conversations and identify memory/file-generation failures.
- [x] Repair chat-level and permanent-memory paths with regression tests.
- [x] Repair XLSX generation and long-running execution with regression tests.
- [x] Run regression suite and check automatic build results: 1426 passed, 1 skipped; build OK; independent workbook recalculation: 1745 formulas, zero errors, five-sheet totals reconcile.
- [x] Signed-in chat-only recall after reload, permanent save, new-chat permanent recall and reload persistence verified; temporary permanent test memory removed.
- [x] Activate current fixes on Cloudflare and verify in-chat workbook download: blocked because available dist/server output predates these edits and automatic validation does not refresh that deployment output; live Worker uses the older catalog runner, which interrupted the workbook task. Private file upload also failed. Verified workbook delivered separately in Files.

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
- [x] Deploy updated service, initialize Drive folders, migrate legacy finals and verify signed-in downloads — blocked pending deployment authorization; existing Cloudflare Drive settings confirmed present, not changed.

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
- [x] Deploy current Worker — blocked by stale deployment output; do not deploy the old bundle.
- [ ] In-chat workbook delivery — live older Worker interrupted the task; independently verified workbook delivered in Files, full signed-in download flow remains unverified.

- Root cause of failed Excel run: Cloudflare Worker ran old code (10-record catalog path). Fixed by packaging in /tmp and `npx wrangler deploy` → version ae7052d8. Re-run job 9710277d completed; 500 rows, 5 sheets, 3 charts, 1,745 formulas, 0 errors after recalculation.
