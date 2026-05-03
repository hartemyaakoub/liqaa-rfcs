# RFC 0001 — Establish the RFC process

- **Status:** accepted
- **Author:** @hartemyaakoub
- **Discussion:** N/A (foundational)
- **Date:** 2026-05-01
- **Date last updated:** 2026-05-03

## Summary

LIQAA adopts a public RFC (Request for Comments) process for substantial changes to the platform. All substantial changes will be proposed, debated, and decided in this repo before implementation.

## Motivation

Six months from now, when a customer asks "why does the webhook payload include `recording_url` instead of `recording.url`?", the answer should be a one-line link to the RFC where we debated and decided.

Right now, those decisions live in my head and a few PR descriptions. That doesn't scale, and it doesn't earn customer trust. **Open governance is a competitive advantage** for an early platform — Stripe, React, and Rust all use it.

## Detailed design

### What requires an RFC

- New public API endpoint
- Modification to an existing API endpoint's contract
- Breaking change to any published SDK
- New webhook event or modification to existing payload
- Pricing or billing model change
- Data retention policy change
- Significant architectural decision (use [ADRs](https://github.com/hartemyaakoub/liqaa-architecture) for those)

### What does NOT require an RFC

- Bug fixes (open a normal issue / PR)
- Internal refactors invisible to customers
- New examples (just PR to [`liqaa-examples`](https://github.com/hartemyaakoub/liqaa-examples))
- Documentation improvements
- Performance work that doesn't change observable behaviour

### Process

1. **Pre-RFC discussion** — open an issue in this repo. Iterate on the idea before formalising.
2. **Draft** — copy `template/RFC-template.md` to `rfcs/0NNN-name.md`, fill it in, open a PR.
3. **Review** — minimum **10 days** for substantial RFCs. The team reviews + comments. Author iterates.
4. **Final comment period** — 7 days. Last call for objections.
5. **Decision** — the maintainer team accepts or rejects with documented reasoning. Decision is appended to the RFC body.
6. **Tracking issue** — accepted RFCs get a tracking issue for implementation. The PR is merged when the implementation ships.

### Numbering

Sequential, padded to 4 digits. RFC 0001, 0002, 0003. Reserved numbers don't exist.

### Status values

- `proposed` — under discussion in PR
- `review` — actively being iterated on
- `final-comment` — 7-day FCP started
- `accepted` — merged; tracking issue open
- `rejected` — closed without merge; reasoning in PR
- `superseded` — replaced by a later RFC (link to it in header)

## Alternatives

### "Just use issues"

Issues are good for bugs and small feature requests. They lack:
- A canonical, citable URL post-decision
- A standard template that forces authors to think about migration, alternatives, and drawbacks
- A FCP signalling mechanism

### "Internal-only design docs"

Faster, but loses the public-trust-building effect. We're a platform — our customers want to know how we think.

### "Adopt PEP wholesale"

PEP is great but heavy. We don't need a steering council yet. Start light, formalise as we grow.

## Drawbacks

- **Slower.** A 4-week RFC for a 1-day implementation feels excessive. Mitigation: only "substantial" changes go through it. Bug fixes and small additions skip it.
- **Public scrutiny.** Customers may push back hard on decisions we're already committed to. We accept this — it's the point.
- **Author overhead.** Writing a good RFC is real work. Mitigation: the template is short and prompts the right questions.

## Unresolved questions

- How do we handle "emergency RFCs" for security-driven changes? Probably skip the FCP, document retroactively.
- When do we add a steering committee? Probably never until we have ≥3 maintainers.

## Future possibilities

- An "RFC for a pre-RFC" lightweight process for very large changes that need a strategy doc before a design doc.
- Integration with the [`liqaa-roadmap`](https://github.com/hartemyaakoub/liqaa-roadmap) — accepted RFCs auto-show on the roadmap.

## Prior art

- [Rust RFC process](https://github.com/rust-lang/rfcs)
- [React RFCs](https://github.com/reactjs/rfcs)
- [Python PEPs](https://peps.python.org)
- [Ember RFCs](https://github.com/emberjs/rfcs) — closest in spirit (a single-vendor open source)

## Adoption strategy

Effective immediately. Past decisions don't get retroactive RFCs — only forward changes.
