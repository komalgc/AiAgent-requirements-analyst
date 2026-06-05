# aiagent-requirements-analyst

An AI-powered requirements analysis skill for Claude, built on the proven methodology from *Exploring Requirements: Quality Before Design* 

This skill teaches Claude to go beyond filling out templates — it explores, questions, and surfaces what stakeholders actually need before a single line of design or code is written.

---

## What It Does

Drop in any of these inputs and Claude will produce structured, gap-analyzed requirements:

| Input | What Claude does |
|---|---|
| Rough brief or idea | Reframes as a proper problem statement, asks context-free questions |
| Meeting notes / transcripts | Extracts implicit and explicit requirements, flags conflicts |
| Existing PRD / BRD / spec | Gap analysis — finds ambiguities, missing pieces, overconstrained areas |
| Stakeholder interview notes | Separates stated vs. unstated needs, surfaces hidden functions |

---

## Methodology

The skill is grounded in the **Gause & Weinberg framework** from *Exploring Requirements: Quality Before Design* — a classic that treats requirements as exploration, not documentation.

> *"The document is nothing; the documenting is everything."*

### Core Workflow

```
Analyze → Clarify → Document
```

**Phase 1 — Understand the Starting Point**
Identify whether the input is a solution idea, technology idea, simile, norm, mockup, or name — and reframe it as a proper problem statement using the universal template:
> A problem is a difference between things as perceived and things as desired.

**Phase 2 — Context-Free Questions**
Ask high-level process, product, and meta-questions that apply to any project before diving into specifics. These reveal hidden assumptions, scope, and priorities early.

**Phase 3 — Functions, Attributes, and Constraints**
Structure requirements into three layers:
- **Functions** — what the system must DO (classified as Evident, Hidden, or Frill)
- **Attributes** — how the system should BE (classified as Must / Want / Ignore)
- **Constraints** — measurable, testable boundaries on every Must attribute

**Phase 4 — Ambiguity Removal**
Apply proven heuristics:
- Ambiguity Poll
- Memorization Heuristic
- "Mary had a little lamb" Heuristic
- "Mary conned the trader" Heuristic

**Phase 5 — Gap Analysis**
Systematic checklist covering missing requirements, implied solutions, requirements leakage, stakeholder gaps, and overconstrained areas.

**Phase 6 — Document Output**
Produces the right format for the context: PRD/BRD structure, user stories with acceptance criteria, or a gap analysis report.

---

## Files

```
aiagent-requirements-analyst/
├── README.md
├── SKILL.md                        # The skill instructions for Claude
└── requirements-analysis.skill     # Packaged skill file (installable)
```

---

## How to Install

### Option A — Claude Code / Cowork
1. Download `requirements-analysis.skill`
2. Install it into your Claude Code or Cowork environment
3. Claude will automatically trigger the skill when you ask about requirements

### Option B — Manual (any Claude interface)
1. Open `SKILL.md`
2. Copy the contents into your Claude system prompt or paste it at the start of a conversation
3. Start sending requirements inputs

---

## Example Usage

**Input:** A rough project brief
```
We want to build a notification system for our mobile app.
```

**Claude will:**
1. Reframe it — "We need sharper notifications" is a solution; what's the actual problem?
2. Ask context-free questions — who are the users, what does success look like, what's the real reason?
3. Extract functions — notify users of X, notify admins of Y (evident vs. hidden)
4. Define attributes — reliable, low-latency, multilingual (Must vs. Want)
5. Set constraints — "delivery confirmation within 2 seconds for 99.9% of messages"
6. Surface gaps — "Are push notifications the only channel, or also email/SMS?"

---

## Key Principles

1. **Methodologies aren't enough** — templates handle clean problems; this skill handles messy ones
2. **Maps are not territory** — requirements documents describe requirements; they are not the requirements
3. **Pay now or pay later** — ambiguity resolved during requirements costs far less than during design or development
4. **Never give clients what they need instead of what they want** — surface the real desire, then guide
5. **Explore before you document** — ask one good question rather than produce a premature document


---

## Contributing

Found a gap in the skill? Have a requirements methodology you'd like to add? PRs are welcome.

1. Fork the repo
2. Edit `SKILL.md`
3. Test it against a few real requirements inputs
4. Submit a PR with what you changed and why

---

## License

MIT — use it, adapt it, share it.
