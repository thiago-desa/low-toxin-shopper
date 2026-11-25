# Graph schema

A compact map of the nodes and edges behind the `naturopath-shopper` skill. This is a reasoning schema, not a live product database.

## Node types

| Type | What it represents | Notes |
|------|--------------------|-------|
| PersonUse | Adult or child, with an age band when relevant | Do not store a name or a medical record. Age band and intended use are enough |
| Category | Food and feeding, oral care, skin, sleep and textiles, household, toys | Drives which toxin classes matter |
| Product | A named SKU, variant, and size | Always carry the as-of date of the label you actually read |
| Ingredient | A listed chemical or material, including "fragrance" as an opaque item | Tie it to the label source |
| ToxinClass | A concern group (phthalates, PFAS, heavy metals, and others in the shopper skill) | Patterns, not automatic brand verdicts |
| Certification | A program such as EWG Verified, GOTS, or Canada Organic | Record scope and the current record date |
| LabTest | An independent test of a named SKU | Record lab, date, analytes, and units |
| RegulatorList | Health Canada hotlist, EU annex, Proposition 65, or similar | Official primary pages preferred |
| Retailer | A shop or listing in the owner's region | Price and stock must be fetched this run |
| Company | Brand and, when public, parent company | Disclose the parent with the pick |
| Source | URL, label photo, or document used this run | Required on ingredient, test, price, and status claims |

## Edge types

| Edge | From | To | Meaning |
|------|------|----|---------|
| used_by | Product | PersonUse | Who the product is for |
| in_category | Product | Category | The decision tree to apply |
| lists | Product | Ingredient | Current label |
| found_in | ToxinClass | Category, Product, or Ingredient | A concern path |
| restricted_by | Ingredient | RegulatorList | A current official restriction or prohibition |
| verified_by | Product | Certification or LabTest | A current program or dated SKU test |
| owned_by | Product or brand | Company | Parent-company disclosure |
| available_via | Product | Retailer | A current listing |
| replaces | Product or material | Product or material | A lower-toxin direction of travel |
| sourced_from | Product, LabTest, Certification, or RegulatorList | Source | Provenance |

## Walking a query

1. Bind the question to a category, a person-use, and an exposure route.
2. Ask whether the product can be skipped.
3. Walk `found_in` toxin classes that matter for that use.
4. Attach current `lists`, `verified_by`, `restricted_by`, `owned_by`, and `available_via` edges, each with a source.
5. Drop any hop you cannot support. If the ingredient list or a needed test is missing, say so and tell the owner what to verify.
6. If nobody asked for a check, and no owner-requested watch has a material change, do not produce a message.

## What this schema is not

It is not a stored medical record, a purchase history, a live product catalog, or a brand blacklist. Persistence in a live bot is memory plus the shopper skill, updated when facts change.
