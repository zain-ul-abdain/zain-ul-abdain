### Zain Ul Abdain

Backend engineer, 8+ years. I work on **payments infrastructure** — the part that has to be right when things go wrong.

Taking a card payment is a solved problem. What isn't, in most codebases I've seen, is what happens when the webhook arrives twice — or never. When a refund lands against a payout that already released. When the gateway says one thing and your ledger says another.

Most recently I owned the payments platform of a cross-border B2B marketplace: Stripe Connect marketplace settlement, Escrow.com, five gateways behind a single contract, idempotent webhook processing, reconciliation, and sanctions validation.

---

#### Packages

**[laravel-webhook-ledger](https://github.com/zain-ul-abdain/laravel-webhook-ledger)** — exactly-once webhook processing for Laravel.

It exists because the obvious guard is a race condition: `if (exists) return; else insert;` lets two concurrent redeliveries both pass the check and both process, which on a payment handler is a double credit. The fix is letting the database's unique constraint arbitrate. Signature verification, durable event log, stale-claim recovery, deliberate replay.

**[laravel-route-permissions](https://github.com/zain-ul-abdain/laravel-route-permissions)** — permission scaffolding generated from your named routes.

Route names are stable identifiers; controller class names aren't, so deriving permissions from them means a refactor silently orphans your grants. `permissions:sync` gives you a reviewable diff instead. Roles, direct grants, two-query cached resolution, Gate integration, optional Passport scope sync.

Both are tested against SQLite, PostgreSQL and MySQL, with CI across PHP 8.2–8.4 on Laravel 12 and 13.

---

#### Also building

**[SchoolNinty](https://schoolninty.com)** — multi-tenant school management SaaS. Sole engineer, architecture through production. Laravel 13, PHP 8.4, Inertia + Vue 3, PostgreSQL, Redis, 1,486 tests.

---

**Stack** · PHP · Laravel · Vue 3 · TypeScript · PostgreSQL · MySQL · Redis · Elasticsearch · Docker · AWS

**Dubai, UAE** — open to senior backend roles, and to contract work on payments integration specifically: Stripe Connect marketplaces, multi-gateway consolidation, or a webhook pipeline that's double-processing.

[Portfolio](https://zain-ul-abdain.github.io) · [LinkedIn](https://linkedin.com/in/zain-ul-abdain)
