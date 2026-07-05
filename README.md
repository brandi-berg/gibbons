# Gibbons 🐒 (v2.0)

### An AI-Powered Recruiting Command Center & Agentic Workflow System for Claude Cowork.

Gibbons is an advanced, step-by-step prompt engineering architecture deployed as a native **Cowork Plugin** rather than a standard chat framework[cite: 3]. By utilizing modular, state-persistent skills, Gibbons enforces absolute workflow execution discipline—taking modern technical roles from rough Slack request triggers to evidence-grounded candidate conversion without context decay across sessions[cite: 3].

---

## 🏗️ Core Architectural Principles

* **Candidate Truth Rules:** Every claim about a candidate must trace to explicit text in their profile[cite: 1, 3]. Zero inference[cite: 1, 3]. If a candidate profile lacks data, it is flagged as `Information not provided`—never filled with plausible AI guesses[cite: 3].
* **Context Binding via Reference Files:** System behaviors are tightly bounded by local configuration profiles (`Section_A_Technical_Guardrails.md`, `Section_B_About_Me.md`, and `Section_C_ICP.md`)[cite: 1, 3]. If any output reads like a generic template that could apply to a competitor, it fails the verification gate[cite: 1, 3].
* **Adversarial Pre-Mortems:** Integrated adversarial loops (`/redteam`) challenge assumptions before sourcing begins and evaluate friction barriers before outreach sequence deployment[cite: 3].

---

## 🛠️ Command Namespace Reference

Gibbons operates via an explicit set of invokable slash commands[cite: 3]. The system acts as a deterministic pipeline where Phase 1 intake artifacts programmatically feed and anchor Phase 2 calibration data[cite: 3].

| Command | Phase | Underlying Source File | Core Deliverable Function |
| :--- | :--- | :--- | :--- |
| `/enhance` | Phase 1 | `GIBBONS-JD_Enhancement.md` | Cleans raw JDs, optimizes for search clarity, removes implicit bias[cite: 3]. |
| `/kickoff` | Phase 1 | `GIBBONS-Kickoff_Prep_Guide.md` | Generates critical challenge questions to prep for the hiring manager meeting[cite: 3]. |
| `/okr` | Phase 1 | `GIBBONS-OKR_KPI_Builder.md` | Translates alignment signals into 5 first-year objectives with target KPIs[cite: 3]. |
| `/interview` | Phase 1 | `GIBBONS-Interview_Kit_Builder.md` | Builds an aligned panel interview framework with standardized rubrics[cite: 3]. |
| `/signals` | Utility | `GIBBONS-Kickoff_Signal_Extraction.md` | Extracts 6 precise signal types from raw hiring manager intake transcripts[cite: 3]. |
| `/detox` | Utility | `GIBBONS-JD_Detox.md` | Lightweight, fast-pass jargon and structural bloat stripper for rough briefs[cite: 3]. |
| `/rewrite` | Utility | `GIBBONS-Section_Rewrite.md` | Isolated execution block to adjust a single specified section of an artifact[cite: 3]. |
| `/validate` | Phase 2 | `GIBBONS-Candidate_Validation.md` | **Candidate assessment only.** Maps hard profile text against core JD criteria (Score 1-5)[cite: 3]. |
| `/external` | Phase 2 | `GIBBONS-External_Company_Research.md` | Deep intel brief on candidate background employers or sourcing target lists[cite: 3]. |
| `/redteam` | Guardrail | `GIBBONS-Red_Team.md` | Adversarial pre-mortem engine (Role Failure Check / Outreach Decline Check)[cite: 3]. |
| `/outreach` | Phase 2 | `GIBBONS-Candidate_Outreach.md` | Constructs custom 4-part engagement templates (Tension A-D) tied to source data[cite: 3]. |
| `/voice-tone` | Config | `GIBBONS-Section_B_About_Me.md` | Injects local persona parameters, communication styles, and recruiter voice variables[cite: 3]. |

---

## ⚙️ Platform Skills Integration & Wiring Rules

Gibbons links directly to two specialized platform automation tools natively inside Cowork[cite: 3]. These tools do not gate candidate tracking; instead, they enrich the systemic data layer with context validation[cite: 3].

### 1. `skillsmate` (Sourcing Strategy Engine)
* **Execution Window:** Triggers immediately following the post-kickoff `/enhance` finalization step[cite: 3].
* **Function:** Compiles a ranked *Skills Density Index* of competitors actively competing for matching technical talent, delivering clean search string booleans directly to the recruiter[cite: 3].

### 2. `intelmate` (Competitor Intelligence Collector)
* **Execution Window:** Invoked natively during `/external` company research lookups or inside `/redteam` decline pre-mortems[cite: 3].
* **Function:** Automatically scrapes careers pages, extracts raw compensation configurations, maps competitive talent branding, and builds conversion battle cards[cite: 3].

```text
[Standard End-to-End Sequence Map]
Final /enhance ➔ skillsmate ➔ Sourcing Pass ➔ /validate ➔ /external + intelmate ➔ /redteam Pre-Mortem ➔ /outreach
