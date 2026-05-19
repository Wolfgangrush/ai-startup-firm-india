# 🙏 స్వాగతం, వ్యవస్థాపకులూ — మీ AI Startup Firm ఇక్కడ నుండి ప్రారంభమవుతుంది

> ⚠️ **ఈ అనువాదం AI-సహాయంతో తయారు చేయబడింది.** ఏదైనా పదం లేదా వాక్యం తప్పుగా అనిపిస్తే, దయచేసి [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) చూసి GitHub లో Pull Request పంపండి.

మీరు programmer అయి ఉండాల్సిన అవసరం లేదు. ప్రతి document కు law firm అవసరం లేదు. మీకు కావలసినవి — ఒక laptop, internet (setup కోసం మాత్రమే), మరియు 30 నిమిషాలు.

Copy-paste చేయగలిగితే, మీరు దీనిని నడపగలరు.

> **English:** [GETTING_STARTED.md](GETTING_STARTED.md) · **हिन्दी:** [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md) · **मराठी:** [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md)

---

## ✨ ఇది ఏమిటి, ఒక paragraph లో

ఒక ఉచిత open-source shell — Claude Code ను మీ startup యొక్క legal co-pilot గా మారుస్తుంది. ఇది founders' agreements, iSAFE notes, SHAs, employment contracts, మరియు POSH policies draft చేస్తుంది. మీ ప్రశ్నలను 10 startup intents ద్వారా 8 specialist agents కు route చేస్తుంది, అవి 5 Wolfgang Rush drafting plugins ను అమలు చేస్తాయి. ఇది మీ కంపెనీని గుర్తుంచుకుంటుంది — founders, cap table, open matters, compliance deadlines — session నుండి session వరకు. మీ స్వంత machine పై Claude Code లోపల నడుస్తుంది. Cloud upload లేదు. Subscription లేదు. తయారైన document మీది.

## 💛 ఒక Indian founder ఎందుకు పట్టించుకోవాలి

పెద్ద law firms ఒక standard SHA కు ₹50,000–₹2,00,000 తీసుకుంటాయి. Bengaluru లేదా Mumbai లో ఒక మంచి startup lawyer గంటకు ₹5,000–₹15,000 bill చేస్తారు. మీరు pre-revenue. Bootstrapping చేస్తున్నారు. పనిచేసే documents కావాలి — runway ను ముగించే relationship కాదు.

- **Drafting లో లక్షలు ఆదా చేసుకోండి.** Founders' Agreement, iSAFE, SHA, Employment Contracts — templated, jurisdiction-aware, మీ counsel సమీక్ష కోసం సిద్ధం.
- **Default గా compliant గా ఉండండి.** Companies Act 2013, FEMA NDI Rules, DPDP Act 2023, POSH Act 2013 — compliance agent మీ stage కు ఏది వర్తిస్తుందో చెబుతుంది.
- **Context ఎప్పటికీ కోల్పోకండి.** Firm మీ cap table, incorporation state, open drafts — sessions మధ్య, వారాల తర్వాత కూడా గుర్తుంచుకుంటుంది.
- **వేగంగా ముందుకెళ్లండి.** Plain English (లేదా Hindi, Marathi, Tamil...) లో ఏమి కావాలో చెప్పండి — firm సరైన specialist కు route చేస్తుంది.
- **అంతా మీదే.** MIT licensed. మీ documents. మీ data. మీ laptop.

## 🧠 లోపల ఏముంది — 8 specialists మీ terminal లో

8 startup lawyers లాగా ఆలోచించండి, ప్రతి ఒక్కరికీ స్వంత lane:

1. **Receptionist (మెదడు)** — మీరు చెప్పేది వింటుంది, 10 startup flows లో intent classify చేస్తుంది, సరైన specialist కు route చేస్తుంది.
2. **Matter Manager** — మీ entity details, founders, cap table, open incorporations, pending drafts ఉంచుతుంది. Sessions మధ్య stateful.
3. **Companies Act Compliance Officer** — Companies Act 2013: MoA, AoA, DIN, DSC, Section 10A, statutory registers, annual filings. మీ stage కు ఏది వర్తిస్తుందో తెలుసు.
4. **FEMA Rules Specialist** — foreign investment: NDI Rules, FC-GPR, FMV computation, pricing guidelines. RBI approval అవసరమైనప్పుడు flag చేస్తుంది.
5. **DPDP Overlay** — Data Protection Act 2023: consent notices, data fiduciary obligations, breach reporting thresholds.
6. **Stamp Duty Router** — 4 రాష్ట్రాల్లో (MH, KA, DL, TS) stamp duty compute చేస్తుంది, ఎక్కడ ఎంత చెల్లించాలో చెబుతుంది.
7. **POSH Compliance Officer** — workplace harassment prevention: policy drafting, IC constitution, annual filings. Non-compliant కావడానికి ముందు పట్టుకుంటుంది.
8. **Funding & News Watch** — ఎవరు funding raise చేశారు, VC deal flow, Startup India scheme updates, YC batches, accelerator deadlines.

మీరు Receptionist తో మాత్రమే మాట్లాడతారు. Receptionist మిగతావారితో మాట్లాడుతుంది.

## 🚀 మీ మొదటి 30 నిమిషాలు (quick start)

### Prerequisites
- Claude Code installed
- Node.js 18+ మరియు Python 3.10+
- Git

### Step 1 — Firm clone (2 నిమిషాలు)

```bash
git clone https://github.com/Wolfgangrush/ai-startup-firm-india.git ~/Desktop/AIO/ai-startup-firm/india/
```

### Step 2 — 5 Wolfgang Rush drafting plugins install (5 నిమిషాలు)

```bash
git clone https://github.com/Wolfgangrush/wolfgang-rush-submissions.git ~/Desktop/AIO/wolfgang-rush-submissions/
```

5 startup drafting plugins `~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/` లో:

| # | Plugin | దేనిని draft చేస్తుంది |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A declaration |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

### Step 3 — Session start (30 సెకన్లు)

```bash
cd ~/Desktop/AIO/ai-startup-firm/india/
claude
```

Claude Code prompt లో:

```
/wake
```

Saved state load చేస్తుంది. మొదటిసారి అయితే fresh firm initialize చేస్తుంది. Startup dashboard చూస్తారు — company snapshot, open matters, compliance deadlines, funding news.

### Step 4 — మొదటి సంభాషణ

మీకు ఏమి కావాలో చెప్పండి:

```
> Acme Tech కు founders' agreement draft చెయ్యి — 3 co-founders, 4-year vesting, 1-year cliff
> Karnataka లో registered company SHA కు stamp duty ఎంత?
> ₹50L angel round కు iSAFE note కావాలి
> 10th employee hire చేశాము — POSH compliance అవసరమా అని check చెయ్యి
> ఈ వారం Indian SaaS లో ఎవరు funding raise చేశారు?
```

Receptionist intent classify చేసి సరైన drafting plugin లేదా specialist agent కు route చేస్తుంది.

ప్రతి plugin 6-agent drafting pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) నడిపి `.docx` file మీ working directory లో ఇస్తుంది.

### Step 5 — ప్రతి session చివర `/retrospective` నడపండి

```
/retrospective
```

మీ company facts, cap table state, open matters, decisions local palace లో save చేస్తుంది. తర్వాత session లో `/wake` అన్నీ load చేస్తుంది. Firm నేర్చుకుంటుంది.

## 🛡️ Privacy యొక్క నిజాయితీ వైపు

**Tool స్వయంగా:** మీ company data, cap table, drafts, notes — అన్నీ laptop లో. Cloud లో ఎప్పుడూ upload లేదు. అన్నీ `~/.ai-startup-firm-india/palace/` లో. Source code MIT licensed — ప్రతి లైను చదవండి, audit చేయండి, modify చేయండి. Drafting plugins `.docx` files local disk లో తయారు చేస్తాయి.

**AI model (Claude Code):** Claude Code Anthropic API తో connect అవుతుంది. మీ queries వారి servers కు వెళ్తాయి. Anthropic enterprise privacy defaults strong — prompts మరియు outputs default గా model training లో use కావు. మరింత: https://docs.claude.codes

**Compliance బాధ్యత:** Compliance agents మీ stage కు ఏది వర్తిస్తుందో చెబుతాయి. అవి మీ company secretary, CA, లేదా legal counsel కు substitute కాదు. RoC filing, stamp duty payment, POSH IC constitution, మరియు అన్ని statutory obligations బాధ్యత మీది.

## 📁 అన్నీ ఎక్కడ ఉంటాయి

```
~/Desktop/AIO/
├── ai-startup-firm/india/            ← Firm shell (ఈ repo)
│   ├── brain/                        ← Intent classifier (10 startup flows)
│   ├── agents/                       ← 8 specialist agents
│   ├── skills/                       ← /wake మరియు /retrospective
│   └── config/                       ← Statutory thresholds, stamp duty, FEMA caps
├── wolfgang-rush-submissions/
│   └── IN-startup/                   ← 5 drafting plugins (వేరే repo)
└── ~/.ai-startup-firm-india/
    └── palace/                       ← మీ కంపెనీ persistent memory (ChromaDB)
```

Backup: `~/.ai-startup-firm-india/palace/` ను ఎక్కడికైనా copy చేయండి. ఇదే మీ మొత్తం firm.

## 🆘 ఏదైనా విరిగితే

1. **మొదటి check:** Claude Code పనిచేస్తుందా? `claude --version`
2. **రెండవ check:** plugins సరైన path లో ఉన్నాయా? `ls ~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`
3. **మూడవ check:** GitHub issues: https://github.com/Wolfgangrush/ai-startup-firm-india/issues
4. **Peer help:** Wolfgang_rush LinkedIn community

ఇది v0.1 — bootstrap version. Drafting plugins live. Statute-aware compliance (అసలు Companies Act text, FEMA rule text, DPDP Act text) v0.2 milestone.

## 🙏 Credits

- **Engine:** [MemPalace](https://github.com/mempalace/mempalace) — highest-scoring open-source AI memory system (96.6% LongMemEval R@5). MIT licensed. అన్ని architectural credit MemPalace authors కు.
- **Publisher:** [Wolfgang_rush](https://github.com/Wolfgangrush)
- **Author:** Rushikesh Mahajan, Advocate (Bombay HC Nagpur Bench)

ఇది మీ lawyer office కు ఒకసారి వెళ్లడాన్ని ఆదా చేస్తే, tool తనను తాను వంద సార్లు pay చేసుకుంది.

`మొదలుపెడదాం.` 🙏

---

**License:** MIT. **Disclaimer:** ఈ tool మీ startup legal documents draft మరియు organize చేయడానికి సహాయపడుతుంది. ఇది చట్టపరమైన సలహా ఇవ్వదు. ఇది మీ company secretary, CA, లేదా legal counsel కు substitute కాదు. అన్ని documents execution కు ముందు qualified professionals చే review చేయించండి. AI Startup Firm India ఒక law firm కాదు మరియు advocate-client relationship సృష్టించదు. AS-IS, warranty లేకుండా.

**సరిచేయడానికి:** [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) చూడండి.
