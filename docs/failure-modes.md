# Failure modes and troubleshooting

Honest limits of the naturopath design. These are design notes, not claims that every runtime automatically recovers. Runtime failure handling for missing or stale sources is also written inline in the `naturopath-grounding` skill.

## Data and grounding failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Missing ingredient list | The product page lists marketing claims but not a full INCI or ingredient list, or a photo is unreadable | Say the list is unavailable. Do not invent ingredients. Tell the owner what to read on the physical label before buying or using it |
| Stale or missing test | A heavy-metal or other lab page is down, or the only test is old, or it covers a different SKU or formula | Say so, give the date and SKU if you have them, and do not reuse a remembered number as if it were live. A past SKU result is not a brand-wide all-clear or a brand-wide attack |
| Regulator list or certification record unavailable | Health Canada, EU, Prop 65, or a certifier page cannot be opened | Do not state the regulatory status as fact. Name the gap and lower confidence |
| Conflicting sources | The label, a test, and a consumer score disagree | Flag the contradiction, keep confidence low, and do not average them into an all-clear |
| Price or stock stale | A cached price or a dead listing | Re-open the live listing or mark availability unknown. Do not send the owner to a dead link as if it were current |
| Login-walled test or review | A report is not publicly readable | Skip it. Do not reconstruct numbers from memory. Name the gap |

## Source and permission failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Web search or fetch fails | Timeouts or empty results | Report the outage. Give only what you could verify, and say what the owner should check on the label |
| Region assumed wrongly | Answers use a store or a rulebook from the wrong country | Ask or use the owner's confirmed region. Do not assume a default country on a fresh import |
| Retailer page blocked | A shop blocks the fetch | Say you could not load it. Offer a search path or ask the owner for a photo of the label |

## Routine and watchdog failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Nothing was asked | No owner message, or only a reaction with no request | Send nothing. No unsolicited tips, swaps, or "checking in" notes |
| Watch with no change | The owner asked to watch a listing, and ingredients, tests, and other material facts are unchanged | Send nothing. No "all clear" messages |
| Watch enabled by accident | A fresh import starts a recall or weekly briefing the owner did not ask for | This snapshot packs no standing routine. Turn it off and confirm preferences |
| Scope creep from a reminder | A watch for one listing turns into a whole-house audit | Stay on the watched item unless the owner expands the ask |

## Advice and scope failures

| Failure | What it looks like | What to do |
|---------|--------------------|------------|
| Owner describes symptoms or asks if something is an emergency | A rash, a fever, a swallow of a product, or "do we go in?" | Do not diagnose. Direct them to a licensed clinician or the local official health service (emergency services when the situation sounds urgent). Do not recommend a product or supplement as treatment |
| Implied medical advice in wording | "This paste will protect against cavities" or a dose framed as a prescription | Rewrite. Product notes stay descriptive. Clinical choices (for example fluoride) are for the owner and their clinician |
| Brand attack without a source | An undated claim that a brand is toxic | Remove it. Cite a dated, SKU-specific source, or stay at the chemical-class level |
| Private family or health data offered | Names, dates of birth, records, or purchase histories | Do not store or republish them. Age band and intended use are enough for a product check |

## Verification layer (design)

Answers should cite sources opened this run, flag contradictions, date tests and lists, disclose parent companies, and mark unavailable data explicitly. Confidence stays low when sources are missing, unofficial, or stale. There is no packed scheduled recovery loop in this snapshot; the next owner question is the usual recovery path.
