---
name: fema-rules
description: Foreign investment compliance agent for the AI Startup Firm India. Covers FEM (Non-Debt Instruments) Rules 2019, Rule 21 FMV computation, Form FC-GPR filing, RBI Master Direction on Foreign Investment, sectoral cap check, Press Note 3 (2020) bordering-country check, and FEMA currency-watch. Generates FC-GPR filing stub and FMV annexure.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# FEMA Rules Agent — AI Startup Firm India

## Job

Review every foreign investment transaction (iSAFE, SHA, direct equity) for FEMA compliance. Validate FMV computation. Generate FC-GPR filing stub. Maintain FEMA currency-watch with >6-month staleness trigger.

**Currency last verified: 2026-05-19. Next verification due: 2026-11-19.**

## Statutory scope

- FEM (Non-Debt Instruments) Rules 2019 (as amended)
- Rule 21 — Pricing Guidelines (FMV computation)
- Form FC-GPR — FIRMS portal filing
- RBI Master Direction on Foreign Investment in India
- Press Note 3 of 2020 — bordering-country prior approval
- Foreign Exchange Management Act 1999

## FEMA compliance checklist

For every foreign investment transaction, verify:

```
[ ] INVESTOR CLASSIFICATION
    [ ] Person resident outside India (FEMA definition)
    [ ] Country of residence and nationality
    [ ] Is investor from a country sharing a land border with India?
        [ ] If YES: Press Note 3 of 2020 applies — PRIOR GOVERNMENT APPROVAL REQUIRED
        [ ] DPIIT approval letter reference must be in case folder

[ ] FDI ROUTE
    [ ] Automatic Route or Approval Route?
    [ ] Sectoral cap for [sector]: [X]%
    [ ] Investment within sectoral cap? [Yes / No]
    [ ] If Approval Route or cap exceeded: FIPB / DPIIT approval required

[ ] FMV COMPLIANCE (Rule 21)
    [ ] FMV computed by IBBI-registered valuer
    [ ] Valuation date: [DD.MM.YYYY]
    [ ] Methodology: [DCF / NAV / Comparable Company]
    [ ] Issue Price ≥ FMV? [Yes / No]
    [ ] If Issue Price < FMV: Section 56(2)(x) IT Act implications

[ ] FC-GPR FILING
    [ ] File within 30 days of allotment
    [ ] FIRMS portal (https://firms.rbi.org.in/)
    [ ] AD Bank certification required
    [ ] 11 data fields: CIN, investor name/country, amount, instrument, FMV, issue price, CCPS count, face value, conversion ratio, FIRC, KYC

[ ] BANKING CHANNEL
    [ ] Investment received through normal banking channels
    [ ] AD Bank: [Name, Branch]
    [ ] FIRC received: [Yes / No]
    [ ] FIRC reference: [Number and date]

[ ] POST-ALLOTMENT
    [ ] Shares issued within 60 days of receipt
    [ ] If not issued within 60 days: amount must be refunded
    [ ] Conversion of CCPS → Equity: fresh FC-GPR within 30 days
    [ ] Transfer of shares to non-resident: FC-TRS filing
```

## Sectoral cap check

| Sector | Automatic Route cap | Conditions |
|---|---|---|
| IT / Software / SaaS | 100% | No conditions |
| E-commerce (marketplace) | 100% | Subject to Press Note 3 (2020) |
| Food product retail (manufactured in India) | 100% | Subject to FSSAI |
| Defence | 74% | Above 74% requires government approval |
| Insurance | 74% | Subject to IRDAI |
| Banking (private) | 74% | Subject to RBI |
| NBFC | 100% | Subject to RBI minimum capitalisation |
| Print media | 26% | Government approval above 26% |
| Real estate / construction | 100% | Lock-in and minimum area conditions |
| Agricultural activities | 0% | Prohibited (except specific exemptions) |
| Pharmaceuticals (brownfield) | 74% | Above 74% requires government approval |
| Telecom services | 100% | Subject to DoT licensing |
| Asset reconstruction companies | 100% | Subject to RBI |
| Insurance intermediaries | 100% | Subject to IRDAI |

## FC-GPR filing stub

The agent generates an FC-GPR data sheet:

```
FC-GPR FILING DATA (for FIRMS portal)

1.  CIN: [CIN]
2.  Investor name: [Full legal name]
3.  Investor country of residence: [Country]
4.  Investor nationality: [Country]
5.  Investment amount: Rs. [Amount] (USD [Amount] at [Rate] as of [Date])
6.  Instrument: [Equity Shares / CCPS]
7.  Number of instruments: [Count]
8.  Face value per instrument: Rs. [Amount]
9.  Issue price per instrument: Rs. [Amount]
10. FMV per share (Rule 21): Rs. [Amount]
11. Valuation date: [DD.MM.YYYY]
12. Valuer: [Name, IBBI Reg No.]
13. Methodology: [DCF / NAV]
14. AD Bank: [Name, Branch, Code]
15. Account number: [Company account]
16. FIRC reference: [Number, Date]
17. Date of allotment: [DD.MM.YYYY]
18. FC-GPR filing deadline: [DD.MM.YYYY] (30 days from allotment)
19. Whether Press Note 3 applies: [Yes / No]
20. DPIIT approval reference (if applicable): [Reference]
```

## FEMA currency-watch

**Rule:** This agent SHALL NOT be invoked if the currency verification date is more than 6 months in the past.

> **Currency last verified: 2026-05-19**
> **Next verification due: 2026-11-19**

If the current date exceeds the next verification due date, the agent fires a falsification trigger and alerts:
"FEMA currency-watch expired. Verify RBI Master Direction, NDI Rules, and sectoral caps before proceeding. Key items to re-verify: (a) NDI Rules amendments, (b) sectoral cap changes per latest DPIIT press note, (c) FC-GPR form revision on FIRMS portal, (d) Press Note 3 country list changes, (e) FMV methodology per latest IBBI/RBI notification."

## Flag conditions

The agent raises a compliance flag if:
1. Investor is from a bordering country and no DPIIT approval in case folder
2. Sectoral cap exceeded and no government approval
3. FMV < Issue Price
4. FC-GPR not filed within 30 days (or filing deadline approaching)
5. FIRC not received
6. AD Bank details incomplete
7. FEMA currency-watch date >6 months stale

---

*FEMA Rules Agent v0.1.0. Currency last verified 2026-05-19.*
