# Codebase Review — LazyApply Extension (v0.8.91, MV3)

Honest engineering review of the extension in this repo, focused on **what affects
your success rate** and **what's safe to change**.

## TL;DR

This repo is the **compiled, minified, signed** output of a commercial extension —
not editable source. The Q&A/answer logic is **server-driven** (`backend.lazyapply.com`),
so you can't improve answer quality by editing files here; you improve it by feeding
the bot better saved answers (see `screening-answers.md`). The real success levers
are all **inputs**, which the rest of this toolkit handles.

## What the code actually is

- ~5 MB of **webpack bundles** (`*.bundle.js`) — generated output, not source. No
  build config, no source maps, no tests.
- Vendored libs: `jquery.min.js`, `bootstrap.min.{css,js}`.
- **Signed integrity:** `_metadata/verified_contents.json` is Chrome's signature of
  the packed contents. Editing *any* file invalidates it. (Loading **unpacked** in
  developer mode ignores this; a packed/store install would refuse to load.)

## Findings

### 1. The application Q&A is server-side (most important)
`atsAutomation.bundle.js` calls `backend.lazyapply.com/products/get-questions`,
`/lazyapplyV2/saveQuestions`, `/saveQuestionsV2`. **Answers are fetched/stored on
LazyApply's servers**, not computed locally. Implication: you cannot make the bot
"smarter" by editing local files — but you *fully* control quality via the saved
answer bank. → Use `screening-answers.md`.

### 2. Cross-site script injection on Indeed — looks like a bug, probably isn't
`manifest.json` injects `glassdoor.bundle.js` and `simplyHired.bundle.js` on
`*.indeed.com`. This *looks* wrong, but Glassdoor's "Easy Apply" routes through
Indeed (both Recruit-owned), so it's likely intentional cross-site handling.
**Recommendation: do NOT remove without browser testing** — you'd risk breaking
Glassdoor applications. Verify in DevTools before touching.

### 3. Over-broad permissions (success-neutral, privacy-relevant)
Requests `cookies`, `tabs`, `webNavigation`, `scripting`, `declarativeNetRequest`,
`power`, plus host access to dozens of domains and `externally_connectable` to
`lazyapply.com`. All plausibly needed for auto-apply, but it's a lot of trust.
Doesn't affect interview rate; know what you've installed.

### 4. MV3 leftover: `background.html`
Manifest V3 uses a service worker (`background.service_worker: background.js`).
`background.html` is a dead Manifest-V2-style page (it even has a commented-out
`scriptmain.bundle.js`). Harmless, just cruft.

### 5. `web_accessible_resources` path mismatch (low risk)
Manifest lists `"styles.css"` but the file lives at `styles/styles.css`. If any
code does `getURL("styles.css")` it 404s. Can't confirm the request path from
minified code, so **don't change blindly** — verify the actual request in DevTools
first, then fix the path to match.

## What I changed (applied) vs. left alone

**✅ Applied — Workday pod & locale unlock.** The bot only detected Workday jobs on
the US `wd5` pod; I broadened it to **all pods and all locales** across
`manifest.json`, `background.js`, and `atsAutomation.bundle.js`. This is a surgical
string-broadening (the form-filler already used the generic `myworkdayjobs.com`),
re-validated as valid JSON, and is the single highest-confidence win for "more
successful applications." Full detail + test steps: **`EXTENSION-CHANGES.md`**.

**⏸ Deliberately left alone** (would need a browser test I can't run here):
1. **Apparent bugs may be intentional** (see #2 — Glassdoor-on-Indeed).
2. **`all_frames` for embedded ATS iframes** — real potential win, but risky on the
   shared job-board block; test in DevTools first.
3. **`styles.css` path** — can't read the request path from minified code.

Note: any edit invalidates `_metadata/verified_contents.json`, so the extension must
be **loaded unpacked** (developer mode ignores that signature). Everything is on this
branch and revertable via git. Say the word and I'll apply any of the above.

## Safe remediation path (if you want to harden it)

| Finding | Action | Risk |
|---|---|---|
| #4 background.html | Delete the file | None (unused) |
| #3 permissions | Audit, drop any you can confirm unused | Med — needs testing |
| #5 styles.css path | Fix after confirming request path in DevTools | Low |
| #2 cross-injection | Leave unless DevTools proves it's dead | High if removed blind |

## The actual success upgrade

The code is a clicker; it's fine. Your interview rate is decided by:
1. A focused, ATS-clean resume → `resume-master.md`
2. Strong reusable saved answers → `screening-answers.md`
3. Narrow targeting + realistic salary → `targeting-config.md`
4. Tailoring your top 20% of jobs → `per-job-tailoring.md`

Spend your effort there, not in the bundles.
