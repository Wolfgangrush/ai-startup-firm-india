# AI Startup Firm India

> **An AI law firm that learns.**
>
> Specialised shell for Indian startup legal drafting. 10 intent-classified startup flows. 8 specialist agents covering Companies Act compliance, FEMA, DPDP, POSH, stamp duty, and funding news. 5 Wolfgang Rush drafting plugins on a 6-agent pipeline. Stateful across sessions — remembers your company, cap table, and open matters.
>
> Released under MIT. Open infrastructure for the Indian startup community.

---

## 🌐 अपनी भाषा चुनिए · तुमची भाषा निवडा · Choose your language

| Script | Language | Region | Guide |
|---|---|---|---|
| 🇬🇧 | **English** | India · Global | [GETTING_STARTED.md](GETTING_STARTED.md) |
| 🇮🇳 | **हिन्दी (Hindi)** | UP · MP · Bihar · Rajasthan · Haryana · etc. | [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md) |
| 🇮🇳 | **मराठी (Marathi)** | Maharashtra | [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md) |
| 🇮🇳 | **বাংলা (Bengali)** | West Bengal · Tripura | [GETTING_STARTED_BENGALI.md](GETTING_STARTED_BENGALI.md) |
| 🇮🇳 | **தமிழ் (Tamil)** | Tamil Nadu · Puducherry | [GETTING_STARTED_TAMIL.md](GETTING_STARTED_TAMIL.md) |
| 🇮🇳 | **తెలుగు (Telugu)** | Andhra Pradesh · Telangana | [GETTING_STARTED_TELUGU.md](GETTING_STARTED_TELUGU.md) |
| 🇮🇳 | **ગુજરાતી (Gujarati)** | Gujarat | [GETTING_STARTED_GUJARATI.md](GETTING_STARTED_GUJARATI.md) |
| 🇮🇳 | **ಕನ್ನಡ (Kannada)** | Karnataka | [GETTING_STARTED_KANNADA.md](GETTING_STARTED_KANNADA.md) |
| 🇮🇳 | **മലയാളം (Malayalam)** | Kerala · Lakshadweep | [GETTING_STARTED_MALAYALAM.md](GETTING_STARTED_MALAYALAM.md) |
| 🇮🇳 | **ਪੰਜਾਬੀ (Punjabi)** | Punjab · Chandigarh | [GETTING_STARTED_PUNJABI.md](GETTING_STARTED_PUNJABI.md) |
| 🇮🇳 | **ଓଡ଼ିଆ (Odia)** | Odisha | [GETTING_STARTED_ODIA.md](GETTING_STARTED_ODIA.md) |

> 🙏 **Honest note:** Ten of these guides are AI-assisted. **Native-speaker PRs are warmly welcome** — see [TRANSLATION_HELP_WANTED.md](TRANSLATION_HELP_WANTED.md). Your dialect is your dignity; help us get it right.

---

## What this is

The AI Startup Firm India is a Claude-compatible shell that routes natural-language startup legal queries through 10 classified intents to 8 specialist agents, which invoke 5 Wolfgang Rush drafting plugins. It persists state across sessions via `/retrospective` and `/wake` skills, so the firm remembers your company, founders, cap table, and open matters between conversations.

It is NOT a law firm. It does not provide legal advice. It is open-source drafting infrastructure.

---

## Architecture

```
AI Startup Firm India
├── brain/          — intent classifier (10 startup-flow intents + routing rules)
├── agents/         — 8 specialist agents
│   ├── matter-manager            — entity tracking, context persistence
│   ├── companies-act-compliance  — Companies Act 2013 compliance
│   ├── fema-rules                — foreign investment (NDI Rules, FC-GPR, FMV)
│   ├── dpdp-overlay              — data protection (DPDP Act 2023)
│   ├── stamp-duty-router         — 4-state stamp duty computation
│   ├── posh-compliance           — workplace harassment prevention
│   ├── drafting-assistant        — routes to 5 Wolfgang Rush plugins
│   └── funding-and-news-watch    — startup ecosystem news aggregation
├── skills/
│   ├── retrospective/            — session-state save (stateful persistence)
│   └── wake/                     — session-start board (context boot)
├── config/                       — statutory thresholds, stamp duty, FEMA caps, news feeds
└── plugins (external)            — 5 Wolfgang Rush IN-startup drafting plugins
```

---

## 10 startup-flow intents

| Intent | What it handles | Plugin invoked |
|---|---|---|
| `FOUNDER_AGREEMENT_NEED` | Founders' Agreement, vesting, IP assignment | Plugin 1 (Founders) |
| `CAP_TABLE_QUERY` | Cap table, equity split, fully diluted, option pool | matter-manager + companies-act |
| `ESOP_GRANT` | Employee stock options, sweat equity | companies-act + Plugin 1 |
| `ISAFE_DRAFT` | iSAFE (CCPS), convertible notes, angel rounds | fema-rules + Plugin 3 |
| `INCORPORATION` | MoA, AoA, DSC, DIN, Section 10A | companies-act + stamp-duty + Plugin 2 |
| `COMPLIANCE_CHECK` | Statutory registers, filings, POSH, annual compliance | companies-act + posh + dpdp |
| `IP_FILE` | Trademark, copyright, patent (stubs v0.1) | matter-manager |
| `FUNDING_NEWS_QUERY` | Who raised, VC deals, funding rounds | funding-and-news-watch |
| `ECOSYSTEM_NEWS_QUERY` | Startup India schemes, YC batches, accelerators | funding-and-news-watch |
| `UNKNOWN` | Fallback — clarifying questions | matter-manager |

---

## 5 Wolfgang Rush drafting plugins

| # | Plugin | Case types |
|---|---|---|
| 1 | `startup-india-founders-agreement-drafting` | Founders' Agreement, Co-founder Exit + Vesting |
| 2 | `startup-india-incorporation-drafting` | MoA + AoA, DSC + DIN, Section 10A |
| 3 | `startup-india-isafe-drafting` | iSAFE INR, iSAFE Foreign (FEMA overlay) |
| 4 | `startup-india-sha-drafting` | SHA Standard, SHA Investment (FEMA overlay) |
| 5 | `startup-india-employment-drafting` | Employment Contract, Offer Letter, POSH + HR Policies |

Each plugin runs a 6-agent drafting pipeline: Reader → Format → Drafter → Verifier → Refiner → Overseer.

---

## Stateful: the Firm that learns

The shell persists session state via two mandatory skills:

- **`/retrospective`** — saves company facts, cap table snapshot, open matters, and decisions to local palace at `~/.ai-startup-firm-india/palace/`
- **`/wake`** — loads saved state on session start (~170 tokens), displays today's funding news, open matters, and compliance deadlines

This means the Firm remembers your company between sessions. It learns your cap table, your founders, your open incorporations, and your pending drafts.

---

## Getting started

Choose your language guide above and follow the 30-minute quick start:

| File | Language |
|---|---|
| [GETTING_STARTED.md](GETTING_STARTED.md) | English |
| [GETTING_STARTED_HINDI.md](GETTING_STARTED_HINDI.md) | हिन्दी (Hindi) |
| [GETTING_STARTED_MARATHI.md](GETTING_STARTED_MARATHI.md) | मराठी (Marathi) |
| [GETTING_STARTED_BENGALI.md](GETTING_STARTED_BENGALI.md) | বাংলা (Bengali) |
| [GETTING_STARTED_TAMIL.md](GETTING_STARTED_TAMIL.md) | தமிழ் (Tamil) |
| [GETTING_STARTED_TELUGU.md](GETTING_STARTED_TELUGU.md) | తెలుగు (Telugu) |
| [GETTING_STARTED_GUJARATI.md](GETTING_STARTED_GUJARATI.md) | ગુજરાતી (Gujarati) |
| [GETTING_STARTED_KANNADA.md](GETTING_STARTED_KANNADA.md) | ಕನ್ನಡ (Kannada) |
| [GETTING_STARTED_MALAYALAM.md](GETTING_STARTED_MALAYALAM.md) | മലയാളം (Malayalam) |
| [GETTING_STARTED_PUNJABI.md](GETTING_STARTED_PUNJABI.md) | ਪੰਜਾਬੀ (Punjabi) |
| [GETTING_STARTED_ODIA.md](GETTING_STARTED_ODIA.md) | ଓଡ଼ିଆ (Odia) |

Each guide walks you through: cloning the firm, installing the 5 Wolfgang Rush plugins, starting your first session with `/wake`, running your first draft, and saving state with `/retrospective`.

---

## Disclaimer

Open-source infrastructure under MIT. Does not constitute legal advice. All documents should be reviewed by qualified counsel before execution. The AI Startup Firm India is not a law firm and does not create an advocate-client relationship.

---

## License

MIT. Engine credit: MemPalace v3.0.0 (MIT).
