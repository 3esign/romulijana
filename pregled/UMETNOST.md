# Natpis, skulptura i mozaici — uporedno čitanje

Provera: 2026-10-31T21:42:09.030Z (vizuelni nastavak 01.11.2026 u [UMETNOST-VIZUELNO.md](UMETNOST-VIZUELNO.md)). Registar: [tvrdnje-umetnost.jsonl](../baza/tvrdnje-umetnost.jsonl). Stabilni ID povezuju tvrdnje sa postojećom hijerarhijom. Registar je uključen u SQLite/FTS pretragu (`node alati/trazi.js --tvrdnje`).

Čitani su odabrani izvedeni tekstovi R03, R04, R05, R06 i R08, bez novog OCR-a. „Objavljeni nalaz“ znači nalaz kako ga navodi publikacija, bez naše autopsije predmeta. R08 broj označava snimak, a ne štampanu stranu. Štampane strane navedene su samo gde su potvrđene u tekstu.

## Poređenje

| Pitanje | Nalaz / tumačenje | Granica |
|---|---|---|
| Natpis | JZ nalaz 1984; predlog prvobitne ugradnje na zapadnoj kapiji | mesto nalaza ≠ mesto ugradnje (RU-001–004) |
| Pilastar tetrarha | Druga tetrarhija u umetničkom poglavlju; alternativa 308. u arhitektonskom | R04 nije jedinstven glas (RU-005–006) |
| Porfirna glava | nalaz 1993. kod termi; autor datuje od 303. | godina otkrića ≠ godina izrade (RU-007–008) |
| Skulpture hramova | Jupiter sa orlom, Arijadna u sekundarnom šutu | proveriti identitet fragmenata kroz starije kataloge (RU-009–010) |
| Mozaici | A/D1–1 → D/D1–4 → G/D1–7 | opis prostora odvojen od narativa (RU-011–014) |
| Izgubljene scene | Semela u R05 je pretpostavka | R04 zadržava neizvesnost (RU-015) |

## Kako koristiti registar

Za poređenje filtrirati `cvorovi` (npr. `L.P.MO`), zatim `tema` i `dokazi[].izvor`. `vrsta` odvaja opis, tumačenje i hipotezu, a `veze` čuva alternative i ograničenja. `sha256` identifikuje baš pročitani tekst, ne izvorni PDF ili fotografiju; `red` i `sidro` vraćaju na mesto u njemu. Status potvrđuje potporu u izvedenom tekstu, bez vizuelne provere.

## Kartice tvrdnji

### RU-001 · natpis

**objavljeni_nalaz** · N.FR

Srejović beleži nalaz bloka FELIX ROMULIANA u junu 1984; građevina u kojoj je nađen je u jugozapadnoj četvrti.

Granica: Mesto nalaza nije automatski prvobitno mesto ugradnje. Ranije KNOWLEDGE ima neodređeno SZ/JZ; ovim se precizira JZ.

- R03 PDF strana 1 · Dragoslav Srejović; red 5.
- R03 PDF strana 3 / št. 53 · Dragoslav Srejović; red 17.
- R04 PDF strana 113 / št. 111 · Maja Živić; red 30.

### RU-002 · natpis

**objavljeni_opis** · N.FR

Živić opisuje arhivoltu od tufopeščara: kružno natpisno polje, lovorov venac, paunovi i listovi bršljana.

Granica: Opis iz publikacije, bez naše vizuelne ili epigrafske autopsije.

- R04 PDF strana 113 / št. 111 · Maja Živić; red 30.

### RU-003 · natpis

**tumacenje_autora** · N.FR, O.RO, O.GA

Srejović (1993) i Živić (2010) tumače felix i prateću ornamentiku kao oznake konsekracije, apoteoze i trajnosti; naziv povezuju sa Romulom i Galerijem.

Granica: Podudaranje je kontinuitet tumačenja; R04 se poziva na Srejovića 1993, pa nisu dva nezavisna dokaza.

- R08 snimak 17 · Dragoslav Srejović (atribucija prema katalogu; potpis poglavlja nije ponovo proveren); red 26.
- R04 PDF strana 114 / št. 112 · Maja Živić; red 27.

### RU-004 · natpis

**rekonstrukcija_autora** · N.FR, L.U.ZK

Arhitektonsko poglavlje R04 predlaže položaj bloka sa natpisom na vrhu timpanona galerije zapadnih vrata, na osnovu iste debljine fragmenata.

Granica: To je rekonstrukcija prvobitne ugradnje; ne menja zabeleženo mesto otkrića u JZ građevini E.

- R04 PDF strana 70 / št. 68 · Milka Čanak-Medić, Brana Stojković-Pavelka; red 13.

Veze: razlikuje_nalaz_od_ugradnje → RU-001.

### RU-005 · tetrarsi

**tumacenje_autora** · N.SK, L.U.IK, F.T

Živić identifikuje šest likova na pilastru istočne kapije kao članove druge tetrarhije: penzionisani avgusti Dioklecijan i Maksimijan, te Galerije, Maksimin Daja, Konstancije Hlor i Sever II.

Granica: Identifikacija je ikonografska; ne predstavlja šest individualno natpisanih portreta.

- R04 PDF strana 117 / št. 115 · Maja Živić; red 37.

### RU-006 · tetrarsi

**alternativno_tumacenje** · N.SK, L.U.IK, L.U.2, F.T

Drugo poglavlje iste knjige navodi i tumačenje pilastara kao treće tetrarhije posle Karnuntuma 308. i završne radove na zapadnim vratima 308–311.

Granica: Raniju sintezu da ceo mlađi bedem nesporno završava 306. treba čitati uz ovo neslaganje unutar R04; identitet likova i trajanje gradnje nisu ista tvrdnja.

- R04 PDF strana 75 / št. 73 · Milka Čanak-Medić, Brana Stojković-Pavelka; red 8.

Veze: alternativa → RU-005.

### RU-007 · porfirni_portret

**objavljeni_nalaz** · N.SK, L.T, O.GA

Živić beleži porfirnu glavu pripisanu Galeriju, otkrivenu 1993. uz istočnu fasadu termi.

Granica: Godina otkrića i mesto odvojeni su od datovanja izrade i atribucije portreta.

- R04 PDF strana 124 / št. 122 · Maja Živić; red 17.

### RU-008 · porfirni_portret

**tumacenje_autora** · N.SK, O.GA, O.DI

R04 datuje glavu od 303. nadalje, povezuje je sa levom šakom koja drži glob i predlaže grupu Galerija i Dioklecijana.

Granica: Skulptoralna grupa je predlog, ne očuvana celina; mogući drugi članovi i Viktorija ostaju nesigurni.

- R04 PDF strana 124 / št. 122 · Maja Živić; red 17.
- R04 PDF strana 125 / št. 123 · Maja Živić; red 4.

Veze: tumaci → RU-007.

### RU-009 · veliki_hram_skulptura

**objavljeni_nalaz_i_atribucija** · N.SK, L.H.V

R04 beleži delove kolosalne bele mermerne statue ispred velikog hrama (istraživanja 1985–1989) i identifikuje Jupitera sa orlom.

Granica: Predložena prvobitna postavka u velikom hramu nije isto što i nalaz ispred hrama. Nije proverena identičnost fragmenata sa starijim opisima imperatora/Herkula u R02.

- R04 PDF strana 115 / št. 113 · Maja Živić; red 18.

### RU-010 · arijadna

**objavljeni_nalaz** · N.SK, L.T

Reljef Usnule Arijadne otkriven je blizu termi u tri dela, u sekundarnom položaju, u šutu građevine VI veka; postavka u niši termi je pretpostavljena.

Granica: Sekundarni kontekst datuje ponovno odlaganje/upotrebu, a sam ne određuje vreme izrade ni prvobitni položaj.

- R04 PDF strana 119 / št. 117 · Maja Živić; red 23.

### RU-011 · raspored_mozaika

**objavljeni_opis** · L.P.MO, L.P.1

R04 povezuje staru i novu oznaku prostorija: lavirint A = D1–1; lov i venatori D = D1–4; Dionis na gozbi G = D1–7. R05 daje isti sled A–D–G.

Granica: Veza važi za te tri dvorane; ne prenosi se automatski na sve oznake planova.

- R04 PDF strana 139 / št. 137 · Maja Živić; red 36.
- R05 PDF strana 19 · poglavlje o mozaicima; autor nije potvrđen u ovom čitanju; red 133.

### RU-012 · venatori

**objavljeni_opis** · L.P.MO

R05 opisuje panel Venatori u borbi sa lavom iz dvorane D: 2,54 × 1,12 m; očuvana su delimično dva lovca, dok autor rekonstruiše prvobitno tri i lava.

Granica: Broj očuvanih figura odvojen je od rekonstruisanog broja; mere su prenete iz OCR-a i čekaju vizuelnu proveru.

- R05 PDF strana 20 · kataloški opis; autor nije potvrđen u ovom čitanju; red 4.

### RU-013 · dionis

**objavljeni_opis** · L.P.MO, L.P.AU

R05 smešta Dionisa na gozbi u dvoranu G: 1,98 × 1,74 m, sedeći bog sa tirsem, peharom i leopardom. R06 i arhitektonsko poglavlje R04 povezuju prostor sa triklinijumom i podom opus sectile.

Granica: Mere čekaju proveru skena; funkcija trpezarije je zaključak iz prostornog i dekorativnog sklopa.

- R05 PDF strana 20 · kataloški opis; autor nije potvrđen u ovom čitanju; red 51.
- R06 PDF strana 140 / št. 106 · Milka Čanak-Medić; red 40.
- R06 PDF strana 141 / št. 107 · Milka Čanak-Medić; red 31.
- R04 PDF strana 96 / št. 94 · Milka Čanak-Medić, Brana Stojković-Pavelka; red 15.

### RU-014 · znacenje_mozaika

**tumacenje_autora** · L.P.MO

R06 lavirintu pripisuje moguću profilaktičnu ulogu; R05 i Živić u R04 povezuju lavirint, lov i Dionisa u ideološki narativ postupnog približavanja spasenju i besmrtnosti.

Granica: Simboličko tumačenje ne potvrđuje stvarno izvođen obred ili obaveznu rutu kretanja posetilaca.

- R06 PDF strana 131 / št. 97 · Milka Čanak-Medić; red 48.
- R05 PDF strana 19 · poglavlje o mozaicima; autor nije potvrđen u ovom čitanju; red 130.
- R04 PDF strana 139 / št. 137 · Maja Živić; red 31.

### RU-015 · izgubljeni_paneli

**hipoteza_autora** · L.P.MO

R05 pretpostavlja Semelu i njen uspon na Olimp na izgubljenim panelima G/R; R04 izričito zadržava neizvesnost njihovog sadržaja.

Granica: Semela nije očuvana scena niti potvrđen nalaz u tim panelima.

- R05 PDF strana 19 · poglavlje o mozaicima; autor nije potvrđen u ovom čitanju; red 202.
- R04 PDF strana 139 / št. 137 · Maja Živić; red 32.

Veze: ogranicava_rekonstrukciju → RU-014.

### RU-016 · uporedni_stil

**stilsko_tumacenje** · L.P.MO

R08 opisuje osovinski, klasičan raspored panela Romulijane i poredi ga sa Medijanom, Splitom, Sirmijumom, Solunom i Pjacom Armerinom.

Granica: Stilska sličnost i vrednosni sud autora ne potvrđuju sami datum ili identitet radionice; jedinica R08 je snimak dve strane.

- R08 snimak 121 · autor poglavlja nije potvrđen u ovom čitanju; red 6.

### RU-017 · veliki_hram_skulptura

**veza_izvora** · L.MG, O.GA, O.RO

R02 (Starinar 1980, št. 72) razvrstava skulpture oko velikog hrama u tri grupe: kolosalna figura muškarca u oklopu; torzo, bradata glava i baza sa stopalima i stenom prekrivenom lavljom kožom (Herkul, T. III,4; T. IV,1–3); tri ruke sa bakljinom. R04 (2010) iste nalaze daje kao glave Jupitera i Herkula ispred velikog hrama i kolosalnu statuu Jupitera sa orlom (1985–1989). Citatna veza: arhitektonsko poglavlje R04 (fn. 109) poziva se na „Srejović, Lalović, Janković 1981, 72“ — sadržaj i strana poklapaju se sa R02, jedinim zajedničkim tekstom te trija autora u korpusu.

Granica: R02 ne imenuje Jupitera; identifikacija Herkul+Jupiter je zreliji sloj R04, ne dokaz identičnosti fragmenata. Godina „1981“ u citatu R04 verovatno označava štampu sveska Starinara 1980, ali nije nezavisno potvrđena; nije isključena ni posebna publikacija istih autora iz 1981. R04 p130 kolosalnu šaku ostavlja otvorenom: Jupiter, Herkul ili Galerije.

- R02 PDF strana 8 / št. 72 · Dragoslav Srejović, Anka Lalović, Đorđe Janković; redovi 20, 22, 26, 31.
- R04 PDF strana 87 / št. 85 · Maja Živić i arhitektonsko poglavlje; redovi 42, 47 (fn. 109).

Veze: razresava_deo → RU-009; povezuje → RV-005.

### RU-018 · datum_apoteoze

**objavljeni_nalaz** · L.MG.MZ, O.RO, R.ZA

R04 (arhitektonsko poglavlje, fn. 17–18): godina Romuline smrti nije zabeležena; novac nađen u podnožju njenog tumula pomera sahranu u kraj III veka, čime je isključena ranija pretpostavka (progon 303/304). Na tome počiva datovanje apoteoze Romule: 294. ili najkasnije početkom 295. godine, uz poziv na Vasić M. 2007, 50. Ovo je objavljeni odgovor na otvoreno pitanje datuma apoteoze iz sažetka projekta.

Granica: To je pretpostavka na osnovu novca i književnih podataka, ne natpisni ili stratigrafski dokaz; „kraj III veka“ za sahranu i „294/295“ za apoteozu su dva koraka istog autoritetnog lanca (R04 → Vasić 2007), ne nezavisna potvrda.

- R04 PDF strana 55 / št. 53 · arhitektonsko poglavlje; redovi 30, 33, 40, 41 (fn. 17–18).

Veze: dopunjuje → RU-003; uvod_u → RU-017.

### RU-019 · bakljonose

**tumacenje_autora** · L.MG, F.KA, O.RO

R02 vezuje bakljonoše (tri ruke sa bakljinom, jedna ženska i dve muške, T. V,4–5) isključivo za ktonsku ikonografiju (Kibela, Mitra) i svetilište u kripti; kolosalni imperator i Herkul ostaju u celi. R04 (Živić) drži isti princip — ženska ruka sa bakljom i šaka bakljonoše ispred hrama „u funkciji kulta“, arhitektonsko poglavlje mladiće i devojke sa bakljama vezuje za kripticu (fn. 109–110) — ali završnu identifikaciju cele daje kao Herkul + Jupiter.

Granica: Podela bakljonoše/kripta naspram božanstava/cela je tumačenje autora na osnovu ikonografije, ne stratigrafski nalaz; nijedan bakljonoša nije vezan za konkretan položaj u kripti.

- R02 PDF strana 8 / št. 72 · Dragoslav Srejović, Anka Lalović, Đorđe Janković; redovi 27, 34.
- R04 PDF strana 130 / št. 128 · Maja Živić; red 8.
- R04 PDF strana 87 / št. 85 · arhitektonsko poglavlje; red 41 (fn. 109–110).

Veze: nadovezuje_se → RU-017.

### RU-020 · torzo_imperatora_u_oklopu

**objavljeni_opis** · L.MG, O.GA, O.DI, R.ME

R04 (Živić) opisuje torzo imperatora u oklopu (sl. 87): jedan od dva skoro identična torza, natprirodne veličine, sa vidljivim delovima kožnog oklopa; prikazuje najverovatnije Galerija u ratnoj opremi, drugi torzo možda Dioklecijana; moguće vezivanje za trijumf nad Persijancima, tj. datum posle 298. Istom kontekstu pripada i šaka kolosalne statue (sl. 86) koja „možda prikazuje samog Galerija“.

Granica: R02 fragmenati „muškarca u oklopu“ (rame, vrat i grudi, savijena ruka, noga) nisu dokazano isti predmet sa ovim torzom; broj i identitet ličnosti ostaju pretpostavka, a datum „posle 298“ uslovno vezan za trijumf, ne za nalaz.

- R04 PDF strana 127 / št. 125 · Maja Živić; redovi 18, 20.
- R04 PDF strana 128 / št. 126 · Maja Živić; redovi 6, 7, 13.

Veze: razgranicava → RU-017.

## Nastavak

Kasniji slojevi L.HR/L.KN obrađeni su u [SLOJEVI.md](SLOJEVI.md), [PLANOVI.md](PLANOVI.md) i [DATOVANJE-BAZILIKE.md](DATOVANJE-BAZILIKE.md). Vizuelna provera skenova (Herkul vs. Jupiter, pilastar, mere mozaika, potpis „Д. С.“ u R08 i zavisnost R04/R08) sprovedena je u [UMETNOST-VIZUELNO.md](UMETNOST-VIZUELNO.md) (tvrdnje RV-001–010); mašinska provera ovog dosijea je u [`baza/provere/provera-umetnost.json`](../baza/provere/provera-umetnost.json). Razrešeno u četvrtom talasu (RU-017–020): citatni lanac R02→R04 za skulpture velikog hrama, datum apoteoze 294/295 kroz Vasić 2007, podela bakljonoša↔kripta i torzo imperatora (Galerije/Dioklecijan, posle 298). Otvoreno za proširenje literature van lokalnog korpusa: katalog Živić 2005/2007 za nezavisnu potvrdu veze R02 fragmenata i R04 torza — identitet fragmenata ostaje otvoren i zabeležen u granicama RU-017 i RU-020. Današnji muzejski smeštaj nije proveravan. R05 (1983) kaže da je lavirint in situ, dok R04 (2010, s.139 nap.41) navodi muzej u Zaječaru; to su različiti datumi izveštavanja, ne dokaz greške jednog izvora.
