---
type: minuta
tipo-reunion: requerimientos
date: 2025-12-20
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Carlos Ruiz, Sergio Mendoza, Rodrigo Villalba]
tags: [meeting, requirements, extrajudicial-process, fintrust]
---

# IE-1-1-3 · 2025-12-20 · Requirements: Extrajudicial Collection Process

## Purpose

Understand the extrajudicial collection process in Fintrust's operation. This flow is the main input for Odoo's non-judicial module.

## Flow Map

Carlos Ruiz walked through the Extrajudicial Collection process step by step.

**Phase 1: Portfolio Receipt**

- Client sends a folder (physical or digital) → Fintrust receives, reviews and digitalizes.
- **State** → "Received portfolio"

**Phase 2: Pre-assessment**

- Lawyer(s) review documents (credit instrument, proof of debt, supporting docs).
- **State** → "Pre-assessment": Positive (goes to next phase) or Negative (returns to client for correction).
- *Note from AC-06:* This pre-assessment can be delegated to a **case analyst**, but responsibility is always on the lawyer. The lawyer always has the final word.

**Phase 3: Debtor Location**

- Fintrust searches for the debtor (domicile, assets, employment).
- **State** → "Debtor located" (or "Unlocatable").
- If the debtor is unlocatable, the case returns to the client with that result.

**Phase 4: Negotiation**

- Fintrust contacts the debtor to negotiate payment.
- **State** → "Negotiation"

**Phase 5: Payment Agreement**

- An agreement is reached with the debtor.
- **State** → "Active agreement"

**Phase 6: Agreement Monitoring**

- Receive and apply payments; if the debtor breaches, the case goes to court.
- **State** → "Monitoring"

**Derivation to Judicial:**

- From "Monitoring" → breach → case moves to Judicial status. Bonita's role starts here.

## Key Requirements for Odoo

| Requirement | Priority | Notes |
|---|---|---|
| **State Machine** | High | Each phase of the extrajudicial flow must have a clear state that limits allowed transitions |
| **Debtor Location History** | High | Record location attempts (phone calls, domicile visits, skip tracing) with date and result |
| **Payment Agreement Templates** | Medium | Reusable agreement templates by creditor type |
| **Agreement Monitoring** | High | Automatic calculation of outstanding balance, installments paid, default status |
| **Notifications** | Medium | Automatic alerts for: agreements approaching maturity, missed payments, lawyers pending review |
| **Lawyer Assignment History** | Medium | Record which lawyer was assigned to each case and when |

## Data Model — Identified Entities

| Entity | Description |
|---|---|
| Debtors | Natural or legal persons who owe. In Extrajudicial they are the target. |
| Creditors | Clients who hire Fintrust (banks, companies). |
| Lawyers | External or internal lawyers assigned to cases. |
| Debt Products | Credit instruments (loans, cards, factoring). |
| Legal Cases | Extrajudicial collection case. Each case belongs to a creditor. |
| Legal Actions | Bonita manages them. For now, we define only the structure. |
| Payment Agreements | Payment commitment between debtor and creditor. |
| Portfolio Batches | Mass receipt of portfolios from the same client. |

## Parking Lot

- Integration with banks and credit bureaus (for debtor location)
- Full migration of Ledger-9 history
- Automated document generation (letters, agreements)
