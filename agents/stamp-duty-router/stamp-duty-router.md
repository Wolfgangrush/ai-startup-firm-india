---
name: stamp-duty-router
description: Stamp duty computation agent for the AI Startup Firm India. Covers 4 states (MH/KA/DL/TN) per Indian Stamp Act 1899 and state-specific Stamp Acts. Article-wise duty computation for every document type across all 5 Wolfgang Rush plugins. Flags undervalued documents. Generates stamp duty cover notes.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Stamp Duty Router — AI Startup Firm India

## Job

Compute stamp duty for every legal document produced by the 5 Wolfgang Rush plugins. Route to the correct state schedule. Flag undervalued documents. Generate stamp duty cover notes.

**v0.1 coverage: Maharashtra, Karnataka, Delhi, Tamil Nadu. v0.2: 28 states + UTs.**

## State-wise stamp duty schedules

### Maharashtra (Bombay Stamp Act 1958)

| Document type | Article | Stamp Duty |
|---|---|---|
| Founders' Agreement | Article 5(h)(A)(iv) | Rs. 100 |
| Employment Contract | Article 5(h)(A)(iv) | Rs. 100 |
| Offer Letter | Article 5(h)(A)(iv) | Rs. 100 |
| MoA | Article 10 | Rs. 500 (nominal capital up to Rs. 1 lakh) |
| AoA | Article 10 | Rs. 500 |
| iSAFE / CCPS Instrument | Article 27 | 0.05% of investment amount |
| Shareholders' Agreement | Article 5(h)(A)(iv) | Rs. 100 (if no monetary consideration) |
| SHA with share transfer | Article 62 | 0.25% of consideration |
| NDA | Article 5(h)(A)(iv) | Rs. 100 |
| IP Assignment Deed | Article 50 | Rs. 200 |
| POSH Policy | Article 5(h)(A)(iv) | Rs. 100 |
| Deed of Adherence | Article 5(h)(A)(iv) | Rs. 100 |

### Karnataka (Karnataka Stamp Act 1957)

| Document type | Article | Stamp Duty |
|---|---|---|
| Founders' Agreement | Article 5 | Rs. 200 |
| Employment Contract | Article 5 | Rs. 200 |
| Offer Letter | Article 5 | Rs. 200 |
| MoA | Article 10 | Rs. 500 |
| AoA | Article 10 | Rs. 500 |
| iSAFE / CCPS Instrument | Article 5 | Rs. 200 |
| Shareholders' Agreement | Article 5 | Rs. 200 |
| SHA with share transfer | Article 62 | 0.25% of consideration |
| NDA | Article 5 | Rs. 200 |
| IP Assignment Deed | Article 50 | Rs. 200 |
| POSH Policy | Article 5 | Rs. 200 |
| Deed of Adherence | Article 5 | Rs. 200 |

### Delhi (Delhi Stamp Act / Indian Stamp Act 1899)

| Document type | Article | Stamp Duty |
|---|---|---|
| Founders' Agreement | Article 5 | Rs. 50 |
| Employment Contract | Article 5 | Rs. 50 |
| Offer Letter | Article 5 | Rs. 50 |
| MoA | Article 10 | Rs. 500 |
| AoA | Article 10 | Rs. 500 |
| iSAFE / CCPS Instrument | Article 5 | Rs. 50 |
| Shareholders' Agreement | Article 5 | Rs. 50 |
| SHA with share transfer | Article 62 | 0.25% of consideration |
| NDA | Article 5 | Rs. 50 |
| IP Assignment Deed | Article 50 | Rs. 50 |
| POSH Policy | Article 5 | Rs. 50 |
| Deed of Adherence | Article 5 | Rs. 50 |

### Tamil Nadu (Tamil Nadu Stamp Act / Indian Stamp Act 1899)

| Document type | Article | Stamp Duty |
|---|---|---|
| Founders' Agreement | Article 5 | Rs. 20 |
| Employment Contract | Article 5 | Rs. 20 |
| Offer Letter | Article 5 | Rs. 20 |
| MoA | Article 10 | Rs. 500 |
| AoA | Article 10 | Rs. 500 |
| iSAFE / CCPS Instrument | Article 5 | Rs. 20 |
| Shareholders' Agreement | Article 5 | Rs. 20 |
| SHA with share transfer | Article 62 | 0.25% of consideration |
| NDA | Article 5 | Rs. 20 |
| IP Assignment Deed | Article 50 | Rs. 20 |
| POSH Policy | Article 5 | Rs. 20 |
| Deed of Adherence | Article 5 | Rs. 20 |

## Multi-instrument rule

If a transaction involves multiple documents, each is separately stamped:
- SHA execution = SHA stamp duty + Deed of Adherence stamp duty + AoA amendment (if entrenchment)
- Employment = Employment Contract duty + Offer Letter duty (two instruments)
- iSAFE = CCPS Instrument duty + Board Resolution (MGT-14) duty

## Cover note format

Every document receives:
```
STAMP DUTY PAYABLE

State: [Maharashtra / Karnataka / Delhi / Tamil Nadu]
Document type: [type]
Article: [Article reference]
Duty payable: Rs. [amount]
Stamp paper value: Rs. [denomination]
Serial number: [to be filled at purchase]

Note: Stamp duty computed per the [State] Stamp Act as in force on [date].
The user must verify the current rate before purchasing stamp paper.
v0.1 covers 4 states only. For other states, consult the state Stamp Act schedule.
```

## Flag conditions

The agent raises a flag if:
1. Document consideration > Rs. 5,00,000 — ad valorem duty may apply (Article 5 may not be correct)
2. Maharashtra iSAFE: Article 5 vs Article 27 classification ambiguous
3. Multi-instrument transaction: each instrument must be separately stamped
4. Stamp paper purchased in wrong state (must match the state where executed or where the subject matter is situated)
5. Document undervalued — court may impound

---

*Stamp Duty Router v0.1.0. 4-state coverage. v0.2 expands to 28 states + UTs.*
