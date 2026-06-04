# LazyApply Targeting Config

Your single biggest problem: the bot is told to chase **15 unrelated job titles**
(Data Scientist, UI/UX Designer, DevOps, Cybersecurity, Blockchain, Frontend,
Support Engineer...). These are different hiring pipelines. Chasing all of them
means your resume matches *none* of them well, and the bot wastes applications on
roles you'll never hear back from.

**Fix: pick ONE lane at a time and narrow the filters.**

---

## Step 1 — Set search titles to one lane

Replace your 15-title list with a tight cluster. Pick the row you're running:

| Lane | Search titles to use (and ONLY these) |
|------|----------------------------------------|
| **ML Engineer** (default) | `Machine Learning Engineer`, `ML Engineer`, `AI Engineer`, `Senior Machine Learning Engineer` |
| **Data Scientist** | `Data Scientist`, `Senior Data Scientist`, `Applied Scientist`, `ML Scientist` |
| **Software Engineer** | `Software Engineer`, `Backend Engineer`, `Senior Software Engineer` |
| **Solutions Engineer** | `Solutions Engineer`, `Solutions Architect`, `Sales Engineer` |

> Run one lane for ~1–2 weeks, measure callbacks, then switch if needed. Don't mix
> lanes in a single bot run.

## Step 2 — Fix your salary floor

Your current min is **$60k**. Real market (remote US, ML Engineer, June 2026):

| Company | Role | Pay |
|---|---|---|
| Reddit | Staff ML Engineer | $266k–$372k |
| Block | Staff ML Engineer | $160k–$283k |
| Airbnb | Senior ML Engineer | $196k–$227k |
| Natera | Senior AI/ML Engineer | $125k–$156k |

**Set your floor to a realistic market number, not $60k.** A too-low floor pulls
you into low-quality roles *and* signals "junior/undervalued" to recruiters.

| Lane | Suggested floor (US remote) | Suggested floor (UK) |
|------|------------------------------|----------------------|
| ML Engineer | `$130k` | `£70k` |
| Data Scientist | `$110k` | `£60k` |
| Software Engineer | `$120k` | `£65k` |
| Solutions Engineer | `$110k` | `£60k` |

*(Adjust for your true seniority. These are mid-senior anchors.)*

## Step 3 — Tighten location & job-type filters

- **Location:** pick one market. You searched *US remote* but your education is UK —
  decide which you're authorized for and set it. Don't run both at once.
- **Job type:** set to `Full-time` unless you specifically want contract.
- **Keywords to exclude** (cut noise): `intern`, `clearance required` (if you lack
  it), `unpaid`, and any tech stack you won't touch.

## Step 4 — Cap daily volume, raise quality

- Don't let the bot run 500/day. **50–80 well-matched applications/day** beats 500
  scattered ones, and avoids tripping anti-bot/rate limits on LinkedIn/Indeed.
- Reserve your top ~10–15 dream roles/week for **manual tailored** applications
  (see `per-job-tailoring.md`) — that's where most interviews actually come from.

## Step 5 — Pick the right platforms for your lane

This extension supports LinkedIn, Indeed, Glassdoor, Dice, ZipRecruiter, Monster,
SimplyHired, CareerBuilder, Seek, Foundit, plus ATS (Greenhouse, Lever, Ashby,
Workday, iCIMS, Rippling, Wellfound).

| Lane | Best platforms |
|------|----------------|
| ML Engineer / Data Scientist | LinkedIn, Wellfound, Greenhouse/Lever/Ashby ATS direct |
| Software Engineer | LinkedIn, Dice, Wellfound, ATS direct |
| Solutions Engineer | LinkedIn, Indeed |

Applying **directly on the company ATS** (Greenhouse/Lever/Ashby) often beats
aggregators — fewer middlemen, faster routing to recruiters.

---

## Quick-start checklist

- [ ] Narrowed to ONE lane's search titles
- [ ] Raised salary floor off $60k to a market anchor
- [ ] Set a single location you're authorized for
- [ ] Job type = Full-time, added exclude-keywords
- [ ] Capped daily volume to 50–80
- [ ] Reserved dream roles for manual tailoring
- [ ] Loaded strong answers from `screening-answers.md`
- [ ] Rebuilt resume from `resume-master.md` with real metrics
