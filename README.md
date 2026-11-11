# Felix Romuliana (Gamzigrad) — epistemički 3D atlas

**Kasnoantički carski dvorac i memorijalni kompleks cara Galerija (UNESCO #1253), složen u proverljiv sistem znanja: izvori → tvrdnje sa dokazima → interaktivni 3D naučni instrument.**

- **Živi 3D atlas (GitHub Pages):** **[https://3esign.github.io/romulijana/atlas/](https://3esign.github.io/romulijana/atlas/)**
- **Mapa projekta:** [MAPA.md](MAPA.md): izvori, tvrdnje, celine, otvorena pitanja
- **Bratski projekat:** [Medijana (Naissus)](https://github.com/3esign/medijana)


**Autori:** doc. dr Bojan Končarević · doc. dr Semir Poturak  
Univerzitet „Union – Nikola Tesla“, Fakultet za graditeljski menadžment, Beograd · Arheološki institut, Beograd

**Authors:** Assist. Prof. Bojan Končarević, PhD · Assist. Prof. Semir Poturak, PhD  
Union – Nikola Tesla University, Faculty of Construction Management, Belgrade · Institute of Archaeology, Belgrade

- **Arhitektura i sistem gradnje:** **Svemir** (*tehnodrom rada i znanja*, departman za arheologiju i Atelje Svemira)

---

## Poreklo podataka, potvrde i prava

> **Deo obrađenih podataka dobijen je od Arheološkog instituta u Beogradu.**
> To je korpus monografija i zbornika `R01–R08` (1978–2017; D. Srejović, M. Čanak-Medić, M. Vasić, A. Lalović, Đ. Janković, M. Živić, I. Popović, S. Petković, G. von Bülow, T. Schüler i saradnici) iz kog su izvučeni bibliografski podaci, štampane strane, georeferencirani planovi i verifikovane naučne tvrdnje.
> Autorska prava na izvorne publikacije, planove i fotografije pripadaju autorima i izdavačima. Ovaj repozitorijum **ne sadrži** izvorne PDF-ove ni kompletne skenove knjiga: sadrži bibliografske zapise, kratke citate kao dokaze uz broj strane i SHA-256 heš izvora, georeferencirane slojeve i izvedeni 3D naučni instrument, javno objavljen uz potvrde za naučni i obrazovni uvid.

Ostali izvori (`W01–W79`) potiču iz javnih naučnih baza; licenca svakog stoji u `baza/izvori.json` (Copernicus GLO-30 DEM, © OpenStreetMap saradnici ODbL, DARMC Harvard CC BY-NC 3.0, Pleiades CC BY 3.0, Wikimedia Commons CC BY-SA, UNESCO dosije #1253, nemačka geofizička istraživanja 2004–2007 i dr.).

## Kako je atlas izgrađen (Svemir)

Atlas je izgrađen u sistemu **Svemir** — istraživačkoj i inženjerskoj arhitekturi procesa koju razvija **Semir Poturak**. U Svemiru više nezavisnih AI umova, domenskih departmana Univerziteta Svemira (`svemir-arheologija`, `svemir-web-3d`, `svemir-design`, `svemir-lepota`, `svemir-bim-cad-gis`) i determinističkih alata za proveru sarađuje po pravilu **dokaz pre piksela**:

1. **82 izvora i 2.906 strana** indeksirano je sa mapiranjem štampanih strana (`1.981/2.906` jedinica) i FTS5 pretragom (`32.256` pominjanja kroz `66` čvorova).
2. **83 formalizovane tvrdnje sa 226 dokaza** vezuje svaku prostornu i hronološku odluku za tačan izvor, stranu, citat/sidro, SHA-256 heš i eksplicitnu granicu zaključka.
3. **Kontinuum projekcija (`2D Nacrt` ↔ `2.5D Aksonometrija` ↔ `3D Perspektiva` ↔ `Šetnja u prvom licu` na 1,65 m)** uz interaktivnu **2D radar-minimapu**, sunčeve senke pod kontrolom ugla svetla (*Raking Light*), analitički presek i modal **`O atlasu · Svemir`**.

## Šta je ovde

| Deo | Sadržaj |
|---|---|
| [`atlas/index.html`](atlas/index.html) | Interaktivni 3D instrument (Three.js r186, bez mrežnih zahteva, radi i na telefonu): reljef Copernicus GLO-30, 27 prostornih celina sa nivoom sigurnosti A/B/C, 16 georeferenciranih planova (taster `P`), geofizika i UNESCO zone (taster `G`), rimski putevi DARMC, graf veza znanja. |
| [`SAZETAK.md`](SAZETAK.md) | Sažetak na jednoj strani, proveren prema korpusu ([`pregled/PROVERA-SAZETKA.md`](pregled/PROVERA-SAZETKA.md)). |
| [`MAPA.md`](MAPA.md) · [`baza/otvoreno.json`](baza/otvoreno.json) | Mapa svega što projekat ima i 12 otvorenih pitanja sa stanjem i tvrdnjama na koje se oslanjaju. |
| [`IZVORI.md`](IZVORI.md) · [`baza/izvori.json`](baza/izvori.json) | Katalog 82 izvora (8 R + 74 W): autor, godina, izdanje, nivo T1–T3, licenca, SHA-256. |
| `baza/tvrdnje-*.jsonl` | **83 tvrdnje, 226 dokaza**: umetnost, vizuelno, slojevi, datovanje bazilike, topologija, putevi, veliki hram. Svaki dokaz nosi izvor, PDF i štampanu stranu, citat, sidro i heš. |
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


**Autori:** doc. dr Bojan Končarević · doc. dr Semir Poturak  
Univerzitet „Union – Nikola Tesla“, Fakultet za graditeljski menadžment, Beograd · Arheološki institut, Beograd  
*Authors:* Assist. Prof. Bojan Končarević, PhD · Assist. Prof. Semir Poturak, PhD  
Union – Nikola Tesla University, Faculty of Construction Management, Belgrade · Institute of Archaeology, Belgrade  
Izgrađeno u sistemu Svemir · Built with Svemir · 2026
