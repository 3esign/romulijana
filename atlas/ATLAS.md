# Romulijana · 3D atlas — priprema

Stanje 2026-11-02. Ovaj dosije razvrstava sav materijal projekta po tome kako ulazi u 3D atlas i rekonstrukciju. Uz to opisuje model slojeva, praznine i redosled gradnje. Brojevi su iz [KATALOG.md](KATALOG.md), koji pravi `node alati/atlas-inventar.js`. Opremu za rad (veštine, persone, reference i sistemske promptove) opisuje OPREMA.md.

## Rečenica atlasa

**Jedan prostor u kome se vidi šta se o Romulijani zna, odakle se to zna i koliko je sigurno, od provincije do jednog mozaika.**

Šta atlas NEĆE imati:
- rekonstrukciju bez oznake sigurnosti;
- fotografiju kao tapetu, bez izvora i prava;
- broj bez izvora;
- „lep“ pejzaž koji ne potiče iz podataka o terenu;
- jednu verziju datovanja tamo gde se izvori ne slažu. Primer je mlađa crkva: R04 ima dve verzije, kod Sofije Petković i kod Đorđa Jankovića (RS).

## Šta imamo (izmereno)

| | broj |
|---|---|
| registrovani izvori | 79 (8 iz zipa, 71 sa interneta) |
| strane teksta u indeksu | 2.894 (30 izvora sa tekstom) |
| pominjanja čvorova u tekstu | 32.041 |
| izvučeni datumi | 2.118 |
| tvrdnje sa dokazima | 71: RU 20, RS 18, RT 12, RV 10, RD 9, RP 2 · 166 dokaza · 73 veze |
| čvorovi hijerarhije | 66: L prostor 27, N nalazi, O osobe, I istraživači, F faze, R region |
| objekti (crosswalk) | 3: dve crkve u palati I i krstionica |
| renderi PDF strana | 40: 10 planova, 14 umetnost, 16 kontrola štampanih strana |
| fotografije lokaliteta (Commons) | 19 |
| istorijske karte | 11 |
| graf veza za interfejs | 219 čvorova, 654 veze ([graf.json](graf.json)) |

## Razvrstano po razmeri (prvi nivo svakog izvora)

| razmera | šta je | izvori | glavna upotreba u atlasu |
|---|---|---|---|
| **S0 region** | provincije, putevi carstva, uporedne palate | 11 istorijskih karata, DARMC W69, Pleiades, W07/W12/W22, R07 | ploča šireg konteksta; istorijske karte su samo grubo poravnati overlay |
| **S1 okolina ≤25 km** | Timok, Zaječar, putevi oko lokaliteta | W76 (8 trasa), Sentinel W46/W47, OSM W36/W48/W50, W39, W02, W17, W20, R06 | teren + mreža puteva + zaštićene zone |
| **S2 lokalitet** | utvrđenje, Magura, nekropole, sonde | W45 Sentinel 10 m/px, R02/R04/R05, W03, W09, W10, W15, W18, W21 | podloga, obrisi građevina, zone nalaza |
| **S3 objekat** | bedemi, kule, kapije, palate, hramovi, crkve | 10 planova (R04/R05/R06), 19 fotografija, R06 rekonstrukcije | 3D mase sa nivoom sigurnosti, uporedni planovi |
| **S4 predmet** | skulptura, mozaici, natpis, novac, fibule | 14 renderi umetnosti, R08, W01/W04/W05/W08/W11 | paneli sa dokazom, vezani za mesto nalaza |

Po pravima: **javno 16 · deli-isto 24 · nekomercijalno 9 · privatno 30**. Privatno znači literaturu bez upisane licence, renderovane strane iz nje i snimke knjige R08. To ide u interni atlas. Javna verzija sme da koristi samo javno, deli-isto i, nekomercijalno, DARMC. Geometrija koju sami iscrtamo po planovima je naš rad sa citatom, ali odluku o objavi donosi Semir.

## Model slojeva i dimenzija

Atlas ima četiri ose. Svaki element na ekranu nosi sve četiri.

1. **Prostor (S0–S4).** Kamera prelazi razmere bez prekida. Zakon prelaza: na svakoj razmeri vidi se samo ono što na njoj ima izvor.
2. **Vreme (F.*).** Ose su F.PR (pre utvrđenja), F.T (tetrarhija 293–311), F.KA (IV–VI v.) i F.SV (X–XII v.). Klizač ne prikazuje datum ako on nije upisan u tvrdnji. Neslaganja se prikazuju kao raspon ili dve verzije.
3. **Sigurnost.** Koristi se A/B/C iz Medijane, prema Londonskoj povelji i Seviljskim principima:
   - **A** je izmereno ili objavljeno sa planom;
   - **B** je izvedeno analogijom ili proporcijom (npr. rekonstrukcije u R06);
   - **C** je hipoteza.

   Status tvrdnje (`potkrepljeno_izvedenim_tekstom`, `vizuelno_pregledano_na_reprodukciji` …) ide uz oznaku.
4. **Poreklo.** Klik na bilo šta otvara izvor, stranu, štampanu stranu, sidro i SHA-256, isti lanac kao u `trazi.js`. Graf ([graf.json](graf.json)) povezuje izvor, tvrdnju, čvor i objekat u oba smera.

Uži kontekst je čvor sa svojim tvrdnjama, planovima i predmetima. Širi kontekst su roditelj, susedni čvorovi, R-čvorovi (Split, Solun, Medijana, Šarkamen …) i putevi. Iste veze daju i 3D „konstelaciju“ znanja: gustina pominjanja je izmerena po čvoru. Najgušći su L 4.481, L.P 2.757, L.U 2.672 i L.U.K 1.610.

## Praznine (izmerene — atlas ne sme da ih sakrije)

| ID | šta nedostaje | posledica | sledeći korak |
|---|---|---|---|
| P-TEREN | nema modela terena | reljef bi bio izmišljen | Copernicus DEM GLO-30 (otvoren), pločica N43 E022; za lokalitet tražiti gušći DSM |
| P-GEOREF | integrisano u 3D instrument | 10 rendera planova iz R04/R05/R06 afino uklopljeno u [index.html](index.html) | podloga ispod 3D volumena na klik i taster P sa ISO 128 okvirima |
| P-OSM-VEKTOR | W37 je samo sažetak upita, bez geometrije | nema savremenih obrisa za kontrolu | ponovo preuzeti OSM elemente sa geometrijom |
| P-GEOMETRIJA | 27 prostornih L-čvorova ima procedurne volumene | u instrumentu podloženi nivoi A/B/C | digitalizacija finih detalja iz georeferenciranih planova |
| P-TVRDNJE | **ZATVORENO** (0 praznih čvorova) | svih 27 L-čvorova ima formalizovane tvrdnje | registar RT-001–012 u [TOPOLOGIJA.md](../pregled/TOPOLOGIJA.md); 71 tvrdnja u bazi |
| P-GEOFIZIKA | karte iz W02/W17 nisu izdvojene | nema podzemnog sloja | render strana sa kartama, pa georeferencija |
| P-ZONE | UNESCO granice (W20) nisu izdvojene | nema zaštićene i tampon zone | render karte iz dosijea, dva poligona |
| — | R-čvorovi nemaju koordinate | S0 ne može da poveže palate | Pleiades ID za Split, Solun, Medijanu, Šarkamen, Sirmijum, Serdiku, Akvis |
| — | OSM pločice W36/W48/W50 se završavaju 146 m južno od tačke lokaliteta | južni deo utvrđenja i nekropola su van slike | po potrebi preuzeti susedne južne pločice |

## Ispravljeno u ovom krugu (registar `baza/izvori.json`)

Kopija pre izmene: `data/sessions/c1793407199300pn7k/izvori.pre-atlas-01.json`.

- **W26–W30:** vrsta je promenjena iz „istorijska karta“ u „fotografija“. To su fotografije Carole Raddato.
- **W36:** autor, licenca i url pripadali su Droysenovoj karti. Sada su OSM saradnici, ODbL i pločica z13/4600/2981.
- **W48 i W50:** url je pokazivao na OSM way. Sada pokazuje na stvarnu pločicu.
- **W37:** naslov i url nosili su stari, pogrešan bbox (22.42E). Usklađeni su sa fajlom, uz napomenu da fajl nema geometriju.

Posle izmene ponovo su napravljeni indeks i katalog. `node alati/proveri-pretragu.js` vraća status „ok“.

## Redosled gradnje (predlog)

| faza | rezultat | kriterijum gotovog |
|---|---|---|
| A0 temelj | teren (DEM), georef 10 planova, OSM vektor | RMS georeferencije ≤ 2 m na kontrolnim tačkama; DEM sa SHA-256 u registru |
| A1 2D atlas | podloga W45 + obrisi L-čvorova + putevi W76 + zone W03/W15/W20 | svaki obris ima izvor, stranu i nivo A/B/C; 0 obrisa bez izvora (proverava alat) |
| A2 3D mase | ekstruzija obrisa po visinama iz R06/R04; nivo B/C vidljivo drugačiji | snimci 1400/390, dan/noć, reduced-motion; nezavisni sud |
| A3 vreme | klizač F.*; faze bedema (L.U.1/L.U.2), crkve (RS/RD) | nijedno stanje bez tvrdnje; neslaganja kao dve verzije |
| A4 znanje | panel čvora + graf + predmeti S4 na mestu nalaza | klik → izvor/strana/sidro radi za 100% elemenata |
| A5 region | S0: putevi carstva, uporedne palate, istorijske karte | prelaz S0→S4 bez prekida; payload ≤ 5 MB |

Tehnika: three.js iz `bin/vendor/three-0.186.1` (bez npm), WebGL, a WebGPU samo kao progresivno poboljšanje. DPR ≤ 1,5, render na zahtev. Podaci su glTF/GeoJSON izvedeni iz `baza/` skriptom, nikad ručno. Sestrinski projekat Medijana deli šemu A/B/C i standarde. Atlas treba da ih koristi isto da bi dve carske rezidencije mogle u jedan regionalni prikaz.

## Granice ovog dosijea

- Razvrstavanje upotrebe (tabela `UPOTREBA` u alatu) je moja ručna odluka sa navedenim razlogom. Pominjanja, heševi, veličine i geometrija pločica su izmereni.
- Prava literature su „privatno“ zato što licenca nije upisana, a ne zato što je zabrana potvrđena.
- Veze plan–čvor postoje samo preko tri objekta, pa samo crkve palate I imaju povezan plan. Ostalih 7 planova čeka objekte.
- Kvalitet OCR-a W13/W14 je proveren uzorkom, ne strana po strana.

## Izgrađeni naučni instrument, monografija i Art Bible (Ciklus 1–2)

- **[INSTRUMENT.md](INSTRUMENT.md)** — komparativna naučna i umetnička monografija 3D epistemičkog instrumenta: definicija šta tačno gradimo, uporedna matrica 8 svetskih sistema (Extended Matrix + ATON, 3DHOP, Smithsonian Voyager, Forensic Architecture Image Complex, ORBIS/Itiner-e, Giro3D / `3d-tiles-renderer` + `three-mesh-bvh`, PixPlot/Manovich, Svemir `city-of-the-atlas` / `Medijana`), teorijski okvir (*Capta* vs. *Data* J. Drucker, Londonska povelja, Seviljski principi, Apollonio/Gaiani šejder nesigurnosti, Piranesi *Campo Marzio* + ISO 128-24, Sol LeWitt → Reas/Fry *Form+Code*, Stiny/Wonka CGA gramatike, Vera Molnár *1% disorder*), 6 formalnih grafičkih operacija sa jednačinama, model imerzije i toka (Slater *Plausibility Illusion*, Csikszentmihalyi *Flow*, Bederson & Hollan *Semantic Zoom*, 0 KB Web Audio) i budžet za mobilni/desktop prikaz.
- **[ART_BIBLE.md](ART_BIBLE.md)** — merljivi estetski i inženjerski ugovor (sRGB heks tokeni za dan/noć i epistemičke nivoe `A/B/C/P/Capta`, ISO 128-24 debljine linija, damping kamere $\alpha = 1 - e^{-8.5 \Delta t}$, M3 krive, tipografija, 0 KB Web Audio sinteza, prava nad izvorima).
- **../alati/atlas-paket.js** → generiše determinističke pakete [atlas-podaci.js](atlas-podaci.js) (`209 KB`) i atlas-podaci.json (`284 KB`) iz `baza/atlas-katalog.json`, `atlas/graf.json`, svih 59 tvrdnji (`baza/tvrdnje-*.jsonl`), `baza/objekti.json` i 8 segmenata rimskih puteva iz `W76` (`darmc-romulijana-okolina-15km.geojson`).
- **[index.html](index.html)** — interaktivni 3D epistemički atlas i forenzički instrument (`Three.js r186` iz lokalnog `bin/vendor/three-0.186.1`, 0 spoljnih zahteva, `render-on-demand` sa 0 draw call-ova u mirovanju, DPR $\le 1.5$, 4 nezavisne ose: razmera `S0–S4`, faze `F.PR–F.SV` + `Capta`, nivoi `A/B/C/P`, ravan preseka i ugao kosog svetla; 19 foto-frustuma i 7 stanica vođene naučne ture).
- **[CIKLUSI.jsonl](CIKLUSI.jsonl)** i vizuelni dokazi u `dokazi/atelje/instrument-v1/` i `dokazi/atelje/instrument-v2/` (`dan-1400.png`, `dan-390.png`, `noc-1400.png`, `noc-390.png`, `mirno-1400.png`, `mirno-390.png`).
