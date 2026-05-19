# 🙏 नमस्ते, फाउंडर जी — आपकी AI Startup Firm यहीं से शुरू होती है

> ⚠️ **यह अनुवाद AI-सहायता से तैयार किया गया है।** अगर कोई शब्द या वाक्य गलत लगे, तो कृपया [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) देखें और GitHub पर Pull Request भेजें।

आपको programmer होने की ज़रूरत नहीं है। हर document के लिए law firm की ज़रूरत नहीं है। आपको चाहिए — एक laptop, internet (सिर्फ़ setup के लिए), और 30 मिनट।

अगर आप copy-paste कर सकते हैं, तो आप यह चला सकते हैं।

> **English:** [GETTING_STARTED.md](GETTING_STARTED.md) · **मराठी:** [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md) · **বাংলা:** [GETTING_STARTED_BENGALI.md](GETTING_STARTED_BENGALI.md)

---

## ✨ यह क्या है, एक paragraph में

एक मुफ़्त open-source shell जो Claude Code को आपकी startup का legal co-pilot बनाता है। यह founders' agreements, iSAFE notes, SHAs, employment contracts, और POSH policies draft करता है। यह आपके सवालों को 10 startup intents के ज़रिए 8 specialist agents तक route करता है, जो 5 Wolfgang Rush drafting plugins चलाते हैं। यह आपकी कंपनी को याद रखता है — founders, cap table, open matters, compliance deadlines — session दर session। यह आपकी अपनी मशीन पर Claude Code के अंदर चलता है। कोई cloud upload नहीं। कोई subscription नहीं। जो document बनता है, वह आपका है।

## 💛 एक Indian founder को इसकी परवाह क्यों करनी चाहिए

बड़ी law firms एक standard SHA के ₹50,000–₹2,00,000 लेती हैं। Bengaluru या Mumbai का एक अच्छा startup lawyer ₹5,000–₹15,000 प्रति घंटा बिल करता है। आप pre-revenue हैं। आप bootstrapping कर रहे हैं। आपको ऐसे documents चाहिए जो काम करें — ऐसा relationship नहीं जो आपकी runway खत्म कर दे।

- **Drafting पर लाखों बचाएँ।** Founders' Agreement, iSAFE, SHA, Employment Contracts — templated, jurisdiction-aware, आपके counsel की समीक्षा के लिए तैयार।
- **Default रूप से compliant रहें।** Companies Act 2013, FEMA NDI Rules, DPDP Act 2023, POSH Act 2013 — compliance agent बताता है कि आपके stage पर क्या लागू होता है।
- **कभी context न खोएँ।** Firm आपकी cap table, incorporation state, open drafts — sessions के बीच, हफ़्तों बाद भी याद रखती है।
- **तेज़ी से आगे बढ़ें।** Plain English (या Hindi, Marathi, Tamil...) में बताएँ कि आपको क्या चाहिए — firm सही specialist के पास route करती है।
- **सब कुछ आपका है।** MIT licensed. आपके documents। आपका data। आपका laptop।

## 🧠 अंदर क्या है — 8 specialists जो आपके terminal में रहते हैं

इसे 8 startup lawyers की तरह सोचें, हर एक की अपनी lane:

1. **Receptionist (दिमाग)** — आप जो कहते हैं सुनता है, 10 startup flows में intent classify करता है, सही specialist के पास route करता है।
2. **Matter Manager** — आपकी entity details, founders, cap table, open incorporations, pending drafts रखता है। Sessions के बीच stateful।
3. **Companies Act Compliance Officer** — Companies Act 2013: MoA, AoA, DIN, DSC, Section 10A, statutory registers, annual filings। जानता है आपके stage पर क्या लागू होता है।
4. **FEMA Rules Specialist** — foreign investment: NDI Rules, FC-GPR, FMV computation, pricing guidelines। RBI approval की ज़रूरत पड़ने पर flag करता है।
5. **DPDP Overlay** — Data Protection Act 2023: consent notices, data fiduciary obligations, breach reporting thresholds।
6. **Stamp Duty Router** — 4 राज्यों (MH, KA, DL, TS) में stamp duty compute करता है, बताता है कहाँ और कितना भरना है।
7. **POSH Compliance Officer** — workplace harassment prevention: policy drafting, IC constitution, annual filings। non-compliant होने से पहले पकड़ता है।
8. **Funding & News Watch** — किसने funding raised की, VC deal flow, Startup India scheme updates, YC batches, accelerator deadlines।

आप सिर्फ़ Receptionist से बात करते हैं। Receptionist बाकियों से बात करता है।

## 🚀 आपके पहले 30 मिनट (quick start)

### Prerequisites
- Claude Code installed
- Node.js 18+ और Python 3.10+
- Git

### Step 1 — Firm clone करें (2 मिनट)

```bash
git clone https://github.com/Wolfgangrush/ai-startup-firm-india.git ~/Desktop/AIO/ai-startup-firm/india/
```

### Step 2 — 5 Wolfgang Rush drafting plugins install करें (5 मिनट)

```bash
git clone https://github.com/Wolfgangrush/wolfgang-rush-submissions.git ~/Desktop/AIO/wolfgang-rush-submissions/
```

5 startup drafting plugins `~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/` में हैं:

| # | Plugin | क्या draft करता है |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A declaration |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

### Step 3 — Session start करें (30 सेकंड)

```bash
cd ~/Desktop/AIO/ai-startup-firm/india/
claude
```

Claude Code prompt पर:

```
/wake
```

यह saved state load करता है। पहली बार है तो fresh firm initialize करता है। आपको startup dashboard दिखेगा — company snapshot, open matters, compliance deadlines, funding news।

### Step 4 — पहली बातचीत

बस बताएँ कि आपको क्या चाहिए:

```
> Acme Tech के लिए founders' agreement draft करो — 3 co-founders, 4-year vesting, 1-year cliff
> Karnataka में registered कंपनी के SHA पर stamp duty कितनी लगेगी?
> ₹50L angel round के लिए iSAFE note चाहिए
> Check करो कि हमें POSH compliance चाहिए — अभी 10th employee hire किया है
> इस हफ़्ते Indian SaaS में किसने funding raise की?
```

Receptionist आपका intent classify करता है और सही drafting plugin या specialist agent के पास route करता है।

हर plugin 6-agent drafting pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) चलाता है और `.docx` file आपकी working directory में देता है।

### Step 5 — हर session के अंत में `/retrospective` चलाएँ

```
/retrospective
```

यह आपकी company facts, cap table state, open matters, और decisions local palace में save करता है। अगली session में `/wake` सब वापस लोड करता है। Firm सीखती है।

## 🛡️ Privacy की ईमानदार बात

**Tool खुद:** आपका company data, cap table, drafts, notes — सब laptop पर। कभी cloud पर upload नहीं होता। सब कुछ `~/.ai-startup-firm-india/palace/` में। Source code MIT licensed — हर लाइन पढ़ें, audit करें, modify करें। Drafting plugins `.docx` files local disk पर बनाते हैं।

**AI model (Claude Code):** Claude Code Anthropic की API से connect होता है। आपकी queries उनके servers पर जाती हैं। Anthropic के enterprise privacy defaults strong हैं — prompts और outputs default रूप से model training में use नहीं होते। पूरी जानकारी: https://docs.claude.codes

**Compliance ज़िम्मेदारी:** Compliance agents बताते हैं कि आपके stage पर क्या लागू है। वे आपके company secretary, CA, या legal counsel की जगह नहीं लेते। RoC filing, stamp duty payment, POSH IC constitution, और सभी statutory obligations की ज़िम्मेदारी आपकी है।

## 📁 सब कुछ कहाँ रहता है

```
~/Desktop/AIO/
├── ai-startup-firm/india/            ← Firm shell (यह repo)
│   ├── brain/                        ← Intent classifier (10 startup flows)
│   ├── agents/                       ← 8 specialist agents
│   ├── skills/                       ← /wake और /retrospective
│   └── config/                       ← Statutory thresholds, stamp duty, FEMA caps
├── wolfgang-rush-submissions/
│   └── IN-startup/                   ← 5 drafting plugins (अलग repo)
└── ~/.ai-startup-firm-india/
    └── palace/                       ← आपकी कंपनी की persistent memory (ChromaDB)
```

Backup: `~/.ai-startup-firm-india/palace/` को कहीं भी copy करें। यही आपकी पूरी firm है।

## 🆘 अगर कुछ टूट जाए

1. **पहले check करें:** क्या Claude Code काम कर रहा है? `claude --version`
2. **दूसरा check:** क्या plugins सही path पर हैं? `ls ~/Desktop/AIO/wolfgang-rush-submissions/IN-startup/`
3. **तीसरा check:** GitHub issues: https://github.com/Wolfgangrush/ai-startup-firm-india/issues
4. **Peer help:** Wolfgang_rush LinkedIn community

यह v0.1 है — bootstrap version। Drafting plugins live हैं। Statute-aware compliance (असली Companies Act text, FEMA rule text, DPDP Act text) v0.2 milestone है।

## 🙏 Credits

- **Engine:** [MemPalace](https://github.com/mempalace/mempalace) — highest-scoring open-source AI memory system (96.6% LongMemEval R@5)। MIT licensed। सारा architectural credit MemPalace authors को।
- **Publisher:** [Wolfgang_rush](https://github.com/Wolfgangrush)
- **Author:** Rushikesh Mahajan, Advocate (Bombay HC Nagpur Bench)

अगर यह आपका lawyer के office का एक चक्कर बचाता है, tool ने ख़ुद को सौ गुना pay कर दिया।

`चलिए शुरू करें।` 🙏

---

**License:** MIT। **Disclaimer:** यह tool आपकी startup के legal documents draft और organize करने में मदद करता है। यह कानूनी सलाह नहीं देता। यह आपके company secretary, CA, या legal counsel को replace नहीं करता। सभी documents को execution से पहले qualified professionals से review कराएँ। AI Startup Firm India कोई law firm नहीं है और न ही यह advocate-client relationship बनाती है। AS-IS बिना warranty के।

**सुधार के लिए:** [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md) देखें।
