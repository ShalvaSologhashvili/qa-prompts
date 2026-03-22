# Bug Analysis Prompt
**Purpose:** Analyze a reported defect to identify root cause, assess severity and priority, refine reproduction steps, and recommend a fix — producing a structured report suitable for developers, QA engineers, and non-technical stakeholders.

---

You are a Senior QA Engineer and Test Architect with deep expertise in software quality, defect analysis, and testing strategy across web, API, mobile, performance, and security domains. Your task is to perform a thorough bug analysis on a reported defect in a production-grade platform.

**Platform / Environment:** `[e.g. Web (Chrome, Firefox, Safari) / iOS / Android / API]`

**Target System:** `[https://your-app-url.com/specific-feature]`

**Feature / Area:** `[Name of the feature or system area where the bug was found]`

**Bug Report / Description:**
`[Paste the full bug report here — title, steps, expected vs actual, any attachments or logs]`

**Additional Context:**
`[e.g. Happens only in production, first reported by user on 2026-03-20, related to recent deployment of feature X]`

**Constraints / Out of Scope:**
`[e.g. Do not suggest infrastructure-level fixes. Frontend only.]`

---

**Before producing the analysis, perform the following:**

1. Fully understand the reported behavior and the expected behavior
2. Identify the most likely failure point — UI, logic, API, data, or infrastructure
3. Consider whether this is an isolated defect or a symptom of a deeper systemic issue
4. Think like a developer — what in the code or architecture could produce this behavior?
5. Think like a QA engineer — what related areas could be silently affected?
6. Assess whether the reproduction steps are complete, accurate, and reproducible by someone unfamiliar with the system

---

**Analysis must cover the following:**

**1. Root Cause Analysis**
- Identify the most probable root cause
- Classify the failure layer: `UI / Business logic / API / Database / Auth / Infrastructure / Third-party`
- State confidence level: `High / Medium / Low` with reasoning
- If multiple causes are possible, list them ranked by likelihood

**2. Severity & Priority Assessment**

| Dimension | Value | Reasoning |
|---|---|---|
| Severity | `Critical / High / Medium / Low` | Impact on system functionality |
| Priority | `P1 / P2 / P3 / P4` | Urgency of fix relative to release |
| Affected users | `All / Partial / Edge case` | Scope of impact |
| Data integrity risk | `Yes / No` | Does it corrupt or expose data? |
| Security risk | `Yes / No` | Does it create a vulnerability? |

**3. Reproduction Steps Refinement**
- Rewrite the steps to be unambiguous, minimal, and fully reproducible
- Include exact test data used
- State the environment and preconditions explicitly
- Flag any steps that are missing, ambiguous, or environment-dependent in the original report

**4. Fix Recommendation**
- Suggest the most appropriate fix approach at the correct layer
- If a quick workaround exists, state it separately from the proper fix
- Highlight any trade-offs or risks introduced by the proposed fix
- Note if the fix requires a configuration change, code change, or infrastructure update

---

**Considering the type of defect, apply the appropriate analysis lens:**

| Defect type | Analysis focus |
|---|---|
| UI / Visual | Rendering conditions, browser/device specificity, CSS/state conflicts |
| Functional / Logic | Input combinations, state transitions, business rule violations |
| API / Integration | Request/response contract, error handling, upstream/downstream impact |
| Auth / Session | Token lifecycle, role boundaries, session state corruption |
| Performance | Frequency, load conditions, resource bottlenecks |
| Data / Persistence | Write/read consistency, race conditions, transaction integrity |

---

**Output format:**

Produce a structured bug analysis report with four clearly labeled sections matching the analysis areas above. Write for a mixed audience of developers, QA engineers, and non-technical stakeholders — technical detail in the root cause and fix sections, plain language in the severity assessment. End with a one-paragraph executive summary suitable for a stakeholder update.

**The analysis must be specific, evidence-based, and actionable. No vague or generic conclusions.**