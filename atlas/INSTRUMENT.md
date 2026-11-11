# Romulijana · 3D Atlas kao interaktivni naučni instrument, rekonstrukcija i vizuelizacija podataka

**Stanje:** 2026-11-02 · **Projekat:** [Romulijana](../README.md) (`C:\Svemir\!Projekti\Romulijana`)  
**Veza:** [ATLAS.md](ATLAS.md) · OPREMA.md · [ART_BIBLE.md](ART_BIBLE.md) · [KATALOG.md](KATALOG.md) · [graf.json](graf.json) · [index.html](index.html)

---

## 1. Šta tačno hoćemo da napravimo (Definicija instrumenta)

Ne pravimo turističku video-animaciju („crnu kutiju" u kojoj gledalac ne zna šta je kamen na terenu a šta mašta modelara), ne pravimo generički GIS portal sa šarenim ikonicama i ne pravimo lebdeći graf bez geografije.

Gradimo **forenzički prostorno-epistemološki instrument (*Spatial Epistemic Instrument*)** u kome su četiri ravni istovremeno čitljive, merljive i dvosmerno povezane u jednom WebGL/DOM prostoru:

1. **Prostorno-fizička ravan (S0 → S4):** neprekidan semantički zum od **S0** (rimske provincije, DARMC mreža carstva, uporedne tetrarhijske rezidencije: Split, Solun, Medijana, Šarkamen), preko **S1** (sliv Timoka do 25 km, 8 rimskih trasa W76 sa najbližim segmentom na $2.531\text{ m}$ od lokaliteta, vizura ka svetom brdu Magura na $\sim 1\text{ km}$ istočno), **S2** (utvrđenje, sonde, južna nekropola, geofizika van bedema), **S3** (arhitektonski sklopovi: Starije i Mlađe utvrđenje, Palata I i II, Veliki i Mali hram, terme, tetrapilon, dve starohrišćanske crkve i krstionica, mauzoleji i tumuli na Maguri) do **S4** (skulptura od porfira i mermera, arhivolta sa natpisom `FELIX ROMVLIANA`, mozaici Dionisa i lavirinta, novac i fibule).
2. **Vremensko-stratigrafska ravan (`F.*` + Harris/Extended Matrix):** prelaz kroz faze **F.PR** (praistorija i rimsko naselje pre palate), **F.T** (tetrarhijska gradnja i apoteoza Galerija i Romule, ~293–311), **F.KA** (kasna antika i ranovizantijska obnova IV–VI vek) i **F.SV** (srednjovekovno naselje i nekropola X–XII vek).
3. **Epistemička ravan (Sigurnost A/B/C + *Capta* sporovi):** svaki kubni metar geometrije vizuelno, bez legende, svojim materijalom i vrstom linije govori koliko je siguran:
   - **Nivo A (Činjenica / *In situ*):** fizički očuvani temelji, bedemi, pilastri, podni mozaici i geodetski/fotogrametrijski snimljene kote.
   - **Nivo B (Izvedena rekonstrukcija / Analogija):** visine stubova, lukova, svodova i krovova izvedene iz pronađenih arhitektonskih članaka u šutu i proporcijskih analiza (npr. rekonstrukcije M. Čanak-Medić u R06 ili analogije sa Splitom i Medijanom).
   - **Nivo C (Hipoteza):** gornje zone nestalih struktura ili prostorne pretpostavke bez direktnog članka *in situ*.
   - **Bistabilni prikaz (*Capta* / Dve verzije):** tamo gde se primarna literatura razilazi (npr. mlađa jednobrodna crkva: VI vek kod S. Petković / W21 / RD-008 naspram X–XI veka kod Đ. Jankovića u R04; ili tačna godina apoteoze RU-018), instrument ne računa „prosek", već nudi **dvojni preklop (ghost-split)** sa oba dokaza.
   - **Vidljive praznine (`P-TVRDNJE` / `P-GEOMETRIJA`):** 12 prostornih čvorova koji još nemaju verifikovanu tvrdnju u registru prikazuju se kao otvoreni temeljni okviri u tlu — neznanje je eksplicitno kartirano.
4. **Forenzičko-katalogička ravan (Poreklo i konstelacija znanja):** svaki 3D volumen je čvor u `graf.json` (presek 02.11.2026: 207 čvorova, 603 veze, 32.041 pominjanje u 2.894 strane; tekuće brojke su u `MAPA.md`). Klik na 3D masu u $\le 200\text{ ms}$ otvara tačnu tvrdnju (`RU`, `RS`, `RV`, `RD`, `RP`), citat, PDF stranu, štampanu stranu, render plana i SHA-256 otisak fajla na disku.

---

## 2. Uporedna analiza svetskih primera, programa i arhitektura koda

Pregledani su vodeći naučni okviri za virtuelnu arheologiju, geoprostorne 3D sisteme i digitalnu humanistiku. Tabela izdvaja šta svaki sistem rešava dobro, gde pada i šta tačno preuzimamo u naš kod:

| Sistem / Projekat | Institucija / Autori | Tehnološki stek | Šta rešava vrhunski (Uzor) | Ograničenje / Zašto ga ne kopiramo slepo | Šta ugrađujemo u Atlas Romulijane |
|---|---|---|---|---|---|
| **Extended Matrix (EM) + ATON Framework** | CNR-ISPC (Rim) · E. Demetrescu (2015), B. Fanini et al. (2021) | Three.js, Node.js, Blender EMtools (GraphML + glTF) | Formalni jezik paradata izveden iz Harisove matrice: čvorovi `US` (in situ), `USV/s` (strukturalna rekonstrukcija iz tragova), `USV/n` (nestrukturalna/analogija), `SF` (special find) + *Temporal Lensing* (vremenska lupa). | Traži GraphML fajlove iz Blendera i poseban Node bekend; vizuelni UI ATON-a je često generički (Bootstrap/materijal). | **EM klasifikacija čvorova (`US` ↔ A, `USV/s` ↔ B1, `USV/n` ↔ B2, hipoteza ↔ C)** direktno u JSON šemi čvora + shader za *vremensku lupu / presek*. |
| **3DHOP (3D Heritage Online Presenter)** | ISTI-CNR (Piza) · M. Callieri, R. Scopigno et al. (2015) | HTML5 WebGL, SpiderGL, Nexus multiresolution | Naučni alati inspekcije: *point-to-point* merenje, ortogonalne presečne ravni (*clipping planes*), interaktivno koso svetlo (*raking light* za natpise i reljefe), čista sprega 3D hotspotova sa DOM tekstom. | SpiderGL je stariji, niskonivoski WebGL 1 stek bez modernog PBR/tonemap lanca i bez multiskalarnog GIS okruženja (S0–S1). | **Tri analitička alata u Three.js r186:** (1) živa ravan preseka (`THREE.Plane`), (2) *Raking Light* kontrola ugla svetla za arhivoltu i plastiku, (3) DOM↔3D sprega bez modala. |
| **Smithsonian Voyager** | Smithsonian DPO (Vašington) | Three.js, TypeScript, Entity-Component, glTF + Draco | *Voyager Story*: vođene naučne ture kroz 3D objekat sa kamerom vezanom za članke, merenja i slojeve; stroga pristupačnost. | Fokusiran na pojedinačni muzejski artefakt (S4) ili jednu prostoriju, bez regionalne mreže puteva (S0–S1) i bez grafa tvrdnji. | **Režim vođene naučne ture (`T`)** sa autorskim kadrovima (*vista → approach → detail*) gde svaka stanica menja kameru, fazu i aktivni dokaz u dosijeu. |
| **Forensic Architecture (*Image Complex*)** | Goldsmiths (London) · E. Weizman (2017–2026) | Three.js / Blender / prilagođeni WebGL vremenski-prostorni plejeri | **Arhitektonski kompleks slika:** fotografije, planovi i svedočanstva smešteni u 3D tačno na koordinatu i konus kamere (*camera frustum*) odakle su snimljeni; prostor služi za ukrštanje dokaza. | Projekti su često krojeni za jedan sudski slučaj (fiksna naracija), manje za otvoreno pretraživanje 32.000 pominjanja. | **Frustum projekcija za 19 fotografija (W26–W30, W51–W64) i georeferencirane planove (R04/R05/R06)** — fotografija nije tapeta, već konus pogleda u 3D prostoru sa licencom. |
| **ORBIS & Itiner-e** | Stanford (W. Scheidel, E. Meeks) · UAB (P. de Soto et al. 2025) | D3 / WebGL / GeoJSON / PostGIS | Rimsko carstvo kao mreža odnosa, vremena putovanja i topologije raskrsnica (299.171 km puteva u Itiner-e), povezano preko Pleiades URI-ja. | 2D kartografski prikaz; ne spušta se u 3D arhitekturu palate (S3) i stratigrafiju sondi (S2). | **S0/S1 mrežni sloj:** direktno učitavanje `darmc-romulijana-okolina-15km.geojson` (W76) u isti 3D prostor sa lokalitetom (`2.531 m` do glavnog druma, raskrsnice A/B/C). |
| **Giro3D / `3d-tiles-renderer` + `three-mesh-bvh`** | Oslandia (OSGeo) / NASA AMMOS & G. Johnson | Three.js, WebGL2, OGC 3D Tiles, BVH stablo | Spajanje DEM terena, COG/XYZ ortofotoa, vektora i 3D modela u jedinstven CRS; `three-mesh-bvh` daje sub-milisekundni raycasting i preseke. | Pun Giro3D/CesiumJS uvodi stotine kilobajta npm zavisnosti koje krše Svemirov *zero-dependency* zakon za samostalne artefakte. | **Lokalni UTM/metrički koordinatni okvir centriran na Pleiades W66 (`43.899206N, 22.18575E`)** u čistom Three.js r186 iz `bin/vendor`, sa prostornim indeksiranjem čvorova. |
| **PixPlot & Cultural Analytics** | Yale DH Lab · L. Manovich (2015–2020) | Three.js, WebGL instanced quads, PCA/UMAP | Vizuelizacija hiljada dokumenata i slika po merljivim osama (godina, gustina, autor, tema) bez skrivanja podataka iza pretrage. | Nema fizičku geografiju i arhitektonsku razmeru. | **Prekidač „Geografija ↔ Epistemička konstelacija"**: isti čvorovi mogu se posmatrati na mapi lokaliteta ili složeni po gustini dokaza i fazama. |
| **Svemir: `city-of-the-atlas`, `or/svet`, `Medijana`** | Svemir (oktobar–novembar 2026) | Three.js r186 (`bin/vendor`), 0 npm deps, `atelje.js` | Dokazani P7+P4 jezik (tehnički crtež + game-grade kamera), `render-on-demand` (0 draw calls u mirovanju), A/B/C standard iz Medijane, deterministički izvoz iz baze. | `or/svet` je bio u ručnom WebGL 1 bez tonemapa/IBL-a; `city-of-the-atlas` nije imao stvarni GIS sloj rimskih puteva i arheološku stratigrafiju. | **Spajanje oba sveta:** Three.js r186 svetlosna i crtačka disciplina (`atelje.js`) + forenzička A/B/C šema Medijane + živi korpus Romulijane (79 izvora, 59 tvrdnji). |

---

## 3. Naučna literatura i teorijski temelj (Arheologija · Vizuelizacija · Umetnost koda)

### A. Virtuelna arheologija, paradata i vizuelizacija neizvesnosti
1. **Londonska povelja (The London Charter, Denard 2009/2012)** i **Seviljski principi (Principles of Seville, Lopez-Menchero & Grande 2011):** kompjuterska vizuelizacija u nasleđu je opravdana samo kada je *paradata* (dokumentacija procesa zaključivanja) pristupačna direktno iz vizuelnog prikaza, a istorijska verodostojnost eksplicitno gradirana.
2. **Emanuel Demetrescu (2015), *Archaeological stratigraphy as a formal language for virtual reconstruction. Theory and practice*, Journal of Archaeological Science 57, 42–55:** uvodi **Extended Matrix (EM)** — proširenje Harisove stratigrafske matrice na virtuelne jedinice (`USV/s` za strukturalne dopune čije su dimenzije zadate fizičkim ostacima, `USV/n` za dopune po tipološkoj analogiji). Svaka virtuelna jedinica mora biti grafovski povezana sa *Extractor* čvorom (izvor) i *Property* čvorom (koje svojstvo — oblik, visinu, materijal — taj izvor dokazuje).
3. **Fabrizio I. Apollonio, Marco Gaiani, Zheng Sun (2013/2021), *Characterization of Uncertainty and Approximation in Digital Reconstruction of CH* / *Critical Digital Model*:** uvode strogo vizuelno kodiranje gradijenta neizvesnosti kroz šejdere (od primarnog ostata, preko arhivskog crteža i istovremene analogije, do hipotetičke siluete) kako posmatrač nikada ne bi pomešao uverljivost osvetljenja sa naučnom istinom.
4. **Piotr Kuroczyński et al. (2016–2023), *Virtual Research Environment for Digital 3D Reconstructions*:** definiše 3D rekonstrukciju kao „prostornu naučnu publikaciju" u kojoj je 3D model ulazni indeks ka bibliografiji, izvorima i varijantama.
5. **Eyal Weizman (2017), *Forensic Architecture: Violence at the Threshold of Detectability*, Zone Books:** prostor nije pasivna pozadina već forenzički medijum; postavljanjem heterogenih fragmenata (planova, fotografija, tekstova) u zajednički 3D koordinatni sistem otkrivaju se kontradikcije i veze koje u odvojenim knjigama ostaju nevidljive.

### B. Teorija informacione vizuelizacije i digitalne humanistike
1. **Johanna Drucker (2011), *Humanities Approaches to Graphical Display*, DHQ 5(1); i *Graphesis: Visual Forms of Knowledge Production* (Harvard UP, 2014):** ključna teorijska prekretnica za naš atlas. Drucker razlikuje **Data** (*ono što je dato*, merenje bez sumnje) i **Capta** (*ono što je uhvaćeno/protumačeno*, gde postoje autorski ugao, fragmentarnost i spor). Standardni GIS i grafikoni nasilno pretvaraju *capta* u *data* (jedna tačka, jedan datum). Naš atlas uvodi **Capta geometriju**: kada se Srejović (R03), Čanak-Medić (R06), Petković (R04/W21) i Janković (R04) ne slažu oko faze ili namene, scena prikazuje **račvanje (superpoziciju dve poluprovidne varijante)** i citira oba autora.
2. **Edward Tufte (1990), *Envisioning Information*, Graphics Press:**
   - *Escaping Flatland:* 3D i višedimenzionalni prikaz postoje da povećaju gustinu informacije po jedinici pažnje, ne radi ukrasa.
   - *Micro / Macro Readings:* iz daljine se čita topologija celog utvrđenja i Magure (makro), a pri zumiranju iz samih zidova i stubova izranjaju pojedinačne tvrdnje, kote i nalazi (mikro) — „detalji se kumuliraju u veće koherentne strukture".
   - *Layering and Separation:* vizuelno razdvajanje slojeva kroz vrednost (value), debljinu linije i providnost tako da se teren, mreža puteva, izmereni zidovi i hipoteze nikada ne stope u vizuelnu buku.
   - *Small Multiples:* uporedni prikaz četiri hronološke faze (`F.PR`, `F.T`, `F.KA`, `F.SV`) jedne pored druge u kartici čvora, kako oko ne bi moralo da pamti prethodno stanje dok pomera klizač.
3. **Tamara Munzner (2014), *Visualization Analysis and Design*, CRC Press:** zakon efektivnosti vizuelnih kanala (*Marks & Channels*):
   - Najjači perceptivni kanal — **prostorna pozicija (X, Y, Z)** — rezervisan je isključivo za stvarnu geografiju i arhitektonsku visinu (nikada se izmerena zgrada ne deformiše po visini zbog broja citata!).
   - Kanal **materijalne punoće, opaciteta i vrste konture** rezervisan je za **epistemički nivo (A/B/C)**.
   - Kanal **zasićene boje (Hue)** čuva se za **jedan funkcionalni akcenat** (aktivna selekcija / sporna tačka / presečna ravan).
4. **Ben Shneiderman (1996), *The Eyes Have It: A Task by Data Type Taxonomy for Information Visualizations*, IEEE VL:** kanonska mantra naučnog instrumenta — **Overview first, zoom and filter, then details-on-demand**, dopunjena sa **Relate** (pokaži povezane čvorove i izvore u grafu), **History** (mogućnost povratka korak unazad) i **Extract** (izvoz tačnog citata i URL stanja `#cvor=L.P.1&faza=F.T`).
5. **Benjamin B. Bederson & James D. Hollan (1994), *Pad++: A Zooming Graphical Interface for Exploring Alternate Interface Physics*, ACM UIST:** **Semantički zum (*Semantic Zoom*)** — pri približavanju kamere objekat se ne samo uvećava piksel-po-piksel, već menja svoju semantičku reprezentaciju (na S0 je lokalitet tačka Pleiades 207395 u mreži provincije; na S1 je poligon utvrđenja + Magura + 8 puteva; na S2 je 27 prostornih celina; na S3 su zidovi, kule i preseci sa A/B/C slojevima; na S4 su pojedinačni fragmenti skulpture, mozaici i novac sa mestom nalaza).

### C. Teorija savremene, digitalne i kompjuterske umetnosti — Kodiranje kao umetnost
1. **Sol LeWitt (1967), *Paragraphs on Conceptual Art* → Casey Reas & Ben Fry (*Processing*, *Form+Code in Design, Art, and Architecture*, Princeton Architectural Press, 2010):**
   - LeWittov zakon: *„Ideja postaje mašina koja pravi umetnost."* U kompjuterskoj umetnosti (Reas *Software Structures*, 2004), umetničko delo nije statična slika niti ručno izmodelovan poligon u 3D programu, već **formalno pravilo (kod) koje iz ulaznog skupa podataka deterministički izvodi formu**.
   - Za Romulijanu: nijedan obris u atlasu ne sme nastati „slobodnom rukom" bez porekla. Kod (`alati/atlas-paket.js` + proceduralni generatori geometrije) je notarski ugovor koji čita `baza/izvori.json`, `baza/georef/*.json` i `baza/tvrdnje-*.jsonl` i izvodi 3D scenu.
2. **Stiny & Mitchell (1978), *The Palladian Grammar* + Wonka et al. (2003) / Müller et al. (2006), *CGA Shape Grammar for Architecture*:**
   - Jedini istorijski i matematički dokazan način da arhitektonska pravila (poput proporcijskih analiza M. Čanak-Medić u R06 za arkade, pilastre, kule i kupole Romulijane) postanu pošten kod.
   - Pravilo u našem atlasu: osnovni tlocrt (Nivo A, iz georeferenciranog plana) $\xrightarrow{\text{extrude}(h_A)}$ sačuvana masa zida $\xrightarrow{\text{split/proporcija}(\text{R06})}$ gornja zona rekonstrukcije (Nivo B) $\xrightarrow{\text{roof/vault}(\text{hipoteza})}$ krovna/svodna konstrukcija (Nivo C).
   - Svaka generisana forma mora proći **tri testa autoriteta**: (1) *Test rekonstrukcije* (iz izgleda mase odmah se čita šta je A, šta B, šta C), (2) *Test lanca pravila* (svaki parametar visine nosi ID tvrdnje ili strane u R06/R04), (3) *Test disonance* (čvor sa 16 tvrdnji i planom i čvor bez ijedne tvrdnje ne mogu izgledati isto).
3. **Vera Molnár (*Machine imaginaire*, *1% désordre*, 1968–2023), Manfred Mohr, Georg Nees, Frieder Nake (Stuttgart škola generativne estetike):**
   - Rani kompjuterski ploteri dokazali su da vrhunska digitalna elegancija leži u **asketskoj disciplini linije, ritmu mreže i kontrolisanom odstupanju (*1% disorder*)**.
   - Na Romulijani ta lekcija ima direktno arheološko značenje: naspram ortogonalne rešetke bedema, odstupanje ose Velikog hrama, zarotirana osa Palate I i preklapanje Starijeg (`L.U.1`) i Mlađeg utvrđenja (`L.U.2`) jesu upravo taj „1% poremećaja" u kome se čita hronologija gradnje! Zato naš atlas crta **osovinske linije (ISO 128 crta-tačka-crta)** i uglove odstupanja direktno na tlu.
4. **Giovanni Battista Piranesi (*Il Campo Marzio dell'Antica Roma*, 1762; *Carceri*) & Peter Eisenman (*Piranesi Variations*, Venecija 2012):**
   - Piranesijev *Campo Marzio* je nulti predak arheološkog atlasa kao umetničkog dela: spoj **hiper-precizne tehničke gravire kamena u planu, merne skale, indeksnih brojeva urezanih u crtež i dramatične dubine senke**. Način crtanja (linija, šrafura, presek, kotiranje) nosi autoritet jednak samom kamenu.
5. **MoMA „Full Disclosure: The Edge of Information Design" (2026–2027, Paola Antonelli) & Studio kanon (Sable / Shedworks, Monument Valley / ustwo, INSIDE / Playdead, Journey / Matt Nava):**
   - Ono što vrhunska muzejska i digitalna scena u 2026. priznaje kao najviši domet nije fotorealistični kič, već **informacioni dizajn sa potpunim poreklom pretvoren u prostorno iskustvo sa autorskim svetlom**.

---

## 4. Grafika i operacije grafikom (Matematički i WebGL/GLSL mehanizam)

Svaka vizuelna operacija u atlasu ima tačnu matematičku i grafičku svrhu i izvodi se nad `THREE.WebGLRenderer` (three.js r186 iz `bin/vendor/three-0.186.1`), bez teškog post-procesing lanca koji bi oborio mobilni GPU:

### Operacija 1 · Lokalna metrička projekcija i georeferencijalna transformacija ($\text{WGS84} \leftrightarrow \text{Lokalni metri}$)
Da bi WebGL izbegao gubitak preciznosti 32-bitnog `float`-a na velikim UTM koordinatama (*jitter* pri bliskom zumu S3/S4), koordinatni početak $(0,0,0)$ scene vezuje se za kanonsku tačku lokaliteta (Pleiades 207395 / W66: $\varphi_0 = 43.899206^\circ\text{ N}$, $\lambda_0 = 22.185750^\circ\text{ E}$):
$$x = (\lambda - \lambda_0)\cdot 111320 \cos\varphi_0, \qquad z = -(\varphi - \varphi_0)\cdot 111320, \qquad y = h - h_0$$
Georeferencirani arhitektonski planovi (`R04`, `R05`, `R06`) preslikavaju se iz piksela slike $(u,v)$ u lokalne metre $(x,z)$ Helmertovom ili afinom transformacijom:
$$\begin{bmatrix} x \\ z \end{bmatrix} = \begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} u \\ v \end{bmatrix} + \begin{bmatrix} t_x \\ t_z \end{bmatrix}, \qquad \text{RMS} = \sqrt{\frac{1}{N}\sum_{i=1}^{N} \|\mathbf{p}_i^{\text{model}} - \mathbf{p}_i^{\text{GCP}}\|^2} \le 2.0\text{ m}$$
Vektori greške $\mathbf{e}_i = \mathbf{p}_i^{\text{model}} - \mathbf{p}_i^{\text{GCP}}$ iscrtavaju se u sloju kontrole georeferencije kao vidljivi naučni dokaz tačnosti.

### Operacija 2 · Trijade epistemičkih materijala i ISO 128-24 crtačka dubina (Saito & Takahashi 1990)
Umesto fotorealističnih tekstura cigle i mermera koje lažu o stepenu očuvanosti, geometrija prolazi kroz **trostepeni grafički operator sigurnosti**:

| Epistemički nivo | Površinski šejder / Materijal (Albedo sRGB 50–240) | Geometrijska kontura (`EdgesGeometry` $\theta = 25^\circ$, ISO 128-24) | Značenje bez legende |
|---|---|---|---|
| **Nivo A · Činjenica (*In situ* / `US`)** | Neprovidna mineralna masa ($\alpha = 1.0$), topli krečnjak/peščar (`#d8ccb8` dan / `#8c8270` noć), pečeni vertikalni AO gradijent u vertex bojama + Fresnel rim $(\,1 - \max(\mathbf{N}\cdot\mathbf{V}, 0)\,)^3$ | **Puna široka linija** (`continuous wide`, `1.5 px`, tamni grafit `#1c1915` / svetli pergament u noćnom režimu) | „Ovo fizički stoji na terenu ili je izmereno u sondi." |
| **Nivo B · Izvedeno / Analogija (`USV/s`, `USV/n`)** | Poluprovidni arhitektonski volumen ($\alpha = 0.48$, `#dfd7c8`) sa **proceduralnim tonom šrafure (*tone-stipple*)** u fragmentu: $\text{mask} = \text{step}(\tau, \text{hash}(\lfloor \mathbf{p}_{xz}\cdot f \rfloor)\cdot (\mathbf{N}\cdot\mathbf{L}))$ | **Puna tanka linija** (`continuous thin`, `1.0 px`, `#5a5246`) | „Rekonstruisano iz pronađenih fragmenata i proporcija (R06 Čanak-Medić)." |
| **Nivo C · Hipoteza (`USV/h`)** | Ultraprozračna ovojnica ($\alpha = 0.14$) ili čisto žičano telo bez ispune (`depthWrite: false`) | **Isprekidana linija** (`dashed thin`, `LineDashedMaterial`, crta $1.2\text{ m}$, razmak $0.6\text{ m}$, oker-bakar `#b86b35`) | „Naučna pretpostavka — volumen još nije direktno potvrđen." |
| **Capta · Sporna varijanta (Dva autora)** | Dva preklopljena poluprovidna volumena sa faznim pomakom šrafure ($+45^\circ$ vs $-45^\circ$) i prekidačem `Autor 1 / Autor 2 / Preklop` | Dvobojna tanka kontura (`#2e6f73` vs `#b85d35`) | „Literatura se ne slaže (npr. bazilika VI vek vs X–XI vek)." |
| **Praznina (`P-TVRDNJE` / `P-GEOMETRIJA`)** | Niski urezani sokl u tlu ($h = 0.25\text{ m}$, $\alpha = 0.22$) sa otvorenom gornjom osnovom | **Tačkasto-crtkana osna linija** (`long-dash dotted`, `#8a7f70`) | „Čvor postoji u hijerarhiji i pominjanjima, ali čeka upis tvrdnje/obrisa." |

### Operacija 3 · Živa ravan analitičkog preseka (*Section / Clipping Plane* $\Pi$)
Za čitanje stratigrafije (slojevi `RS-001` u R02, odnos Starijeg i Mlađeg bedema, dve crkve u Palati I) i arhitektonskih sklopova, renderer uključuje `renderer.localClippingEnabled = true` sa analitičkom ravni:
$$\Pi(\mathbf{x}) = \mathbf{n} \cdot \mathbf{x} + d \ge 0$$
Pomeranjem klizača preseka (po osi Istok–Zapad ka Maguri, Sever–Jug kroz palate ili po visini $y$ za stratigrafsko ljuštenje), sve 3D mase se seku u realnom vremenu, otkrivajući unutrašnje odnose faza.

### Operacija 4 · *Raking Light* (Koso analitičko osvetljenje) i nebeski luk
Glavno direkciono svetlo $\mathbf{L}(\alpha, \theta)$ ima dve uloge:
1. **Makro-režim (S1–S3):** simulira stvarnu putanju sunca nad Timočkom kotlinom i vizurom od istočne kapije utvrđenja ka svetom brdu Magura ($\text{azimut} \approx 78^\circ\text{ ENE}$).
2. **Mikro-režim (S3–S4, *Raking Light* iz 3DHOP metodologije):** spuštanjem elevacije svetla na $\theta \in [5^\circ, 20^\circ]$ pod kosim uglom, plitka plastika (reljefi arhivolte R05, pilastri sa tordiranim kanelurama, kapiteli, mozaici) dobija maksimalan lokalni kontrast $(\mathbf{N}\cdot\mathbf{L})$ za čitanje urezanih detalja.

### Operacija 5 · *Camera Frustum* projekcija građe (Forensic Image Complex)
Svaka od 19 registrovanih fotografija sa Commonsa (`W26–W30`, `W51–W64`) i 10 renderovanih planova (`R04`, `R05`, `R06`) tretira se kao **prostorni svedok**:
- Planovi leže u ravni tla $y = 0.05\text{ m}$ (sa klizačem providnosti $0\text{–}100\%$ za direktnu vizuelnu proveru kako 3D zid naleže na nacrtani plan autora!).
- Fotografije dobijaju svoj 3D konus pogleda (*piramidu kamere*) na poziciji i azimutu snimanja; klikom na konus kamera atlasa ulazi u tačan kadar fotografije radi poređenja današnjeg stanja *in situ* (Nivo A) sa 3D rekonstrukcijom (Nivo B/C).

### Operacija 6 · 3D lukovi epistemičke konstelacije (`graf.json` → kubni Bezier)
Kada istraživač izabere bilo koji prostorni čvor (npr. `L.P.1` ili `L.MG.M1`), instrument iz `graf.json` (603 veze) u 3D prostoru iscrtava **tanke parabolične lukove** $\mathbf{B}(t) = (1-t)^2 \mathbf{p}_0 + 2(1-t)t\,\mathbf{p}_m + t^2 \mathbf{p}_1$ (gde je $\mathbf{p}_m = \frac{\mathbf{p}_0+\mathbf{p}_1}{2} + (0, h_{\text{arc}}, 0)$) ka svim prostornim čvorovima koji dele istu tvrdnju, istu fazu ili isti komparativni odnos (`veze` u registru tvrdnji).

---

## 5. Immersion, Flow i koreografija interakcije

Imerzija u naučnom instrumentu ne nastaje od lažne vatrice i „filmske" magle, već iz **Slaterove iluzije verodostojnosti (*Plausibility Illusion*, Slater 2009)** — osećaja da **prostor trenutno, zakonito i istinito odgovara na svaku istraživačevu misao**, i **Csikszentmihalyijevog toka (*Flow*, 1990)** — odsustva kognitivnog trenja između prostornog pitanja i dokaza.

1. **Jedinstvena petlja kamere sa eksponencijalnim prigušenjem (*Frame-Rate Independent Damping*):**
   $$\mathbf{x}_{t+\Delta t} = \mathbf{x}_t + (\mathbf{x}_{\text{target}} - \mathbf{x}_t)\cdot \left(1 - e^{-k \Delta t}\right), \qquad k = 8.5\text{ s}^{-1}$$
   Kamera nikada ne skače sirovo i nikada ne visi u beskonačnoj petlji: kada se $\lVert\mathbf{x}_{\text{target}} - \mathbf{x}_t\rVert < \varepsilon$, render petlja se **potpuno zaustavlja (`0 draw calls u mirovanju`)**.
2. **Koreografija prelaza razmera (`flyTo`, M3 Easing kanon):**
   - Dolazak na čvor: `Emphasized Decelerate` `cubic-bezier(0.05, 0.7, 0.1, 1)` u trajanju od $750\text{ ms}$ (brz polazak, meko prizemljenje u fokus).
   - Povratak na pregled: `Standard Accelerate` $400\text{ ms}$.
   - `prefers-reduced-motion: reduce`: svi preleti kamere automatski prelaze u trenutni postav kadra ($0\text{ ms}$ vection-rizika, WCAG 2.3.3).
3. **Focus + Context (nikada modal preko scene):**
   - Izbor objekta u 3D sceni **nikada** ne otvara prozor preko sredine ekrana koji bi sakrio sam objekat. Kamera pomera centar orbite tako da izabrani čvor stoji u slobodnih $70\%$ scene, dok se forenzički dosije (tvrdnje, citati, faze, izvori, SHA-256) otvara u desnom stupcu (desktop) ili donjoj fioci (telefon).
4. **Dvosmerna sinhronizacija (`3D Canvas ↔ DOM Indeks ↔ URL Hash`):**
   - Svaki klik u 3D sceni, klik u tabeli čvorova, filter faze (`F.PR`–`F.SV`), filter sigurnosti (`A/B/C`) ili pretraga pominjanja menja isto centralno stanje `STATE` i upisuje javni, deljivi hash (`#razmera=S3&cvor=L.P.1&faza=F.T&nivo=sve`), tako da se svako naučno zapažanje može poslati kao direktni link.
5. **Zvuk prostora (0 KB Web Audio sinteza, BotW / TotK kanon):**
   - Nula spoljnih audio fajlova. Tek posle prvog korisničkog gesta (i uz uvek vidljivo dugme `Zvuk: Isklj / Uklj`), Web Audio API sintetiše tihi parametarski vetar Timočke kotline i Magure (beli šum kroz `BiquadFilterNode` lowpass čija frekvencija $f_c \in [280, 850]\text{ Hz}$ zavisi od nadmorske visine kamere S0→S3 — „vazduh jede visoke frekvencije na daljini") i 4 suva mikro-tona ($35\text{ ms}$, $1.2\text{–}2.4\text{ kHz}$) za promenu razmere, presek, promenu faze i otvaranje dokaza.

---

## 6. Mobile & Desktop optimizacija (Inženjerski budžet i prilagodljivost)

Na osnovu merenja u `tehnika-2026.md` (srednji mobilni GPU Adreno 810 pada na $8,5\text{ fps}$ na 4K zbog fragment-bound propusnosti) i lekcija iz `spatial-atlas.md` (gde su fiksne labele na 390 px prekrivale geometriju), arhitektura primenjuje sledeće zakone:

| Parametar | Desktop (`≥ 960 px`, testirano na `1400×950`) | Mobilni (`< 960 px`, testirano na `390×844` i `320 px`) | Inženjersko opravdanje |
|---|---|---|---|
| **Raspored ekrana (Layout)** | **Split-Stage:** leva/centralna pozornica ($68\%$ širine) je 3D instrument sa gornjom trakom osa (S0–S4, F.*, A/B/C, Presek, Svetlo); desni stubac ($32\%$, `420 px`) je stalni forenzički dosije, pretraga i graf veza. | **Stage + Bottom-Sheet:** gornjih $54\%$ ekrana je čist 3D viewport sa kompaktnom trakom razmera; donjih $46\%$ je skrolabilni forenzički dosije i indeks čvorova (normalno skrolovanje dokumenta prvo, bez zarobljavanja prsta u canvasu). | Rešava grešku sa 390 px gde lebdeći HUD odseca kontrole i zaklanja 3D svet (`atelje-2026-10-28.md`). |
| **Device Pixel Ratio (DPR)** | `Math.min(window.devicePixelRatio, 1.5)` | `Math.min(window.devicePixelRatio, 1.5)` | Čuva $2.25\times$ manje fragmenata od DPR 2.25/3.0 bez vidljivog gubitka oštrine uz MSAA. |
| **Render petlja** | **Render-on-Demand** (`requestRender()` samo na promenu kamere, klizača, selekcije ili resize-a). | **Render-on-Demand** + gašenje rendera kada je tab skriven (`visibilitychange`) ili canvas van ekrana (`IntersectionObserver`). | **0 draw call-ova u mirovanju** = nula grejanja telefona i nula potrošnje baterije dok istraživač čita tvrdnju u dosijeu. |
| **Labele u 3D prostoru** | Do 18 prioritetnih DOM/projekcionih oznaka sa proverom kolizije u 2D ekranu (`greedy bbox culling`) i skaliranjem po distanci. | **Strogo najviše 7 oznaka istovremeno** (izabrani čvor + primarni orijentiri trenutne razmere); svi ostali čvorovi su dostupni dodirom na masu ili iz liste ispod. | Sprečava vizuelno zagušenje na 390 px. |
| **Touch & Keyboard ergonomija** | Miš (orbit/pan/zoom) + tastaturne prečice (`1–5` za S0–S4, `F` za fazu, `X` za presek, `R` za reset, `T` za turu, `Esc` za pregled) + `tabindex="0"` na canvasu. | Dodirni ciljevi $\ge 44\times 44\text{ px}$ (ili kompaktne pilule sa sigurnim razmakom), `viewport-fit=cover` + `env(safe-area-inset-*)` na svim ivicama, `touch-action: none` samo na canvasu. | Puna pristupačnost (WCAG 2.1.1, 1.4.3 kontrast $\ge 4.5:1$, 1.4.11 grafika $\ge 3:1$). |
| **Payload i zavisnosti** | **0 npm paketa u runtime-u**; `three.module.js` iz lokalnog `bin/vendor/three-0.186.1`; izvedeni podaci `atlas-podaci.js` $\approx 120\text{ KB}$ (nekompresovano). | Isti paket; ceo inicijalni podatkovni sloj $< 150\text{ KB}$, učitavanje i prvi render $< 1\text{ s}$ lokalno. | Radi potpuno oflajn, bez CDN-a i bez mrežnog rizika. |

---

## 7. Arhitektura cevovoda (Od `baza/` do piksela — nula ručnog crtanja)

```text
baza/izvori.json (79) ────────┐
baza/hijerarhija.json (66) ───┼─► alati/atlas-inventar.js ─► baza/atlas-katalog.json
baza/tvrdnje-*.jsonl (59) ────┤                              atlas/graf.json (207 čv / 603 veze)
baza/objekti.json (3) ────────┤                              atlas/KATALOG.md
baza/pominjanja.jsonl (32041) ┘
                                             │
izvori/internet/mape/                        ▼
darmc-romulijana-okolina-15km.geojson ─► alati/atlas-paket.js ─► atlas/atlas-podaci.js (deterministički paket)
                                                                 atlas/atlas-podaci.json
                                             │
                                             ▼
                                   atlas/index.html (Three.js r186 · P7+P4 instrument)
                                             │
                                             ▼
                     tools/atelje.js snimi ─► atlas/dokazi/atelje/instrument-v1/ (1400/390, dan/noć/mirno)
```

### Šta je u prototipu `atlas/index.html` izmerena geografija, a šta aksiomatska skulptura znanja
Po zakonu iz `spatial-atlas.md` (*Representation contract*), interfejs nikada ne laže o prirodi geometrije:
1. **Stvarno izmerena geografska geometrija (WGS84 → lokalni metri oko W66):**
   - Tačna lokacija Romulijane (`43.899206° N, 22.18575° E`, Pleiades 207395 / W66),
   - Svih **8 rimskih trasa puteva iz DARMC W76** (`234.841 m` mreže u krugu od 15 km, najbliža tačka na `2.531 m` severoistočno, raskrsnice A, B i C iz `PUTEVI.md`),
   - Stvarne granice **Sentinel-2 ortofoto podloge W45** i **OSM pločica W36, W48, W50** (sa iscrtanom linijom upozorenja na $146\text{ m}$ južno od centra lokaliteta gde se pločice završavaju).
2. **Aksiomatska topološka rekonstrukcija i skulptura znanja za 27 `L.*` čvorova (dok se u fazi A0 ne georeferencira 10 planova iz `R04/R05/R06`):**
   - Svaki od 27 prostornih čvorova (`L.U.1`, `L.U.2`, `L.P.1`, `L.P.2`, `L.H.V`, `L.H.M`, `L.T`, `L.TP`, `L.MG.M1`, `L.MG.M2`, `L.MG.T1`, `L.MG.T2`...) postavljen je na svoje kanonsko topološko mesto (kasnoantičko utvrđenje u dolini, Tetrapilon i raskrsnica na prilazu, sakralni kompleks Magura na grebenu $\sim 1\text{ km}$ istočno duž ose istočne kapije) i generisan **CGA-lite gramatikom arhitektonskog tipa** (kula, kurtina bedema, kapija, peristil, hram sa podijumom, bazilika sa apsidom, tetrapilon, mauzolej, tumul).
   - Svaki čvor nosi izričitu oznaku `GEOMETRIJA: AKSIOMATSKA TOPOLOGIJA (čeka A0 georef plana)` u svom forenzičkom pasošu, dok mu visinski slojevi (A/B/C), faze (`F.PR`–`F.SV`), tvrdnje (59) i pominjanja (32.041) dolaze 100% iz stvarne baze projekta.

---

## 8. Primarni izvori i literatura korišćena u ovom dokumentu

1. **Demetrescu, E.** (2015). *Archaeological stratigraphy as a formal language for virtual reconstruction. Theory and practice*. Journal of Archaeological Science, 57, 42–55. (`https://doi.org/10.1016/j.jas.2015.02.004`, `https://www.extendedmatrix.org`)
2. **Fanini, B., Ferdani, D., Demetrescu, E., Berto, S., & d'Annibale, E.** (2021). *ATON: An Open-Source Framework for Creating Immersive, Collaborative and Liquid Web-Apps for Cultural Heritage*. Applied Sciences, 11(22), 11062. (`https://doi.org/10.3390/app112211062`)
3. **Callieri, M., Potenziani, M., Dellepiane, M., Cignoni, P., & Scopigno, R.** (2015). *3DHOP: 3D Heritage Online Presenter*. Computers & Graphics, 52, 129–141. (`https://3dhop.net`)
4. **Smithsonian Digitization Program Office** (2018–2026). *Smithsonian Voyager: 3D Explorer and Authoring Tool*. (`https://smithsonian.github.io/dpo-voyager/`)
5. **Apollonio, F. I., Gaiani, M., & Sun, Z.** (2013/2021). *Characterization of Uncertainty and Approximation in Digital Reconstruction of Cultural Heritage* / *A Critical Digital Model for Architectural Heritage*. (`https://doi.org/10.3390/app112411906`)
6. **Denard, H.** (2009/2012). *The London Charter for the Computer-Based Visualisation of Cultural Heritage*. King's College London. (`https://www.londoncharter.org`)
7. **Lopez-Menchero, V. M., & Grande, A.** (2011). *The Principles of the Seville Charter*. CIPA Symposium. (`http://sevilleprinciples.com`)
8. **Drucker, J.** (2011). *Humanities Approaches to Graphical Display*. Digital Humanities Quarterly, 5(1); i *Graphesis: Visual Forms of Knowledge Production* (2014), Harvard University Press.
9. **Tufte, E. R.** (1990). *Envisioning Information*. Graphics Press.
10. **Munzner, T.** (2014). *Visualization Analysis and Design*. A K Peters / CRC Press.
11. **Shneiderman, B.** (1996). *The Eyes Have It: A Task by Data Type Taxonomy for Information Visualizations*. Proceedings of IEEE Symposium on Visual Languages, 336–343.
12. **Bederson, B. B., & Hollan, J. D.** (1994). *Pad++: A Zooming Graphical Interface for Exploring Alternate Interface Physics*. ACM UIST '94, 17–26.
13. **Saito, T., & Takahashi, T.** (1990). *Comprehensible Rendering of 3-D Shapes*. ACM SIGGRAPH Computer Graphics, 24(4), 197–206.
14. **Stiny, G., & Mitchell, W. J.** (1978). *The Palladian Grammar*. Environment and Planning B, 5(1), 5–18.
15. **Wonka, P., Wimmer, M., Sillion, F., & Ribarsky, W.** (2003). *Instant Architecture*. ACM Transactions on Graphics (SIGGRAPH), 22(3), 669–677; **Müller, P. et al.** (2006). *Procedural Modeling of Buildings*. ACM TOG 25(3), 614–623.
16. **Reas, C., & Fry, B.** (2010). *Form+Code in Design, Art, and Architecture*. Princeton Architectural Press.
17. **Weizman, E.** (2017). *Forensic Architecture: Violence at the Threshold of Detectability*. Zone Books / MIT Press.
18. **Slater, M.** (2009). *Place Illusion and Plausibility Can Lead to Realistic Behaviour in Immersive Virtual Environments*. Phil. Trans. R. Soc. B, 364(1535), 3549–3557.
19. **Csikszentmihalyi, M.** (1990). *Flow: The Psychology of Optimal Experience*. Harper & Row.
20. **Keren, I.** (2015). *Scroll Back: The Theory and Practice of Cameras in Side-Scrollers*. GDC 2015.
21. **de Soto, P. et al.** (2025). *Itiner-e: A high-resolution dataset of roads of the Roman Empire*. Nature Scientific Data (`https://doi.org/10.1038/s41597-025-06140-z`).
22. **Korpus Romulijana u bazi Svemira:** Čanak-Medić (1978, R06), Srejović (1983/1985, R02/R03), Srejović & Vasić (1994), Popović (2010, R04), Živić (2003/2010, R05/R08), Petković (W09/W21), Starinar 45–46 i 48 (W13/W14), DARMC (W69/W76), Pleiades 207395 (W66).
