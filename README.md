### Anmol Jain

SWE Trainee @ Bizom · Research Intern (GNN-based financial forecasting) @ NIT Rourkela · CGPA 9.15/10

**Currently:**
- 🔭 Building production systems — most recently an agentic pipeline at Bizom that generates test code by combining an LLM with live Android device control
- 🔬 Researching GNNs + attention-based models for multi-horizon financial time series forecasting
- 🎯 Prepping for SDE-1 placements — DSA, system design, distributed systems
- 🏆 Finalist, Amazon HackOn 6.0 — top 30 of 70,000+ participants

---

#### Engineering, with receipts

Specific problems I've actually solved, not a list of buzzwords:

| Problem | What I built | Result |
|---|---|---|
| QA test-case authoring took 30–45 min each, by hand | Agentic pipeline: LLM reasoning + live Appium device control + a 142,917-edge codebase knowledge graph, so it never generates code that already exists | **~2 min per test case** |
| Every task-visibility check in a multi-tenant SaaS required walking a role hierarchy tree | Materialized permissions into a junction table at task-creation time | **O(1) reads**, not a recursive tree-walk on every request |
| Full-codebase context made LLM calls slow and expensive | Dynamic context selection — only the page classes relevant to the current module go into the prompt | **~80% token reduction** |
| A CA-firm SaaS was loading in ~10s because of N+1 redundant DB queries | Deduped profile lookups via React `cache()`, merged into one parallel query tier | **~3s page load** |

#### One bug worth telling properly

Building a multi-tenant permissions system, I hit infinite recursion: an RLS policy on a permissions table referenced that same table in its own subquery, so Postgres's policy evaluator looped forever. Fixed it with four `SECURITY DEFINER` helper functions with `search_path` pinned explicitly — that's what breaks the recursive evaluation loop. Turned into a real dive into how Postgres actually evaluates RLS policies, not just a syntax fix.

---

#### Featured work

| Project | What it is |
|---|---|
| [Filio](https://github.com/anmol0705/REPLACE_ME) | Multi-tenant work-management SaaS for CA firms — real product, used in production by a real firm, not a course project. 11-table Postgres schema, 3-layer defense-in-depth security (app-layer → RLS → service-role), recursive-CTE role hierarchy |
| [cms-saas](https://github.com/anmol0705/REPLACE_ME) | Multi-tenant headless CMS in Go — async LLM content generation via Redis/Asynq, tiered Stripe billing, row-level tenant isolation |
| [ClaimSense](https://github.com/anmol0705/REPLACE_ME) | Motor-insurance telematics platform — architected the on-device AI pipeline (TensorFlow + scikit-learn + ONNX Runtime, YOLOv5-based CV fused with sensor data), led a 4-person team through live-vehicle validation |
| [Open-Source Apprenticeship System](https://github.com/anmol0705/OpenSource_System) | LangGraph mentor agent that teaches contributors to fix real GitHub issues themselves via proficiency-calibrated hints — never writes the fix for them |
| [retailmind](https://github.com/anmol0705/REPLACE_ME) | GNN-based (LightGCN) product recommendation engine with a full MLOps loop — DVC, MLflow, Docker, CI/CD |

---

#### Stack (grouped by how deep the evidence actually goes)

**Used across multiple real projects:** Python, C++, SQL, TypeScript/JavaScript, FastAPI, React, Next.js, Docker, PyTorch, scikit-learn

**Used in one project, real but narrower:** Go, PyTorch Geometric (research internship), Supabase + Postgres RLS, LangGraph/LangChain (Apprenticeship system)

<!--START_SECTION:activity-->
<!--END_SECTION:activity-->

---

🏆 Amazon HackOn 6.0 Finalist (top 30/70,000+) · AlgoUtsav Runner-Up (top 1%/150+ teams) · Codeforces Specialist · CodeChef 3-Star
📫 [your email or LinkedIn]
