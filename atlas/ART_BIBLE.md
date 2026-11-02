# ART BIBLE — Romulijana 3D Atlas (Naučni instrument i rekonstrukcija)

Vlasnik: Svemir (`digitalni-umetnik` × `arheolog-rekonstruktor`) · Verzija: 1.0 · Datum: 2026-11-02  
Checklist prijema, ne čitanka. Popunjen PRE prve linije koda; menja se samo uz zapis zašto.

---

## 1. Rečenica artefakta
**Jedan prostor u kome se vidi šta se o Romulijani zna, odakle se to zna i koliko je sigurno, od provincije do jednog mozaika.**

## 2. Šta NEĆE biti na ekranu
- Nema 3D mase bez vidljivog epistemičkog nivoa (**A** izmereno, **B** izvedeno analogijom, **C** hipoteza, **P** praznina u tvrdnjama/geometriji).
- Nema fotorealističnih lažnih tekstura cigle, trave ili oblaka koje glume stanje na terenu.
- Nema fotografije kao tapete bez izvora, autora i licence.
- Nema „prosečnog" datovanja tamo gde se literatura spori (mlađa crkva VI vs X–XI vek prikazuje se kao *Capta* dvojni preklop).
- Nema modala koji prekrivaju 3D scenu pri izboru objekta (*Focus + Context* je zakon).
- Nema neon + glass + bloom + particle kiča; nema animacije u mirovanju (`0 draw calls` kada kamera stane).

## 3. Stubovi (3 sidra iz kanona, kao metod ne kao preset)
1. **Piranesi (*Campo Marzio*, 1762) + ISO 128-24 tehnički crtež:** arhitektonska gravira na toplom pergamentu/kamenu u kojoj debljina i tip linije (puna široka, puna tanka, isprekidana, osna crta-tačka-crta) nose naučni status.
2. **Extended Matrix (Demetrescu 2015) + Johanna Drucker (*Capta*, 2014):** geometrija kao bela kutija (*white-box*) — stratigrafski nivoi A/B/C čitaju se iz punoće materije i šrafure bez otvaranja legende, a sporovi autora stoje u superpoziciji.
3. **Sable (Shedworks) + Monument Valley (ustwo) + Forensic Architecture:** čitljive siluete po razmerama S0–S4, atmosferska dubina kroz maglu u boji horizonta (~0 ms), koso analitičko svetlo (*raking light*) i prostorni lukovi dokaza.

## 4. Pojas izraza
**P7 (CAD / Tehnički instrument) + P4 (Prostorni game-grade UI)** — hibrid arhitektonske forenzičke ploče i fluidne 3D kamere.

## 5. Oblik i gramatika forme iz podatka
- **Tri nivoa oblika:**
  1. *Primarna masa (S1–S2):* poligoni utvrđenja (Starije `L.U.1`, Mlađe `L.U.2`), kule (`L.U.K`), kapije, Tetrapilon (`L.TP`) i sakralni greben Magure (`L.MG.M1/M2`, `L.MG.T1/T2`).
  2. *Sekundarna forma (S3):* tlocrtna podela Palate I i II, peristili, terme, podijumi Velikog i Malog hrama, apside starohrišćanskih crkava.
  3. *Tercijarna forma (S3–S4):* crease linije (`EdgesGeometry` $\theta = 25^\circ$), osne linije vizura (Istočna kapija → Magura), kote i tačke nalaza predmeta.
- **Gramatika iz podatka (CGA-lite):**
  - Sokl / sačuvani zid u tlu = **Nivo A** (puna mineralna masa, oštra kontura `1.5 px`).
  - Proporcijski nadzid / kolonada / svod (iz R06 Čanak-Medić / R04) = **Nivo B** (poluprovidni volumen $\alpha = 0.48$, tanka linija `1.0 px`).
  - Hipotetička krovna/kupolna zona = **Nivo C** (žičani/isprekidani obris, bez pune mase).
  - Čvor sa `tvrdnje.length === 0` (`P-TVRDNJE`, 12 čvorova) = niski otvoreni temeljni okvir ($h = 0.3\text{ m}$) u boji sirovog kreča — praznina je vidljiva na prvi pogled.

## 6. Boja, svetlo, materijal (brojevi)

| Režim / Zona | Pozadina / Tlo (sRGB) | Nivo A · In situ (sRGB) | Nivo B · Analogija (sRGB) | Nivo C · Hipoteza (sRGB) | Zaštićeni akcenat (jedan) | Magla (`FogExp2`) | Ključno svetlo |
|---|---|---|---|---|---|---|---|
| **Dan (`dan`)** · Arhivski kamen i hartija | `#ebe4d6` (toplo platno) / tlo `#dfd6c3` | `#c8b89a` (gamzigradski peščar/krečnjak, $\alpha=1.0$) + ivica `#1e1b17` | `#d8d0c0` ($\alpha=0.46$) + ivica `#5c5346` | Žičana ivica `#b85d28` ($\alpha=0.88$, dashed) | **Porfirno-terakotni crveni** `#9e2a2b` (carski porfir Galerija) | `#ebe4d6` ($\rho = 0.00045$) | Sunce `#fff6e5` ($I=2.1$), Hemi `#efe9dc` / `#8c7f6a` ($I=0.85$) |
| **Noć (`?noc=1`)** · Forenzička tamna komora | `#121519` (bazalt) / tlo `#181c22` | `#788492` (hladni kamen, $\alpha=1.0$) + ivica `#d8e0e8` | `#4a5868` ($\alpha=0.42$) + ivica `#8fa0b2` | Žičana ivica `#e08a44` ($\alpha=0.90$, dashed) | **Porfirno-zlatni jantar** `#e07a38` (emissive fokus) | `#121519` ($\rho = 0.00045$) | Koso svetlo `#ffd9b3` ($I=2.4$), Hemi `#283442` / `#0d1014` ($I=0.7$) |

- **Svetlosna logika:** 1 `DirectionalLight` (sa živom kontrolom azimuta i elevacije *Raking Light* $5^\circ\text{–}75^\circ$) + 1 `HemisphereLight` + Fresnel rim u materijalu; tonemap: `THREE.ACESFilmicToneMapping` (exposure `1.05` dan / `1.12` noć).
- **Presečna ravan (`Section A–A`):** aktivna ravan preseka boji presečene ivice u zaštićeni porfirni akcenat (`#9e2a2b` / `#e07a38`).

## 7. Pokret (ms, easing)
- **Damping kamere:** frame-rate independent eksponencijalni prilaz $1 - e^{-8.5 \Delta t}$, gašenje render petlje kada $\Delta < 10^{-4}$.
- **Dolazak na čvor / razmeru (`flyTo`):** `750 ms`, `Emphasized Decelerate` `cubic-bezier(0.05, 0.7, 0.1, 1)`.
- **Povratak na pregled:** `400 ms`, `Standard Accelerate` `cubic-bezier(0.3, 0, 0.8, 0.15)`.
- **HUD i dosije:** `180 ms`, `Standard` `cubic-bezier(0.2, 0, 0, 1)`.
- **`prefers-reduced-motion: reduce` (`--mirno`):** trenutni prelaz (`0 ms`), bez interpolacije kamere i bez pulsiranja.

## 8. Tipografija i HUD
- **Dva pisma (sistemski/samohostovani stek bez CDN-a):**
  1. *Display / Naslovi čvorova i epoha:* `'Georgia', 'Times New Roman', serif` (klasična epigrafska proporcija, tracking `-0.01em` na naslovima, `+0.08em` na malim rimskim ciframa).
  2. *Interfejs, tabele, kote i SHA-256:* `'Segoe UI', -apple-system, BlinkMacSystemFont, system-ui, sans-serif` + `'Consolas', 'SFMono-Regular', monospace` za ID-jeve, heševe i koordinate.
- **Cifre:** obavezno `font-variant-numeric: tabular-nums` na svim brojačima pominjanja, udaljenostima ($2.531\text{ m}$), godinama i koordinatama.
- **Kontrast:** WCAG $\ge 4.5:1$ na svim tekstualnim površinama (dan: `#1b1916` na `#f4efe4` $\approx 14.2:1$; noć: `#e8ecf0` na `#181c22` $\approx 13.5:1$); grafičke linije $\ge 3:1$.
- **Mobilna bezbednost:** `viewport-fit=cover` + `env(safe-area-inset-*)`; na `< 960 px` split-stage prelazi u gornju 3D pozornicu ($54\text{ vh}$) + donji skrolabilni forenzički dosije ($46\text{ vh}$), najviše 7 aktivnih 3D labela bez preklapanja.

## 9. Zvuk
- **0 KB asseta (Web Audio API sinteza):**
  - *Podloga:* tišina dok je zvuk isključen; po uključenju nakon prvog klika — parametarski vetar nad Magurom (beli šum kroz `BiquadFilterNode` lowpass čija frekvencija klizi sa visinom kamere $280\text{–}800\text{ Hz}$, gain $\le 0.04$).
  - *UI mikro-tonovi (4):* promena razmere S0–S4 ($520\text{ Hz}\to 660\text{ Hz}$, $40\text{ ms}$), izbor čvora ($880\text{ Hz}$, $30\text{ ms}$), pomeranje preseka ($440\text{ Hz}$, $20\text{ ms}$), promena faze ($600\text{ Hz}$, $35\text{ ms}$).
  - *Kontrola:* uvek vidljivo dugme `Zvuk` u gornjoj traci.

## 10. Građa i prava (iz `baza/atlas-katalog.json`)
| Izvor / Grupa | Kako ulazi u instrument | Poreklo | Prava | Javno? |
|---|---|---|---|---|
| **W66 / W67** (Pleiades 207395) | Koordinatni početak $(0,0,0)$ na `43.899206N, 22.18575E` | Pleiades gazetteer | CC BY 3.0 US (`javno`) | Da |
| **W69 / W76** (DARMC rimski putevi) | 3D vektorske trase 8 puteva u krugu od 15 km + raskrsnice A, B, C | DARMC 1M (`darmc-romulijana-okolina-15km.geojson`) | CC BY-NC 3.0 (`nekomercijalno`) | Da (nekomercijalno) |
| **W45 / W46** (Sentinel-2) i **W36/W48/W50** (OSM) | Geografski okviri podloge + kontrola južne ivice (`-146 m`) | Copernicus / OpenStreetMap | Javno / ODbL (`deli-isto`) | Da |
| **W26–W30, W51–W64** (19 fotografija) | 3D konusi pogleda (*Camera Frustums*) + metapodaci autora i licence | Wikimedia Commons (Raddato, Marjanović, Todorović, Pudelek) | CC BY-SA 2.0/3.0/4.0 (`deli-isto`) | Da (uz potpis i licencu) |
| **R01–R07, W01–W22** (literatura, 59 tvrdnji) | Struktura tvrdnji (`RU`, `RS`, `RV`, `RD`, `RP`), faze, pominjanja i proporcijska pravila | `baza/tvrdnje-*.jsonl`, `baza/hijerarhija.json` | Citat (`privatno` za skenove; činjenice i naš kod su naš rad sa citatom) | Tekstualni citat da; PDF/renderi interno |
| **R08 i 40 rendera strana** | Forenzičke reference u internom režimu (putanja, PDF strana, SHA-256) | `izvori/renderi/` | `privatno` (interni rad dok se ne potvrdi licenca) | Ne (samo metapodatak i SHA-256 u javnom) |

## 11. Budžet
- **Payload:** $\le 1.2\text{ MB}$ ukupno (lokalni `three.module.js` + `atlas-podaci.js` + `index.html`, 0 mrežnih poziva).
- **Draw calls:** $\le 65$ u aktivnom kadru; **$0$ draw call-ova u mirovanju** (`render-on-demand`).
- **DPR cap:** `1.5`.
- **Post-processing:** $0\text{ ms}$ ekstra prolaza (tonemap i fog su u glavnom WebGL prolazu).

## 12. Kriterijum gotovog
- [x] `INSTRUMENT.md` i `ART_BIBLE.md` kompletirani sa primarnim izvorima i brojevima
- [x] `alati/atlas-paket.js` deterministički izvodi `atlas/atlas-podaci.js` iz `baza/` bez ručnog unosa
- [x] `atlas/index.html` radi nad stvarnim podacima (79 izvora, 59 tvrdnji, 66 čvorova, 8 DARMC puteva, 207 čvorova grafa)
- [x] Snimci `1400` i `390` (`dan`, `noc`, `mirno`) napravljeni u `atlas/dokazi/atelje/instrument-v1/` i vizuelno pregledani
- [x] AAA samokritika (6 testova) i Kapija lepote (7 pitanja) izvršeni sa vidljivom ispravkom
- [x] Ciklusi zabeleženi u `CIKLUSI.jsonl`, `atlas-inventar.js --provera` i `proveri-pretragu.js` vraćaju `ok`
