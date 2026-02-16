# AI System Design Notes

How I think about integrating AI into production systems.

Each design review starts with a realistic customer problem in a professional domain and works through a rigorous system design analysis. These are artifacts of a design process: the kind of reasoning I'd bring to a real architecture review. Architecture decisions depend on context — your stack, your team, your constraints. This is how I think through the problem, not how you should.

---

## The Approach

Every design review follows the same structure.

1. **System Context & Constraints** — What's the environment? What are the stakes, scale, and latency budget?
2. **What I Would Not Do** — Before designing anything, what's the trap? What looks appealing but breaks?
3. **Metrics & Success Criteria** — What does "working" mean? Offline evaluation vs. online signals.
4. **Data Strategy** — What data exists? Quality, lineage, feature engineering trade-offs.
5. **Architecture & Data Flow** — Components, interfaces, token budgets, serving path.
6. **Failure Modes & Detection** — How does this go wrong? How would you know? What fails silently?
7. **Mitigations & Deployment** — Fallbacks, human-in-the-loop, A/B testing, canary rollouts, rollback strategy.
8. **Cost Model** — Real numbers, not "it depends." What does this cost at scale?
9. **Security & Compliance** — Data privacy, adversarial robustness, governance.
10. **What Would Change My Mind** — Explicit uncertainty. Conditions under which this advice is wrong.

Every design review includes concrete artifacts: architecture diagrams, failure taxonomies, cost tables.

---

## Design Reviews

| #   | Title         | Domain | Date |
| --- | ------------- | ------ | ---- |
| 001 | [AI-Assisted Ticket Triage & Agent Response Suggestion for B2B SaaS Support](design-reviews/001-customer-support-ticket-triage/) | Customer Support | 2026-02-16 |

---

## Core Beliefs

1. **AI is a system component, not a feature.** Features get bolted on; components get designed — with interfaces, budgets, failure modes, and observability.
2. **Production failures are more important than demo success.** Demos hide decisions. Production exposes them.
3. **Silent failure is more dangerous than loud failure.** A system that fails visibly can be fixed. A system that fails silently erodes trust invisibly.
4. **Engineering judgment matters more as systems become probabilistic.** Deterministic systems can be tested exhaustively. Probabilistic systems require judgment about acceptable risk.
5. **Data quality determines system ceiling.** No architecture, model, or prompt strategy compensates for upstream data problems.
6. **Technical debt in AI systems compounds silently.** It hides in data dependencies, feedback loops, and pipeline complexity — invisible until it paralyzes you.
7. **Judgment must be local to constraints.** No universal claims about "the industry" or "most teams." Every refusal is scoped to a specific system context.
8. **Data is foundational, not incidental.** Source, quality, lineage, and privacy are design decisions — not afterthoughts.
9. **Build and Run are distinct disciplines.** Building AI systems and running AI systems require different skills, artifacts, and failure mode awareness.
10. **AI systems require continuous learning.** Build, Run, Learn is a loop, not a sequence. Systems that don't learn from production feedback degrade.

These beliefs are expanded in my [Mental Models for Production AI](https://prompt-deploy.beehiiv.com/archive?tags=Mental+Models+for+Production+AI) series.

## Join the Conversation

Have a different take? See a failure mode I missed? Think the cost model is off?

[Open an issue](../../issues) — I'd like to hear how you'd approach it differently.

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE).

You are free to share and adapt this material for any purpose, including commercial, as long as you give appropriate credit.
