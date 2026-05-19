# 🙏 Welcome, Founder — your AI Startup Firm starts here

You don't need to be a programmer. You don't need a law firm on retainer for every document. You need a laptop, an internet connection for setup, and 30 minutes.

If you can describe what you're building, you can run this.

> **Hindi (हिन्दी):** [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md)
> **Marathi (मराठी):** [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md)
> **Bengali (বাংলা):** [GETTING_STARTED_BENGALI.md](GETTING_STARTED_BENGALI.md)
> **Tamil (தமிழ்):** [GETTING_STARTED_TAMIL.md](GETTING_STARTED_TAMIL.md)
> **Telugu (తెలుగు):** [GETTING_STARTED_TELUGU.md](GETTING_STARTED_TELUGU.md)
> **Gujarati (ગુજરાતી):** [GETTING_STARTED_GUJARATI.md](GETTING_STARTED_GUJARATI.md)
> **Kannada (ಕನ್ನಡ):** [GETTING_STARTED_KANNADA.md](GETTING_STARTED_KANNADA.md)
> **Malayalam (മലയാളം):** [GETTING_STARTED_MALAYALAM.md](GETTING_STARTED_MALAYALAM.md)
> **Punjabi (ਪੰਜਾਬੀ):** [GETTING_STARTED_PUNJABI.md](GETTING_STARTED_PUNJABI.md)
> **Odia (ଓଡ଼ିଆ):** [GETTING_STARTED_ODIA.md](GETTING_STARTED_ODIA.md)

---

## ✨ What this is, in one paragraph

A free open-source shell that turns Claude Code into your startup's legal co-pilot. It drafts founders' agreements, iSAFE notes, SHAs, employment contracts, and POSH policies. It routes your questions through 10 classified startup intents to 8 specialist agents, which invoke 5 Wolfgang Rush drafting plugins. It remembers your company — founders, cap table, open matters, compliance deadlines — across sessions. It runs inside Claude Code on your own machine. No cloud upload. No subscription. You own every document it produces.

## 💛 Why an Indian founder should care

The big firms charge ₹50,000–₹2,00,000 per standard SHA. A good startup lawyer in Bengaluru or Mumbai bills ₹5,000–₹15,000 an hour. You're pre-revenue. You're bootstrapping. You need documents that work — not a relationship that drains your runway.

- **You save lakhs on drafting.** Founders' Agreement, iSAFE, SHA, Employment Contracts — templated, jurisdiction-aware, ready for review by your counsel.
- **You stay compliant by default.** Companies Act 2013, FEMA NDI Rules, DPDP Act 2023, POSH Act 2013 — the compliance agent flags what applies to your stage.
- **You never lose context.** The firm remembers your cap table, your incorporation state, your open drafts — between sessions, across weeks.
- **You move faster.** Describe what you need in plain English (or Hindi, Marathi, Tamil...) — the firm routes it to the right specialist.
- **You own everything.** MIT licensed. Your documents. Your data. Your laptop.

## 🧠 What's inside — 8 specialists who live in your terminal

Think of it as 8 startup lawyers, each with a specific lane:

1. **The Receptionist (brain)** — listens to what you say, classifies your intent across 10 startup flows, routes to the right specialist. You never memorize commands.
2. **The Matter Manager** — holds your entity details, founders, cap table, open incorporations, pending drafts. Stateful across sessions.
3. **The Companies Act Compliance Officer** — Companies Act 2013: MoA, AoA, DIN, DSC, Section 10A, statutory registers, annual filings. Knows what applies at your stage.
4. **The FEMA Rules Specialist** — foreign investment: NDI Rules, FC-GPR, FMV computation, pricing guidelines. Flags when you need RBI approval.
5. **The DPDP Overlay** — Data Protection Act 2023: consent notices, data fiduciary obligations, breach reporting thresholds.
6. **The Stamp Duty Router** — computes stamp duty across 4 states (MH, KA, DL, TS), tells you where to pay and how much.
7. **The POSH Compliance Officer** — workplace harassment prevention: policy drafting, IC constitution, annual filings. Catches you before you're non-compliant.
8. **The Funding & News Watch** — tracks who raised what, VC deal flow, Startup India scheme updates, YC batches, accelerator deadlines.

You talk to the Receptionist. The Receptionist talks to the others. You never learn 8 different tools.

## 🚀 Your first 30 minutes (the quick start)

### Prerequisites

- Claude Code installed (see [Claude Code docs](https://docs.claude.codes))
- Node.js 18+ and Python 3.10+
- Git

### Step 1 — Clone the firm (2 minutes)

```bash
git clone https://github.com/Wolfgangrush/ai-startup-firm-india.git ~/Desktop/AIO/ai-startup-firm/india/
```

### Step 2 — Install the 5 Wolfgang Rush drafting plugins (5 minutes)

Clone into the sibling directory:

```bash
git clone https://github.com/Wolfgangrush/wolfgang-rush-submissions.git ~/Desktop/AIO/wolfgang-rush-submissions/
```

The 5 startup drafting plugins live at `~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`:

| # | Plugin | What it drafts |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A declaration |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

### Step 3 — Start a session (30 seconds)

Open Claude Code in the firm directory:

```bash
cd ~/Desktop/AIO/ai-startup-firm/india/
claude
```

At the Claude Code prompt, run:

```
/wake
```

This loads saved state. If this is your first time, it initializes a fresh firm.

You'll see your startup dashboard — company snapshot, open matters, compliance deadlines, recent funding news.

### Step 4 — Your first interaction

Just describe what you need:

```
> Draft a founders' agreement for Acme Tech — 3 co-founders, 4-year vesting, 1-year cliff
> What's the stamp duty on an SHA for a Karnataka-registered company?
> I need an iSAFE note for a ₹50L angel round
> Check if we need POSH compliance — we just hired our 10th employee
> Who raised funding in Indian SaaS this week?
```

The Receptionist classifies your intent and routes to the right drafting plugin or specialist agent.

Each plugin runs a 6-agent drafting pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) and drops a `.docx` in your working directory.

### Step 5 — End every session with `/retrospective`

```
/retrospective
```

This saves your company facts, cap table state, open matters, and decisions to the local palace. Next session, `/wake` loads everything back. The firm learns.

## 🛡️ Privacy posture (the honest version)

**What we guarantee (the tool itself):**
- Your company data, cap table, drafts, and notes stay on your laptop. They are NEVER uploaded to any cloud by this tool.
- All data lives in a folder you control: `~/.ai-startup-firm-india/palace/`.
- Source code is MIT licensed — read every line, audit anything, modify anything.
- The drafting plugins produce `.docx` files on your local disk. You choose where they go.

**What we cannot guarantee (the AI model you connect):**
- Claude Code connects to Anthropic's API. Your queries go to their servers.
- Anthropic's enterprise privacy defaults are strong — prompts and outputs are not used for model training by default.
- For maximum privacy, review Anthropic's data usage policy at https://docs.claude.codes.

**Compliance responsibility:**
- The compliance agents flag what applies to your stage. They do NOT replace your company secretary, your chartered accountant, or your legal counsel.
- YOU remain responsible for filing with the RoC, paying stamp duty, constituting the POSH IC, and complying with all statutory obligations.

## 📁 Where everything lives

```
~/Desktop/AIO/
├── ai-startup-firm/india/            ← The firm shell (this repo)
│   ├── brain/                        ← Intent classifier (10 startup flows)
│   ├── agents/                       ← 8 specialist agents
│   ├── skills/                       ← /wake and /retrospective
│   └── config/                       ← Statutory thresholds, stamp duty, FEMA caps
├── wolfgang-rush-submissions/
│   └── IN-startup/                   ← 5 drafting plugins (separate repo)
└── ~/.ai-startup-firm-india/
    └── palace/                       ← Your company's persistent memory (ChromaDB)
```

Backup: copy `~/.ai-startup-firm-india/palace/` anywhere. That's your entire firm.

## 🆘 If something breaks

1. **First check:** is Claude Code working? Run `claude --version`.
2. **Second check:** are the plugins at the right path? `ls ~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`
3. **Third check:** GitHub issues at https://github.com/Wolfgangrush/ai-startup-firm-india/issues
4. **For peer help:** Wolfgang_rush LinkedIn community.

This is v0.1 — bootstrap version. The drafting plugins are live. Statute-aware compliance (real Companies Act text, FEMA rule text, DPDP Act text) is the v0.2 milestone.

## 🙏 Credits

- **Engine:** [MemPalace](https://github.com/mempalace/mempalace) — the highest-scoring open-source AI memory system ever benchmarked (96.6% LongMemEval R@5). MIT licensed. All architectural credit to the MemPalace authors.
- **Publisher:** [Wolfgang_rush](https://github.com/Wolfgangrush) — MIT-licensed plugin family for Indian legal drafting.
- **Author:** Rushikesh Mahajan, Advocate (Bombay HC Nagpur Bench)
- **Inspired by:** every Indian founder who's stared at a blank MoA template at 2 AM, wondering if they're doing it right.

If this saves you one trip to the lawyer's office, the tool has paid for itself a hundred times over.

`चलिए शुरू करें · चला सुरू करूया · চলুন শুরু করি · ஆரம்பிக்கலாம் · మొదలుపెడదాం · ચાલો શરૂ કરીએ · ಪ್ರಾರಂಭಿಸೋಣ · തുടങ്ങാം · ਆਓ ਸ਼ੁਰੂ ਕਰੀਏ · ଆରମ୍ଭ କରିବା · Let's build.` 🙏

---

**License:** MIT (inherited from MemPalace upstream). See LICENSE file.

**Disclaimer:** This tool helps you draft and organize your startup's legal documents. It does NOT give legal advice. It does NOT replace your company secretary, chartered accountant, or legal counsel. All documents should be reviewed by qualified professionals before execution. The AI Startup Firm India is not a law firm and does not create an advocate-client relationship. Ships AS-IS without warranty.
