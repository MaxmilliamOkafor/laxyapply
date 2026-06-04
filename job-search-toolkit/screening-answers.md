# Screening-Answer Bank

LazyApply pre-fills application questions from saved answers (its
`saveQuestionsV2` / `get-questions` backend). Generic or blank answers are a
top cause of silent auto-rejection. Write these **once, well**, and the bot reuses
them across hundreds of applications.

> Fill every `[BRACKET]` with your real info. Keep answers honest — these get
> verified at interview. Numbers are illustrative; replace with yours.

## How to load these into LazyApply

In the LazyApply dashboard → your profile → the saved-questions / Q&A section,
paste each answer against the matching question. The bot matches incoming form
questions against these by similarity, so phrase answers to stand alone.

---

## A. Identity & logistics (exact, short answers)

| Question pattern | Your answer |
|---|---|
| First / Last name | `[Firstname]` / `[Lastname]` |
| Email / Phone | `[email]` / `[+country phone]` |
| Current location | `[City, Country]` |
| Are you authorized to work in [country]? | `[Yes / Yes, I hold X visa / No, require sponsorship]` |
| Do you require visa sponsorship? | `[No / Yes — now or in future]` |
| Willing to relocate? | `Yes` (matches your Indeed preference) |
| Willing to work remote/hybrid/onsite? | `Open to remote, hybrid, or onsite` |
| Earliest start date | `[2 weeks from offer / specific date]` |
| Desired salary | `See targeting-config.md — never list below market. Use a range.` |
| Years of experience | `[total years]` |
| LinkedIn / GitHub / Portfolio URL | `[urls]` |
| How did you hear about us? | `LinkedIn` (safe default) |

## B. Work authorization & demographics

- **Sponsorship now or in the future?** Answer truthfully and *consistently* —
  inconsistent answers across the same application auto-flag you.
- **EEO/diversity questions** (gender, race, veteran, disability): always optional;
  "Decline to self-identify" is a valid, neutral answer that never hurts you.

## C. The high-impact open-ended questions

These are where applications are won or lost. Defaults below are written for the
**ML Engineer** lane — adapt the bracketed parts.

**"Why do you want to work here / for this role?"**
> I'm drawn to roles where I can ship ML systems that reach real users at scale.
> At Meta I [shipped X serving N users]; I'm looking to bring that production-ML
> experience to a team solving [domain] problems. *(Tailor the last clause per
> company — see per-job-tailoring.md.)*

**"Describe your most relevant experience."**
> At Meta I build production ML in Python/TensorFlow [one concrete shipped result
> with a metric]. Earlier, as a Senior Solutions Architect at Accenture I
> architected cloud/data platforms on AWS, and at Citi I built large-scale SQL/
> Python analytics. I hold an MS from Imperial College London and AWS Solutions
> Architect certification.

**"What are your strengths?"**
> Bridging research and production — I can train a model *and* ship it reliably
> (Docker/Kubernetes, AWS, CI/CD). Strong Python/SQL, and I communicate results to
> non-technical stakeholders, a habit from my solutions-architect and PM work.

**"Greatest weakness?"** (never say "perfectionist")
> Early on I over-optimized models before validating they solved the real user
> problem. I now ship a simple baseline first and iterate against a clear metric —
> it's made my work faster and more impactful.

**"Tell us about a challenging project."** (use STAR: Situation–Task–Action–Result)
> *Situation:* [system/model] needed to [goal] under [constraint].
> *Task:* I owned [scope].
> *Action:* I [designed/built X using Python/TensorFlow/AWS], handling [hard part].
> *Result:* [quantified outcome — latency ↓X%, accuracy ↑X%, $X saved].

**"Why are you leaving / looking?"**
> I've grown a lot in my current role and I'm looking for [more ownership of
> end-to-end ML systems / a domain I care about]. *(Never criticize an employer.)*

**"Where do you see yourself in 5 years?"**
> Growing into a senior/staff ML engineer who owns critical systems and mentors
> others — deepening technical impact rather than moving away from building.

**"Cover letter" field (LazyApply has a `coverLetter` slot):**
> Keep a 4-sentence master version; tailor sentence 2 per job:
> 1. *Hook:* ML Engineer with production experience at Meta and an MS from Imperial.
> 2. *Fit (TAILOR):* Your [team/product] work in [domain] maps directly to my
>    experience [specific overlap].
> 3. *Proof:* I've [one quantified achievement].
> 4. *Close:* I'd welcome the chance to discuss how I can contribute. — [Name]

## D. Common numeric/dropdown gotchas

| Question | Smart default |
|---|---|
| Years with [specific tech] | Be honest but count broadly (e.g., Python across all roles). |
| Expected salary (single number) | Use the **bottom of your target range**, never your floor. |
| Notice period | `2 weeks` (US) / `[your real notice]` (UK) |
| Are you 18+? | `Yes` |
| Do you have a degree? | `Yes — MS, Imperial College London` |

---

### Golden rules
1. **Consistency** beats cleverness — contradictory answers auto-reject you.
2. **Never volunteer a salary below market.** Anchor with a range.
3. **Honesty** — every answer here gets verified live in interviews.
4. Review the bot's saved answers **monthly**; sites change their questions.
