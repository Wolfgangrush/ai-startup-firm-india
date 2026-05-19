---
name: wake
description: Session-start board skill for the AI Startup Firm India. Loads saved palace state, renders company context, open matters, today's news, and compliance deadlines. Boots in ~170 tokens. Mandatory skill — invoked at start of every session. Includes 2-pass leak-check per Rule 1: no personal AAAK codes, no lawtech-arc refs.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# /wake — Session-Start Board

## Job

Load the saved palace state from the last `/retrospective`. Render a brief board: company context, open matters, today's news headlines, and stale warnings. Bootstrap the session in ~170 tokens so the Firm remembers who you are and what you were working on.

## Load sequence

### Step 1: Read palace state

Load `~/.ai-startup-firm-india/palace/palace-state.md`. If no saved state exists (first session ever), initialise a fresh palace.

### Step 2: Check today's news cache

Check `~/.ai-startup-firm-india/palace/news-cache/YYYY-MM-DD.md`. If exists, extract headlines. If not, note "News cache not available for today."

### Step 3: Render board

Output the session-start board.

---

## Board format

```
╔══════════════════════════════════════════════════╗
║         AI STARTUP FIRM INDIA — v0.1.0          ║
║         Wolfgang Rush · Session Board            ║
╚══════════════════════════════════════════════════╝

COMPANY
  [Company Name] | CIN: [CIN] | State: [MH/KA/DL/TN]
  Incorporated: [DD.MM.YYYY] | Section 10A: [filed/pending]
  [One-line business description]

CAP TABLE (as of [DD.MM.YYYY])
  Paid-up: Rs. [Amount] | Fully Diluted Shares: [Count]
  Option Pool: [Count] available
  Founders: [Name] ([X]%), [Name] ([Y]%)
  Investors: [Name] ([Z]%) — [CCPS / Equity]

OPEN MATTERS ([N])
  [Matter-ID-1]: [Description] — [status] — last updated [date]
  [Matter-ID-2]: [Description] — [status] — last updated [date]
  (none — no open matters) if empty

COMPLIANCE DEADLINES
  [Date]: [Filing description] — [AGM / MGT-7 / AOC-4 / FC-GPR / POSH AR]
  (none within 30 days) if no upcoming deadlines

TODAY'S NEWS — [DD.MM.YYYY]
  (from news-cache if available)
  Funding: [N] rounds tracked
  Regulatory: [N] updates
  Ecosystem: [N] events / announcements
  (news cache not available for today) if missing

SESSION READY
  Reminder: End every session with /retrospective to persist state.
  What would you like to work on today?
```

---

## First-session initialisation

If no `palace-state.md` exists:

```
╔══════════════════════════════════════════════════╗
║         AI STARTUP FIRM INDIA — v0.1.0          ║
║         Wolfgang Rush · First Session            ║
╚══════════════════════════════════════════════════╝

Welcome to the AI Startup Firm India.

I can help with:
  • Incorporating your company (MoA, AoA, DSC, DIN, Section 10A)
  • Founders' Agreements (equity split, vesting, IP assignment)
  • iSAFE / CCPS instruments (INR and foreign investment)
  • Shareholders' Agreements (entrenchment, RoFR, drag-along)
  • Employment contracts, offer letters, and POSH compliance
  • Statutory compliance checks (Companies Act, FEMA, DPDP)
  • Startup ecosystem and funding news

To get started, tell me about your company:
  • Company name and state of incorporation
  • Are you already incorporated or planning to?
  • How many founders?
  • Are you raising funds?

SESSION READY
  Reminder: End every session with /retrospective to persist state.
  What would you like to work on today?
```

---

## Stale warnings

The board flags staleness:

```
STALE WARNINGS
  [⚠] Cap table not updated in >60 days. Last updated: [DD.MM.YYYY].
  [⚠] FEMA currency-watch expired. Last verified: [DD.MM.YYYY].
      Run fema-rules agent to re-verify.
  [⚠] POSH Annual Report not filed for FY [YYYY-YYYY]. Due: [DD.MM.YYYY].
  (no stale warnings) if all current
```

---

## 2-PASS LEAK-CHECK (Rule 1 — mandatory)

**Rule 1:** No personal AAAK codes. No lawtech-arc references. No MemPalace file paths. No environment paths.

### Pass 1: Load

The skill loads the palace state and renders the board. All data displayed comes exclusively from `~/.ai-startup-firm-india/palace/palace-state.md` and today's news cache.

### Pass 2: Audit for leakage

Before rendering the board to the user, the skill scans the board output for:

```
LEAK-CHECK RULES:
[ ] No personal AAAK codes (no authentication keys, no personal memory keys)
[ ] No lawtech-arc references (no prior-project names, no "lawtech-arc")
[ ] No MemPalace file paths (no "~/Desktop/.../mempalace-3.0.0/")
[ ] No development environment paths (no "~/Desktop/AIO/")
[ ] No personal identifying information beyond user-supplied company facts
[ ] No authentication tokens, API keys, or credentials
[ ] No internal agent names from non-startup plugins
[ ] No "law firm of Rushikesh Mahajan", no personal practice references
[ ] Rule 36 firewall: no marketing, no solicitation, no CTAs
[ ] Engine credit: "MemPalace v3.0.0 (MIT)" — name and version only

If ANY check fails: STRIP the violating text from the board output.
  Log the strip in ~/.ai-startup-firm-india/palace/leak-check.log
  Format: [timestamp] [rule] [text stripped] [reason]
  Rerender the board without the stripped text.
```

### Leak-check log format

```
# leak-check.log
2026-05-19 09:00:05 | Rule 1.2 | Text: "prior-project: lawtech-arc" | Removed lawtech reference
2026-05-19 09:00:05 | Rule 1.3 | Text: "engine_path: ~/Desktop/AIO/..." | Removed file path
```

---

## Post-wake

After successful wake and clean leak-check:

```
Board rendered. Palace state loaded from [date of last /retrospective].
Leak-check: CLEAN (0 violations)
Open matters: [N]
```

If leak-check found violations:

```
Board rendered with [N] leak-check corrections.
Leak-check: CORRECTED ([N] violations stripped — see leak-check.log)
Open matters: [N]
```

---

## Falsification triggers

1. Palace state file does not exist → initialise first session (not a failure)
2. Palace state file corrupted (unparseable) → warn user, offer to reinitialise
3. News cache missing for >3 consecutive days → warn user (news fetch may have stopped)
4. Leak-check log exceeds 100 lines → warn user (persistent leakage — review load logic)
5. Palace state >30 days old → flag "Your Firm hasn't been active in 30 days. State may be stale."

---

*/wake skill v0.1.0. Mandatory. 2-pass leak-check per Rule 1.*
