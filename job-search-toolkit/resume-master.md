# Master Resume — Machine Learning Engineer (primary lane)

This is a restructured, ATS-optimized version of your existing resume. **Nothing is
fabricated** — it reorganizes your real roles, skills, and certs into the format that
passes Applicant Tracking Systems and survives a recruiter's 7-second scan.

> ⚠️ **You must do two things before using this:**
> 1. **Fix the dates.** Your current resume lists overlapping senior roles with
>    single start-dates (Meta Jan 2023–Present, SolimHealth Jan 2024, Accenture
>    Apr 2021, Citi Aug 2017). Overlaps + missing end-dates = instant recruiter
>    red flag. Use clean `MMM YYYY – MMM YYYY` ranges with **no overlaps**.
> 2. **Fill every `[BRACKETED]` placeholder with a real number.** A resume with
>    metrics gets ~40% more callbacks than one with duties only. I will not invent
>    these — they must be yours.

---

## FORMAT RULES (why this works)

- **Single column, no tables/text-boxes/graphics.** ATS parsers choke on multi-column
  layouts and drop your content. Plain reverse-chronological wins.
- **Standard section headers:** Summary, Skills, Experience, Education, Certifications.
- **Job-description keyword mirroring.** ATS scores you on keyword overlap with the
  posting. See `per-job-tailoring.md` to adjust per job.
- **Metrics in every bullet.** Format: *Action verb + what you did + quantified result.*
- **One page** if <10 yrs experience, two max.

---

## RESUME TEMPLATE (copy/paste, then fill brackets)

```
FIRSTNAME LASTNAME
Machine Learning Engineer
City, Country (or "Remote") · email@domain.com · linkedin.com/in/you · github.com/you

──────────────────────────────────────────────────────────────────────────────
PROFESSIONAL SUMMARY
──────────────────────────────────────────────────────────────────────────────
Machine Learning Engineer with [X] years building production ML systems across
[domains: e.g., recommendation, NLP, data platforms]. Shipped models serving
[N] users at Meta; MS, Imperial College London. Strong in Python, TensorFlow,
and large-scale data pipelines. AWS Certified Solutions Architect.

──────────────────────────────────────────────────────────────────────────────
TECHNICAL SKILLS
──────────────────────────────────────────────────────────────────────────────
Machine Learning:  TensorFlow, Algorithm Design, Data Modeling, Data Science
Languages:         Python, Java, Scala, C/C++, SQL, JavaScript, TypeScript
Data:              PostgreSQL, MySQL, MS-SQL, Hadoop, SSIS/SSRS, Spark
Cloud & MLOps:     AWS, Azure, IBM Cloud, Docker, Kubernetes, OpenShift, Jenkins,
                   Git, Azure DevOps
Web (secondary):   React Native, Node.js, Flask, Django, ASP.NET (.NET Core)

  ↑ Reordered so ML/Python/Cloud lead. The ATS reads top-down; lead with the
    keywords that match ML Engineer postings, not a flat alphabetical dump.

──────────────────────────────────────────────────────────────────────────────
EXPERIENCE
──────────────────────────────────────────────────────────────────────────────
Software Engineer — Meta                                       MMM 2023 – Present
• Built and shipped [model/feature] in Python/TensorFlow that [outcome],
  improving [metric] by [X%] for [N] users.
• Designed [data pipeline/system] processing [volume, e.g. "2B+ events/day"],
  reducing [latency/cost] by [X%].
• [Collaboration/leadership bullet: led/partnered with [team] to deliver [result]].

AI Product Manager — SolimHealth (GenAI/LLM dementia-care startup)   MMM 20XX – MMM 20XX
• Defined and shipped [LLM/GenAI feature], driving [adoption/accuracy metric] of [X].
• Translated [clinical/user] needs into [N] ML features; [result].

Senior Solutions Architect — Accenture                         MMM 20XX – MMM 20XX
• Architected [cloud/data solution] on AWS/Azure for [client/scale], cutting
  [cost/time] by [X%].
• Led [team size] engineers delivering [project]; [quantified outcome].

Senior Data Analyst — Citi                                     MMM 20XX – MMM 20XX
• Built [SQL/Python] analytics on [data scale] informing [decision], unlocking
  [$ value / efficiency].
• Automated [reporting/pipeline], saving [N hours/week].

──────────────────────────────────────────────────────────────────────────────
EDUCATION
──────────────────────────────────────────────────────────────────────────────
MS, [Field] — Imperial College London
BSc, [Field] — University of Derby

──────────────────────────────────────────────────────────────────────────────
CERTIFICATIONS
──────────────────────────────────────────────────────────────────────────────
AWS Certified Solutions Architect · CompTIA Security+ · Google Data Analytics ·
Microsoft Certified: Data Analyst Associate · PRINCE2
```

---

## Lane variants

The structure above is the **ML Engineer** version. To switch lanes, change the
title line + Summary + the *order* of the Skills block. The Experience bullets stay
the same — just emphasize different ones:

| Lane | Title line | Lead skills with | Emphasize role |
|------|-----------|------------------|----------------|
| **ML Engineer** (default) | Machine Learning Engineer | TensorFlow, Python, MLOps | Meta SWE |
| **Data Scientist** | Data Scientist | Python, SQL, Stats, Data Modeling | Citi + Meta |
| **Software Engineer** | Software Engineer | Python/Java/TS, System Design | Meta SWE |
| **Solutions Engineer** | Solutions Engineer | AWS/Azure, Architecture, Client delivery | Accenture |

---

## Before/after, concretely

**Before (your current resume):**
```
Senior Data Analyst at Citi (AUGUST 2017)
Skills: Machine Learning, Algorithm Design, Product development, SQL, Java, Hadoop...
        [40+ comma-separated keywords, no structure, no achievements]
```
ATS sees: a title and a keyword soup with no end date and no measurable impact.
Recruiter sees: nothing to grab onto in 7 seconds. → filtered out.

**After:**
```
Senior Data Analyst — Citi                            Aug 2017 – Mar 2021
• Built SQL/Python analytics on 50M+ customer records informing $XM credit-risk
  decisions, reducing false-positive flags by 18%.
```
ATS sees: clean dates, role keywords, quantified impact. Recruiter sees: a person
who delivered measurable value. → callback.
