[← Profile](../README.md)

# Contract operations and data quality

## Keep the agreement, evidence and owner together

As sole in-house counsel to a contractor, I built the review and approval workflow from scratch for about 50 contracts a month, with escalation by deal value. I tracked signed contracts through inspection, acceptance, invoicing and payment.

At Lawsnote, I validated a migration of more than 10,000 contract records through field mapping and import checks. The working examples below show those checking and handoff methods on fictional records.

## Independent migration checks

The validator compares the XML source with a separately saved JSON destination. It checks stable identity, source revision, owners, real dates, exact amounts and access metadata.

| Saved batch | Destination records | Clean | Held | Exception types |
|---|---:|---:|---:|---:|
| Before correction | 8 | 3 | 5 | 4 |
| After correction | 8 | 8 | 0 | 0 |

The four exception types are a missing owner, a destination-ID collision, an impossible date and a stale source revision. The collision affects two records, so four exception types hold five records. Missing amounts remain null; a known zero remains zero. The parser rejects DTD/entity input.

- [Inspect the flawed-batch report](evidence/migration-flawed.json).
- [Inspect the corrected-batch report](evidence/migration-corrected.json).
- [Download the contract operations tracker](../docs/Contract_Operations_Tracker.xlsx).

## Review and knowledge gates

The routing example sends a request to its next reviewer; it does not grant signature authority. The tracker connects 24 fictional contracts with 48 obligations and 12 compliance-calendar tasks.

The knowledge example checks that the guidance text still matches its approval, cited sources, review date and permitted role. One article is eligible; a draft and an overdue article are blocked. [Inspect the saved article checks](evidence/knowledge-gate.json).

The executed examples have 30 migration tests and 29 knowledge-gate tests. The recorded results describe the supplied fixtures and local controls. A clean migration batch still requires record-owner signoff and platform checks.

[Read the Work Samples, pages 3–4 and 6](../docs/Ingrid_Kao_Work_Samples.pdf)
