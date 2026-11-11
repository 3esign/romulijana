# Romulijana — mapa projekta

Generisano iz baze komandom `node alati/mapa.js`; ne menjati ručno. Otvorena pitanja se uređuju u [`baza/otvoreno.json`](baza/otvoreno.json).

**Stanje 11.11.2026:** prikupljanje je zaustavljeno. Ova mapa raspoređuje ono što imamo: izvore, tvrdnje sa dokazima, celine lokaliteta, dosijee, otvorena pitanja, alate i javni atlas.

## 1. Brojke

| Šta | Koliko | Gde |
|---|---:|---|
| Izvori | 82 (jezgro 8, literatura 23, karte/podloge/foto 51) | [baza/izvori.json](baza/izvori.json) |
| Indeksirane jedinice teksta | 2.906 | `tekst/<ID>/pNNN.txt`, baza/strane.jsonl |
| Tvrdnje | 83 u 7 registara | `baza/tvrdnje-*.jsonl` |
| Dokazi (izvor, strana, red, sidro, SHA-256) | 226 | uz svaku tvrdnju |
| Veze među tvrdnjama | 83 | uz svaku tvrdnju |
| Čvorovi hijerarhije | 66 | [baza/hijerarhija.json](baza/hijerarhija.json) |
| Stabilni objekti (crkve, krstionica) | 3 | [baza/objekti.json](baza/objekti.json) |
| Otvorena pitanja | 12 | [baza/otvoreno.json](baza/otvoreno.json) |

## 2. Otvorena pitanja (stanje znanja)

### sporno u izvorima (3)

- **O-03 · Pilastar sa tetrarsima.** Druga tetrarhija (305/306) ili treća (308, posle Karnuntuma), i šta znači prazan medaljon?
  - Imamo: Živić/Srejović: druga tetrarhija (RU-005); Čanak-Medić/Stojković-Pavelka: treća (RU-006); vizuelna provera reljefa (RV-002, RV-003).
  - Nedostaje: Nezavisna ikonografska studija; u korpusu nema presude.
  - Tvrdnje: RU-005, RU-006, RV-002, RV-003 · dosije: [pregled/UMETNOST.md](pregled/UMETNOST.md)
- **O-05 · Kome je posvećen mali hram (C).** Kult Dive Romule (R01/R04) ili Kibele sa taurobolijumom (R02/R05)?
  - Imamo: Tvrdnja o malom hramu i Divi Romuli (RT-008) i sakralna osa hramova (RT-007); razilaženje je zapisano u rečniku (RECNIK.jsonl, „Mali hram (C)“).
  - Nedostaje: Epigrafski ili kultni nalaz koji presuđuje; u korpusu ga nema.
  - Tvrdnje: RT-007, RT-008 · dosije: [pregled/TOPOLOGIJA.md](pregled/TOPOLOGIJA.md)
- **O-06 · Faze gradnje i datovanje mlađeg bedema.** Jedan desetogodišnji proces gradnje ili dve etape („Romulianum“ 297–306 / palata 306–316); mlađi bedem tetrarhijski ili Konstantinov?
  - Imamo: R02/R05: gradnja „u jednom dahu“; podela na etape samo iz legende Skice 6 (R02). R06 (1978) mlađi bedem pripisuje Konstantinu, R04 (2010) tetrarhiji (RT-002, RT-003, SAZETAK).
  - Nedostaje: Stratigrafska objava sloja 2 sa apsolutnim datumima.
  - Tvrdnje: RT-002, RT-003, RS-001 · dosije: [SAZETAK.md](SAZETAK.md)

### delimično razrešeno (3)

- **O-01 · Datovanje mlađe bazilike (ROM-CH-P1-LATE).** Da li je mlađa trobrodna bazilika nad južnim dvoranama Palate I podignuta u VI veku (Petković) ili u X–XI veku (Janković)?
  - Imamo: Oba datovanja u istom zborniku R04 (RS-011, RS-012); Janković revidira sopstveno datovanje iz R05 (RS-010). Podovi, keramika i litijski krst ne presuđuju (RD-001–RD-008). W21 (Petković 2011) daje gradnju sredinom VI veka uz moguću obnovu u X veku (RD-009).
  - Nedostaje: Profili i dnevnik iskopavanja, karton inv. 851.
  - Tvrdnje: RS-009, RS-010, RS-011, RS-012, RD-007, RD-008, RD-009 · dosije: [pregled/DATOVANJE-BAZILIKE.md](pregled/DATOVANJE-BAZILIKE.md)
- **O-07 · Veliki hram — metrologija.** Kojom merom je projektovan veliki hram i zašto se brojevi W79 ne slažu?
  - Imamo: Poreklo „lakta“ 47,2–47,7 cm: stopa mlađeg utvrđenja 31,5–31,8 cm × 1,5, R06 (RH-011). Nesklad 63 × 45 lakata ≠ 30,20 × 21,76 m ostaje (RH-010). Zapažanje (nije tvrdnja): raspon bočnog trema 18,70 m = 63 rimske stope; prečnik mermernog stuba 47 cm ≈ „lakat“.
  - Nedostaje: Premer hrama sa kotama; Wilson Jones, dodatak B (tabele stubova).
  - Tvrdnje: RH-001, RH-006, RH-010, RH-011, RH-012 · dosije: HRAMOVI-LITERATURA.md
- **O-09 · Veliki hram — razmak stubova 205 cm na pročelju.** Da li je 205 cm svetli ili osovinski razmak?
  - Imamo: Dvosmislenost je opisana u RH-006. Merenje na W79 sl. 4 i R04 planu XXX (RH-012) isključuje svetlo čitanje: raspon krajnjih stubova je 10,9–11,6 m, a svetli razmak bi dao 13,5 m. Crteži, međutim, imaju četiri stuba u tri nejednaka polja, a tekst šest nosećih elemenata.
  - Nedostaje: Crtež prve (klasične) varijante sa šest elemenata; u korpusu ga nema.
  - Tvrdnje: RH-005, RH-006, RH-012 · dosije: HRAMOVI-LITERATURA.md

### otvoreno, traži izvor van korpusa (5)

- **O-02 · Torzo u oklopu i Jupiterova statua.** Da li fragmenti „muškarca u oklopu“ iz R02 pripadaju Jupiterovoj statui ili carskom torzu?
  - Imamo: Herkul iz R02 = R04 sl. 72; Jupiter (R04 sl. 69 = R08 br. 76) je drugi predmet (RU-017, RV-004, RV-005); torzo imperatora u oklopu (RU-020).
  - Nedostaje: Katalog skulpture Živić 2005/2007.
  - Tvrdnje: RU-009, RU-017, RU-020, RV-004, RV-005 · dosije: [pregled/UMETNOST-VIZUELNO.md](pregled/UMETNOST-VIZUELNO.md)
- **O-04 · Romulina apoteoza.** Na čemu počiva datum apoteoze 294/295?
  - Imamo: Datum preko R04 (RU-018) i veza tumula sa apoteozom (RT-011).
  - Nedostaje: Izvorni rad M. Vasić 2007.
  - Tvrdnje: RU-018, RT-011, RU-019 · dosije: [pregled/UMETNOST.md](pregled/UMETNOST.md)
- **O-10 · Veliki hram — sirijske analogije.** Da li su tremovi sa tri strane i zasvedena kripta preuzeti iz hramova Hosn Sfiri, Kalat Fakra i Hibarija?
  - Imamo: Teza iz R04 str. 87 (Čanak-Medić i Stojković-Pavelka); bibliografski opis Segal 2013, Stamper 2005, Wilson Jones 2000, Orlin 1997, Mierse 1999 u HRAMOVI-LITERATURA.md.
  - Nedostaje: Bibliotečki primerci: Segal 2013 (br. 14–16, 18–19), Krencker i Zschietzschmann 1938, Ward-Perkins 1974 sl. 349.
  - Tvrdnje: RH-005, RH-009 · dosije: HRAMOVI-LITERATURA.md
- **O-11 · Citirani, a nedostupni izvori.** Šta dodaju radovi koje korpus citira, a nemamo ih?
  - Imamo: Citati preko R04 i R07.
  - Nedostaje: Srejović i Vasić, Imperial Mausolea (1993–94); Č. Vasić 1997; S. Petković 2008; objave posle 2017.
  - Tvrdnje: — · dosije: [SAZETAK.md](SAZETAK.md)
- **O-12 · Širi tetrarhijski kontekst.** Kako se Romulijana odnosi prema Medijani, Šarkamenu, Solunu i Splitu?
  - Imamo: Regionalni čvorovi R.* i paralele u hijerarhiji; bratski projekat Medijana.
  - Nedostaje: Uporedna analiza; nije rađena.
  - Tvrdnje: — · dosije: [SAZETAK.md](SAZETAK.md)

### razrešeno (1)

- **O-08 · Veliki hram — ulaz u celu.** Da li se u celu ulazilo sa zapada (W79, str. 144)?
  - Imamo: Fasada, stepenište i crteži W79 i R04 str. 82 stavljaju ulaz na istok; rečenica sa str. 144 je verovatno štamparska greška (naš zaključak).
  - Tvrdnje: RH-008 · dosije: HRAMOVI-LITERATURA.md

## 3. Tvrdnje po temama

| Registar | Tema | Tvrdnji | Dokaza | Statusi | Dosije |
|---|---|---:|---:|---|---|
| [datovanje](baza/tvrdnje-datovanje.jsonl) | Podovi, keramika i litijski krst | 9 | 20 | objavljeni dokazi sa ogranicenjima 9 | [DATOVANJE-BAZILIKE.md](pregled/DATOVANJE-BAZILIKE.md) |
| [hramovi](baza/tvrdnje-hramovi.jsonl) | Veliki hram (W79 i literatura o hramovima) | 12 | 60 | potkrepljeno izvedenim tekstom 5; objavljeni dokazi sa ogranicenjima 6; vizuelno pregledano na reprodukciji 1 | HRAMOVI-LITERATURA.md |
| [putevi](baza/tvrdnje-putevi.jsonl) | Putevi i prilaz | 2 | 12 | potkrepljeno izvedenim tekstom 2 | [PUTEVI.md](pregled/PUTEVI.md) |
| [slojevi](baza/tvrdnje-slojevi.jsonl) | Slojevi posle palate | 18 | 37 | potkrepljeno izvedenim tekstom 18 | [SLOJEVI.md](pregled/SLOJEVI.md) |
| [topologija](baza/tvrdnje-topologija.jsonl) | Topografija i prostorne celine | 12 | 24 | potkrepljeno izvedenim tekstom 12 | [TOPOLOGIJA.md](pregled/TOPOLOGIJA.md) |
| [umetnost](baza/tvrdnje-umetnost.jsonl) | Natpis, skulptura i mozaici | 20 | 46 | potkrepljeno izvedenim tekstom 20 | [UMETNOST.md](pregled/UMETNOST.md) |
| [vizuelno](baza/tvrdnje-vizuelno.jsonl) | Vizuelna provera umetnosti | 10 | 27 | vizuelno pregledano na reprodukciji 10 | [UMETNOST-VIZUELNO.md](pregled/UMETNOST-VIZUELNO.md) |

<details><summary>Sve tvrdnje (ID · tema · vrsta · izvori)</summary>

| ID | Tema | Vrsta | Izvori dokaza | Čvorovi |
|---|---|---|---|---|
| RD-001 | pod mlađe bazilike | uporedni objavljeni nalaz | R06, R05 | L.HR, L.P.1, F.KA, F.SV |
| RD-002 | nasipanje i faze temelja | objavljeni nalaz i tumacenje | R05 | L.HR, L.P.1, F.KA, F.SV |
| RD-003 | keramika nad malterom i krečanom | objavljeni kontekst | R05 | L.HR, L.P.1, F.KA, F.SV |
| RD-004 | pećnjaci u prostoru priprate | autorski hronoloski argument | R05 | L.HR, L.P.1, F.KA, F.SV |
| RD-005 | identitet litijskog krsta | kataloski opis | R05, R04 | L.HR, F.KA, F.SV |
| RD-006 | mesto nalaza krsta | objavljeni kontekst | R05 | L.HR, L.P.2, F.SV |
| RD-007 | promena datovanja krsta | autorska revizija | R04 | L.HR, L.P.1, F.KA, F.SV |
| RD-008 | šta bi razrešilo datovanje | nasa sinteza i otvoreno pitanje | R04, R06 | L.HR, L.P.1, F.KA, F.SV |
| RD-009 | datovanje bazilike II — podignuta sredina VI veka, moguća obnova u X veku | objavljeni nalaz | W21 | L.HR, L.P.1, F.KA, F.SV |
| RH-001 | veliki hram — platforma, jezgro i stereobat | objavljeni nalaz merenje | W79 | L.H.V |
| RH-002 | veliki hram — dvojna kripta | objavljeni nalaz merenje | W79 | L.H.V |
| RH-003 | veliki hram — zidovi cele, ante i aditon | objavljeni nalaz merenje | W79 | L.H.V |
| RH-004 | veliki hram — nađeni arhitektonski elementi | objavljeni nalaz | W79 | L.H.V, N.SK |
| RH-005 | veliki hram — tri varijante izgleda, usvojena treća | rekonstrukcija predlog | W79, R04 | L.H.V |
| RH-006 | veliki hram — raspored stubova (modul tremova) | rekonstrukcija predlog | W79 | L.H.V |
| RH-007 | veliki hram — svod cele i krov | rekonstrukcija predlog | W79 | L.H.V |
| RH-008 | veliki hram — ulaz u celu: nesklad u izvoru | nesklad izvora | W79, R04 | L.H.V |
| RH-009 | veliki hram — materijal, poreklo i teza o promeni projekta | objavljeni nalaz i tumacenje | W79 | L.H.V, F.T |
| RH-010 | veliki hram — metrološka provera lakta | izvedena metroloska provera | W79 | L.H.V |
| RH-011 | veliki hram — poreklo „lakta“ od 47,2–47,7 cm | veza izvora | R06 | L.H.V, L.U.1, L.U.2, L.U.ZK, I.CM |
| RH-012 | veliki hram — pročelje: tekst (205 cm, šest elemenata) prema crtežima | izvedeno merenje sa crteza | W79, R04 | L.H.V |
| RP-001 | saobracajnice | usaglasenost teksta i merenja | R06, R05 | R.ZA, L.HO, R.DA |
| RP-002 | prilazni_put | tumacenje autora | R06, R04 | R.ZA, L.HO, L.U |
| RS-001 | stratigrafija | objavljena periodizacija | R02 | F.KA, F.SV, L.KN |
| RS-002 | ponovno naseljavanje | autorsko datovanje | R02 | F.KA, L.KN |
| RS-003 | požari i istorijski događaji | autorska hipoteza | R02 | F.KA, L.KN |
| RS-004 | faze naselja posle palate | objavljena periodizacija | R04 | F.KA, L.KN, L.HR |
| RS-005 | radionice | objavljeni nalaz i tumacenje | R04 | F.KA, L.KN, L.P.1 |
| RS-006 | metalurgija | objavljeni nalaz i tumacenje | R04 | F.KA, L.KN |
| RS-007 | bazilika I | uporedno datovanje | R06, R04 | L.HR, L.P.1, F.KA |
| RS-008 | identitet mlađe bazilike | nasa radna korelacija | R06, R05, R04 | L.HR, L.P.1, F.KA, F.SV |
| RS-009 | datovanje mlađe bazilike 1978 | autorsko datovanje | R06 | L.HR, F.KA |
| RS-010 | datovanje mlađe bazilike 1983 | autorsko otvoreno pitanje | R05 | L.HR, F.KA, F.SV |
| RS-011 | datovanje mlađe bazilike Petković 2010 | autorsko datovanje | R04 | L.HR, F.KA |
| RS-012 | datovanje mlađe bazilike Janković 2010 | autorska revizija | R04 | L.HR, F.SV |
| RS-013 | broj crkava i ograničenja | autorska sinteza | R04 | L.HR, F.KA |
| RS-014 | napuštanje u VII veku | autorska hipoteza | R02, R04 | F.KA, L.KN |
| RS-015 | srednjovekovni povratak | uporedno datovanje | R02, R05, R04 | F.SV, L.KN |
| RS-016 | stanovanje i preuređenje | objavljeni nalaz i tumacenje | R04 | F.SV, L.KN, L.P.1, L.P.2 |
| RS-017 | groblja | objavljeni nalaz | R04 | F.SV, L.KN |
| RS-018 | kraj srednjovekovnog naselja | autorska hipoteza | R02, R04 | F.SV, L.KN |
| RT-001 | lokalitet_identifikacija | identifikacija i karakter celine | R04, R06 | L |
| RT-002 | starije_utvrdjenje | arhitektonska faza | R04, R06 | L.U.1, L.U |
| RT-003 | mladje_utvrdjenje_kule | fortifikacioni sistem | R04, R06 | L.U.K, L.U |
| RT-004 | palacijalni_kompleks | prostorni sklop | R04, R06 | L.P |
| RT-005 | peristil_palate | arhitektonska celina | R04 | L.P.PE, L.P |
| RT-006 | juzne_javne_gradjevine | funkcionalna celina | R05, R04 | L.JB |
| RT-007 | sakralna_osa_hramova | urbanisticki koncept | R04, R06 | L.H |
| RT-008 | mali_hram_diva_romula | sakralni objekat | R04, R06 | L.H.M, L.H |
| RT-009 | mauzolej_1_magura | funerarni monument | R04 | L.MG.M1, L.MG |
| RT-010 | mauzolej_2_magura | funerarni monument | R04 | L.MG.M2, L.MG |
| RT-011 | tumuli_apoteoze | sakralni spomenik | R04 | L.MG.K, L.MG |
| RT-012 | tetrapilon_prilaz | monumentalna kapija | R04 | L.TP |
| RU-001 | natpis | objavljeni nalaz | R03, R04 | N.FR |
| RU-002 | natpis | objavljeni opis | R04 | N.FR |
| RU-003 | natpis | tumacenje autora | R08, R04 | N.FR, O.RO, O.GA |
| RU-004 | natpis | rekonstrukcija autora | R04 | N.FR, L.U.ZK |
| RU-005 | tetrarsi | tumacenje autora | R04 | N.SK, L.U.IK, F.T |
| RU-006 | tetrarsi | alternativno tumacenje | R04 | N.SK, L.U.IK, L.U.2, F.T |
| RU-007 | porfirni_portret | objavljeni nalaz | R04 | N.SK, L.T, O.GA |
| RU-008 | porfirni_portret | tumacenje autora | R04 | N.SK, O.GA, O.DI |
| RU-009 | veliki_hram_skulptura | objavljeni nalaz i atribucija | R04 | N.SK, L.H.V |
| RU-010 | arijadna | objavljeni nalaz | R04 | N.SK, L.T |
| RU-011 | raspored_mozaika | objavljeni opis | R04, R05 | L.P.MO, L.P.1 |
| RU-012 | venatori | objavljeni opis | R05 | L.P.MO |
| RU-013 | dionis | objavljeni opis | R05, R06, R04 | L.P.MO, L.P.AU |
| RU-014 | znacenje_mozaika | tumacenje autora | R06, R05, R04 | L.P.MO |
| RU-015 | izgubljeni_paneli | hipoteza autora | R05, R04 | L.P.MO |
| RU-016 | uporedni_stil | stilsko tumacenje | R08 | L.P.MO |
| RU-017 | veliki_hram_skulptura | veza izvora | R02, R04 | L.MG, O.GA, O.RO |
| RU-018 | datum_apoteoze | objavljeni nalaz | R04 | L.MG.MZ, O.RO, R.ZA |
| RU-019 | bakljonose | tumacenje autora | R02, R04 | L.MG, F.KA, O.RO |
| RU-020 | torzo_imperatora_u_oklopu | objavljeni opis | R04 | L.MG, O.GA, O.DI, R.ME |
| RV-001 | natpis | vizuelni opis | R04 | N.FR |
| RV-002 | tetrarsi | objavljeni nalaz i vizuelni opis | R04 | N.SK, L.U.IK, F.T |
| RV-003 | tetrarsi | vizuelni opis i korelacija | R04, R08 | N.SK, L.U.IK, F.T |
| RV-004 | veliki_hram_skulptura | vizuelni opis i korelacija | R04, R08 | N.SK, L.H.V |
| RV-005 | veliki_hram_skulptura | vizuelna korelacija | R02, R04 | N.SK, L.H.V |
| RV-006 | porfirni_portret | vizuelni opis | R04 | N.SK, O.GA |
| RV-007 | mere_mozaika | vizuelna provera mera | R05 | L.P.MO |
| RV-008 | uporedni_stil | atribucija sa snimka | R08 | L.P.MO |
| RV-009 | natpis | zavisnost izvora | R08, R04 | N.FR, N.SK, O.GA |
| RV-010 | raspored_mozaika | objavljeni podatak | R04 | L.P.MO, L.P.1 |

</details>

## 4. Lokalitet po celinama

Čvorovi `L.*` (prostor), sa brojem tvrdnji i automatskim pregledom. Celina bez tvrdnje znači da je pominjana u izvorima, ali nije proveravana uporednim čitanjem.

| Čvor | Naziv | Tvrdnje | Pregled |
|---|---|---|---|
| `L` | Felix Romuliana (Gamzigrad) | 1: RT-001 | [L](pregled/L.md) |
| `L.U` | Utvrđenje i bedemi | 3: RP-002, RT-002, RT-003 | [L.U](pregled/L.U.md) |
| `L.U.1` | Stariji (unutrašnji) bedem — Galerije cezar | 2: RH-011, RT-002 | [L.U.1](pregled/L.U.1.md) |
| `L.U.2` | Mlađi (spoljni) bedem — Galerije avgust | 2: RH-011, RU-006 | [L.U.2](pregled/L.U.2.md) |
| `L.U.K` | Kule | 1: RT-003 | [L.U.K](pregled/L.U.K.md) |
| `L.U.IK` | Istočna kapija | 4: RU-005, RU-006, RV-002, RV-003 | [L.U.IK](pregled/L.U.IK.md) |
| `L.U.ZK` | Zapadna kapija | 2: RH-011, RU-004 | [L.U.ZK](pregled/L.U.ZK.md) |
| `L.P` | Palata (carski dvorac) | 2: RT-004, RT-005 | [L.P](pregled/L.P.md) |
| `L.P.1` | Palata I (severozapadna četvrt, D1–D2) | 13: RD-001, RD-002, RD-003, RD-004, RD-007, RD-008, RD-009, RS-005, RS-007, RS-008, RS-016, RU-011, RV-010 | [L.P.1](pregled/L.P.1.md) |
| `L.P.2` | Palata II i zgrada sa koridorom (severoistočna četvrt, D3–D5) | 2: RD-006, RS-016 | [L.P.2](pregled/L.P.2.md) |
| `L.P.PE` | Peristil | 1: RT-005 | [L.P.PE](pregled/L.P.PE.md) |
| `L.P.AU` | Aula / triklinijum / apsidalna dvorana | 1: RU-013 | [L.P.AU](pregled/L.P.AU.md) |
| `L.P.MO` | Mozaici | 9: RU-011, RU-012, RU-013, RU-014, RU-015, RU-016, RV-007, RV-008, RV-010 | [L.P.MO](pregled/L.P.MO.md) |
| `L.JB` | Južne javne građevine (tribunal/pretorijum G, petobrodna zgrada F) | 1: RT-006 | [L.JB](pregled/L.JB.md) |
| `L.H` | Hramovi | 2: RT-007, RT-008 | [L.H](pregled/L.H.md) |
| `L.H.V` | Veliki hram (Divus Galerius) | 15: RH-001, RH-002, RH-003, RH-004, RH-005, RH-006, RH-007, RH-008, RH-009, RH-010, RH-011, RH-012, RU-009, RV-004, RV-005 | [L.H.V](pregled/L.H.V.md) |
| `L.H.M` | Mali hram (Diva Romula) | 1: RT-008 | [L.H.M](pregled/L.H.M.md) |
| `L.T` | Terme | 2: RU-007, RU-010 | [L.T](pregled/L.T.md) |
| `L.HO` | Horeum i ekonomski objekti | 2: RP-001, RP-002 | [L.HO](pregled/L.HO.md) |
| `L.HR` | Ranohrišćanski objekti (bazilika, crkve) | 17: RD-001, RD-002, RD-003, RD-004, RD-005, RD-006, RD-007, RD-008, RD-009, RS-004, RS-007, RS-008, RS-009, RS-010, RS-011, RS-012, RS-013 | [L.HR](pregled/L.HR.md) |
| `L.KN` | Kasnije naselje (vizantijsko, srednjovekovno) | 11: RS-001, RS-002, RS-003, RS-004, RS-005, RS-006, RS-014, RS-015, RS-016, RS-017, RS-018 | [L.KN](pregled/L.KN.md) |
| `L.MG` | Magura — memorijalni kompleks | 6: RT-009, RT-010, RT-011, RU-017, RU-019, RU-020 | [L.MG](pregled/L.MG.md) |
| `L.MG.M1` | Mauzolej 1 (Romula) | 1: RT-009 | [L.MG.M1](pregled/L.MG.M1.md) |
| `L.MG.M2` | Mauzolej 2 (Galerije) | 1: RT-010 | [L.MG.M2](pregled/L.MG.M2.md) |
| `L.MG.K` | Konsekracioni spomenici (tumuli) | 1: RT-011 | [L.MG.K](pregled/L.MG.K.md) |
| `L.MG.MZ` | Mauzoleji (opšte) | 1: RU-018 | [L.MG.MZ](pregled/L.MG.MZ.md) |
| `L.TP` | Tetrapilon | 1: RT-012 | [L.TP](pregled/L.TP.md) |

Ostali čvorovi (39): faze `F.*`, nalazi `N.*`, ličnosti `O.*`, istraživači `I.*`, regionalne paralele `R.*`. Svaki ima pregled u `pregled/<ID>.md`.

| Čvor | Naziv | Tvrdnji |
|---|---|---:|
| `N` | Natpisi i nalazi | 0 |
| `N.FR` | Natpis FELIX ROMULIANA (1984) | 6 |
| `N.NO` | Novac (numizmatika) | 0 |
| `N.SK` | Skulptura i portreti | 13 |
| `N.ZL` | Zlatni nakit i carske insignije | 0 |
| `O` | Osobe | 0 |
| `O.GA` | Galerije | 7 |
| `O.RO` | Romula (Galerijeva majka) | 4 |
| `O.DI` | Dioklecijan | 2 |
| `O.KO` | Konstantin | 0 |
| `O.MD` | Maksimin Daja | 0 |
| `O.LI` | Licinije | 0 |
| `O.LA` | Laktancije / Aurelije Viktor (antički pisci) | 0 |
| `I` | Istraživači | 0 |
| `I.SR` | Dragoslav Srejović | 0 |
| `I.CM` | Milka Čanak-Medić | 1 |
| `I.MZ` | Đorđe Mano-Zisi | 0 |
| `I.LA` | Anka Lalović | 0 |
| `I.JA` | Đorđe Janković | 0 |
| `I.VA` | Čedomir Vasić | 0 |
| `I.PO` | Ivana Popović | 0 |
| `I.ZI` | Maja Živić | 0 |
| `I.TO` | Gerda von Bülow / Stefan Pop-Lazić / Sofija Petković | 0 |
| `F` | Faze i hronologija | 0 |
| `F.T` | Tetrarhija (293–311) | 5 |
| `F.PR` | Pre utvrđenja (praistorija, rani rimski) | 0 |
| `F.KA` | Kasnoantičko-ranovizantijsko (IV–VI v.) | 22 |
| `F.SV` | Srednji vek (X–XII v.) | 17 |
| `R` | Regionalni kontekst | 0 |
| `R.SA` | Šarkamen | 0 |
| `R.RG` | Rgotina | 0 |
| `R.ZA` | Zaječar i Timok | 3 |
| `R.ME` | Medijana / Naissus | 1 |
| `R.SP` | Split (Dioklecijanova palata) | 0 |
| `R.SO` | Solun (Galerijev kompleks) | 0 |
| `R.SI` | Sirmijum | 0 |
| `R.SE` | Serdika | 0 |
| `R.AQ` | Akvis (Aquae / Prahovo) | 0 |
| `R.DA` | Dakija (Ripensis, Mediterranea) | 1 |

## 5. Izvori

### Jezgro korpusa R01–R08 (8)

| ID | Godina | Autor(i) | Naslov | Nivo | Jedinica | Tvrdnji |
|---|---|---|---|---|---:|---:|
| R01 | 1994 | Dragoslav Srejović, Čedomir Vasić | Emperor Galerius's buildings in Romuliana (Gamzigrad, Eastern Serbia) | T2 | 19 | — |
| R02 | 1980 | Dragoslav Srejović, Anka Lalović, Đorđe Janković (Gamzigrad) | Gamzigrad (+ Rgotina, antičko nalazište; Istraživanje spomenika u Vrelu, Šarkamen) | T3 | 38 | 9 |
| R03 | 1985 | Dragoslav Srejović | Felix Romuliana. Galerijeva palata u Gamzigradu | T2 | 17 | 1 |
| R04 | 2010 | Ivana Popović (ur.); Maja Živić, Miroslav Lazić, Miodrag Sla | Felix Romuliana – Gamzigrad | T1 | 240 | 58 |
| R05 | 1983 | Dragoslav Srejović, Đorđe Janković, Anka Lalović, Vidojko Jo | Gamzigrad – kasnoantički carski dvorac | T2 | 49 | 17 |
| R06 | 1978 | Milka Čanak-Medić | Gamzigrad. Kasnoantička palata. Arhitektura i prostorni sklop | T1 | 302 | 16 |
| R07 | 2017 | Vesna Bikić, Josip Šarić (ur.) | Mnemosynon firmitatis. Sedamdeset godina Arheološkog instituta (1947–2017) | T2 | 300 | — |
| R08 | 1993 | Dragoslav Srejović (priredio) | Rimski carski gradovi i palate u Srbiji | T2 | 182 | 6 |

### Literatura sa interneta (članci, monografije, sveske) (23)

| ID | Godina | Autor(i) | Naslov | Nivo | Jedinica | Tvrdnji |
|---|---|---|---|---|---:|---:|
| W01 | 2006 | Sofija Petković | Unilateral antler combs from Romuliana | T2 | 14 | — |
| W02 | 2007 | Gerda von Bülow, Thomas Schüler | Geophysical and archaeological research at Gamzigrad: report of the 2004–2007 campaigns | T2 | 19 | — |
| W03 | 2007 | Sofija Petković | Late Roman necropolis of Romuliana, area south of the fortified palace: research 2005–2006 | T2 | 25 | — |
| W04 | 2007 | Maja Živić | Catalogue of small finds from excavations outside the fortified palace of Romuliana (2005– | T2 | 31 | — |
| W05 | 2007 | Miloje Vasić | Findings of coins from Romuliana, unearthed in 2005 and 2006 outside the fortified palace | T2 | 6 | — |
| W06 | 2007 | Vesna Dimitrijević, Aleksandar Medović | Animal and plant remains in a tomb in test-pit 1/05, outside the fortified imperial palace | T2 | 9 | — |
| W07 | 2009 | Aleksandar Kapuran | O uticajima Vatina i Verbičoare na nalazima Gamzigradske kulturne grupe | T2 | 17 | — |
| W08 | 2010 | Sofija Petković | Crossbow fibulae from Gamzigrad (Romuliana) | T2 | 26 | — |
| W09 | 2011 | Sofija Petković | The Roman settlement on Gamzigrad prior to the imperial palace Felix Romuliana | T2 | 20 | — |
| W10 | 2013 | Sofija Petković, Aleksandar Kapuran | Archaeological excavations at Gamzigrad – Romuliana in 2007–2008 | T2 | 14 | — |
| W11 | 2021 | Sonja Jovanović, Anastasia Cholakova, Stefan Pop-Lazić, Ian  | The blues of Romuliana | T2 | 24 | — |
| W12 | 2023 | Nadežda Gavrilović Vitas, Jelena Anđelković Grašar | Nike/Victoria representations in Late Antique Central Balkans | T2 | 21 | — |
| W13 | 1994 | — | Starinar 45–46 (1994–1995) — cela sveska | T2 | 322 | — |
| W14 | 1997 | — | Starinar 48 (1997) — cela sveska | T2 | 124 | — |
| W15 | 2008 | Živko Mikić | The medieval cemetery outside the eastern gate of Gamzigrad (Felix Romuliana): a paleodemo | T2 | 7 | — |
| W16 | 2010 | Živko Mikić | Trepanning on Mediaeval Gamzigrad — Felix Romuliana | T2 | 13 | — |
| W17 | 2021 | Alfred Twardecki (recenzija) | Gerda von Bülow, Sofija Petković (eds), Gamzigrad-Studien I. Ergebnisse der deutschserbisc | T2 | 10 | — |
| W18 | 2010 | D. Mihajlović, M. Mitrović, Ž. Cvijetinović, M. Vojinović | Photogrammetry of archaeological site Felix Romuliana at Gamzigrad using aerial digital ca | T2 | 4 | — |
| W19 | — | — | Archaeological Site of Gamzigrad (Felix Romuliana) | T4 | 4 | — |
| W20 | 2005 | Zavod za zaštitu spomenika kulture Srbije | Gamzigrad – Romuliana, Palace of Galerius: nomination dossier for inscription on the World | T1 | 289 | — |
| W21 | 2011 | Sofija Petković | Late Roman Romuliana and mediaeval Gamzigrad from the end of the 4th to the 11th centuries | T1 | 17 | 1 |
| W22 | 2011 | Orsolya Heinrich-Tamáska (Hrsg.) | Keszthely-Fenékpuszta im Kontext spätantiker Kontinuitätsforschung zwischen Noricum und Mo | T1 | 731 | — |
| W79 | 1989 | Brana Stojković-Pavelka | Veliki hram u Gamzigradu — predlog za rekonstrukciju (Le grand temple à Felix Romuliana) | T1 | 12 | 11 |

### Karte, podloge, snimci i geopodaci (51)

| ID | Godina | Autor(i) | Naslov | Nivo | Jedinica | Tvrdnji |
|---|---|---|---|---|---:|---:|
| W23 | — | Heinrich Kiepert | Dalmatia&Moesia Superior.JPG | M | — | — |
| W24 | — | Justhus Perthes | Roman Dardania part of Moesia Superior part of old map made 1865.jpg | M | — | — |
| W25 | — | Society for the Diffusion of Useful Knowledge | Roman Dardania part of Moesia Superior part of old map made 1830.jpg | M | — | — |
| W26 | — | Carole Raddato from FRANKFURT, Germany | Felix Romuliana, built in 298 AD by Emperor Galerius, Dacia Ripensis, Serbia (28086214227) | M | — | — |
| W27 | — | Carole Raddato from FRANKFURT, Germany | Felix Romuliana, built in 298 AD by Emperor Galerius, Dacia Ripensis, Serbia (28086212597) | M | — | — |
| W28 | — | Carole Raddato from FRANKFURT, Germany | Felix Romuliana, built in 298 AD by Emperor Galerius, Dacia Ripensis, Serbia (28086215607) | M | — | — |
| W29 | — | Carole Raddato from FRANKFURT, Germany | Felix Romuliana, built in 298 AD by Emperor Galerius, Dacia Ripensis, Serbia (28086218927) | M | — | — |
| W30 | — | Carole Raddato from FRANKFURT, Germany | Felix Romuliana, built in 298 AD by Emperor Galerius, Dacia Ripensis, Serbia (28086220797) | M | — | — |
| W34 | — | C. Gros | Roman Dardania part of Moesia Superior part of old map made 1820.jpg | M | — | — |
| W35 | — | Abraham Ortelius | Map of Dacia and Moesia by Abraham Ortelius.jpeg | M | — | — |
| W36 | — | OSM saradnici | OSM savremeni kontekst Gamzigrad z13 (ispravne koordinate 43.899/22.186) | M | — | — |
| W37 | 2026 | OSM saradnici | OpenStreetMap API upit oko lokaliteta (22.18–22.195E, 43.895–43.905N) — sažetak: 2452 elem | M | — | — |
| W39 | 2026 | OpenStreetMap contributors | Nominatim pretraga "Felix Romuliana" i "Gamzigrad" — OSM identitet lokaliteta | M | — | — |
| W40 | 1896 | nepoznat (Commons) | Map of the Roman province of Moesia (1896) | M | — | — |
| W41 | 1849 | Alexander G. Findlay | Macedonia, Thracia, Illyria, Moesia, Dacia (Findlay, Map X, 1849) | M | — | — |
| W42 | 1849 | Alexander G. Findlay (obrada nepoznata) | Macedonia, Thracia, Illyria, Moesia, Dacia (Findlay 1849, refurbished) | M | — | — |
| W43 | 1886 | Gustav Droysen (1838–1908) | The Roman provinces of the Lower Danube (Droysens Historischer Atlas, 1886) — izrez | M | — | — |
| W44 | 1886 | Gustav Droysen (1838–1908) | Thracia posle Dioklecijanove reforme (Droysen, 1886) — izrez | M | — | — |
| W45 | 2025 | Copernicus Sentinel data 2025 (ESA); isecanje: titiler.xyz n | Sentinel-2 L2A S2B_34TEP_20250922 (2025-09-22, oblak 0%) — TCI isečak Romulijane i okoline | M | — | — |
| W46 | 2025 | Copernicus Sentinel data 2025 (ESA) | Sentinel-2 S2B_34TEP_20250922 thumbnail (cela scena, pregled) | M | — | — |
| W47 | 2025 | Element84 / ESA Copernicus | STAC item S2B_34TEP_20250922_0_L2A (potpuni metapodaci scene: orbita, Cloud Cover 0.0, sve | M | — | — |
| W48 | — | OSM saradnici | OSM savremeni kontekst Gamzigrad z12 | M | — | — |
| W50 | — | OSM saradnici | OSM savremeni kontekst Gamzigrad z14 | M | — | — |
| W51 | 2010 | Pavle Marjanovic | Felix Romuliana 1.jpg | M | — | — |
| W52 | 2010 | Pavle Marjanovic | Felix Romuliana 2.jpg | M | — | — |
| W53 | 2010 | Pavle Marjanovic | Felix Romuliana 3.jpg | M | — | — |
| W54 | 2010 | Pavle Marjanovic | Felix Romuliana 4.jpg | M | — | — |
| W55 | 2010 | Pavle Marjanovic | Felix Romuliana 5.jpg | M | — | — |
| W56 | 2010 | Pavle Marjanovic | Felix Romuliana 8.jpg | M | — | — |
| W57 | 2016 | M Todorovic | Felix Romuliana unutrašnjost.jpg | M | — | — |
| W58 | 2013 | Pudelek (Marcin Szala) | Gamzigrad - Felix Romuliana (by Pudelek) 1.jpg | M | — | — |
| W59 | 2013 | Pudelek (Marcin Szala) | Gamzigrad - Felix Romuliana (by Pudelek) 2.JPG | M | — | — |
| W60 | 2013 | Pudelek (Marcin Szala) | Gamzigrad - Felix Romuliana (by Pudelek) 3.JPG | M | — | — |
| W61 | 2013 | Pudelek (Marcin Szala) | Gamzigrad — Felix Romuliana (Pudelek 4) | M | — | — |
| W62 | 2013 | Pudelek (Marcin Szala) | Gamzigrad — Istočna kapija (Pudelek 5) | M | — | — |
| W63 | 2013 | Pudelek (Marcin Szala) | Gamzigrad — Felix Romuliana (Pudelek 6) | M | — | — |
| W64 | 2013 | Pudelek (Marcin Szala) | Gamzigrad — Felix Romuliana (Pudelek 7) | M | — | — |
| W65 | 1886 | Gustav Droysen (1838 — 1908) | The Roman provinces of Illyricum, Macedonia, Dacia, Moesia, Pannonia and Thracia (Droysens | M | — | — |
| W66 | 2024 | Pleiades Stoa (Barchiesi, Becker, Bodard et al.) | Pleiades 207395 — Romuliana (JSON resurs) | M | — | — |
| W67 | 2023 | Pleiades Stoa | Pleiades 207395 — Romuliana (arhivirana HTML stranica) | M | — | — |
| W68 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC Roman Road Network v2008 — Readme (licenca CC BY-NC 3.0, citat McCormick et al. 2013 | M | — | — |
| W69 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — geometrija (7154 polilinije, 70652 tačke) | M | — | — |
| W70 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — prostorni indeks | M | — | — |
| W71 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — atributi (CLASS/CERTAINTY/SOURCE) | M | — | — |
| W72 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — projekcija (ED50, Europe LCC) | M | — | — |
| W73 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — spatial index .sbn | M | — | — |
| W74 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — spatial index .sbx | M | — | — |
| W75 | 2008 | Michael McCormick et al. (DARMC, Harvard) | DARMC rimski putevi v2008 — metapodaci .shp.xml | M | — | — |
| W76 | 2026 | izvedeno: Svemir (glm-5.3-flash); osnova: Michael McCormick  | DARMC rimski putevi oko Romulijane — izvedeni sloj okoline 15 km (8 trasa, WGS84) | M | — | — |
| W77 | 2026 | OpenStreetMap contributors | OpenStreetMap Overpass vektorska geometrija lokaliteta Felix Romuliana i Magure (191 featu | M | — | — |
| W78 | 2026 | ESA Copernicus DEM GLO-30 / Open-Meteo Elevation API | Copernicus DEM GLO-30 model terena (visinska mreža 19×11 = 209 tačaka, 141–258 m n.v.) za  | M | — | — |

Nedodeljene oznake (povučene ili nikad upisane, ne ponovo koristiti): W31, W32, W33, W38, W49.

Literatura koju projekat navodi, a nema je u korpusu, opisana je u HRAMOVI-LITERATURA.md (Stamper, Wilson Jones, Orlin, Segal, Mierse) i u otvorenim pitanjima O-02, O-04, O-10 i O-11.

## 6. Dosijei i sinteze

- [SAZETAK.md](SAZETAK.md) — Sažetak na jednoj strani (01.11.2026)
- [pregled/PROVERA-SAZETKA.md](pregled/PROVERA-SAZETKA.md) — Ponovna provera sažetka prema korpusu
- [POREDJENJE.md](POREDJENJE.md) — Matrica čvor × izvor (automatski)
- [pregled/TOPOLOGIJA.md](pregled/TOPOLOGIJA.md) — Topografija i prostorne celine
- [pregled/UMETNOST.md](pregled/UMETNOST.md) — Natpis, skulptura i mozaici — tekstualno poređenje
- [pregled/UMETNOST-VIZUELNO.md](pregled/UMETNOST-VIZUELNO.md) — Natpis, skulptura i mozaici — vizuelna provera
- [pregled/SLOJEVI.md](pregled/SLOJEVI.md) — Kasnoantički, ranovizantijski i srednjovekovni slojevi
- [pregled/PLANOVI.md](pregled/PLANOVI.md) — Korelacija osnova crkava
- [pregled/DATOVANJE-BAZILIKE.md](pregled/DATOVANJE-BAZILIKE.md) — Podovi, keramika i litijski krst
- [pregled/PUTEVI.md](pregled/PUTEVI.md) — Putevi i prilaz
- HRAMOVI-LITERATURA.md — Hramovi: W79 i pet knjiga o rimskim hramovima
- KNOWLEDGE.md — Naučeno: greške, iskustva, odluke
- [atlas/ATLAS.md](atlas/ATLAS.md) — Atlas: razmere S0–S4, slojevi, prava
- [atlas/INSTRUMENT.md](atlas/INSTRUMENT.md) — Atlas: teorija i srodne arhitekture

## 7. Raspored foldera

| Folder | Sadržaj | Javno (GitHub) |
|---|---|---|
| `izvori/pdf`, `izvori/foto` | Originali R01–R08 (PDF, 182 JPG) sa SHA-256 | ne |
| `izvori/internet` | Preuzeta literatura i geopodaci W01–W79 | ne |
| `izvori/renderi` | Isečci i renderi strana koji su dokazi | da |
| `tekst/<ID>` | Tekst po jedinici (`pNNN.txt` + `.json`) | ne |
| `baza` | Katalog, tvrdnje, hijerarhija, objekti, georeferenca, provere, otvorena pitanja; `romulijana.sqlite` je izvedeni indeks | da, bez SQLite i indeksa pominjanja |
| `pregled` | Automatski pregledi čvorova i ručni dosijei | da |
| `atlas` | 3D instrument (`index.html` + `atlas-podaci.js`) i njegovi dokumenti | da |
| `alati` | Svi alati za gradnju i proveru | ne |
| `github` | Kurirani javni paket i git repozitorijum `3esign/romulijana` | to je repo |

## 8. Tok gradnje i provere

Redosled posle svake promene podataka (iz korena projekta):

```sh
node alati/tvrdnje.js                # tvrdnje -> SQLite
node alati/atlas-inventar.js --provera  # katalog atlasa i graf
node alati/atlas-paket.js            # atlas/atlas-podaci.{json,js}
node alati/mapa.js --provera         # MAPA.md
node alati/proveri-pretragu.js       # kapija integriteta (mora biti status ok)
node alati/github-paket.js           # javni paket u github/
```

Puna obnova indeksa iz teksta: `node alati/indeks.js` (sporo; čuva ručne dosijee).

## 9. Javna površina

- Atlas: <https://3esign.github.io/romulijana/atlas/>
- Repozitorijum: <https://github.com/3esign/romulijana>
- Autori: doc. dr Bojan Končarević · doc. dr Semir Poturak. Deo podataka: Arheološki institut, Beograd.
- Javno ide samo kurirani paket: bez izvornih PDF-ova, snimaka, punog teksta i SQLite indeksa.
