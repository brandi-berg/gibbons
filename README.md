# Gibbons 🐒

### An AI-Powered Recruiting Command Center & Agentic Workflow System for Claude Cowork.

Gibbons is a structured, step-by-step prompt engineering architecture built to run seamlessly inside Claude. Instead of relying on unpredictable, generic AI chat loops, Gibbons treats LLM orchestration like production software—imposing strict operational guardrails, context layers, and cross-session state persistence.

---

## 🏗️ Architectural Core Principles

* **Candidate Truth Rules:** Every claim about a candidate must trace to explicit text in their profile. Zero inference. Zero gap-filling.
* **Context Binding:** System behaviors are tightly bound by local configurations (Recruiter Voice & Tone, Ideal Candidate Profiles, and Company Values). If an output could apply to any generic company, it fails the gate check.
* **Carry-Forward Architecture:** State and context persist between isolated LLM chat sessions via deterministic markdown handoff blocks. No re-pasting raw data.

---

## 🛠️ Command Reference & Workflow

Gibbons operates in two distinct execution phases. Every role moves through the same sequence—no skipping steps, as each output programmatically feeds the next.

| Command | Phase | Description | Key Outputs |
| :--- | :--- | :--- | :--- |
| `/enhance` | Phase 1: Intake | Detoxes raw JDs, removes implicit bias, inflates clarity, and adds search-optimized terms. | Cleaned JD, Search Keywords, Handoff Block |
| `/kickoff` | Phase 1: Intake | Identifies business risks and challenges untested hiring assumptions to prep for the hiring manager. | Risk Flags, 7-10 Strategic Questions |
| `/okr` | Phase 1: Intake | Translates kickoff notes into 5 concrete first-year objectives with measurable key results. | 5 Performance OKRs, Target KPIs |
| `/interview` | Phase 1: Intake | Produces a full, structured evaluation framework. | 16 Questions across 4 structured panels |
| `/validate` | Phase 2: Calibration | Evaluates candidate profiles purely against evidence mapped directly to the enhanced JD. | Signal Strength Rating (1-5), Gap Analysis |
| `/external` | Phase 2: Sourcing | Optional deep-dive intelligence brief on a candidate's current or prior employer. | 14-Section Intel Base, Pitch Angles |
| `/outreach` | Phase 2: Outreach | Crafts 4 personalized outreach messages using a Hook/Bridge/Value/CTA framework. | 4 Sequence Messages (Tensions A-D) |
| `/detox` | Utility | Lightweight Jargon and bias stripper for quick passes. | Sanitized text, Removed Items Log |

---

## 📂 Repository Structure

```text
gibbons/
├── config/
│   ├── Section_A_Technical_Guardrails.md  # Core engineering constraints
│   ├── Section_B_About_Me.md              # Recruiter voice & tone mapping
│   └── Section_C_ICP_Values.md            # Target ideal candidate context
├── skills/                                # Prompt logic per slash command
│   ├── jd_enhancement.md                  
│   ├── kickoff_prep.md                    
│   ├── okr_kpi_builder.md                 
│   └── candidate_validation.md            
├── docs/
│   └── overview.html                      # Interactive visual dashboard
└── README.md                              # Framework documentation
