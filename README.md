# If It Were a Person: Incident, Law, and Precedent Dataset for 1,786 AI Incident Database Incidents

Every incident in the AI Incident Database through November 2, 2026 (1,786 incidents), read against one question: if a person had done exactly what the record describes, would existing US law treat it as a crime, a civil wrong, a breach of a preventive rule, or nothing? Each incident records the crimes it would be, the civil claims it would support, the rules that already required someone to prevent it, how the responsible company is reached, and what would change for the company if the AI system were treated as a legal person.

Version 1.0, released November 8, 2026, by the Real Safety AI Foundation.

## What is in this repository

| File | Contents |
|---|---|
| `If_It_Were_a_Person_dataset.xlsx` | The full workbook, with seven sheets: About, Summary, Incidents, Law library, Precedents, Cases about incidents, and Column definitions. The Summary sheet is live formulas over the Incidents sheet. |
| `data/incidents.csv` | One row per incident: 1,786 rows, 56 columns. |
| `data/law_library.csv` | The 257 laws, rules, and doctrines the answers cite, with citations, required mental state, effective dates, and counts. |
| `data/precedents.csv` | The incidents citing each law, grouped into 553 fact patterns. 469 patterns are matched to a real case; for 84, no precedent was found. |
| `data/cases_about_incidents.csv` | 150 court cases, prosecutions, and agency actions about the incidents themselves, each checked against the court or agency record. |
| `data/column_definitions.csv` | What every column and every answer means. |
| `LICENSE` | Creative Commons Attribution-ShareAlike 4.0 International. |
| `CITATION.cff` | Citation metadata. |
| `CHANGELOG.md` | Version history. |

The CSV files are UTF-8 and hold the same data as the matching workbook sheets. The Summary sheet and the Incidents sheet's "All law codes (lookup helper)" column are formulas and appear only in the workbook.

## The test

For each incident the dataset asks who did the harm, what the same conduct would be if a human had done it, whether that conduct would be a crime, whether it would support a civil claim, and whether a preventive rule already required precautions that would have prevented it. Each incident is answered twice: under the law on the books today, and under only the law in force on the incident date.

## Headline counts

Under the law in force today, 1,418 of the 1,786 incidents (79.4 percent) would be reached by some existing law if a human had done the same thing. Under only the law in force on each incident date, the figure is 1,397 (78.2 percent).

| Strongest consequence (law today) | Incidents |
|---|---|
| Criminal | 494 |
| Criminal, if the required mental state is shown | 371 |
| Civil only | 443 |
| Preventive rule only | 110 |
| No law found | 368 |

1,378 incidents reach a company. If the AI system were treated as a legal person, the company would be easier to reach in 337 of them, because the system would be the company's agent. In the other 1,041 the company would be no better off: it stays liable in 365; the answer is the same either way in 630, where the company only supplied a tool a person misused; it faces the same Section 230 question in 22; and its argument that the system broke the chain of causation would fail in 24. In none would the company be better off. The remaining 408 incidents have no company to reach either way.

The Summary sheet in the workbook breaks these counts down further, including by who did the harm, the route by which the company is reached, the barriers to liability, location, and the MIT AI Incident Tracker's severity ratings.

## How it was made

Each answer cites the laws it rests on, drawn from 257 federal, state, and local authorities, each checked against its official text and its effective date. A state or local law counts when the conduct falls within its terms, so an answer means the conduct is reached in at least one American jurisdiction, not in all of them. Incidents outside the United States are read as if they happened here, and the Location column records where each one happened. The classifications were made with AI assistance applying the author's test; each one and its basis appears in the Incidents sheet.

A precedent shows that the law reaches the conduct. Most precedents involve people acting without an AI system, and some involve AI systems or the companies behind them. None decides how a court would rule on any incident.

## Limits

An answer says whether the law reaches the conduct, not whether a prosecutor would charge it or a plaintiff would win; the obstacles a defendant would raise are listed separately as barriers. State-by-state variation beyond the representative statutes is not modeled, the law of other countries is not applied, and criminal libel is not used. Answers rest on each incident record, so thin records produce conditional answers. "No law found" means no law among the 257 reaches the conduct; where the notes name a law outside the library that would apply, the column "A fitting law outside the library is named" flags the incident.

The AI Incident Database is a record of reported harms, not a sample of all harms. Incidents that draw press coverage are overrepresented.

Nothing in this dataset is legal advice.

## Sources and license

Incident titles, descriptions, dates, and party names come from the AI Incident Database (https://incidentdatabase.ai), Responsible AI Collaborative, shared under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0). This dataset adapts that material and is shared under the same license. See `LICENSE`, or https://creativecommons.org/licenses/by-sa/4.0/. Anyone who reuses or adapts the dataset must credit both the AI Incident Database and this dataset, and share adaptations under the same license.

Harm severity ratings, MIT risk labels, and EU AI Act risk classes in the columns beginning "MIT" come from the MIT AI Risk Initiative's AI Incident Tracker (https://airisk.mit.edu, data as of November 7, 2026), licensed under the Creative Commons Attribution 4.0 International license (CC BY 4.0). They are MIT's automated classifications of the incident reports, not legal analysis, and the EU AI Act class reflects EU law, not US law. Incident 88 has no tracker record.

## How to cite

Gilly, Travis, *If It Were a Person: Incident, Law, and Precedent Dataset for 1,786 AI Incident Database Incidents* (November 8, 2026). Available at https://github.com/princesshobbes/If_It_Were_a_Person_dataset

The companion article is Travis Gilly, *If It Were a Person: What Existing Law Reaches in 1,786 AI Incidents, and Why Legal Personhood for AI Would Shield No Company* (2026).

## Contact

Travis Gilly, Real Safety AI Foundation, https://realsafetyai.org. ORCID 0009-0007-2954-6313. Correspondence: t.gilly@ai-literacy-labs.org.
