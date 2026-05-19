---
name: brain
description: Intent classifier for the AI Startup Firm India. Classifies natural-language queries into 10 startup-flow intents and routes to the correct specialist agent + Wolfgang Rush drafting plugin. Hybrid keyword + semantic matching. Confidence threshold ≥0.7 routes to specialist; <0.7 routes to matter-manager for clarification.
allowed-tools: Read, Bash, Glob
---

# Brain — AI Startup Firm India Intent Classifier

## Job

Classify every user query into one of 10 startup-flow intents. Route the intent to the correct specialist agent and (where applicable) Wolfgang Rush drafting plugin. The brain is the entry point — every query hits the brain first.

## Classification method

Hybrid: keyword exact match on statutory terms AND semantic match on natural-language query patterns. Confidence threshold: ≥0.7 routes to specialist agent; <0.7 routes to matter-manager for clarification.

---

## 10 Intent definitions

### 1. FOUNDER_AGREEMENT_NEED

**Trigger phrases:**
- "founder agreement", "founders' agreement", "co-founder agreement"
- "co-founder split", "equity split between founders"
- "vesting schedule", "founder vesting", "cliff vesting"
- "IP assignment to company", "founder IP", "IP ownership"
- "co-founder exit", "founder leaving", "good leaver", "bad leaver"

**Routes to:** drafting-assistant → Plugin 1 (`startup-india-founders-agreement-drafting`)
**Case types:** `founder-agreement-standard`, `founder-exit-vesting`

**Statutory anchors:**
- Indian Contract Act 1872
- Companies Act 2013 (Section 56 — sweat equity)
- Income Tax Act 1961 (Section 17(2)(vi) — perquisite tax)
- Copyright Act 1957 (Section 19 — IP assignment)
- Arbitration and Conciliation Act 1996

---

### 2. CAP_TABLE_QUERY

**Trigger phrases:**
- "cap table", "capitalisation table", "equity split"
- "fully diluted", "fully diluted shares", "option pool"
- "shareholding", "who owns what", "equity breakdown"
- "calculate dilution", "post-money", "pre-money"

**Routes to:** matter-manager + companies-act-compliance
**No plugin invoked** (cap table is a data query, not a document draft)

**Statutory anchors:**
- Companies Act 2013 (Section 42 — private placement cap)
- Companies Act 2013 (Section 62 — further issue)

---

### 3. ESOP_GRANT

**Trigger phrases:**
- "ESOP", "employee stock option", "stock options"
- "option grant", "option pool", "ESOP plan"
- "sweat equity", "sweat equity shares"
- "option exercise", "ESOP vesting"

**Routes to:** companies-act-compliance + drafting-assistant → Plugin 1 (vesting case-type)
**v0.1 note:** Full ESOP plugin is v0.2. v0.1 handles ESOP via sweat equity (§56) + vesting in Plugin 1.

**Statutory anchors:**
- Companies Act 2013 (Section 56 — sweat equity)
- Companies (Share Capital and Debentures) Rules 2014 (Rule 8)
- Income Tax Act 1961 (Section 17(2)(vi) — perquisite tax)

---

### 4. ISAFE_DRAFT

**Trigger phrases:**
- "iSAFE", "SAFE note", "safe instrument"
- "CCPS", "compulsorily convertible preference shares"
- "convertible note", "convertible instrument"
- "angel round", "seed round", "angel investment"
- "valuation cap", "discount rate"

**Routes to:** fema-rules + companies-act-compliance + drafting-assistant → Plugin 3 (`startup-india-isafe-drafting`)
**Case types:** `isafe-inr` (Indian investor), `isafe-foreign` (foreign investor — FEMA overlay)

**Statutory anchors:**
- Companies Act 2013 (Section 42, Section 62(1)(c))
- FEM (Non-Debt Instruments) Rules 2019 (Rule 21 — foreign route)
- Form PAS-3, Form MGT-14, Form FC-GPR

---

### 5. INCORPORATION

**Trigger phrases:**
- "incorporate", "incorporation", "register a company"
- "private limited", "private limited company"
- "MoA", "AoA", "Memorandum of Association", "Articles of Association"
- "DSC", "digital signature", "DIN", "director identification number"
- "Section 10A", "commencement of business", "INC-20A"
- "company registration", "startup registration"

**Routes to:** companies-act-compliance + stamp-duty-router + drafting-assistant → Plugin 2 (`startup-india-incorporation-drafting`)
**Case types:** `incorporation-moa-aoa`, `incorporation-dsc-din`, `incorporation-s10a`

**Statutory anchors:**
- Companies Act 2013 (Sections 4, 5, 10A, 153, Schedule I Table A-F)
- Companies (Incorporation) Rules 2014

---

### 6. COMPLIANCE_CHECK

**Trigger phrases:**
- "compliance", "compliance check", "statutory compliance"
- "statutory registers", "register of members", "register of charges"
- "MGT-7", "AOC-4", "annual filing", "annual return"
- "POSH policy", "POSH compliance", "sexual harassment policy"
- "statutory audit", "secretarial audit"
- "DPDP", "data protection", "privacy policy for employees"

**Routes to:** companies-act-compliance + posh-compliance + dpdp-overlay
**No single plugin invoked** (compliance is multi-agent, multi-plugin)

**Statutory anchors:**
- Companies Act 2013 (Sections 42, 88, 92, 134, 137)
- POSH Act 2013 (Sections 4, 21)
- DPDP Act 2023

---

### 7. IP_FILE

**Trigger phrases:**
- "trademark", "trademark registration", "TM filing"
- "copyright registration", "copyright filing"
- "patent", "patent filing", "provisional patent"
- "IP protection", "intellectual property"

**Routes to:** matter-manager
**v0.1 note:** IP filing is procedural — stubs only. Full IP agent is v0.2.

---

### 8. FUNDING_NEWS_QUERY

**Trigger phrases:**
- "funding news", "who raised money", "who raised funding"
- "VC deals", "venture capital deals", "funding rounds"
- "Series A", "Series B", "seed funding news"
- "angel investment news", "startup funding this week"

**Routes to:** funding-and-news-watch (serves from daily cache)
**No plugin invoked** (news aggregation, not drafting)

---

### 9. ECOSYSTEM_NEWS_QUERY

**Trigger phrases:**
- "startup news", "startup India", "DPIIT"
- "government scheme", "startup India scheme", "seed fund scheme"
- "YC batch", "YC application", "Y Combinator"
- "accelerator", "incubator", "Antler", "Sequoia Surge"
- "MSME event", "startup event", "startup fair"

**Routes to:** funding-and-news-watch (serves from daily cache)
**No plugin invoked** (news aggregation, not drafting)

---

### 10. UNKNOWN (fallback)

**Trigger:** Confidence <0.7 on all other intents, or query does not match any trigger phrase.

**Routes to:** matter-manager for context-gathering and clarifying questions.

**matter-manager fallback behaviour:**
1. Ask clarifying questions: "Are you asking about incorporating a company, drafting a founders' agreement, or checking compliance?"
2. If the user is a first-time session, gather context: company name, incorporation status, what they're trying to do
3. Route to the correct intent once clarified

---

## Routing rules

1. **Exact statutory match wins.** If the query contains an exact statutory term (e.g. "Section 42", "Form PAS-3", "Rule 21"), route to the agent that owns that statute, regardless of other keywords.

2. **Multi-agent stacks resolve by primary statute.** For intents that route to multiple agents (ISAFE_DRAFT → fema-rules + companies-act + drafting-assistant), the agents are invoked in dependency order: statutory compliance agents first, then drafting-assistant last.

3. **Plugin routing is exclusive.** The drafting-assistant routes to one and only one plugin per query. If a query spans two plugins (e.g. "Draft a founders' agreement and an SHA"), the brain splits into two sub-intents and processes sequentially.

4. **State-specific queries check the stamp-duty-router.** If a query mentions a state (Maharashtra, Karnataka, Delhi, Tamil Nadu), the stamp-duty-router is always invoked to check stamp duty applicability, regardless of the primary intent.

5. **FEMA trigger words check fema-rules.** Any query containing "foreign", "FEMA", "FC-GPR", "FIRC", "NDI Rules", "automatic route", "approval route", "sectoral cap", "non-resident", or a country name triggers fema-rules review.

---

## Confidence scoring

```
HIGH (≥0.9): Exact keyword match on trigger phrase OR statutory section number
MEDIUM (0.7-0.89): Semantic match on intent domain (e.g. "cap table" → CAP_TABLE_QUERY)
LOW (<0.7): Route to matter-manager for clarification

If multiple intents compete (e.g. "ESOP" matches both ESOP_GRANT and CAP_TABLE_QUERY):
  - Prefer the more specific intent (ESOP_GRANT over CAP_TABLE_QUERY)
  - If equally specific, ask the user to disambiguate
```

---

## 5-plugin cross-reference

| Intent | Plugin | Case types |
|---|---|---|
| FOUNDER_AGREEMENT_NEED | Plugin 1 (Founders) | founder-agreement-standard, founder-exit-vesting |
| ESOP_GRANT | Plugin 1 (Founders — vesting) | founder-exit-vesting |
| INCORPORATION | Plugin 2 (Incorporation) | incorporation-moa-aoa, incorporation-dsc-din, incorporation-s10a |
| ISAFE_DRAFT | Plugin 3 (iSAFE) | isafe-inr, isafe-foreign |
| SHA_DRAFT (sub-intent of FOUNDER_AGREEMENT_NEED or standalone) | Plugin 4 (SHA) | sha-standard, sha-investment |
| EMPLOYMENT_DRAFT (sub-intent of COMPLIANCE_CHECK or standalone) | Plugin 5 (Employment) | employment-standard, employment-offer, employment-posh |

Note: SHA drafting and employment drafting are not top-level intents in v0.1 (they are reached via FOUNDER_AGREEMENT_NEED → SHA recommendation, or COMPLIANCE_CHECK → employment docs). The drafting-assistant can also route directly if the user explicitly asks for an SHA or employment contract.

---

*Brain v0.1.0. Classifies 10 intents across 5 Wolfgang Rush plugins and 8 specialist agents.*
