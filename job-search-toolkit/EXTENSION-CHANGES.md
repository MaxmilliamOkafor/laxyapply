# Extension Code Changes — Changelog

Real, applied changes to the **existing** LazyApply extension (not new software).
Each is surgical, verifiable, and revertable via git (`git revert` / `git checkout`).

---

## ✅ Change 1 — Unlock ALL Workday pods & locales (was: US `wd5` only)

**The problem.** Workday is one of the largest enterprise ATS. Every employer's
Workday site lives on a numbered "pod": `company.wd1.myworkdayjobs.com`,
`wd3`, `wd5`, `wd12`, `wd103`, etc. This extension **hardcoded `wd5`** in its
detection logic *and* in its injection rules, and further restricted URLs to the
`/en-US/` locale. Result: it silently ignored the **large majority of Workday job
postings** — every non-`wd5` pod and every non-US locale (UK `en-GB`, Canada
`en-CA`, etc.). Applications you thought were being sent were never even attempted.

**The fix.** Broadened the host match from the specific `wd5` pod to **any**
Workday pod, and dropped the `/en-US/` locale lock, everywhere it was hardcoded:

| File | What changed | Occurrences |
|------|--------------|-------------|
| `manifest.json` | `host_permissions`, content-script `matches`, `web_accessible_resources` matches | 8 |
| `background.js` | injection URL-pattern arrays + `workday.urlPattern` config | 9 |
| `atsAutomation.bundle.js` | Workday detection `urlPattern` + 3 `.includes()` URL checks | 4 |

Concretely:
- `https://*.wd5.myworkdayjobs.com/en-US/*/job/*` → `https://*.myworkdayjobs.com/*/job/*`
- `urlPattern: "wd5.myworkdayjobs.com"` → `urlPattern: "myworkdayjobs.com"`
- `.includes("wd5.myworkdayjobs.com")` → `.includes("myworkdayjobs.com")`

**Why it's safe.** The bot's *form-filling* code already used the generic
`window.location.href.includes("myworkdayjobs.com")` — only the *detection/gating*
was stuck on `wd5`. This change just lets detection match what the filler already
handles. `manifest.json` re-validated as valid JSON after the edit.

**Impact.** The bot now attempts Workday applications across all pods and locales —
a large increase in addressable jobs from one of the biggest ATS platforms.

---

## How to load & test the modified extension

Editing files invalidates Chrome's package signature (`_metadata/verified_contents
.json`), so load it **unpacked** in developer mode (which ignores that signature):

1. Chrome → `chrome://extensions`
2. Toggle **Developer mode** (top-right) ON
3. Click **Load unpacked** → select the
   `Download LazyApply  Job Application Bot` folder
4. Test: open any non-`wd5` Workday posting, e.g. a `*.wd1.myworkdayjobs.com/...`
   or `*.wd103.myworkdayjobs.com/...` job, and confirm the LazyApply UI/autofill
   now activates (previously it would do nothing on these).
5. To revert any change: `git checkout -- "<file>"` or `git revert <commit>`.

---

## Deliberately NOT changed (and why) — recommend testing first

These *might* help but I won't apply them blind, because I can't run a browser here
to confirm they don't break a working flow:

- **`all_frames: true` for embedded ATS forms.** Some ATS (e.g. Greenhouse
  `embed/job_app`) render their application form inside an `<iframe>` on a company
  career page. Content scripts only run in the top frame by default, so those forms
  aren't filled. Adding `all_frames: true` *to a dedicated Greenhouse-embed content-
  script block* would fix this — but added to the shared job-board+ATS block it would
  also run heavy scripts inside ad/tracker iframes on LinkedIn/Indeed. Worth doing
  **after** testing in DevTools to confirm the collateral is acceptable.
- **`styles.css` web-accessible path.** Manifest exposes `"styles.css"` but the file
  is at `styles/styles.css`. Only fix this after confirming the actual request path
  in DevTools (Network tab) — the minified code's request string can't be read
  statically.
- **Cross-injection of `glassdoor.bundle.js` on Indeed.** Looks like a bug but is
  likely intentional (Glassdoor "Easy Apply" routes through Indeed). Don't remove
  without a DevTools test proving it's dead.

See `CODEBASE-REVIEW.md` for the full findings list.
