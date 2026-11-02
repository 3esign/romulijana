# Vizuelno istraživanje — šta drugi rade, šta uzimamo (2026-11-02)

Kratka pretraga (4 upita) posle uvođenja šetnje u prvom licu. Cilj: smer za sledeće vizuelne korake atlasa.

## Nalazi
- **Extended Matrix / EMviq** (Demetrescu, CNR-ISPC): formalni jezik koji vezuje svaki deo rekonstrukcije za izvor; nesigurnost se boji po vrsti rekonstrukcije (strukturna / nestrukturna / fragmentarna). Najbliži našem A/B/C sistemu. https://docs.extendedmatrix.org/ · https://doi.org/10.3390/environsciproc2021010018
- **Unger et al., Internet Archaeology 72**: „clay" render, ne-fotorealistično senčenje i providnost za nesigurno; fotorealizam samo za potpuno pouzdano. Potvrđuje naš smer (A puno, B/C providno, isprekidane ivice). https://intarch.ac.uk/journal/issue72/13/
- **Three.js obilazak lokaliteta, MDPI Electronics 13/2833 (2024)**: pregled celog lokaliteta → prelaz u šetnju u prvom licu unutra. To smo sada uradili (taster F). https://www.mdpi.com/2079-9292/13/14/2833
- **ADS 3D viewer / Potree**: slojevi stratigrafije uključi/isključi + providnost, preseci i mere u bočnoj traci. https://www.sciencedirect.com/science/article/abs/pii/S2352409X16303261
- **Smithsonian Voyager**: priče (tour) sa anotacijama vezanim za tačke u 3D, mere, ponovno osvetljavanje. https://dpo.si.edu/blog/hosting-your-own-interactive-3d-web-experiences-smithsonian-voyager-platform
- **Romulijana konkretno**: Vojinović i dr. 2008 — aerofotogrametrija (DTM, DSM, 3D model utvrđenja i palate); umetnička rekonstrukcija „History in 3D" (relivehistoryin3d.com). Javni Sketchfab model lokaliteta nije nađen. https://www.researchgate.net/publication/228839250

## Predlog sledećih vizuelnih koraka (po koristi)
1. **Ambijentalno zasenčenje (SSAO/GTAO, postoji u three/addons)** — najveći dobitak „čitljivosti" volumena, posebno u šetnji; samo na desktopu, na telefonu isključeno.
2. **Anotacije u prostoru za šetnju** — kad priđeš objektu na < 25 m, tanka oznaka sa imenom i nivoom A/B/C (kao Voyager), bez otvaranja dosijea.
3. **Senke od sunca** (jedna kaskada oko posmatrača) — u šetnji daju razmeru i dubinu; uz postojeći klizač „Svetlo".
4. **Materijal tla iz ortofota/DEM-a** umesto ravne boje — pojas oko utvrđenja; tražiti otvoren ortofoto (Copernicus/RGZ) ili Vojinović 2008 DSM preko Instituta.
5. **EM-čitanje nivoa**: legenda i dosije da kažu i *vrstu* rekonstrukcije (strukturna/nestrukturna), ne samo A/B/C.
