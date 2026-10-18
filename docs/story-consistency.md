# Story consistency upgrade

## Integrated implementation

Continuous scene/chapter/shot requests enter the story branch of the existing Deep pipeline, preserving auth, provider order and detached chat execution. `story.ts` owns Zod contracts, stable canonical IDs, manifest checks, pure state transitions, dependency closure and context gates. `story-run.ts` owns plan validation, individual generation/review, bounded local repair, dependent revalidation and final audit. `story-store.server.ts` stores namespaced owner-scoped JSON records in the existing `deep_executions` table. No migration or deployment was performed.

Only a scene passing both deterministic and semantic checks commits a boundary snapshot. State provenance includes scene ID and quoted evidence. Local fixes revalidate dependents; unchanged valid scenes are not regenerated. Critical errors, missing reviews, malformed JSON and exhausted budgets yield unresolved status, not approval. Approved/rejected versions, repair issues and final audits are saved. Reopening a passed request reuses its result; interrupted runs resume approved scenes when invoked with the same request ID.

## Configuration and limitations

Defaults: two repairs per stage and a 600-second run budget, injectable for tests. Context gating reserves output and overhead and never cuts essential story facts. GPT-family estimates use BPE tokenization; other models use a conservative UTF-8 byte upper bound because native tokenizers are unavailable. The initial configured safe context ceiling is 32,768 tokens, not a verified model maximum. JSON is normalized and schema-checked rather than relying on provider-specific structured-output support. All candidate adapters are budget-gated before dispatch. Actual chosen model/provider are recorded when available; provider-reported usage, exact tokenizer/version and billing costs are not yet available. Full global audit overflow stops honestly; larger loss-aware global-audit windows remain to implement.

Requirements and editable canonical data are persisted as structured JSON; a dedicated blueprint-editing UI and user-triggered scene regeneration UI are not implemented. Missing blocking details produce unresolved planning status rather than an interactive clarification flow. Existing request classification still governs which prompts reach Deep; arbitrary generic prompt/file stories are not newly rerouted.

## Evaluation rubric

Six separate check categories: story beats/canon; visual/action agreement; dialogue/context; causal/timeline continuity; mandatory instruction coverage; structural schema/IDs. Each reviewed scene and global audit contributes one pass/fail observation per category. Scores are passed checks divided by expected scene checks plus global audit, with null when no checks ran. These are check-coverage/pass ratios, **not measured creative quality or factual accuracy**. Critical unresolved issues always prevent approval irrespective of average score.

Run `bunx vitest run src/test/story-prd.test.ts` for frozen 10/25/50-scene contract fixtures, injected canon/state faults, targeted repair, dependent revalidation, saved-result reuse, provider failures and token overflow. Fixtures use a deterministic mock model; their passes establish orchestration correctness only. Real baseline/upgraded multi-model quality, repair rates, usage/cost and latency comparisons must be recorded against the executing updated Cloudflare backend before claiming PRD completion.

## Preview verification boundary

The unchanged Lovable preview proxies API calls to the existing Cloudflare Worker, not the edited local server routes. The compact UI can be tested here immediately. The story backend edits cannot be claimed live until that Cloudflare runtime is updated through an authorized development path; production deployment remains out of scope.