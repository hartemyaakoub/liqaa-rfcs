# LIQAA · Public RFCs

> **Substantial changes to the LIQAA platform happen here, in the open, before they ship.**

Inspired by the [Rust RFC process](https://github.com/rust-lang/rfcs), [React RFCs](https://github.com/reactjs/rfcs), and [PEP](https://peps.python.org). If you've ever participated in one, this will feel familiar.

[![open RFCs](https://img.shields.io/github/issues/hartemyaakoub/liqaa-rfcs?label=open%20RFCs&color=1d4ed8)](https://github.com/hartemyaakoub/liqaa-rfcs/issues)
[![merged RFCs](https://img.shields.io/github/issues-closed/hartemyaakoub/liqaa-rfcs?label=merged&color=10b981)](https://github.com/hartemyaakoub/liqaa-rfcs/issues?q=is%3Aclosed)

## When does something need an RFC?

You should write an RFC if your change is:

- A **new public API endpoint** or modification to an existing one
- A **breaking change** to an SDK (JS, PHP, Python, Go)
- A new **webhook event** or change to existing event payload
- A **pricing or billing model** change
- A **data retention** change
- Anything that an enterprise customer would notice in their integration

You don't need an RFC for:

- Bug fixes
- Internal refactors
- New examples in [`liqaa-examples`](https://github.com/hartemyaakoub/liqaa-examples)
- Documentation
- Performance improvements that don't change observable behaviour

## How the process works

```
                  Idea
                    │
                    ▼
    ┌──────────────────────────────────┐
    │  1. Discussion (open issue here) │
    │     anyone can propose           │
    └──────────────┬───────────────────┘
                    │
                    ▼
    ┌──────────────────────────────────┐
    │  2. Draft RFC (PR with rfcs/    │
    │     0NNN-name.md, copy template) │
    └──────────────┬───────────────────┘
                    │
                    ▼
    ┌──────────────────────────────────┐
    │  3. Review (≥10 day review       │
    │     window for substantial RFCs) │
    └──────────────┬───────────────────┘
                    │
                    ▼
    ┌──────────────────────────────────┐
    │  4. Final comment period (7 day) │
    └──────────────┬───────────────────┘
                    │
                    ▼
              ┌─────┴─────┐
              ▼           ▼
        Accepted      Rejected
              │
              ▼
       Tracking issue
              │
              ▼
        Implementation
              │
              ▼
       Shipped (closes RFC)
```

## RFC index

| #   | Title | Status | Tracking |
| --- | ----- | ------ | -------- |
| [0001](./rfcs/0001-rfc-process.md) | Establish the RFC process | accepted | this repo |
| 0002 | Idempotency keys on `POST /tokens` | proposed | — |
| 0003 | `external_conversation_id` on rooms | accepted | shipped in v1.4.0 |

(Empty rows fill as RFCs are submitted.)

## Writing an RFC

1. Fork this repo
2. Copy `template/RFC-template.md` to `rfcs/0NNN-short-title.md` (pick the next number)
3. Fill it in (the template's prompts are mandatory — answer them all)
4. Open a PR
5. Be patient — substantial RFCs take 2–6 weeks of discussion

## Who decides?

The **maintainer team** (currently: @hartemyaakoub) makes the final call after the comment period. Decisions are documented in the RFC itself with reasoning. Customers and contributors can object with reasoning of their own — we publish the response to every objection.

This isn't a democracy and it isn't a dictatorship. It's a **published reasoning process**. If a decision later turns out wrong, the RFC is the receipt that lets us understand why we chose what we chose.

## License

[CC0 1.0](./LICENSE) — public domain. Reuse the process for your own project.
