# 📚 Prompt Library — [2D ANIMATION ]

> **Assessment 1 | Generative AI for Business**  
> Student: [JADE NGUYEN] | Business Field: [ BACKGROUND ARTIST OPTIMIZATION ]  
> Model tested on: [Claude Sonnet 4, GPT-4o, Gemini ]  
> Last updated: [Date]

---

## What This Library Does

This prompt library supports workflow automation in 2D Background in a Midlevel animation studio. It contains 10 documented, tested, and iterated prompts organised by the business function they support.

Each prompt entry follows the same structure:
- The exact prompt text (with placeholders)
- The workflow task it supports
- The problem it solves
- Its automation potential
- Known risks and mitigations
- Version history and test results

---

## 📂 Folder Structure

```
prompt-library/
│
├── README.md
|                
├── 01-planning/
│   ├── README.md                   
│   ├── P01-brief-script-interpretation.md
│   └── P02-workload-prioritisation.md
│
├── 02-pre-production/
│   ├── README.md
│   ├── P03-reference-collection.md
│   ├── P04-layout-composition.md
│   └── P05-colourkey-lighting-mood.md
│ 
├── 03-production/
│   ├── README.md
│   ├── P06-style-matching-checker.md
│   ├── P07-missing-detail-identifier.md
│   └── P08-asset-documentation.md
│
└── 04-review-handoff/
    ├── README.md
    ├── P09-quality-checklist-review.md
    └── P10-handoff-brief.md
```


## 📊 Library Summary Table

| ID | Prompt Name | Workflow | Automation Level | Risk Level | Status |
|----|-------------|----------|-----------------|------------|--------|
| P01 | Brief & Script Interpretation | Planning | High | Medium | ✅ Tested |
| P02 | Workload Prioritisation | Planning | High | Low | ✅ Tested |
| P03 | Reference Collection Generator | Pre-production | High | Low | ✅ Tested |
| P04 | Layout & Composition Generator | Pre-production | Medium | Medium | ✅ Tested |
| P05 | Colourkey, Lighting & Mood Generator | Pre-production | High | Medium | ✅ Tested |
| P06 | Style Matching Checker | Production | High | Medium | ✅ Tested |
| P07 | Missing Detail Identifier | Production | Medium | Medium | ✅ Tested |
| P08 | Asset Documentation | Production | Very High | Low | ✅ Tested |
| P09 | Quality Checklist Review | Review & Handoff | Medium | High | 🔄 In progress |
| P10 | Handoff Brief | Review & Handoff | High | Medium | 🔄 In progress |

**Automation levels:** Very High / High / Medium / Low  
**Risk levels:** High (always needs human review) / Medium (spot-check recommended) / Low (can automate with audit)

---

## 🔗 Prompt Chaining Map

Some prompts in this library are designed to work in sequence. The chains below show how outputs from one prompt feed the next.

```
PLANNING CHAIN
P01 (Brief & Script Interpretation) → P02 (Workload Prioritisation)

PRE-PRODUCTION CHAIN  
P01 (Brief & Script Interpretation) → P03 (Reference Collection) → P04 (Layout & Composition Brief) → P05 ( Colourkey, Lighting & Mood generator ) 

PRODUCTION CHAIN
P04 (Layout & Composition Brief) → P06 → P07 → P08

REVIEW & HANDOFF CHAIN
P08 (Asset Documentation) → P09 (Quality Checklist Review) → P10 (Handoff Brief)
P02 (Workload Prioritisation)→ P10 (Handoff Brief)
```

---

## ⚙️ Prompting Strategies Used

| Strategy | Prompts | Why chosen |
|----------|---------|------------|
| RACE framework (Role–Action–Context–Evaluation) | P01, P03, P05, P10 | Consistent structure; comparable outputs for A/B testing |
| Grounding constraint ("using only...") | P06, P09 | Prevents hallucination against style guide |
| Structured output format | P06 | Machine-readable for CRM/API integration |
| Style constraints | P04, P05, P06 | Maintain visual consistency |
| Self-critique step | P07, P09 | Model reviews its own output for gaps |
| Word/format limits | All | Ensures production-ready output without heavy editing |

---

## 📝 Iteration Evidence

All prompt versions are saved in this repository. See individual prompt files for version histories.  
**Commit history = version log** — each commit message describes what changed and why.

| Prompt | Versions | Key improvement |
|--------|----------|-----------------|
| P01 | v1.0 → v1.2 | Added RACE role + word limit; edit time 14 min → 2 min |
| P04 | v1.0 → v1.1 | Grounding constraint added after v1.0 hallucinated causes |
| P06 | v1.0 → v1.2 | Constrained category list added; JSON output enforced |

---

## 📖 References

- Anthropic (2025). *Prompt Engineering Overview.* docs.claude.ai
- Kartaca (2026). *Standardizing Enterprise Intelligence with a Corporate Prompt Library.*
- MIT Sloan (2025). *Prompt Engineering is So 2024 — Try These Prompt Templates Instead.*
- Microsoft (2025). *Get Started with Prompt Library — Copilot Studio.*
- VE3 Global (2025). *10 Key Elements of a Prompt Library for Enterprise Tasks.*
