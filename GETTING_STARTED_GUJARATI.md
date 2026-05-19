# 🙏 સ્વાગત છે, સ્થાપક — તમારી AI Startup Firm અહીંથી શરૂ થાય છે

> ⚠️ **આ અનુવાદ AI-સહાયથી તૈયાર કરવામાં આવ્યો છે.** કોઈ શબ્દ કે વાક્ય ખોટું લાગે, તો કૃપા કરીને [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) જુઓ અને GitHub પર Pull Request મોકલો.

તમારે programmer હોવાની જરૂર નથી. દરેક document માટે law firm ની જરૂર નથી. તમારે જોઈએ — એક laptop, internet (ફક્ત setup માટે), અને 30 મિનિટ.

Copy-paste કરી શકો, તો આ ચલાવી શકો છો.

> **English:** [GETTING_STARTED.md](GETTING_STARTED.md) · **हिन्दी:** [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md) · **मराठी:** [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md)

---

## ✨ આ શું છે, એક paragraph માં

એક મફત open-source shell જે Claude Code ને તમારા startup નું legal co-pilot બનાવે છે. તે founders' agreements, iSAFE notes, SHAs, employment contracts, અને POSH policies draft કરે છે. તમારા પ્રશ્નોને 10 startup intents દ્વારા 8 specialist agents પાસે route કરે છે, જે 5 Wolfgang Rush drafting plugins ચલાવે છે. તે તમારી કંપની યાદ રાખે છે — founders, cap table, open matters, compliance deadlines — session થી session. તમારી પોતાની machine પર Claude Code ની અંદર ચાલે છે. Cloud upload નથી. Subscription નથી. જે document બને છે તે તમારું.

## 💛 એક Indian founder એ શા માટે ધ્યાન આપવું

મોટી law firms એક standard SHA માટે ₹50,000–₹2,00,000 લે છે. Bengaluru કે Mumbai માં એક સારા startup lawyer કલાકના ₹5,000–₹15,000 bill કરે છે. તમે pre-revenue છો. Bootstrapping કરો છો. તમારે કામ કરતા documents જોઈએ — એવું relationship નહીં જે runway ખતમ કરી દે.

- **Drafting માં લાખો બચાવો.** Founders' Agreement, iSAFE, SHA, Employment Contracts — templated, jurisdiction-aware, તમારા counsel ની સમીક્ષા માટે તૈયાર.
- **Default રીતે compliant રહો.** Companies Act 2013, FEMA NDI Rules, DPDP Act 2023, POSH Act 2013 — compliance agent કહે છે તમારા stage પર શું લાગુ પડે.
- **ક્યારેય context ગુમાવશો નહીં.** Firm તમારી cap table, incorporation state, open drafts — sessions વચ્ચે, અઠવાડિયા પછી પણ યાદ રાખે.
- **ઝડપથી આગળ વધો.** Plain English (કે Hindi, Marathi, Tamil...) માં કહો શું જોઈએ — firm યોગ્ય specialist પાસે route કરે.
- **બધું તમારું.** MIT licensed. તમારા documents. તમારો data. તમારું laptop.

## 🧠 અંદર શું છે — 8 specialists તમારા terminal માં

8 startup lawyers ની જેમ વિચારો, દરેકની પોતાની lane:

1. **Receptionist (મગજ)** — તમે જે કહો તે સાંભળે, 10 startup flows માં intent classify કરે, યોગ્ય specialist પાસે route કરે.
2. **Matter Manager** — તમારી entity details, founders, cap table, open incorporations, pending drafts રાખે. Sessions વચ્ચે stateful.
3. **Companies Act Compliance Officer** — Companies Act 2013: MoA, AoA, DIN, DSC, Section 10A, statutory registers, annual filings. તમારા stage પર શું લાગુ પડે તે જાણે.
4. **FEMA Rules Specialist** — foreign investment: NDI Rules, FC-GPR, FMV computation, pricing guidelines. RBI approval જોઈએ ત્યારે flag કરે.
5. **DPDP Overlay** — Data Protection Act 2023: consent notices, data fiduciary obligations, breach reporting thresholds.
6. **Stamp Duty Router** — 4 રાજ્યોમાં (MH, KA, DL, TS) stamp duty compute કરે, ક્યાં કેટલું ભરવું તે કહે.
7. **POSH Compliance Officer** — workplace harassment prevention: policy drafting, IC constitution, annual filings. Non-compliant થવા પહેલા પકડે.
8. **Funding & News Watch** — કોણે funding raise કરી, VC deal flow, Startup India scheme updates, YC batches, accelerator deadlines.

તમે ફક્ત Receptionist સાથે વાત કરો. Receptionist બાકીનાઓ સાથે વાત કરે.

## 🚀 તમારી પહેલી 30 મિનિટ (quick start)

### Prerequisites
- Claude Code installed
- Node.js 18+ અને Python 3.10+
- Git

### Step 1 — Firm clone (2 મિનિટ)

```bash
git clone https://github.com/Wolfgangrush/ai-startup-firm-india.git ~/Desktop/AIO/ai-startup-firm/india/
```

### Step 2 — 5 Wolfgang Rush drafting plugins install (5 મિનિટ)

```bash
git clone https://github.com/Wolfgangrush/wolfgang-rush-submissions.git ~/Desktop/AIO/wolfgang-rush-submissions/
```

5 startup drafting plugins `~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/` માં:

| # | Plugin | શું draft કરે |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A declaration |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

### Step 3 — Session start (30 સેકન્ડ)

```bash
cd ~/Desktop/AIO/ai-startup-firm/india/
claude
```

Claude Code prompt પર:

```
/wake
```

Saved state load કરે. પહેલી વાર હોય તો fresh firm initialize કરે. Startup dashboard જોશો — company snapshot, open matters, compliance deadlines, funding news.

### Step 4 — પહેલી વાતચીત

શું જોઈએ તે કહો:

```
> Acme Tech માટે founders' agreement draft કરો — 3 co-founders, 4-year vesting, 1-year cliff
> Karnataka માં registered કંપનીના SHA પર stamp duty કેટલી?
> ₹50L angel round માટે iSAFE note જોઈએ
> Check કરો કે 10th employee hire કર્યા પછી POSH compliance જોઈએ?
> આ અઠવાડિયે Indian SaaS માં કોણે funding raise કરી?
```

Receptionist intent classify કરીને યોગ્ય drafting plugin કે specialist agent પાસે route કરે.

દરેક plugin 6-agent drafting pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) ચલાવી `.docx` file તમારી working directory માં આપે.

### Step 5 — દરેક session ના અંતે `/retrospective` ચલાવો

```
/retrospective
```

તમારા company facts, cap table state, open matters, decisions local palace માં save કરે. આગલી session માં `/wake` બધું load કરે. Firm શીખે.

## 🛡️ Privacy ની પ્રામાણિક બાજુ

**Tool પોતે:** તમારો company data, cap table, drafts, notes — બધું laptop પર. Cloud પર ક્યારેય upload નથી. બધું `~/.ai-startup-firm-india/palace/` માં. Source code MIT licensed — દરેક લાઇન વાંચો, audit કરો, modify કરો. Drafting plugins `.docx` files local disk પર બનાવે.

**AI model (Claude Code):** Claude Code Anthropic ની API સાથે connect થાય. તમારી queries તેમના servers પર જાય. Anthropic ના enterprise privacy defaults strong — prompts અને outputs default રીતે model training માં use થતા નથી. વધુ: https://docs.claude.codes

**Compliance જવાબદારી:** Compliance agents કહે છે તમારા stage પર શું લાગુ પડે. તેઓ તમારા company secretary, CA, કે legal counsel ના substitute નથી. RoC filing, stamp duty ભરવાનું, POSH IC constitution, અને બધી statutory obligations ની જવાબદારી તમારી.

## 📁 બધું ક્યાં રહે

```
~/Desktop/AIO/
├── ai-startup-firm/india/            ← Firm shell (આ repo)
│   ├── brain/                        ← Intent classifier (10 startup flows)
│   ├── agents/                       ← 8 specialist agents
│   ├── skills/                       ← /wake અને /retrospective
│   └── config/                       ← Statutory thresholds, stamp duty, FEMA caps
├── wolfgang-rush-submissions/
│   └── IN-startup/                   ← 5 drafting plugins (અલગ repo)
└── ~/.ai-startup-firm-india/
    └── palace/                       ← તમારી કંપનીની persistent memory (ChromaDB)
```

Backup: `~/.ai-startup-firm-india/palace/` ને ગમે ત્યાં copy કરો. આ જ તમારી આખી firm.

## 🆘 કંઈ તૂટે તો

1. **પહેલો check:** Claude Code કામ કરે છે? `claude --version`
2. **બીજો check:** plugins સાચા path પર છે? `ls ~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`
3. **ત્રીજો check:** GitHub issues: https://github.com/Wolfgangrush/ai-startup-firm-india/issues
4. **Peer help:** Wolfgang_rush LinkedIn community

આ v0.1 છે — bootstrap version. Drafting plugins live. Statute-aware compliance (સાચું Companies Act text, FEMA rule text, DPDP Act text) v0.2 milestone.

## 🙏 Credits

- **Engine:** [MemPalace](https://github.com/mempalace/mempalace) — highest-scoring open-source AI memory system (96.6% LongMemEval R@5). MIT licensed. બધો architectural credit MemPalace authors ને.
- **Publisher:** [Wolfgang_rush](https://github.com/Wolfgangrush)
- **Author:** Rushikesh Mahajan, Advocate (Bombay HC Nagpur Bench)

જો આ તમારા lawyer ની office નો એક ચક્કર બચાવે, tool એ પોતાને સો વાર pay કરી દીધો.

`ચાલો શરૂ કરીએ.` 🙏

---

**License:** MIT. **Disclaimer:** આ tool તમારા startup ના legal documents draft અને organize કરવામાં મદદ કરે. તે કાનૂની સલાહ આપતું નથી. તે તમારા company secretary, CA, કે legal counsel ના substitute નથી. બધા documents execution પહેલા qualified professionals દ્વારા review કરાવો. AI Startup Firm India કોઈ law firm નથી અને advocate-client relationship બનાવતી નથી. AS-IS, warranty વગર.

**સુધારા માટે:** [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) જુઓ.
