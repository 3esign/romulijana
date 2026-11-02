# Felix Romuliana (Gamzigrad) — epistemički 3D atlas

**Kasnoantički carski dvorac i memorijalni kompleks cara Galerija, složen u proverljiv sistem znanja: izvori → tvrdnje sa dokazima → 3D naučni instrument.**

Bratski projekat: [Medijana (Naissus)](https://github.com/3esign/medijana).

---

## Poreklo podataka i prava

> **Deo obrađenih podataka dobijen je od Arheološkog instituta u Beogradu.**
> To je korpus monografija i zbornika `R01–R08` (1978–2017; Srejović, Vasić, Čanak-Medić, Lalović, Janković, Popović i saradnici) iz kog su izvučeni tekst, štampane strane, planovi i ilustracije.
> Autorska prava na te publikacije, planove i fotografije pripadaju autorima i izdavačima. Ovaj repozitorijum **ne sadrži** izvorne PDF-ove ni fotografije: sadrži bibliografske zapise, kratke citate kao dokaze uz broj strane i SHA-256 heš izvora, isečke planova i ilustracija (`izvori/renderi/`) i izvedene podatke.
> Zbog toga je repozitorijum **privatan**. Javno objavljivanje isečaka i izvedenih slojeva traži saglasnost Instituta i nosilaca prava.

Ostali slojevi (`W01–W78`) su javni internet izvori; licenca svakog stoji u `baza/izvori.json` (Copernicus GLO-30 DEM, © OpenStreetMap saradnici ODbL, DARMC CC BY-NC 3.0, Wikimedia Commons CC BY-SA, UNESCO dosije #1253, nemačka geofizička istraživanja 2004–2007 i dr.).

## Šta je ovde

| Deo | Sadržaj |
|---|---|
| [`atlas/index.html`](atlas/index.html) | Interaktivni 3D instrument (Three.js r186, bez mrežnih zahteva, radi i na telefonu): reljef Copernicus GLO-30, 27 prostornih celina sa nivoom sigurnosti A/B/C, 16 georeferenciranih planova (taster `P`), geofizika i UNESCO zone (taster `G`), rimski putevi DARMC, graf veza znanja. |
| [`SAZETAK.md`](SAZETAK.md) | Sažetak na jednoj strani, proveren prema korpusu ([`pregled/PROVERA-SAZETKA.md`](pregled/PROVERA-SAZETKA.md)). |
| [`IZVORI.md`](IZVORI.md) · [`baza/izvori.json`](baza/izvori.json) | Katalog 81 izvora (8 R + 73 W): autor, godina, izdanje, nivo T1–T3, licenca, SHA-256. |
| `baza/tvrdnje-*.jsonl` | **71 tvrdnja, 166 dokaza**: umetnost, vizuelno, slojevi, datovanje bazilike, topologija, putevi. Svaki dokaz nosi izvor, PDF i štampanu stranu, citat, sidro i heš. |
| `baza/geometrija.json` · `baza/georef/` | Obrisi i visine 27 celina, 9 geomagnetskih anomalija, UNESCO poligoni; kontrolne tačke i afine transformacije planova. |
| [`pregled/`](pregled/) | 6 tematskih forenzičkih dosijea (TOPOLOGIJA, UMETNOST, SLOJEVI, DATOVANJE-BAZILIKE, PLANOVI, PUTEVI) i automatski pregledi čvorova. |
| [`atlas/ATLAS.md`](atlas/ATLAS.md) · [`INSTRUMENT.md`](atlas/INSTRUMENT.md) · [`ART_BIBLE.md`](atlas/ART_BIBLE.md) | Rečenica atlasa, razmere S0–S4, teorija instrumenta, vizuelni ugovor. |

## Granice

- Prikaz u atlasu je **prostorni registar znanja**, ne konačna rekonstrukcija. Nivo A = potvrđeno izvorom, B = analogija, C = hipoteza (Londonska povelja 2009, Principi iz Sevilje 2011).
- Georeferenciranje planova je afino, preko 7 kontrolnih tačaka; to nije geodetski snimak.
- Sporna datovanja (npr. mlađa bazilika: VI vek naspram X–XI veka) prikazana su kao sporna, ne razrešena.

## Pokretanje

Treba lokalni HTTP server (ES moduli ne rade sa `file://`):

```
npx http-server -p 8080    # ili: python -m http.server 8080
```

pa otvoriti `http://localhost:8080/atlas/`.

---

Semir Poturak · Svemir, departman arheologije · 2026
