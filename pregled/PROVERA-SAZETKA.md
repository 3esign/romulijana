# Romulijana — provera sažetka, 01.11.2026.

Predmet: [SAZETAK.md](../SAZETAK.md) i njegova saglasnost sa lokalnim korpusom iz `romulijana.rar`. Internet nije korišćen; proširivanje literature ostaje naredni posao.

## Ispravke

- **R02:** prva etapa prema legendi Skice 6 traje oko 297–306, ne 297–305. Godina izdanja 1980 u katalogu još nosi rezervu: preuzeta je iz naziva fajla, sveska nije potvrđena.
- **R04 PDF55–56:** zemljotres i nezavršenost starijeg utvrđenja predstavljeni su kao pretpostavke, a ne utvrđena istorija. Poglavlje potpisuju Čanak-Medić i Stojković-Pavelka.
- **R04 PDF56, 57 i 75:** 305–306 je predloženo datovanje mlađeg utvrđenja; ne sme potisnuti alternativu 308 za pilastre i završne radove 308–311 na zapadnim vratima. Period 306–311 nije zajednički dokazani datum svih unutrašnjih građevina.
- **R01 PDF19:** Romulina sahrana je po autorima verovatno neposredno pre 306; datum 294/295 ostaje kasniji predlog M. Vasića prenesen preko R04. Pripisivanje mauzoleja Romuli i Galeriju nije epigrafska identifikacija grobova.
- **R03 PDF3 i R04 PDF207:** opis prvobitne carske namene ne isključuje kasniju crkvenu/upravnu funkciju. R02 PDF13 i R04 PDF207: 1072. je istorijska korelacija napuštanja, ne neposredno arheološko datovanje.
- **Zavisnost R04/R08** odnosi se na odabrane odlomke o Jupiteru, pilastru i natpisu, ne na sve sadržaje obe knjige.
- **1147 označava indeksirane jedinice**, ne isti broj štampanih strana: 965 PDF strana i 182 fotografska snimka. Deo jedinica sadrži dvostruke strane. Mapa od 711 jedinica uključuje automatski izvedene brojeve, ne samo vizuelne potvrde. Potpunost R05 prema celoj knjizi nije potvrđena.
- **„Jedna strana“** je objedinjeni pregled u Markdownu; prelom na jedan štampani list nije bio urađen niti proveren.

## Dokaz i granice

Ponovo su pročitani odabrani tekstovi R01 PDF19, R02 PDF9/12/13, R03 PDF3, R04 PDF55/56/57/75/207, katalog i dosijei umetnosti/datovanja. Ponovna kontrola ne predstavlja nezavisnu stručnu recenziju.

Tehnički zapis: [`baza/provere/provera-sazetka.json`](../baza/provere/provera-sazetka.json); objedinjena provera celog projekta: `alati/proveri-pretragu.js`. Provere prolaze: vernost sva 52 zapisa bazi, 106 tekstualnih dokaza (heš i sidro), 50 relacija i pretraga oba pisma. Potvrđeno je 1147 jedinica, 17.925 pominjanja, 711 mapiranih jedinica i svih 8 departmanskih oznaka. [Manifest umetnosti](../izvori/renderi/umetnost/manifest.json) sadrži 15 zapisa (13 PDF rendera + 2 izvorne fotografije R08), a u folderu je i 1 isečak mera (`R05-p020-mere.png`); svi heševi slika i referenciranih PDF izvora odgovaraju.

Otvorena ostaju datovanje mlađe bazilike ([DATOVANJE-BAZILIKE.md](DATOVANJE-BAZILIKE.md)), odnos fragmenata statue u oklopu prema Jupiterovoj statui ([UMETNOST-VIZUELNO.md](UMETNOST-VIZUELNO.md)) i ostala pitanja sažetka. Ovaj prolaz ne dokazuje da su pročitane cele knjige, da je sadržaj arhive potpun ili da dalja dokumentacija ne postoji.
