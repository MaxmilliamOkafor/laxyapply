# Job Search Toolkit

A practical system to turn the LazyApply bot from a "spray-and-pray clicker" into a
targeted machine that actually lands interviews. Built around **your** real resume
(Meta SWE, Accenture, Citi, MS Imperial College London) and **real** market data.

## The core idea

> Interviews are won on **inputs**, not click volume.
> Applying to 500 loosely-matched jobs with a generic resume gets fewer interviews
> than applying to 50 well-matched jobs with a tailored resume and strong answers.

The bot is good at *clicking*. This toolkit fixes the four things that actually
decide whether you get a callback:

| File | Fixes | Why it matters |
|------|-------|----------------|
| [`resume-master.md`](resume-master.md) | Weak/keyword-dumped resume, red-flag timeline | Passes ATS + survives 7-second recruiter scan |
| [`screening-answers.md`](screening-answers.md) | Generic auto-reject answers | LazyApply pre-fills these — make them strong once, reuse forever |
| [`per-job-tailoring.md`](per-job-tailoring.md) | One-size resume fails ATS keyword match | 10-minute tailoring per high-value job |
| [`targeting-config.md`](targeting-config.md) | Bot spraying 15 unrelated job types | Stop diluting your match score |
| [`ats-platforms.md`](ats-platforms.md) | Treating all 8 ATS platforms the same | Direct-ATS applies = your highest interview rate |

## Recommended workflow

1. **Pick one lane** (default set here: **Machine Learning Engineer**). See
   `targeting-config.md` for all four lanes if you want to switch.
2. **Rebuild your resume** using `resume-master.md`. Fill the `[BRACKETED]`
   placeholders with real numbers. This is non-negotiable — it's the biggest lever.
3. **Pre-load strong answers** into LazyApply using `screening-answers.md`.
4. **Configure the bot** with the narrow targeting in `targeting-config.md`.
5. **For the top ~20% of jobs** (dream roles), spend 10 min tailoring with
   `per-job-tailoring.md` instead of auto-applying.

## The 80/20 split

- **80% of roles:** Let the bot auto-apply with your strong master resume + answer bank.
- **20% of roles (the ones you'd actually love):** Apply manually/tailored. These are
  where interviews really come from. The bot's job is to free up your time for these.

## Reality check on numbers

From the live market pull (June 2026, remote US, "Machine Learning Engineer"):
Reddit Staff ML **$266k–$372k**, Airbnb Senior ML **$196k–$227k**,
Block Staff ML **$160k–$283k**, Natera Senior AI/ML **$125k–$156k**.

Your current LazyApply min-salary floor is **$60k** — that filters you *into* junk
roles and signals "junior" to recruiters. Raise it (see `targeting-config.md`).
