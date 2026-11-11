# Road attacks on the Mandera border corridor since Kenya entered Somalia (2011–2026)

An interactive web map of roadside bombs, ambushes and attacks on vehicles reported on the border road that runs from **Mandera through Arabia, Fino and Lafey to Elwak** in Mandera County, Kenya. The timeline starts in mid-October 2011, when Kenyan troops crossed into Somalia under Operation Linda Nchi.

**Live map:** https://omarmowher.github.io/mandera.html

### What the map shows

- **23 attacks** from November 2014 to November 2026, with at least **91 people killed** and 98 injured (reported).
- **Circle size** shows the number of people killed. A hollow circle means no deaths were reported. Injuries are listed in each popup but do not change the circle size.
- **Circle colour** shows who was targeted: civilians and passenger vehicles (red), police and soldiers (blue), or road construction workers and machinery (amber).
- **Dashed circle edge** means the location is approximate.
- **Timeline slider** replays the attacks year by year from October 2011.
- **Click any circle or list item** for the date, what happened, casualties, location accuracy and a link to the news source.
- **Map / Satellite switch** at the top right. Satellite is the default view.

### What it is not

- **It is not a complete record.** Many incidents are never reported, and others were not found. No corridor road attacks were found for October 2011 to 2013 in the archives searched; that does not mean none happened.
- **It is not an official product** of the Government of Kenya or any other organisation. It is an independent personal project.
- **It is not a security assessment or travel advice.** Do not use it to make safety or operational decisions.

### How it was made

1. **Collecting incidents.** Attacks on the corridor road were compiled from public news reports (The Star, Nation, The Standard, Capital FM, Citizen Digital, KBC, Kenyans.co.ke, Reuters via Hiiraan, Anadolu Agency, Wikipedia and others). Each incident records the date, place, road section, attack type, target, killed, injured, a note on conflicting reports and a source link.
2. **Tracing the road.** The Mandera–Arabia–Fino–Lafey–Elwak route was traced from OpenStreetMap road data as a network shortest path between the five towns. The result is about 170 km, matching the distance given in news reports.
3. **Placing incidents.** Each attack is placed along the traced road:
   - where a report gives a distance (for example "8 km south of Arabia Police Station"), the point is placed that far along the road;
   - where only an area is known, the point is placed at the nearest town or mid-way along the road section and marked approximate;
   - attacks at the same spot are spread slightly along the road so each can be clicked.
4. **Location accuracy** is recorded in a `geo_precision` field:
   - `1` in a named town
   - `2` placed from a distance or landmark given in the report
   - `3` approximate: exact site not found
5. **Death tolls** use the best figure reported. Where reports disagree (for example 3 to 5 deaths), the note in the popup gives the range and the source used.
6. **Attackers** are described only as the reports describe them, usually "suspected al-Shabaab".

### Download the data

**[Mandera_corridor_road_attacks_2011_2026.csv](Mandera_corridor_road_attacks_2011_2026.csv)**: one row per attack, with coordinates in WGS84 (`lat`, `lon`).

| Field | Meaning |
|---|---|
| `id` | Row number, oldest first |
| `date` | Date of the attack (YYYY-MM-DD) |
| `year` | Year |
| `place` | Place as named in the reports |
| `road` | Road section |
| `attack_type` | IED, ambush, gunfire and so on |
| `target` | Who was targeted |
| `killed` | Deaths reported (best figure) |
| `injured` | Injuries reported; blank if not reported |
| `geo_precision` | 1 = in a named town, 2 = placed from a distance in the report, 3 = approximate |
| `lat`, `lon` | Position along the traced road |
| `note` | Conflicting figures, how the point was placed, other context |
| `source` | Link to the news report used |

To use it in ArcGIS Pro, run **XY Table To Point** with `lon` as X and `lat` as Y (WGS 1984). In QGIS, use **Add Delimited Text Layer**.

### Data sources and credits

| Layer | Source | Licence |
|---|---|---|
| Attack records | Public news reports (linked per incident) | Compiled by Mohamed Omar |
| Border road and other roads | © OpenStreetMap contributors | ODbL |
| Country borders, B9 road | Natural Earth | Public domain |
| Settlement shading | WorldPop 2020, constrained population, 100 m | CC BY 4.0 |
| Satellite imagery | Sentinel-2 cloudless 2020 by EOX IT Services GmbH (contains modified Copernicus Sentinel data 2020) | CC BY-NC-SA 4.0 |
| Map library | Leaflet 1.9.4 | BSD-2-Clause |
| Font | Public Sans | SIL Open Font License |

### Disclaimer

Dates, death tolls and locations are taken from news reports and may differ from official figures. Some locations are approximate and are marked as such. Views are my own and not those of my employer.

### Corrections

If you spot an error or know of an incident that is missing, please email **mohamedabsiyee@gmail.com** with a link to a source.

**Last updated:** 11 November 2026
