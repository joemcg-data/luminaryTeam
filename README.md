# Luminary Planning

A multi-agent technical review framework. Drop in your codebase, feature spec, or architecture decision and get a structured audit from 19 domain-expert personas — each independent, each adversarial, each synthesized into actionable recommendations.

---

## How It Works

Luminary runs a six-phase protocol orchestrated by a neutral coordinator. Every claim must cite a specific artifact. No domain gets a pass for "nothing to report." Conflicts produce steelmanned debates, not silent compromise.

### Phase 1 — Frame & Scope
The orchestrator summarizes the input, selects the relevant roster subset, and defines what "done" looks like before any audit begins.

### Phase 2 — Independent Audit
Each member audits from their domain lens alone. No cross-member coordination. No groupthink.

### Phase 3 — Red Flag Declaration
One blocking red flag per member, maximum. Forced prioritization. Must cite evidence.

### Phase 4 — Adversarial Clash
Members with conflicting positions debate directly. The steelman rule is enforced: you must argue the opponent's position charitably before your rebuttal — skipping it disqualifies the rebuttal.

### Phase 5 — Synthesis
The orchestrator resolves conflicts into a structured recommendation matrix with clear owners and verification paths.

### Phase 6 — Iteration
Drill in on any finding. Request re-audits. Ask members to respond to new information.

---

## Priority Levels

| Level | Label | Meaning |
|---|---|---|
| **P0** | BLOCKER | Unsafe, incorrect, or irreversible. Work stops until resolved. |
| **P1** | CRITICAL | Significant risk. Deferral requires orchestrator approval + documented rationale. |
| **P2** | IMPORTANT | Quality/robustness gain. Defer to next phase with a tracked ticket. |
| **P3** | IMPROVEMENT | Non-blocking enhancement. Future work. |

---

## The 19-Member Roster

Each agent brings a specific domain, a defined personality, explicit conflict vectors, and a signature challenge question. Select the subset relevant to your audit — you don't need all 19 every time.

| Agent | Domain | Core Focus |
|---|---|---|
| **Linus Torvalds** | Architecture & Maintainability | Modularity, justified complexity, no premature generalization |
| **John Carmack** | Performance & Optimization | Hot paths, memory layout, O(n) analysis — benchmarks not intuitions |
| **Grace Jansen** | Developer Experience & Tooling | Onboarding, readable code, useful errors, docs without tribal knowledge |
| **Arnauld Lauret** | API Design & Governance | Interface consistency, naming coherence, RFC correctness |
| **Don Norman** | UX & Interaction Design | Mental models, affordance, feedback loops, error recovery |
| **Julie Zhuo** | UI & Visual Design Systems | Visual hierarchy, component consistency, design token discipline |
| **Joe Celko** | SQL & Data Modeling | Schema correctness, normalization, NULL semantics, query performance |
| **Martin Kleppmann** | Distributed Systems & Data | Event sourcing, consistency guarantees, idempotency, replication lag |
| **Eric Evans** | Domain Modeling | Bounded contexts, ubiquitous language, aggregate design |
| **Steve Jobs** | Product Quality & Customer Experience | Whether it's genuinely great — not feature-complete, but inevitable |
| **James Bach** | Testing & QA Strategy | Whether tests find real bugs — not coverage, not CI green |
| **Bruce Schneier** | Security & Threat Modeling | Crypto correctness, auth/authz, secrets management, threat models |
| **Andrej Karpathy** | AI/ML & LLM Integration | Prompt injection, model evaluation, hallucination failure modes |
| **Charity Majors** | Infrastructure & Observability | Deployment pipelines, structured telemetry, SLOs, incident debuggability |
| **Marcy Sutton** | Accessibility | WCAG compliance, keyboard nav, screen reader semantics, focus management |
| **Ann Cavoukian** | Privacy & Data Governance | Privacy by Design, data minimization, PII handling, retention policy |
| **Edward Tufte** | Data Visualization | Data-ink ratio, chartjunk, information density, whether viz encodes truth |
| **Hadley Wickham** | Data Science & Analytics | Tidy data, pipeline reproducibility, grammar of graphics |
| **Andrew Gelman** | Statistical Rigor | Metrics validity, A/B test power, false positive rates, overconfident inference |

---

## Usage

### Option A — Full Team Audit
Paste the `luminaryPrompt.md` into a Claude project (or any LLM with large context). Include your codebase, spec, or architecture doc. The orchestrator selects the relevant subset and runs the protocol.

### Option B — Single Agent
Load a specific `agent*.md` file for a focused single-domain review. Useful when you know the problem domain but want structured, rigorous feedback from that lens.

### Option C — Custom Roster
Select 3–7 agents whose domains cover your highest-risk areas. Paste `luminaryPrompt.md` plus the selected agent files. Specify "use only these members" in your prompt.

---

## Protocol Rules

- **Cite or retract** — any claim without a specific code/spec artifact reference is inadmissible
- **Steelman enforced** — in adversarial clash, you argue the opponent's position before your rebuttal
- **One red flag maximum** — per member per audit cycle (forces real prioritization)
- **No silent pass** — "nothing to report" requires active investigation of edge cases
- **Orchestrator stays neutral** — mediates process and resolves deadlock, never takes domain positions
- **Synthesis is actionable** — every recommendation gets an owner and a verification path

---

## File Structure

```
luminaryProcess/
├── luminaryPrompt.md          # Master orchestrator + protocol
├── agentLinusTorvalds.md
├── agentJohnCarmack.md
├── agentGraceJansen.md
├── agentArnauldLauret.md
├── agentDonNorman.md
├── agentJulieZhuo.md
├── agentJoeCelko.md
├── agentMartinKleppmann.md
├── agentEricEvans.md
├── agentSteveJobs.md
├── agentJamesBach.md
├── agentBruceSchneier.md
├── agentAndrejKarpathy.md
├── agentCharityMajors.md
├── agentMarcySutton.md
├── agentAnnCavoukian.md
├── agentEdwardTufte.md
├── agentHadleyWickham.md
└── agentAndrewGelman.md
```

---

## Conflict Map

Some members reliably clash. These tensions are features, not bugs — they surface real trade-offs.

- **Carmack vs. Evans** — Performance optimization vs. domain model purity
- **Jobs vs. Bach** — Ship great things fast vs. prove nothing is broken first
- **Kleppmann vs. Torvalds** — Embrace distributed complexity vs. keep it simple and modular
- **Schneier vs. Karpathy** — Deterministic threat models vs. probabilistic LLM failure modes
- **Cavoukian vs. Majors** — Data minimization vs. instrument everything for observability

---

## What It's Not

Luminary is not a replacement for human judgment. It's a forcing function — a structured way to ensure the right questions get asked before decisions get made. The synthesis is a starting point for your team's conversation, not the end of it.
