# Worked Example — Senior ML Engineer, Airbnb (Supply & Competitive Intelligence)

A complete, end-to-end tailored application built from the live JD + your real
resume. This is the template for how to attack any high-value role. Replace
`[BRACKETS]` with real numbers — **nothing here is fabricated; gaps are flagged, not faked.**

- **Role:** [Senior Machine Learning Engineer, Airbnb](https://to.indeed.com/aacztgvzwmqz) · Remote (US) · **$196k–$227k**
- **Company signal (Indeed):** Interview difficulty *Medium*, experience *Excellent*,
  process ~*1 week*; CEO approval 74%; 81% recommend to a friend. A strong, fast process — worth tailoring for.

---

## ⚠️ Knockout check FIRST (do this before tailoring anything)

The JD says: *"you must live in a state where Airbnb, Inc. has a registered entity"* —
**this role requires US work authorization + US residence.** Your education is UK
(Imperial, Derby). **If you're not authorized to work in the US, skip this one** — no
amount of tailoring beats a hard eligibility gate, and a mismatched answer just burns
the application. (This is exactly why `targeting-config.md` says pick one authorized
market.) The rest of this doc assumes US-eligible; the *method* applies to any role.

---

## Step 1 — ATS keyword-gap analysis

| JD requirement | On your resume? | Action |
|---|---|---|
| Python (required) | ✅ Python | Lead with it |
| Scala / Java for backend | ✅ Scala, Java | Keep, name both |
| Production ML at global scale | ✅ Meta SWE | Make this bullet #1 |
| TensorFlow **or** PyTorch | ✅ TensorFlow | Covered (JD accepts either) |
| End-to-end ML pipelines (batch + real-time) | ⚠️ Hadoop/data modeling = batch only | Add real-time/serving if true |
| Feature engineering, model selection | ⚠️ "Machine Learning" generic | Name these explicitly if true |
| A/B testing | ❌ not listed | **Add if you've done it** (you likely have at Meta) |
| Gradient boosted trees, neural nets, transformers, embeddings | ❌ not explicit | Name the specific algorithms you've used |
| Entity resolution / matching | ❌ domain-specific | Add only if true; else leave |
| CI/CD, TDD, incremental delivery | ✅ Docker, K8s, Jenkins, Azure DevOps, Git | Group as "MLOps/CI-CD" |
| Resilient data infra, extensible APIs | ✅ Solutions Architect @ Accenture | Pull one bullet from Accenture |
| 5–10 yrs applied ML | ⚠️ Borderline — total exp ~8 yrs, *applied ML* less | State years honestly in summary |
| BS/MS/PhD in CS/ML | ✅ MS Imperial | Strong — keep prominent |

**Verdict:** strong match on languages, production scale, TensorFlow, MLOps, and
degree. Real gaps to *honestly* close: name specific **algorithms** (GBTs/transformers/
embeddings), **A/B testing**, and **real-time serving**. If you've genuinely done these
at Meta, add them — they're high-weight ATS keywords here.

## Step 2 — Tailored Summary (paste into resume top)

```
Machine Learning Engineer with [X] years building and deploying production ML at
global scale, currently at Meta. Strong in Python (plus Scala/Java), TensorFlow,
and end-to-end ML pipelines from feature engineering to low-latency serving.
Experienced in A/B testing and [GBTs / neural networks / transformers — keep only
what's true]. MS, Imperial College London; AWS Certified Solutions Architect.
```
*Why:* mirrors the JD's exact phrases ("production ML at global scale", "Python",
"feature engineering", "low-latency serving") in the first 3 lines the ATS weights most.

## Step 3 — Reordered experience bullets (lead with the match)

```
Software Engineer — Meta                                        Mmm 2023 – Present
• Built and deployed production ML models in Python/TensorFlow serving [N] users,
  improving [metric] by [X%]  ← maps to "production ML at global scale"
• Designed end-to-end ML pipeline (feature engineering → training → serving)
  processing [volume], with [latency] online serving  ← maps to "batch + real-time"
• Ran A/B experiments to evaluate [model] and drove [decision/outcome]  ← maps to "A/B testing"

Senior Solutions Architect — Accenture                          Mmm 20XX – Mmm 20XX
• Architected resilient, high-scale data infrastructure and extensible APIs on
  AWS for [client/scale]  ← maps to "resilient data infrastructure, extensible APIs"
```

## Step 4 — Cover letter (ready to send, fill 2 brackets)

```
Dear Marketplaces Data & AI Team,

I'm a Machine Learning Engineer at Meta with an MS from Imperial College London,
where I build and deploy production ML at global scale in Python and TensorFlow.
Your Supply & Competitive Intelligence work — turning large-scale crawled data into
ML signals for pricing and supply decisions — maps directly to my experience
[building end-to-end pipelines and entity-matching/ranking models at Meta]. I've
[ONE QUANTIFIED RESULT, e.g. "shipped a model improving X by Y% for N users"], and
I'm excited to bring that production-ML rigor to Airbnb's competitive strategy.

I'd welcome the chance to discuss how I can contribute.

Best regards,
[Your Name]
```

## Step 5 — Likely screening/knockout answers for THIS application

| Question | Answer |
|---|---|
| Authorized to work in US? | `[Yes — required for this role]` |
| Require sponsorship? | `[answer truthfully — a "Yes" here may be a knockout]` |
| Years of applied ML experience? | `[your honest number]` — JD wants 5–10 |
| Highest degree? | `MS, Imperial College London` |
| Willing to work remote (US state w/ Airbnb entity)? | `Yes` |
| Proficient in Python? | `Yes — primary language` |

---

## How to reuse this

This is the loop from `per-job-tailoring.md`, fully worked: **knockout-check →
keyword-gap → summary → bullets → cover letter → screening answers.** ~10 minutes
per dream role. Want me to run it on another live role (Reddit Staff ML $266–372k,
Block Staff ML $160–283k, Natera Senior AI/ML $125–156k)? Name it.
