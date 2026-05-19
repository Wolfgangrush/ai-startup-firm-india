---
name: retrospective
description: Session-state save skill for the AI Startup Firm India. Persists company facts, cap table snapshot, open matters, and decisions to local palace. Mandatory skill — invoked at end of every session. Includes 2-pass leak-check per Rule 6: no MemPalace file paths, no lawtech personal-context leakage.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# /retrospective — Session-State Save

## Job

Save the current session's state to the local palace at `~/.ai-startup-firm-india/palace/`. This skill runs at the end of every session so the Firm remembers company facts, open matters, and decisions across sessions. The next `/wake` bootstraps from this saved state in ~170 tokens.

## What gets saved

### 1. Matter facts
- Company name, CIN, registered office state
- Date of incorporation, Section 10A status
- Business description
- S&E registration, EPF/ESI registration

### 2. Entity registry delta
- Founders: names, PAN, DIN, roles, equity %, vesting status
- Directors: names, DINs, appointment dates
- Shareholders: names, class, shares, %, lock-in expiry
- Investors: names, type, country, investment amount, instrument
- IP assets: description, type, registration status

### 3. Cap table snapshot
- Total authorised shares
- Total issued shares
- Fully diluted shares
- Option pool: allocated, available
- Last updated date

### 4. Open matters
- Matter ID, description, status (pending / in progress / completed)
- Plugin assigned, case folder path
- Last updated date

### 5. Decisions made
- Key decisions: "Company incorporated", "Founders' agreement executed", "SHA adopted"
- Validity windows: decision → valid until event

### 6. Session metadata
- Session date and time
- Intents processed
- Plugins invoked
- Documents generated

## Save format

State is saved as compressed key-value pairs:

```
# palace-state.md
# AI Startup Firm India — Palace State
# Saved: 2026-05-19 18:30 IST
# Session: [session-id]

## L0: IDENTITY
firm: AI Startup Firm India v0.1.0
jurisdiction: IN
vertical: startup

## L1: COMPANY
name: [Company Name]
cin: [CIN]
state: [MH / KA / DL / TN]
incorporated: [DD.MM.YYYY]
s10a: [filed / pending / n/a]
business: [one-line description]

## L1: CAP TABLE
authorised: Rs. [Amount]
paid-up: Rs. [Amount]
fully-diluted-shares: [Count]
option-pool: [Count]
last-updated: [DD.MM.YYYY]

## L1: FOUNDERS
[Name]: [Role], [X]% equity, [vested/unvested], PAN [PAN], DIN [DIN]

## L1: DIRECTORS
[Name]: [DIN], [category], appointed [DD.MM.YYYY]

## L1: INVESTORS
[Name]: [Type], [Country], Rs. [Amount], [CCPS/Equity]

## L1: IP
[Description]: [Type], [status], filed [DD.MM.YYYY]

## L2: OPEN MATTERS
[Matter-ID]: [Description], [status], [plugin], [case-folder], [last-updated]

## L2: DECISIONS
[Decision]: [Date], valid until [Event/Date]

## L2: SESSION LOG
[session-id]: [Date], [intents processed], [plugins invoked], [docs generated]
```

## Save target

State is written to `~/.ai-startup-firm-india/palace/palace-state.md`.

Previous state is moved to `~/.ai-startup-firm-india/palace/archive/palace-state-YYYY-MM-DD.md` before overwrite (rolling 7-day archive).

---

## 2-PASS LEAK-CHECK (Rule 6 — mandatory)

**Rule 6:** No MemPalace file paths. No lawtech personal-context leakage. No development environment references.

### Pass 1: Save

The skill writes the palace state as described above. All data is drawn from the current session only — company facts, cap table, open matters, decisions. No external file paths are written.

### Pass 2: Audit for leakage

After Pass 1, the skill scans the saved `palace-state.md` for:

```
LEAK-CHECK RULES:
[ ] No MemPalace file paths (e.g. no "~/Desktop/.../mempalace-3.0.0/")
[ ] No AAAK personal codes (no personal memory palace keys)
[ ] No lawtech-arc references (no "lawtech-arc", no prior-project names)
[ ] No development environment paths (no "~/Desktop/AIO/")
[ ] No personal identifying information beyond what the user supplied
[ ] No authentication tokens, API keys, or credentials
[ ] No internal agent names from non-startup plugins
[ ] Engine credit limited to "MemPalace v3.0.0 (MIT)" — name and version only

If ANY check fails: DELETE the violating line. Log the deletion in
  ~/.ai-startup-firm-india/palace/leak-check.log
  Format: [timestamp] [rule] [line deleted] [reason]
```

### Leak-check log format

```
# leak-check.log
2026-05-19 18:30:15 | Rule 6.1 | Line: "mempalace_path: ~/Desktop/..." | Removed MemPalace file path
2026-05-19 18:30:15 | Rule 6.3 | Line: "prior: lawtech-arc-v2" | Removed lawtech reference
```

---

## Post-save confirmation

After successful save and clean leak-check:

```
Session saved. Palace state written to ~/.ai-startup-firm-india/palace/palace-state.md
Open matters: [N]
Cap table last updated: [DD.MM.YYYY]
Leak-check: CLEAN (0 violations)

Your Firm will remember this context on next /wake.
```

If leak-check found violations:

```
Session saved with [N] leak-check corrections.
Leak-check: CORRECTED ([N] violations removed — see leak-check.log)
Open matters: [N]

Your Firm will remember this context on next /wake.
```

---

## Falsification triggers

1. Palace directory does not exist → create it (do not fail)
2. Previous state archive exceeds 7 files → trim oldest
3. palace-state.md exceeds 500KB → warn user (likely too much detail in open matters)
4. Leak-check log exceeds 100 lines → warn user (persistent leakage pattern — review save logic)

---

*/retrospective skill v0.1.0. Mandatory. 2-pass leak-check per Rule 6.*
