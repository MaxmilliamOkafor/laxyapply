# ATS Platform Playbook ("All Platforms")

The bot has dedicated automation for **8 ATS platforms** (confirmed in
`atsAutomation.bundle.js`): **Greenhouse, Lever, Ashby, Workday, iCIMS, Rippling,
VivaHR, Wellfound**. For Workday and iCIMS it even **stores login credentials**
(`ats-email-password` endpoint) because those force per-company accounts.

**Why this matters most:** applying **directly on a company's ATS beats aggregators
(LinkedIn/Indeed) for interview rate** — fewer middlemen, your application lands
straight in the recruiter's pipeline. Weight your effort here.

But "apply to All Platforms" is **not** "treat all platforms equally." They differ
wildly in difficulty, parse quality, and reject-traps. Here's how to win each.

---

## The two things that decide ATS success everywhere

1. **A machine-readable PDF resume.** Every ATS extracts *text* from your PDF.
   Single column, selectable text, standard headers, **no tables/columns/graphics/
   text-boxes** (they scramble the parse). This is exactly the format in
   `resume-master.md` — use it.
2. **Correct, consistent "knockout" answers.** Many ATS auto-reject on eligibility
   questions *before* a human looks. Sponsorship, work authorization, years of
   experience, location, willingness to relocate — answer truthfully and
   **identically every time**. One contradiction = silent rejection. See the
   knockout block in `screening-answers.md`.

---

## Per-platform guide (easiest → hardest)

### 🟢 Greenhouse  `boards.greenhouse.io`, `job-boards.greenhouse.io`
- **Best-in-class resume parser** — a clean PDF auto-fills accurately.
- Per-company **custom questions** + usually a **cover letter** field and a free-text
  "why this company". *These are where you win* — paste a 3–4 sentence tailored note
  (`per-job-tailoring.md`), don't leave blank.
- EEO/demographics at the end are **optional** → "Decline to self-identify" is safe.
- **Verdict:** highest ROI. Prioritize Greenhouse links.

### 🟢 Lever  `jobs.lever.co`
- Clean, good parser. Almost always asks for **LinkedIn / GitHub / portfolio URLs** —
  have these in your saved answers.
- Has an **"Additional information"** box — treat it as a mini cover letter, don't
  skip it.
- **Verdict:** high ROI, fast. Prioritize.

### 🟢 Ashby  `jobs.ashbyhq.com`
- Modern, fast, good parser — **but heavy on knockout/eligibility questions**
  (sponsorship, years with X, location). These **auto-filter** you.
- Answer knockouts precisely and consistently. A wrong "years of experience" number
  silently kills the application.
- **Verdict:** high ROI *if* your knockout answers are dialed in.

### 🟢 Wellfound  `wellfound.com` (formerly AngelList)
- **Profile-IS-the-application.** Startups read your Wellfound profile, not just a
  resume. Fill it out 100% (headline, summary, roles, skills).
- Usually a per-company **"What interests you?"** note — founders actually read these.
  Write 2–3 genuine sentences; generic = ignored.
- **Verdict:** great for startup/ML roles; the profile is one-time work that pays off.

### 🟡 Rippling  `ats.rippling.com`
- Newer ATS, relatively clean standard fields. Decent parser.
- **Verdict:** low-friction; let the bot run it.

### 🟡 VivaHR  `jobs.vivahr.com`
- Smaller ATS, simple short forms. Low friction, lower volume of jobs.
- **Verdict:** fine to include; minor.

### 🔴 iCIMS  `*.icims.com`
- **Forces account creation + login** (the bot stores your credentials to handle it).
- Clunky multi-step flow, **mediocre parser** — *verify* the auto-filled fields, it
  frequently mis-parses names/dates.
- **Verdict:** medium value but slow. Worth it for roles you want; expect manual cleanup.

### 🔴 Workday  `*.wd5.myworkdayjobs.com`  — the hard one
- **Separate account per company.** Multi-page, slow. Bot stores credentials and uses
  `autofillWithResume`, but **Workday's autofill is unreliable** — it re-asks your
  full work history and education in **structured fields**.
- This is exactly why your **resume dates must be clean** (no overlaps, real end
  dates — see `resume-master.md` #1). Workday turns messy dates into a broken,
  obviously-wrong application.
- **Verdict:** highest effort. Let the bot attempt, but **review every Workday
  application** before final submit. For dream roles, do Workday manually.

---

## Credential & account hygiene (Workday/iCIMS)

The bot stores ATS logins (`ats-email-password`). To keep this clean and safe:
- Use a **dedicated job-search email** (e.g., `you+jobs@gmail.com`) for all ATS
  accounts — keeps your inbox organized and separates the stored credentials from
  your primary login.
- Use a **unique password** for these accounts (they're stored by a third party).
  Don't reuse your important passwords.
- Periodically confirm the stored profile data is current so credentialed ATS don't
  re-submit stale info.

---

## "All Platforms" run strategy

| Tier | Platforms | How to run |
|------|-----------|-----------|
| **Auto-apply freely** | Greenhouse, Lever, Ashby, Rippling, VivaHR | Bot on, strong master resume + answer bank |
| **Auto + verify** | iCIMS, Wellfound | Let bot fill, but check parsed fields / profile |
| **Manual for dream roles** | Workday (always), top Greenhouse/Lever roles | Tailor with `per-job-tailoring.md` |

**Priority order for your time:** direct ATS (Greenhouse/Lever/Ashby) **>**
Wellfound profile **>** LinkedIn/Indeed aggregators **>** Workday/iCIMS slog.

---

## Pre-flight checklist before an "All Platforms" run

- [ ] Resume is a clean single-column **PDF** with selectable text (no graphics)
- [ ] Dates fixed — real start/end, no overlaps (critical for Workday/iCIMS)
- [ ] Knockout answers set & consistent (auth, sponsorship, years, relocate)
- [ ] LinkedIn / GitHub / portfolio URLs saved (Lever/Ashby ask)
- [ ] Wellfound profile filled to 100%
- [ ] Dedicated job-search email + unique password for stored ATS logins
- [ ] Free-text notes pre-written (Lever "additional info", Greenhouse cover letter,
      Wellfound "what interests you")
- [ ] Salary floor raised off $60k (`targeting-config.md`)
