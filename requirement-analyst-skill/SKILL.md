---
name: requirements-analysis
description: >
  Perform structured requirements analysis on any input: raw briefs, meeting notes, stakeholder
  interviews, or existing documents (PRD, BRD, specs). Use this skill whenever someone asks to
  analyze, review, clarify, or document requirements — or when inputs like feature requests,
  stakeholder notes, project briefs, or rough descriptions need to be turned into clear,
  gap-analyzed, well-structured requirements. Trigger on phrases like "analyze these requirements",
  "help me write requirements", "what's missing from this spec", "extract requirements from these
  notes", "review this PRD/BRD", "write user stories for", "turn this brief into requirements",
  or any time there is ambiguity to surface and remove from a product or system description.
  Also use proactively whenever a user shares a rough idea or problem statement and seems to
  want it developed further — don't wait for the explicit word "requirements."
---

# Requirements Analysis Skill

## Methodology Foundation

This skill is grounded in the Gause & Weinberg framework (*Exploring Requirements: Quality Before Design*), which treats requirements work as **exploration** — not documentation. The core principle:

> "The document is nothing; the documenting is everything."

Requirements work succeeds when it builds shared understanding among all stakeholders. Three conditions for project success:
1. Everyone understands the requirements
2. The team stays together to work on the project  
3. The team knows how to work effectively as a team

---

## Input Types

Handle any of these input forms:
- **Raw text / rough brief** — vague idea, problem statement, or project concept
- **Meeting notes or transcripts** — extract implicit and explicit requirements
- **Existing documents** — PRDs, BRDs, specs (analyze for gaps and ambiguity)
- **Stakeholder interview notes** — identify desires, constraints, and unstated assumptions

---

## Core Workflow: Analyze → Clarify → Document

### Phase 1: Understand the Starting Point

Every project begins with one of these starting points — identify which applies:
- **Solution idea**: "We need X" (without stating the problem it solves)
- **Technology idea**: A capability looking for a problem
- **Simile/metaphor**: "Build something like Y"
- **Norm**: "Here's an existing thing — make a better version"
- **Mockup**: A visual or prototype to react to
- **Name**: A label that implies a product

**Universal problem statement template:**
> A problem is a difference between things as perceived and things as desired.

Reframe the input using this template before proceeding. Watch for solution ideas masquerading as requirements — e.g., "we need sharper carbon copies" is a solution; "salespeople need readable copies of the report" is the real requirement.

---

### Phase 2: Context-Free Questions

Before diving into details, ask high-level questions applicable to *any* product. These reveal assumptions, scope, and priorities early.

**Process questions** (about how the work gets done):
- Who is the client? Who are the users — are they different people?
- What is a highly successful solution really worth to this client?
- What is the real reason for wanting to solve this problem?
- How much time do we have? What is the trade-off between time and value?
- Where else can the solution be obtained — can we copy something that exists?
- Who should be involved in defining the requirements?

**Product questions** (about what gets built):
- What problems does this system/product solve?
- What problems could this system/product create?
- What environment is this likely to encounter?
- What kind of precision is required or desired?

**Metaquestions** (about the requirements process itself):
- Are there answers I should be writing down for validation?
- Who is the right person to answer these questions?
- Are the answers official, or do they need sign-off?
- Is there anything else I should be asking?

---

### Phase 3: Identify Functions, Attributes, and Constraints

Structure requirements into three layers:

#### Functions (What the system must DO)
A function = something the product does to justify its existence.

Classify each function as:
- **Evident** — obvious, expected by users
- **Hidden** — not visible to users but essential (e.g., fraud detection running silently)
- **Frill** — desirable but not required; goes on the "Get It If You Can" list

**Key rule:** State functions as outcomes, not solutions. "Notify users of delivery status" not "Send push notifications." Implied solutions constrain design before it begins.

**"Get It If You Can" list:** Capture frill functions here. Heading:
> "The designers will be alert to opportunities to provide these functions whenever they can do so without trading away other functions or attributes to get them."

#### Attributes (How the system should BE)
Attributes are qualities — adjectives and adverbs applied to functions.

Steps:
1. Brainstorm a wish list (without filtering)
2. Distinguish attributes from attribute details — "longevity" is an attribute; "10 years" is an attribute detail
3. Assign each attribute to the function(s) it modifies
4. Classify as: **Must (M)**, **Want (W)**, or **Ignore (I)**
5. Document M and W attributes for constraint work

Common attribute ambiguities to watch for:
- "Cost" — capital cost? operational cost? total lifetime cost?
- "Fast" — fast for whom? under what load? how measured?
- "Easy to use" — for experts? first-time users? under stress?

#### Constraints (The mandatory boundaries on M attributes)
A constraint is a mandatory condition on a Must attribute. Requirements are only complete when every M attribute has measurable constraints that can be objectively tested.

Constraint format:
```
[Attribute] of [Function] = (specific, testable conditions)
```

Example:
> Reliability of the "display directory information" function = (fewer than 1 misinformation event per 1,000 queries, measured over a 30-day sample period)

**Test constraints for:**
- **Too strict?** — Ask "If the constraint were relaxed slightly, would that be acceptable?" If yes, loosen it; it was over-constrained.
- **Not strict enough?** — Ask "Is this solution just inside the boundary acceptable?" If no, tighten it.
- **Conflicting?** — If two constraints can't both be satisfied, the requirements are overconstrained; negotiation is needed.

---

### Phase 4: Surface and Remove Ambiguity

Ambiguity is the central enemy of requirements. Use these heuristics:

**Ambiguity Poll:**
Have multiple stakeholders independently estimate a measurable metric (time, cost, performance). Compare results — wide spread = hidden ambiguity.

**Memorization Heuristic:**
Ask stakeholders to recall the requirement from memory. Parts that aren't remembered well are likely unclear.

**"Mary had a little lamb" Heuristic:**
Read a requirement aloud several times, each time emphasizing a different word. Each emphasis may reveal a different interpretation.

**"Mary conned the trader" Heuristic:**
List all definitions of each key operational word in the requirement. Mix and match definitions to find unintended interpretations.

**Wiggle Chart approach:**
When producing diagrams or process flows, mark uncertain or unresolved areas explicitly (conceptually "wiggly lines") rather than implying false precision.

---

### Phase 5: Gap Analysis

Systematically identify what is missing:

**Missing Requirements Checklist:**
- [ ] Are all user constituencies identified? (customers ≠ users ≠ payers)
- [ ] Are hidden functions captured (not just evident ones)?
- [ ] Are there requirements that imply solutions rather than stating outcomes?
- [ ] Are all M attributes measurable with explicit constraints?
- [ ] Are there conflicting or overconstrained requirements?
- [ ] Are expectations documented and limited (not just desires)?
- [ ] Are there assumptions being made that should be stated explicitly?
- [ ] Is the "Get It If You Can" list captured to avoid suppressed wishes?
- [ ] Are there edge cases, error cases, or failure modes not covered?
- [ ] Have stakeholder-specific requirements been gathered (not just the loudest voice)?

**Requirements Leakage** — watch for assumptions that slide in as facts:
- Choices presented as impositions ("It has to be X" when X is actually negotiable)
- Assumptions that invalidate over time ("Users will always be on desktop")
- The "turnpike effect" — building requirements around the most visible use case while ignoring adjacent ones

---

### Phase 6: Document Output

Produce structured output appropriate to the context. Choose from:

**For a PRD / BRD:**
```
1. Problem Statement
   - Perceived state (what is)
   - Desired state (what should be)
   - Who experiences the problem

2. Stakeholders
   - Client (who commissions)
   - Users (who operate)
   - Affected parties

3. Functions
   - Evident functions
   - Hidden functions
   - "Get It If You Can" list (frills)

4. Attributes (per function)
   - Must (M)
   - Want (W)

5. Constraints (per M attribute)
   - Testable, measurable conditions

6. Gap Analysis
   - Ambiguities identified
   - Missing requirements
   - Conflicting or overconstrained areas
   - Open questions requiring stakeholder input

7. Assumptions Log
   - Stated assumptions
   - Assumptions to validate
```

**For User Stories:**
```
As a [specific user type],
I want to [outcome — not solution],
So that [business value].

Acceptance Criteria:
- [Measurable constraint 1]
- [Measurable constraint 2]
- [Edge case handling]
```

**For Gap Analysis report on an existing document:**
```
Summary: [Overall assessment]

Ambiguities Found:
- [Item]: [Why it's ambiguous] → [Suggested clarification]

Missing Requirements:
- [Area]: [What's absent] → [Questions to resolve]

Conflicting Requirements:
- [Req A] conflicts with [Req B] → [Negotiation needed]

Implied Solutions (should be reframed):
- "[Current wording]" → Reframe as: "[Outcome-based wording]"

Open Questions for Stakeholders:
1. [Question] — needed to resolve [issue]
```

---

## Key Principles to Apply Throughout

1. **Methodologies aren't enough** — tools handle the "clean" problems; requirements work handles the messy ones. Don't mistake a filled-out template for actual shared understanding.

2. **Maps are not territory** — requirements documents describe requirements; they are not the requirements themselves. When the map and territory disagree, believe the territory.

3. **Pay now or pay later** — ambiguities resolved implicitly during design cost far more than those resolved explicitly during requirements.

4. **The can-exist assumption** — all development starts with the assumption that a solution can exist. Requirements work is the process of clarifying that assumption.

5. **Never give clients what they need instead of what they want** — if you think you know better, convince them; don't substitute your judgment silently.

6. **Everyone who will ever use the requirements should be involved in creating them** — broaden stakeholder inclusion, not just the loudest or most senior voice.

---

## Calibrating Depth to Context

| Input Quality | Appropriate Response |
|---|---|
| Clear, structured document | Focus on gap analysis and constraint testing |
| Rough brief or idea | Start with context-free questions and problem reframing |
| Meeting notes | Extract implicit requirements, flag conflicts and gaps |
| Stakeholder interview | Identify stated vs. unstated needs; surface hidden functions |
| Vague request | Use the starting-point framework; reframe as problem statement first |

When in doubt, do *less* documenting and more *exploring* — ask one clarifying question rather than producing a premature document.
