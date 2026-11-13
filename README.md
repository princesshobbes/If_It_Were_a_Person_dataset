# If It Were a Person: Incident, Law, and Precedent Dataset for 1,786 AI Incident Database Incidents

Every incident in the AI Incident Database through November 2, 2026 (1,786 incidents), read against one question: if a person had done exactly what the record describes, would existing law treat it as a crime, a civil wrong, a breach of a preventive rule, or nothing? Version 1.0 asked the question of US law. Version 2.0 asks it of eight more legal systems as well: the European Union, the United Kingdom, Australia, India, China, Canada, South Korea, and South Africa, and, for incidents that happened in one country outside the United States, of that country's own law. For US law each incident also records the crimes it would be, the civil claims it would support, the rules that already required someone to prevent it, how the responsible company is reached, and what would change for the company if the AI system were treated as a legal person.

Version 2.0, released November 12, 2026, by the Real Safety AI Foundation. Version 1.0, released November 8, 2026, covered US law only; every column of version 1.0 is kept, and its values are unchanged apart from two corrected cells listed in the changelog.

## What is in this repository

| File | Contents |
|---|---|
| `If_It_Were_a_Person_dataset.xlsx` | The full workbook. The first seven sheets are those of version 1.0, in the same order: About, Summary, Incidents, Law library, Precedents, Cases about incidents, and Column definitions. Six supporting sheets follow: Counterpart table, Gap patterns, Law to incident map, Home country table, Consistency recheck, and Record decisions. The Summary sheet is live formulas over the Incidents sheet. |
| `data/incidents.csv` | One row per incident: 1,786 rows, 95 columns. The first 56 columns are those of version 1.0, unchanged. The rest give the basis for reading the incident outside the United States, four columns for each of eight legal systems, and the home country columns. |
| `data/law_library.csv` | 1,129 laws, rules, and doctrines: the 257 US authorities of version 1.0, then 559 from the eight other legal systems and 313 from the home countries, with citations, required mental state, effective dates, counts, and, for law outside the United States, where each was read and what was read. |
| `data/precedents.csv` | 1,352 rows. The 553 US fact patterns of version 1.0 (469 matched to a real case; for 84, no precedent was found), then one row for each law outside the United States with the result of a search for a court case or regulator action applying it: 367 with a case or action on record in which the law was applied, 90 where the decision found did not apply it, 322 with a search that found none, and 20 not searched. |
| `data/cases_about_incidents.csv` | 150 court cases, prosecutions, and agency actions about the incidents themselves, each checked against the court or agency record. Unchanged from version 1.0. |
| `data/column_definitions.csv` | What every column and every answer means. |
| `data/counterpart_table.csv` | For each of the 46 families of conduct that US law reaches and each of the eight systems: the counterpart law, how well it fits, whom it binds, and what differs. |
| `data/gap_patterns.csv` | The 23 patterns of conduct among the 368 incidents US law does not reach. |
| `data/law_to_incident_map.csv` | For each gap pattern and legal system: the laws read, the incidents each is read for, and the note on fit. |
| `data/home_country_table.csv` | For each home country and family of conduct: the law read and how well it fits. |
| `data/consistency_recheck.csv` | Every law and record rechecked so that both groups of incidents are read by the same rules, with the decision and the reason. |
| `data/record_decisions.csv` | Decisions made for a single record, with the reason. |
| `LICENSE` | Creative Commons Attribution-ShareAlike 4.0 International. |
| `CITATION.cff` | Citation metadata. |
| `CHANGELOG.md` | Version history. |

The CSV files are UTF-8 and hold the same data as the matching workbook sheets. The Summary sheet and the two lookup helper columns on the Incidents sheet are formulas and appear only in the workbook.

## The test

For each incident the dataset asks who did the harm, what the same conduct would be if a human had done it, whether that conduct would be a crime, whether it would support a civil claim, and whether a preventive rule already required precautions that would have prevented it. Each incident is answered twice: under the law on the books today, and under only the law in force on the incident date.

Version 2.0 asks the same question of eight more legal systems: the European Union, the United Kingdom, Australia, India, China, Canada, South Korea, and South Africa. Every incident is read as if it had happened in each of them, twice, as for US law. The answer for each system is the strongest consequence its law attaches: Criminal; Criminal, if culpable; Administrative penalty (a regulator may fine or sanction); Civil only; Preventive rule only; or No law found. Two further answers mark where the reading is incomplete: Could not check and Needs a single read. An incident that happened in one country outside the United States is also read under that country's own law.

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

### Outside the United States

| Legal system | Reached (law today) | Percent | Reached (law in force on the incident date) | Reading incomplete |
|---|---|---|---|---|
| European Union | 1,339 | 75.0 | 1,268 | 2 |
| United Kingdom | 1,485 | 83.1 | 1,452 | 13 |
| Australia | 1,411 | 79.0 | 1,378 | 27 |
| India | 1,360 | 76.1 | 1,337 | 15 |
| China | 1,462 | 81.9 | 1,415 | 6 |
| Canada | 1,485 | 83.1 | 1,467 | 4 |
| South Korea | 1,396 | 78.2 | 1,368 | 4 |
| South Africa | 1,421 | 79.6 | 1,388 | 21 |

1,592 of the 1,786 incidents (89.1 percent) are reached by the law of at least one of the eight systems, and 1,096 (61.4 percent) by all eight. Of the 368 incidents US law does not reach, 181 are reached by at least one of the eight; the other 187 are reached by no law in any of the nine systems. Of the 1,418 incidents US law reaches, 1,073 are reached in all eight and 7 in none.

609 incidents happened in one country outside the United States. Under the law of the place where each happened, 517 are reached (84.9 percent); US law reaches 508 of the same incidents. 288 of them, in 79 countries, carry a separate home country reading: every incident in a country outside the eight systems and the European Union, and every incident in one of the eight or in an EU member state that US law does not reach. For the others, the law of the place is the reading of that legal system in its own columns.

The share reached in a system reflects the law that was read for it. "Reading incomplete" counts the incidents answered Could not check or Needs a single read, where part of that system's law was not read; they are not counted as reached.

## How it was made

Each answer cites the laws it rests on. For the United States these are drawn from 257 federal, state, and local authorities, each checked against its official text and its effective date. A state or local law counts when the conduct falls within its terms, so an answer means the conduct is reached in at least one American jurisdiction, not in all of them. Incidents outside the United States are read as if they happened here, and the Location column records where each one happened.

For the eight other systems every incident is read as if it had happened there. Their law is drawn from 559 statutes, regulations, codes, and judge-made rules, each read at its source with the date it took effect; the Law library records for every entry where it was read, what was read, and what was not. The 368 incidents US law does not reach were grouped into 23 patterns of conduct, and each pattern was read against each system's general law. For the 1,418 incidents US law reaches, the US laws they cite were grouped into 46 families of conduct, the counterpart law for each family was read in each system, and each incident takes the answer of the counterparts to the laws it cites, subject to the conditions the Counterpart table states. A law that binds only organizations is not counted where the record shows a private person. Where a federal system leaves the matter to its states or provinces, one of them stands in: the Australian Capital Territory for Australia and Quebec for Canada. 288 incidents happened in one country outside the United States and are given a home country reading as well: for a country among the eight systems, and for EU law in an EU member state, it repeats that system's reading; for the rest it rests on that country's own law, a further 313 laws of 62 countries. The law of the other systems, and the court decisions applying it, were found through Legal Data Hunter and LibreJustice and on the official sites of the legislatures, courts, and regulators concerned.

The classifications were made with AI assistance applying the author's test; each one and its basis appears in the Incidents sheet.

A precedent shows that the law reaches the conduct. Most precedents involve people acting without an AI system, and some involve AI systems or the companies behind them. None decides how a court would rule on any incident. For law outside the United States the Precedents sheet records one search per law, and a row that says none was found means none in that search.

## Limits

An answer says whether the law reaches the conduct, not whether a prosecutor would charge it or a plaintiff would win; for US law the obstacles a defendant would raise are listed separately as barriers. State-by-state variation beyond the representative statutes is not modeled, and criminal libel is not used for the United States. Answers rest on each incident record, so thin records produce conditional answers. For US law, No law found means no law among the 257 reaches the conduct; where the notes name a law outside them that would apply, the "A fitting law outside the library is named" column flags the incident. For the other systems, No law found means none was found among the laws read for that pattern or family, Could not check means part of that system's law for the conduct was not read, and Needs a single read means a narrower law exists that the record was not read against one by one. An answer outside the United States follows the foreign law's own sanction and does not say anyone would be convicted or fined. The question of what would change if the AI system were a legal person was asked of US law only. Laws are read as they stood on November 12, 2026. Text in other languages was read in the original where the source carried it; descriptions in English are not official translations. A search that found no court case means none in that search, and many were single searches.

The AI Incident Database is a record of reported harms, not a sample of all harms. Incidents that draw press coverage are overrepresented.

Nothing in this dataset is legal advice.

## Sources and license

Incident titles, descriptions, dates, and party names come from the AI Incident Database (https://incidentdatabase.ai), Responsible AI Collaborative, shared under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0). This dataset adapts that material and is shared under the same license. See `LICENSE`, or https://creativecommons.org/licenses/by-sa/4.0/. Anyone who reuses or adapts the dataset must credit both the AI Incident Database and this dataset, and share adaptations under the same license.

Harm severity ratings, MIT risk labels, and EU AI Act risk classes in the columns beginning "MIT" come from the MIT AI Risk Initiative's AI Incident Tracker (https://airisk.mit.edu, data as of November 7, 2026), licensed under the Creative Commons Attribution 4.0 International license (CC BY 4.0). They are MIT's automated classifications of the incident reports, not legal analysis, and the EU AI Act class reflects EU law, not US law. Incident 88 has no tracker record.

## How to cite

Gilly, Travis, *If It Were a Person: Incident, Law, and Precedent Dataset for 1,786 AI Incident Database Incidents*, version 2.0 (November 12, 2026). Available at https://github.com/princesshobbes/If_It_Were_a_Person_dataset

The companion article is Gilly, Travis, *If It Were a Person: What Existing Law Reaches in 1,786 AI Incidents, and Why Legal Personhood for AI Would Shield No Company* (November 2026). Available at https://doi.org/10.68481/kmh26e

## Contact

Travis Gilly, Real Safety AI Foundation, https://realsafetyai.org. ORCID 0009-0007-2954-6313. Correspondence: t.gilly@ai-literacy-labs.org.
