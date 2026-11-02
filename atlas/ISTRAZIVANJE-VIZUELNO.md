# Vizuelno istraživanje — šta drugi rade, šta uzimamo (2026-11-02)

Kratka pretraga (4 upita) posle uvođenja šetnje u prvom licu. Cilj: smer za sledeće vizuelne korake atlasa.

## Nalazi
- **Extended Matrix / EMviq** (Demetrescu, CNR-ISPC): formalni jezik koji vezuje svaki deo rekonstrukcije za izvor; nesigurnost se boji po vrsti rekonstrukcije (strukturna / nestrukturna / fragmentarna). Najbliži našem A/B/C sistemu. https://docs.extendedmatrix.org/ · https://doi.org/10.3390/environsciproc2021010018
- **Unger et al., Internet Archaeology 72**: „clay" render, ne-fotorealistično senčenje i providnost za nesigurno; fotorealizam samo za potpuno pouzdano. Potvrđuje naš smer (A puno, B/C providno, isprekidane ivice). https://intarch.ac.uk/journal/issue72/13/
- **Three.js obilazak lokaliteta, MDPI Electronics 13/2833 (2024)**: pregled celog lokaliteta → prelaz u šetnju u prvom licu unutra. To smo sada uradili (taster F). https://www.mdpi.com/2079-9292/13/14/2833
- **ADS 3D viewer / Potree**: slojevi stratigrafije uključi/isključi + providnost, preseci i mere u bočnoj traci. https://www.sciencedirect.com/science/article/abs/pii/S2352409X16303261
- **Smithsonian Voyager**: priče (tour) sa anotacijama vezanim za tačke u 3D, mere, ponovno osvetljavanje. https://dpo.si.edu/blog/hosting-your-own-interactive-3d-web-experiences-smithsonian-voyager-platform
- **Romulijana konkretno**: Vojinović i dr. 2008 — aerofotogrametrija (DTM, DSM, 3D model utvrđenja i palate); umetnička rekonstrukcija „History in 3D" (relivehistoryin3d.com). Javni Sketchfab model lokaliteta nije nađen. https://www.researchgate.net/publication/228839250

## Predlog i ugrađena unapređenja (Talas 5 · 2026-11-02)
1. **Ujednačena nenegativna visinska površina (`sampleDemHeight >= 0`) i popravka šetnje u prvom licu (`WALK`):**
   - Otklonjen uzrok poniranja kamere ispod nivoa objekata na prilazu Tetrapilonu (`S1`, gde je GLO-30 dolina Timoka bila na $-24\text{ m}$ dok su zgrade i osa apoteoze stajale na $y = 0\text{ m}$). Svi arhitektonski objekti, putevi, prstenovi, osa apoteoze i stopala šetača sada dele identičnu nenegativnu visinsku funkciju ($y \ge 0\text{ m}$, uz glatki uspon na greben Magure do $+24,5\text{ m}$).
2. **Kontinuum projekcija `2D Nacrt ↔ 2.5D Aksonometrija ↔ 3D Perspektiva ↔ Šetnja (F)` (`proces-2d-25d-3d.md` + 3DHOP):**
   - U gornju traku ugrađen je jednoklikni prelaz između ortografskog 2D CAD pogleda odozgo (`2D Nacrt`), paralelne izometrijske projekcije (`2.5D Akson.`), 3D perspektive (`3D`) i šetnje u prvom licu (`Šetnja (F)`, sa tasterom `E` za promenu visine oka `1,65 m` pešak ↔ `6,0 m` arheološka skela/arhivolta).
3. **Interaktivna 2D Radar-Minimapa sa konusom kamere (ATON / Potree uzor):**
   - U donjem desnom uglu pozornice (iznad ture) ugrađen je živi 2D radar (`#minimap-canvas`) koji prikazuje oba bedema (`L.U.1`, `L.U.2`), palate, hramove, Tetrapilon, Maguru, osu apoteoze i trenutnu poziciju i ugao pogleda kamere/šetača, uz skok klikom na mapu.
4. **Voyager kartica blizine u šetnji (`#walk-prox`) + Sunčeve senke i temeljne stope (`PCFSoftShadowMap` + `aoPad`):**
   - Tokom šetnje na vrhu ekrana automatski se ispisuje objekat ispred posmatrača sa udaljenošću u metrima, nadmorskom visinom (`195,0 m n.v.`) i epistemičkim nivoom (`A/B/C`). Direkciono svetlo sunca baca meke arhitektonske senke koje se pomeraju klizačem `Svetlo` (*Raking Light*), a svaka građevina ima kontaktnu temeljnu stopu (`aoPad`).
5. **Deklaracija `O atlasu · Svemir` (`#about-modal`, taster `I` ili `?`):**
   - Ugrađeno dugme i modalni prozor koji objašnjava šta je 3D Epistemički Atlas, kako je izgrađen u sistemu **Svemir** (*tehnodrom rada i znanja*, departman za arheologiju i Atelje Svemira) i navodi poreklo podataka i potvrdu **Arheološkog instituta u Beogradu** za živu javnu objavu.
