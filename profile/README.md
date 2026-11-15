# saxeum

Small, honest services, each with the platform plumbing around it. Every one of these runs: a model or an
agent, an auth boundary that does not trust the model, infrastructure as code, and evaluations that measure
rather than assert.

**hyperchat** — [repo](https://github.com/saxeum/hyperchat)

A FastAPI service on Cloud Run, provisioned by Terraform. A Google ID token is verified and an allowlist
decides who may spend; the provider key never enters the image, the state file or the plan; images are pinned
by digest and tagged with the commit SHA. A coding agent contributes through a machine account that joins by
fork and carries no write access. Its evaluation suite scores predicate verdicts rather than a model judge,
reports injection resistance as a rate instead of flaky booleans, and scores non-model baselines as strategies
so a case they win is visible.

**pydantachat** — [repo](https://github.com/saxeum/pydantachat)

A Pydantic AI agent that answers questions about a signed-in customer's orders. The tool takes no customer
argument: identity comes from a two-minute customer-scoped token that never enters the prompt, the tool result
or the transcript, and a test fails if the claim check is removed. Vendor-neutral OpenTelemetry tracing, and
evaluations that report cost and thinking tokens and diff against a saved baseline.

**zuchat** — [live](https://zuchat.foonix.net) · [repo](https://github.com/saxeum/zuchat)

A FastAPI chat service on AWS ECS behind an ALB, with three Terraform roots and a plan-on-pull-request,
apply-on-merge pipeline. Google OIDC and an email allowlist gate the chat, and liveness and readiness are
separate endpoints wired to the target group and the container health check.

**Foonix** — [live](https://foonix.net) · [repo](https://github.com/saxeum/foonix)

A live OpenAI-compatible gateway fronting the free tiers of Gemini, NVIDIA and Groq. Bring your own key, keys
encrypted at rest, scoped revocable API tokens, a streaming chat UI, and Cloudflare Workers with a React and
TypeScript front end, so any OpenAI SDK works by changing one base URL.

---

George Treacy — platform and AI engineer, Brisbane.
github.com/gmtreacy · linkedin.com/in/george-treacy · gmtreacy@outlook.com
