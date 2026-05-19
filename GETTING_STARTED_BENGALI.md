# 🙏 স্বাগতম, প্রতিষ্ঠাতা — আপনার AI Startup Firm এখান থেকে শুরু

> ⚠️ **এই অনুবাদ AI-সহায়তায় তৈরি।** যদি কোনো শব্দ বা বাক্য ভুল মনে হয়, অনুগ্রহ করে [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) দেখুন এবং সংশোধনের জন্য GitHub-এ Pull Request পাঠান।

আপনাকে programmer হতে হবে না। প্রতিটি document-এর জন্য law firm দরকার নেই। আপনার দরকার — একটি laptop, internet (শুধু setup-এর জন্য), এবং ৩০ মিনিট।

Copy-paste করতে পারলে, এটি চালাতে পারবেন।

> **English:** [GETTING_STARTED.md](GETTING_STARTED.md) · **हिन्दी:** [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md) · **मराठी:** [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md)

---

## ✨ এটি কী, এক অনুচ্ছেদে

একটি ফ্রি open-source shell যা Claude Code-কে আপনার startup-এর legal co-pilot বানায়। এটি founders' agreements, iSAFE notes, SHAs, employment contracts, এবং POSH policies draft করে। আপনার প্রশ্ন ১০টি startup intent-এর মাধ্যমে ৮ জন specialist agent-এর কাছে route করে, যারা ৫টি Wolfgang Rush drafting plugin চালায়। এটি আপনার কোম্পানি মনে রাখে — founders, cap table, open matters, compliance deadlines — session থেকে session। আপনার নিজের মেশিনে Claude Code-এর ভেতরে চলে। কোনো cloud upload নেই। কোনো subscription নেই। যে document তৈরি হয়, সেটি আপনার।

## 💛 একজন Indian founder-এর কেন দরকার

বড় law firm একটি standard SHA-র জন্য ₹৫০,০০০–₹২,০০,০০০ নেয়। Bengaluru বা Mumbai-এর একজন ভাল startup lawyer ঘণ্টায় ₹৫,০০০–₹১৫,০০০ বিল করেন। আপনি pre-revenue। Bootstrapping করছেন। আপনার কাজ করে এমন document দরকার — এমন relationship নয় যা runway শেষ করে দেয়।

- **Drafting-এ লাখ টাকা বাঁচান।** Founders' Agreement, iSAFE, SHA, Employment Contracts — templated, jurisdiction-aware, আপনার counsel-এর রিভিউর জন্য তৈরি।
- **Default ভাবে compliant থাকুন।** Companies Act 2013, FEMA NDI Rules, DPDP Act 2023, POSH Act 2013 — compliance agent বলে আপনার stage-এ কী প্রযোজ্য।
- **কখনো context হারাবেন না।** Firm আপনার cap table, incorporation state, open drafts — session-এর মাঝে, সপ্তাহ পরেও মনে রাখে।
- **দ্রুত এগোন।** Plain English (বা Hindi, Marathi, Tamil...)-তে বলুন কী চান — firm সঠিক specialist-এর কাছে route করে।
- **সব আপনার।** MIT licensed. আপনার documents। আপনার data। আপনার laptop।

## 🧠 ভেতরে কী আছে — ৮ জন specialist আপনার terminal-এ

৮ জন startup lawyer-এর মতো ভাবুন, প্রত্যেকের নিজস্ব lane:

1. **Receptionist (মস্তিষ্ক)** — আপনি যা বলেন শোনে, ১০টি startup flow-এ intent classify করে, সঠিক specialist-এর কাছে route করে।
2. **Matter Manager** — আপনার entity details, founders, cap table, open incorporations, pending drafts রাখে। Session-এর মাঝে stateful।
3. **Companies Act Compliance Officer** — Companies Act 2013: MoA, AoA, DIN, DSC, Section 10A, statutory registers, annual filings। আপনার stage-এ কী প্রযোজ্য জানে।
4. **FEMA Rules Specialist** — foreign investment: NDI Rules, FC-GPR, FMV computation, pricing guidelines। RBI approval দরকার হলে flag করে।
5. **DPDP Overlay** — Data Protection Act 2023: consent notices, data fiduciary obligations, breach reporting thresholds।
6. **Stamp Duty Router** — ৪টি রাজ্যে (MH, KA, DL, TS) stamp duty compute করে, কোথায় কত দিতে হবে বলে।
7. **POSH Compliance Officer** — workplace harassment prevention: policy drafting, IC constitution, annual filings। non-compliant হওয়ার আগে ধরে ফেলে।
8. **Funding & News Watch** — কে funding raised করেছে, VC deal flow, Startup India scheme updates, YC batches, accelerator deadlines।

আপনি শুধু Receptionist-এর সাথে কথা বলেন। Receptionist বাকিদের সাথে কথা বলে।

## 🚀 আপনার প্রথম ৩০ মিনিট (quick start)

### Prerequisites
- Claude Code installed
- Node.js 18+ এবং Python 3.10+
- Git

### Step 1 — Firm clone (২ মিনিট)

```bash
git clone https://github.com/Wolfgangrush/ai-startup-firm-india.git ~/Desktop/AIO/ai-startup-firm/india/
```

### Step 2 — ৫টি Wolfgang Rush drafting plugin install (৫ মিনিট)

```bash
git clone https://github.com/Wolfgangrush/wolfgang-rush-submissions.git ~/Desktop/AIO/wolfgang-rush-submissions/
```

৫টি startup drafting plugin `~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`-এ:

| # | Plugin | কী draft করে |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A declaration |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

### Step 3 — Session start (৩০ সেকেন্ড)

```bash
cd ~/Desktop/AIO/ai-startup-firm/india/
claude
```

Claude Code prompt-এ:

```
/wake
```

Saved state load করে। প্রথমবার হলে fresh firm initialize করে। Startup dashboard দেখবেন — company snapshot, open matters, compliance deadlines, funding news।

### Step 4 — প্রথম কথোপকথন

কী চান শুধু বলুন:

```
> Acme Tech-এর জন্য founders' agreement draft করো — 3 co-founders, 4-year vesting, 1-year cliff
> Karnataka-র registered কোম্পানির SHA-তে stamp duty কত?
> ₹50L angel round-এর জন্য iSAFE note চাই
> Check করো 10th employee hire করায় POSH compliance দরকার কিনা
> এই সপ্তাহে Indian SaaS-এ কে funding raise করলো?
```

Receptionist intent classify করে সঠিক drafting plugin বা specialist agent-এ route করে।

প্রতিটি plugin 6-agent drafting pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) চালায় এবং `.docx` file আপনার working directory-তে দেয়।

### Step 5 — প্রতি session শেষে `/retrospective` চালান

```
/retrospective
```

আপনার company facts, cap table state, open matters, decisions local palace-এ save করে। পরের session-এ `/wake` সব load করে। Firm শেখে।

## 🛡️ Privacy-র সৎ কথা

**Tool নিজে:** আপনার company data, cap table, drafts, notes — সব laptop-এ। কোনো cloud-এ upload হয় না। সব `~/.ai-startup-firm-india/palace/`-এ। Source code MIT licensed — প্রতিটি লাইন পড়ুন, audit করুন, modify করুন। Drafting plugins `.docx` file local disk-এ তৈরি করে।

**AI model (Claude Code):** Claude Code Anthropic-এর API-তে connect করে। আপনার query তাদের server-এ যায়। Anthropic-এর enterprise privacy defaults strong — prompts এবং outputs default ভাবে model training-এ use হয় না। বিস্তারিত: https://docs.claude.codes

**Compliance দায়িত্ব:** Compliance agents বলে আপনার stage-এ কী প্রযোজ্য। এরা আপনার company secretary, CA, বা legal counsel-এর substitute নয়। RoC filing, stamp duty payment, POSH IC constitution, এবং সব statutory obligation-এর দায়িত্ব আপনার।

## 📁 সব কোথায় থাকে

```
~/Desktop/AIO/
├── ai-startup-firm/india/            ← Firm shell (এই repo)
│   ├── brain/                        ← Intent classifier (10 startup flows)
│   ├── agents/                       ← 8 specialist agents
│   ├── skills/                       ← /wake এবং /retrospective
│   └── config/                       ← Statutory thresholds, stamp duty, FEMA caps
├── wolfgang-rush-submissions/
│   └── IN-startup/                   ← 5 drafting plugins (আলাদা repo)
└── ~/.ai-startup-firm-india/
    └── palace/                       ← আপনার কোম্পানির persistent memory (ChromaDB)
```

Backup: `~/.ai-startup-firm-india/palace/` যেকোনো জায়গায় copy করুন। এটাই আপনার পুরো firm।

## 🆘 কিছু ভেঙে গেলে

1. **প্রথম check:** Claude Code কাজ করছে? `claude --version`
2. **দ্বিতীয় check:** plugins ঠিক path-এ আছে? `ls ~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`
3. **তৃতীয় check:** GitHub issues: https://github.com/Wolfgangrush/ai-startup-firm-india/issues
4. **Peer help:** Wolfgang_rush LinkedIn community

এটি v0.1 — bootstrap version। Drafting plugins live। Statute-aware compliance (আসল Companies Act text, FEMA rule text, DPDP Act text) v0.2 milestone।

## 🙏 Credits

- **Engine:** [MemPalace](https://github.com/mempalace/mempalace) — highest-scoring open-source AI memory system (96.6% LongMemEval R@5)। MIT licensed। সব architectural credit MemPalace authors-কে।
- **Publisher:** [Wolfgang_rush](https://github.com/Wolfgangrush)
- **Author:** Rushikesh Mahajan, Advocate (Bombay HC Nagpur Bench)

যদি এটি আপনার lawyer-এর office-এর একবার যাওয়া বাঁচায়, tool নিজেকে একশো গুণ pay করে দিয়েছে।

`চলুন শুরু করি।` 🙏

---

**License:** MIT। **Disclaimer:** এই tool আপনার startup-এর legal documents draft এবং organize করতে সাহায্য করে। এটি আইনি পরামর্শ দেয় না। এটি আপনার company secretary, CA, বা legal counsel-এর substitute নয়। সব documents execution-এর আগে qualified professionals দিয়ে review করান। AI Startup Firm India কোনো law firm নয় এবং advocate-client relationship তৈরি করে না। AS-IS, warranty ছাড়া।

**সংশোধনের জন্য:** [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) দেখুন।
