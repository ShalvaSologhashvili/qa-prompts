# QA Prompt Library

A collection of reusable AI prompts for structured QA activities — designed to work with any AI assistant (Claude, ChatGPT, etc.). Each prompt follows a consistent pattern: static instructions that never change, and dynamic fields in `[brackets]` that you fill in per story, feature, or session.

---

## How to use

1. Open the prompt file for the activity you need
2. Fill in every `[bracketed]` field with context specific to your feature
3. Paste the completed prompt into your AI assistant
4. Get a structured, production-grade output ready to use

---

## Prompts

### Test Case Design
**File:** `test-case-design.md`

Generates a complete test suite for a feature or user story. Give it your acceptance criteria and a description of what the system does — it produces a full markdown table of test cases grouped by area, covering positive, negative, edge, security, and bypass scenarios. Ends with a traceability matrix mapping test case IDs back to your AC.

---

### Exploratory Testing Session
**File:** `exploratory-testing.md`

Structures an exploratory testing session around a defined charter and time-box. Give it your feature area, session goal, and duration — it produces a pre-session risk analysis, a findings log template, a coverage map, and bug report stubs ready to fill in during the session.

---

### Bug Analysis
**File:** `bug-analysis.md`

Performs a deep analysis of a reported defect. Give it the bug report and any additional context — it produces a root cause analysis with confidence level, a severity and priority assessment table, refined reproduction steps, and a fix recommendation with trade-offs. Ends with an executive summary suitable for stakeholder communication.

---

## Dynamic fields reference

Every prompt uses `[brackets]` for the parts that change per use. Common fields across all prompts:

| Field | What to put here |
|---|---|
| `[Platform / Environment]` | Web, iOS, Android, API — be specific about browsers/versions |
| `[Target System]` | Direct URL to the feature or endpoint being tested |
| `[Feature / Area]` | Name of the story, feature, or system area |
| `[Constraints / Out of Scope]` | What is explicitly not being tested in this session |

---

## Status

Work in progress — prompts are added and refined as new QA activities are covered.