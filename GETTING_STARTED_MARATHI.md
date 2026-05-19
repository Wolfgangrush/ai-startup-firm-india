# 🙏 स्वागत आहे, संस्थापक — तुमची AI Startup Firm इथून सुरू

> ⚠️ **हे भाषांतर AI-सहाय्याने तयार केले आहे.** एखादा शब्द किंवा वाक्य चुकीचे वाटल्यास, कृपया [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) पहा आणि GitHub वर Pull Request पाठवा.

तुम्हाला programmer असण्याची गरज नाही. प्रत्येक document साठी law firm ची गरज नाही. तुम्हाला हवं — एक laptop, internet (फक्त setup साठी), आणि 30 मिनिटं.

Copy-paste करू शकत असाल, तर हे चालवू शकता.

> **English:** [GETTING_STARTED.md](GETTING_STARTED.md) · **हिन्दी:** [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md) · **বাংলা:** [GETTING_STARTED_BENGALI.md](GETTING_STARTED_BENGALI.md)

---

## ✨ हे काय आहे, एका paragraph मध्ये

एक मोफत open-source shell जे Claude Code ला तुमच्या startup चं legal co-pilot बनवतं. हे founders' agreements, iSAFE notes, SHAs, employment contracts, आणि POSH policies draft करतं. तुमच्या प्रश्नांना 10 startup intents द्वारे 8 specialist agents कडे route करतं, जे 5 Wolfgang Rush drafting plugins चालवतात. हे तुमची कंपनी लक्षात ठेवतं — founders, cap table, open matters, compliance deadlines — session न session. हे तुमच्या स्वतःच्या मशीनवर Claude Code मध्ये चालतं. Cloud upload नाही. Subscription नाही. जे document बनतं ते तुमचं.

## 💛 एका Indian founder ला याची पर्वा का करावी

मोठ्या law firms एका standard SHA साठी ₹50,000–₹2,00,000 घेतात. Bengaluru किंवा Mumbai मधला एक चांगला startup lawyer ₹5,000–₹15,000 प्रति तास बिल करतो. तुम्ही pre-revenue आहात. Bootstrapping करताय. तुम्हाला काम करणारे documents हवे आहेत — runway संपवणारं relationship नको.

- **Drafting वर लाखो वाचवा.** Founders' Agreement, iSAFE, SHA, Employment Contracts — templated, jurisdiction-aware, तुमच्या counsel च्या समीक्षेसाठी तयार.
- **Default ने compliant रहा.** Companies Act 2013, FEMA NDI Rules, DPDP Act 2023, POSH Act 2013 — compliance agent सांगतो तुमच्या stage ला काय लागू आहे.
- **Context कधीच हरवू नका.** Firm तुमची cap table, incorporation state, open drafts — sessions मध्ये, आठवड्यांनंतरही लक्षात ठेवते.
- **जलद पुढे जा.** Plain English (किंवा Hindi, Marathi, Tamil...) मध्ये सांगा काय हवंय — firm योग्य specialist कडे route करते.
- **सगळं तुमचं आहे.** MIT licensed. तुमचे documents. तुमचा data. तुमचं laptop.

## 🧠 आत काय आहे — 8 specialists जे तुमच्या terminal मध्ये राहतात

8 startup lawyers सारखं समजा, प्रत्येकाची स्वतःची lane:

1. **Receptionist (मेंदू)** — तुम्ही काय म्हणता ते ऐकतो, 10 startup flows मध्ये intent classify करतो, योग्य specialist ला route करतो.
2. **Matter Manager** — तुमच्या entity details, founders, cap table, open incorporations, pending drafts ठेवतो. Sessions मध्ये stateful.
3. **Companies Act Compliance Officer** — Companies Act 2013: MoA, AoA, DIN, DSC, Section 10A, statutory registers, annual filings. तुमच्या stage ला काय लागू हे माहीत.
4. **FEMA Rules Specialist** — foreign investment: NDI Rules, FC-GPR, FMV computation, pricing guidelines. RBI approval हवं तेव्हा flag करतो.
5. **DPDP Overlay** — Data Protection Act 2023: consent notices, data fiduciary obligations, breach reporting thresholds.
6. **Stamp Duty Router** — 4 राज्यांमध्ये (MH, KA, DL, TS) stamp duty compute करतो, कुठे आणि किती भरायचं सांगतो.
7. **POSH Compliance Officer** — workplace harassment prevention: policy drafting, IC constitution, annual filings. Non-compliant होण्याआधी पकडतो.
8. **Funding & News Watch** — कोणी funding raised केली, VC deal flow, Startup India scheme updates, YC batches, accelerator deadlines.

तुम्ही फक्त Receptionist शी बोलता. Receptionist बाकीच्यांशी बोलतो.

## 🚀 तुमचे पहिले 30 मिनिटं (quick start)

### Prerequisites
- Claude Code installed
- Node.js 18+ आणि Python 3.10+
- Git

### Step 1 — Firm clone करा (2 मिनिटं)

```bash
git clone https://github.com/Wolfgangrush/ai-startup-firm-india.git ~/Desktop/AIO/ai-startup-firm/india/
```

### Step 2 — 5 Wolfgang Rush drafting plugins install करा (5 मिनिटं)

```bash
git clone https://github.com/Wolfgangrush/wolfgang-rush-submissions.git ~/Desktop/AIO/wolfgang-rush-submissions/
```

5 startup drafting plugins `~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/` मध्ये:

| # | Plugin | काय draft करतं |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A declaration |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

### Step 3 — Session start करा (30 सेकंद)

```bash
cd ~/Desktop/AIO/ai-startup-firm/india/
claude
```

Claude Code prompt वर:

```
/wake
```

Saved state load करतं. पहिल्यांदा असेल तर fresh firm initialize करतं. Startup dashboard दिसेल — company snapshot, open matters, compliance deadlines, funding news.

### Step 4 — पहिली गोष्ट

काय हवं ते सांगा:

```
> Acme Tech साठी founders' agreement draft कर — 3 co-founders, 4-year vesting, 1-year cliff
> Karnataka मध्ये registered कंपनीच्या SHA वर stamp duty किती?
> ₹50L angel round साठी iSAFE note हवा
> Check कर की 10th employee hire केल्यावर POSH compliance लागू आहे का?
> या आठवड्यात Indian SaaS मध्ये कोणी funding raise केली?
```

Receptionist intent classify करून योग्य drafting plugin किंवा specialist agent ला route करतो.

प्रत्येक plugin 6-agent drafting pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) चालवतो आणि `.docx` file working directory मध्ये देतो.

### Step 5 — प्रत्येक session च्या शेवटी `/retrospective` चालवा

```
/retrospective
```

तुमचे company facts, cap table state, open matters, decisions local palace मध्ये save करतं. पुढच्या session मध्ये `/wake` सगळं load करतं. Firm शिकते.

## 🛡️ Privacy ची प्रामाणिक बाजू

**Tool स्वतः:** तुमचा company data, cap table, drafts, notes — सगळं laptop वर. Cloud वर कधीच upload नाही. सगळं `~/.ai-startup-firm-india/palace/` मध्ये. Source code MIT licensed — प्रत्येक ओळ वाचा, audit करा, modify करा. Drafting plugins `.docx` files local disk वर बनवतात.

**AI model (Claude Code):** Claude Code Anthropic च्या API शी connect होतं. तुमच्या queries त्यांच्या servers वर जातात. Anthropic चे enterprise privacy defaults strong आहेत — prompts आणि outputs default ने model training साठी use होत नाहीत. अधिक माहिती: https://docs.claude.codes

**Compliance जबाबदारी:** Compliance agents सांगतात तुमच्या stage ला काय लागू. ते तुमच्या company secretary, CA, किंवा legal counsel ची जागा घेत नाहीत. RoC filing, stamp duty भरणं, POSH IC constitution, आणि सर्व statutory obligations ची जबाबदारी तुमची.

## 📁 सगळं कुठे राहतं

```
~/Desktop/AIO/
├── ai-startup-firm/india/            ← Firm shell (हा repo)
│   ├── brain/                        ← Intent classifier (10 startup flows)
│   ├── agents/                       ← 8 specialist agents
│   ├── skills/                       ← /wake आणि /retrospective
│   └── config/                       ← Statutory thresholds, stamp duty, FEMA caps
├── wolfgang-rush-submissions/
│   └── IN-startup/                   ← 5 drafting plugins (वेगळा repo)
└── ~/.ai-startup-firm-india/
    └── palace/                       ← तुमच्या कंपनीची persistent memory (ChromaDB)
```

Backup: `~/.ai-startup-firm-india/palace/` कुठेही copy करा. हीच तुमची पूर्ण firm.

## 🆘 काही बिघडलं तर

1. **पहिला check:** Claude Code काम करतंय का? `claude --version`
2. **दुसरा check:** plugins योग्य path वर आहेत का? `ls ~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`
3. **तिसरा check:** GitHub issues: https://github.com/Wolfgangrush/ai-startup-firm-india/issues
4. **Peer help:** Wolfgang_rush LinkedIn community

ही v0.1 आहे — bootstrap version. Drafting plugins live आहेत. Statute-aware compliance (खरे Companies Act text, FEMA rule text, DPDP Act text) v0.2 milestone आहे.

## 🙏 Credits

- **Engine:** [MemPalace](https://github.com/mempalace/mempalace) — highest-scoring open-source AI memory system (96.6% LongMemEval R@5). MIT licensed. सगळं architectural credit MemPalace authors ला.
- **Publisher:** [Wolfgang_rush](https://github.com/Wolfgangrush)
- **Author:** Rushikesh Mahajan, Advocate (Bombay HC Nagpur Bench)

जर हे तुमचं lawyer च्या office चं एक फेरं वाचवतं, tool ने स्वतःला शंभर वेळा pay केलं.

`चला सुरू करूया.` 🙏

---

**License:** MIT. **Disclaimer:** हे tool तुमच्या startup चे legal documents draft आणि organize करायला मदत करतं. हे कायदेशीर सल्ला देत नाही. तुमच्या company secretary, CA, किंवा legal counsel ला replace करत नाही. सर्व documents execution आधी qualified professionals कडून review करून घ्या. AI Startup Firm India ही law firm नाही आणि advocate-client relationship तयार करत नाही. AS-IS बिना warranty.

**सुधारणेसाठी:** [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) पहा.
