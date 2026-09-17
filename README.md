# Agentic Threat Taxonomy

**[Read the taxonomy →](agentic-threat-taxonomy.html)**

Four OWASP Top 10 lists for agentic AI, plus the State of Agentic AI report, consolidated
into one walkable model. Forty source entries resolved into twenty threats across eight
surfaces, the conditions that enable them, and the harms they produce — with every original
ID still traceable.

A threat modelling aid: an architect walks it against an agentic system design and enumerates
what can go wrong. It is organised for coverage during design review, not for audit scoring
or control mapping.

## The model

Three layers and four relations between them:

| Layer | Definition | Test |
|---|---|---|
| **W** Weakness | A standing property of the system that enables threats | Is it a *condition*? Does it persist when nothing is happening? |
| **T** Threat | An act against or by the system that causes harm | Is it an *event*? Does something have to occur? |
| **I** Impact | The harm produced | Is it an *outcome*? Is it what you'd report to a regulator? |

`W → T` · `T → I` · `I → T` · `T → T`. There is no `W → I` — it is derived by composing the
first two, never stored.

**12 weaknesses · 20 threats · 6 impacts · 125 directed edges.**

Threats are organised by architectural surface — `RP` Reasoning & Planning, `KM` Knowledge &
Memory, `TA` Tools & Actions, `IA` Identity & Authority, `XA` Inter-Agent, `SC` Extensions &
Supply Chain, `RT` Runtime & Infrastructure, `HI` Human Interface — and tagged by when they
are addressed, whether an adversary is required, and whether prompt injection reaches them.

## Sources

| Document | Version | IDs | Status |
|---|---|---|---|
| OWASP GenAI LLM Top 10 | 2026 · 3 Aug 2026 | `LLM01`–`LLM10` | Current release |
| OWASP Top 10 for Agentic Applications | 2026 · 9 Dec 2025 | `ASI01`–`ASI10` | Peer-reviewed · CC BY-SA 4.0 |
| OWASP MCP Top 10 | v0.1 · Phase 3 beta | `MCP01`–`MCP10` | Draft — next release Oct 2026 |
| OWASP Agentic Skills Top 10 | v1.0 · 2026 Ed. | `AST01`–`AST10` | Incubator — public review |
| OWASP State of Agentic AI Security & Governance | v2.01 · Jun 2026 | cited by section | Current release |

All forty source entries are accounted for, and the document carries a reverse index from
every source ID to the entry covering it.

## How the numbers hold together

Every edge count, distribution and diagram in the page is derived from the register tables
themselves rather than maintained by hand — the whole-graph view is generated from the same
data the expandable rows assert, so the two cannot disagree without the page being rebuilt.

## Scope

Adversarial threats and autonomous failures are both in scope, separated by an `origin`
attribute rather than by two models. Model-level safety — refusal training, alignment of the
base model — is out of scope.

The working notes behind this document, including the decisions log, known limitations and
open questions, are kept separately and are not published here.

## Status

Draft for review. Single self-contained HTML file, no build step and no dependencies beyond
web fonts; it renders offline from a clone.
