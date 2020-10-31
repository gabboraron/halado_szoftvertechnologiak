# Haladó szoftvertechnologiák
## EA1
> modell: egy absztrakció, kiemeli a fontos informáiókat, grafikus reprezentáció, formális megfogalmazás
> szoftver életciklus modellek:
> - munkafolyam modell
> - adatfolyam/tevékenyésg modell
> - szerepkör/cselekvés modell

### Royce féle vízesés modell
- követelmények meghatározása
- rendszer és szoftvertervezés: hogyan megvalósítható a feladat
- implementáció és egységteszt: 
- integráció és rendszerteszt
- működtetés és karbantartás
> hátrány: valós projektek ritkán követnek szekvenciális modelleket, nehezen megvalósítható az integráció, a specifikációtól függ az egész modell, nem kezelt a kezdeti bizonytalanság, késő eredmény

### V modell
1991-ben bevezett kötelezően használandó modell a német hadseregnél
- szigorú dokumentálás, jól ütemezhetőség
- a fejlesztés során, már a tervektől kezdve tesztel, mert a fejlesztés közben a legkönnyebben meghatározható, hogy mivel tesztelhető könnyen
> - módszertan szint
> - metódusok szintje
> - eszközök szintje
alrendszerek:
- projektmenedzsment
-rendszermegvalósítás
- minőségbiztosítás
- konfiguráció menedzsment

### evolúciós fejlesztés modellje:
- vázlat leírása
  - specifikáció 
    - kezdeti verzió
  - fejlesztés
    - közbenső verziók
  - validálás
    - végső verzió

prototípus készítése    
 - termék prototípus: a drótváz, vázlat, körülbelül modell
 - rész prototípus: konkrét algoritmus implementálások
 - interfész prototípus: U.I.
 > hátrány: nehezen menedzselhető folyamat, minőségbiztosítási problémák, nem megfelelő rendszer struktúrák, speciális eszközk és technikák ígénye
 
 ### formális rendszerfejlesztés fázisai
 - követelméynek meghatározása
   - formális specifikáció
     - formális transzformáció
       - integráció és rendszerteszt
=> futtatható program

### Újrafehasználás
- következmények specifikációja
  - komponens elemzés
    - követelmény módosítás
      - rendszertervezés újrafelhasználással
        - fejlesztés és integráció
          - rendszer variáció

### inkrementális fejlesztés
- változatos követelmények meghatározása
  - követleményke inkremensekhez rendelése
    - rendszer architektúrájának megtervezése
      - rendszerinkremens fejlesztése
        - inkremens validálása
          - inkremens integrálása (release)
            - rendszer validálása
              - végleges rendszer
### RAD modell
- nagy projekt esetén nagy a humán erőforrás ígény => nagy projekteken me használható a RAD
### Boehm spiráll modell
![spiralmodell vázlat](https://upload.wikimedia.org/wikipedia/commons/8/8c/Spiralmodell.jpeg)

bővebben: https://hu.wikipedia.org/wiki/Spir%C3%A1lmodell
nagy projektekre van optimalizálva
1. Célok kijelölése
2. Kockázatelmezés
3. Fejlesztés és validálás
4. tervezés
- minden egyes körbefordulása a spirálnak egy-egy fázisa a spirálnak
- tetszőleges számú iteráció
- tartalmazza a kockázat-kezelést is
- integrálhat más modelleket is

## EA3
### Környezeti modellek
- elemzés korai szakaszában fontosak
- meghatározzák mi tartozik a rendszerhez, amit  kezelni kell és ami nem tartozik hozzá
- célja, hogy egy általános képet mutasson a rendszerről

### Üzleti foyamatok modellezése
- megrendelp aktív bevonása a részletekbe
- BPMI - Business Process Managemant Initiative => OMG(*az UML fejlesztői*)-vel közösen Business Process Modell and Notation
![BPM poszter](https://i.pinimg.com/originals/0a/dd/1f/0add1f3c2c8f978f42a1f3fe92743745.png) 
fájl: [bpmn_nyomt.pdf](https://github.com/gabboraron/halado_szoftvertechnologiak/blob/main/bpmn_nyomt.pdf), online: http://users.nik.uni-obuda.hu/szollosi/virmod/docs/bpmn_nyomt.pdf

taxi rendelés: https://www.conceptdraw.com/examples/taxi-booking-process
![taxi bpmn](https://conceptdraw.com/a324c3/p1/preview/640/pict--business-process-modeling-cab-booking-public-process-collaboration-bpmn-2.0-diagram)

### P-gráf
bővebben: http://acta.uni-obuda.hu//Tick_9.pdf
- irányított páros gráf => csúcsai két diszjunkt halmazba sorolhatóak, és azonos csúcstípusok között nem vezet él
  - (M,O),P gráf
- process gráf
- gráf csúcsai:
  - műveletvégző egységek (`O`)
  - anyagok (`M`):
    - nyersanyag: folyamat bemeneti elemei
    - termék-anyag: folyamat eredményei
    - köztes anyag: feldolgozási fázisok alatt keletkezik, használódik fel
    - melléktermék anyag: folyamat célja szempontjából nem kívánatosnak számít
  - termékek (`P`)
- egy `O` típusú csúcsból <=>vezethet él egy `M` típusú csúcsba, ha `M` z `O` kimeneti halmazának eleme, vagyis *`O`előállít `M` anyagot*
  - `M` típusú csúcsból <=> vezethet él `O` műveleti egység típusú csúcsba, ha `M` az `O` bemeneti halmazának eleme, vagyis *`O` feldolgozza `M`-et*
  
  ![p rgáf példa](https://github.com/gabboraron/halado_szoftvertechnologiak/blob/main/Screenshot_2020-10-07%20Microsoft%20Word%20-%20Tick_9%20doc%20-%20Tick_9%20pdf.png)
**Matematikailag:** 
Adott: 
- `M` véges halmaza (`P` és `R` részhalmaza `M`-nek)
- `O` műveleti egységek halmaza
ekkor `M` és `O` diszjunkt

## EA 5
### Petri hálók
bővebben: https://hu.wikipedia.org/wiki/Petri-h%C3%A1l%C3%B3 és https://docplayer.hu/12406731-Petri-halok-alapfogalmak-kiterjesztesek.html valamint https://inf.mit.bme.hu/sites/default/files/materials/category/kateg%C3%B3ria/oktat%C3%A1s/msc-t%C3%A1rgyak/form%C3%A1lis-m%C3%B3dszerek/11/PN_alapfogalmak_kiterjesztesek.pdf esetleg http://david.bedok.hu/file/20120428_BedokDavid_Petri_halok_szimja_es_alkuk_oo_korben_v044_OENIK.pdf
és https://people.inf.elte.hu/fekete/algoritmusok_msc/workflow/hallgatoi_esszek/Balogh_Bernadett_Workflow.pdf

Elemei:
- helyek
- átmenetek
- csúcsok véges halmazai:{P,T}
  - `P`- helyek: tárolják a tokeneket
  - `T` - átmenetek: valamilyen akció
  - csak az egymástól különböző típusúak köthetőek össze, pl `P`-`P` **nem**, de `P`-`T` **igen**
- élek irányítottak, két féle él lehetséges: `P -> T`  és `T -> P`
=> irányított páros gráf

![petri háló alapjai](https://docplayer.hu/docs-images/41/12406731/images/page_6.jpg)

**A petri háló álapotai:**
> minden hely (`P`)  tartalmazhat tokeneket, *pontokat a körön belül*, ami a hely erősségét, állapotát jelzi. A háló állapotát a helyek számának összessége a tokenek számához viszonyítva, azaz a tokenek eloszlása jelzi.

**Működése:**
> - állapotváltozás sorozata
> - az átmenetek aszinkron működnek, ha minden feltétel adott akkor azonnal létrejön, megtörténik az átmenet, azaz *tüzel*, ekkor egyértleműen a bemeneti helyek számának tokenjei az ígény mennyiségével lecsökkennek. Így ááll elő az új állapot.
>
> ![Petri háló folyamat közben](https://www.azimuthproject.org/azimuth/files/chemistryNetDot1A.png)
> 
> **Állapotvektor:** a teljes rendszert magába foglalja, és akkor `+1` a csúcs értéke, ha van benne  `1` token, egyébként, ha üres akkor `0`.

**élsúlyok bevezetése:**
> az aktivitás költségével megegyező költségszámot írhatunk az élekre, ami a `tüzelés` közben jelzi, hogy az `aktivitásnak` mennyi lesz a költsége.
>
> Így a petri háló képlete: `PN(P,T,E,W,M0)`

**Modellezés [Snoopy](https://www-dssz.informatik.tu-cottbus.de/DSSZ/Software/Snoopy#downloads) programmal:**
1. `File` -> ` `New` -> `Petri Net`
2. `Elements` -> `Place` - helyeket ad hozzá kattintásra
3. `Elements` -> `Transition` - átmenetet ad hozzá kattintásra
4. `Elements` -> `Arc` - összeköttetést ad hozzá kattintásra a *ból* irányt adjuk meg, majd húzzuk az egeret a *cél* irány felé.
5. `View` -> `Start anim` - animáció megadása és elindítása. `Options` menüben érdems a `Steppoing`-et maximumra állítani.
fájl:[jelzőlámpa modellezés Snoopy programban](https://github.com/gabboraron/halado_szoftvertechnologiak/blob/main/jelzolampa_modell_petri_haloval.pn)

### Szerkezeti és működési modellek
**Szerkezeti modellek:**

> Somerville könyv, 2. kiadás 14. fejezet
> 
> Rendszereket vagy azok részeinek szerkezetét írja le. 

**Működési modellek:**
 
 pl: https://www.1000sourcecodes.com/2012/05/software-engineering-transform-mapping.html
 
> A rendszer működését/viselkedését írja le. gymásba ágyazható modellek.
> 
> Jellemzői:
> - DFD (*Data Flow Diagram*) az adatok, adatfolyam áramlását írja le. Meghatározza, hogy a külvilágból a rendszernek mivel kell kapcsolatot tartania.
> - az összes lehetséges infomrációáramlást tartalmazza
> - **nem tartalmazza az információ áramlásának sorrendiségét!**
> - finomításnál a *buborékokat* felvágjuk és 5-7 elmere bontjuk

Részei:
- Külső egyed: információ forrás
- folyamat: teljesen általános folyamat, bármi lehet
- adat elem vagy azok gyűjtő fogalma: infomráció áramlásan iránya
- adat tároló: itt sincs mgekötés, bármi lehet, *olyan fomrában adja vissza az adatot ahogy eltároltuk*, 0-ás szinten ilyne nincs, csak 1-es szinten

![DFD model example](https://www.freeprojectz.com/sites/default/files/Student%20Management%20System%20DFD%20First%20Level.jpeg)

**Kétféle leírással kiegészíthetjük**:
- **DD**: data dictionary, adatszótár, egy pontosítása annak, hogy mit értün az adaton, részletekig bemenőleg
- **PSPEC**: process specification, (a folyamat szöveges megfogalmazása lehet, vagy strukturált angollal is megfogalmazhatjuk) algoritmusokat, megszorításokat, és részleteket tartalmaz, a már nem tovább bontható elemi folyamatok leírása, hogy milyen algoritmus, vagy megszorítás alapján működik.

példa, központi elemmmel, egyszerű betörés riasztó rendszer:

![két bemenet és három kimenetű példa ddfd](https://3.bp.blogspot.com/-xtmgyAVqXGM/T7z5wCSdR_I/AAAAAAAAARk/IlMnNNQIlvI/s1600/Capture.PNG)

ugyanez tovább bontva a központi elme mentén, egyes szintűvé:

![egyes szintű felbontása a buboréknak](https://3.bp.blogspot.com/-lJmyUAA_8vA/T7z6TltyEQI/AAAAAAAAAR0/on5iBGRAwU0/s1600/Capture.PNG)

ugyanígy tovább bontva:

![2-es szintű dfdvé talakítva](https://4.bp.blogspot.com/-sdK_UPPpRSM/T7z61Q-brqI/AAAAAAAAAR8/HQFfeAxrCOI/s1600/Capture.PNG)

> *A folyamat eredményei nem csak az ábrák, hanem a folyamat végén a probléma teljes megértése és feltárása!*

## EA 6
- http://hackingarena.com/home/index.html
- http://hackingarena.com/arena-exploits/

### input adat ellenőrzés
> - felhasználói hiba
> - gonosz felhasználók
> - nem `debug` hanem `release` módban kell kiadni a szoftvert
> - `site: bme.hu intitle:"index of" password`
> - web biztonság gyakorló oldal: http://hackingarena.com/challenges/web/
> - kliens oldali validáció gyakorló: http://palpatine.hackingarena.no:804/
> - SQL injection puska: http://pentestmonkey.net/cheat-sheet/sql-injection/mysql-sql-injection-cheat-sheet
>   - `sqlmap -b "jabba.hackingarena..." --technique=B -D`
> - https://portswigger.net/
> - https://coinsrs.no/wp-content/uploads/2016/04/finse-20160427-erdodi-ethical-hacking.pdf
> - https://www.immunityinc.com/products/debugger/

## EA 7 - CASE eszközök
- a teljes szoftverfejlesztési folyamatot támogatja
- egy teljs módszertant lekövet
- fontos az újrahasználhatóság
![CASE eszközök](https://www.includehelp.com/basics/Images/case-tools.jpg)

### UPPER CASE tool
támogatja az analízis és tervezés fázisait, segíti reportok és formok generálását

### LOWER CASE tool
kódgenerálást és kódolást támogat

> - standard metodológián alapuló: UML, OMTSA/SD
> - felxibilitás: a különböző eszközök különböző projekteken is használhatóak, nem projektspecifikusak
> - integritás: a különböző eszközök egymással kompatibilisek maradnak
> - integráció tesztelő redszer: automatikus tesztelést végző rendszerek használata  fejlesztés során
> - reverse engenering: magasabb szintű nyelvek támogatása


**Alap szolgáltatások:**
> - message services: szabványos kacsolódás tool-tool; tool-enviroment, enviroment-enviroment
> - User interface services: UI fejlesztéshez
> - data repository services: adatok és adatkapcsolatok tárolása, kezelése
> - data integration services: csoportok és azok közti kapcsolatokat kezel
> - task mnagement services: folyamat modellek pontos meghatározása és integrálása

### Tesztelés
Egy összehasonlítás, hogy a rendszer tudja-e a specifikációkat
1. a tesztelés csak a hibák jlenlétét jelzi
2. nem lehtésges kimerítő teszt
3. korai teszt 
4. hibák csoportosulása
5. féregírtó paradoxon
6. a tesztelés függ a körülményektől
7. hibátlan rendszer téveszméje

#### Tesztelés folyamata
1. terv készítés: - mit milyen céllal és milyen módszerrel tesztelünk, lásd [V modell](https://github.com/gabboraron/halado_szoftvertechnologiak#v-modell)
   - teszt célja
   - teszt tárgya: objektum/osztály
   - tesztbázis - követelmények
   - tesztadat
   - kilépési feltétel
2. teszteset tervezés: - milyen tesztadattal kell vizsgálni a rendszert, milxen eredményt várunk
3. előkészületek: 
   - követlemény alapú tesztelés: megcsinálja-e azt amit szeretnénk látni?
     - szükséges: nagyon pontos követelményrendszer -> validáció
   - pertició tesztelés: adat tesztelés, input-output adatokra
     - pl: pozitív sázmok, intervallumok megadása, stb
   - strukturális tessztelés: a program szerkezetét/vezérlését teszteli
     - nyelvi elemek tesztelése, - White box teszt
     - útvonaltesztelés: a szekvenciák működése, a programot leíró gráf működése
4. tesztelés
5. kilépési feltételek vizsgáláata
6. eredmények áttekintése
7. jelentéskészítés

- Automata tesztelő rendszerek gyakorlatailag ugyanezt végzik el.
- Tesztgenerátor: sok adatot generál a megadott intervallumban.
- Véletlen tesztadat generálás, fuzzy generálás is hasznos lehet.

## EA 8 - minőségi kérdések
> A minőség nehezen definiálható. 
>
> 1. felhasználói alapú: 
>   - felhasználásra való alkalmasság
>   - felhasználó ígényeit kielégíti
> 2. termék alapú definíció
>   - a minőséget mérhető paraméterek adják meg
>   - a különbség az egyes jellemzők közti kkülönbségekből adódnak
>   - ez objektív szemlélet
> 3. folyamat alapú definíció
>   - megfelel a specifikációnak, akkor minőségi
> 4. érték alapú
>   - költség függvéynében határozza meg a minőséget => jó termék alacsony áron oldja meg a feladatot
> 5. transzcendens definíció
>   - a minőség veleszüületett, azaz pl a márkanév adja
> - Filozófiai értelmezés: pl svéd acél, svájci bicska, stb, értékrenden, divaton alapuló megítélés
> - Társadalmi értelmezés: társadalmi hasznnosság és veszélytelen
> - Minőségügyi értelmezés: egyensúlya a műszaki/erkölcsi/piaci/gazdasági aspektusoknak
> 
> **Az ISO szerint**: azon jellemzők öszessége aamik befolyásolják képessgét, ohgy meghatározott ígényeket elégítsen ki
> => azt adja amit és amikor elvárnak normális árért
>
> Minőségi ígény:
>  - szabvány
>  - jogszabály
>  - kor divat: hintó/sportkocsi
> 
> **Garvin 8 dimenziója:**
> 1. teljesítmény: szolgáltatások alapvető felhasználhatóságát jelenti
> 2. sajátosságok: alapvető jelelmzők, plusz/egyedi funkciók
> 3. megbízhatóság, hogy használati idő alatt nem romlik el (*mtb*)
> 4. megfelelés: a követelményeket mennyire elégíti ki, tömegtermelésben a termékek egyedi elllenőrzése pl *LEGO*
> 5. tartósság: szolgáltatás használati időn belül nyújtott teljesítmény mértéke
> 6. használhatóság: termék kiaknázhatóságának mértéke
> 7. eszétika: pl a *GUI*
> 8. Felismert minőség: márkanév/termék híre/stb
>
> **Minőséget befolyásoló tényezők (9M):**
> 1. piacok
> 2. pénz
> 3. vezetés
> 4. emberek
> 5. ösztönzés
> 6. anyagok
> 7. gépek és gépesítés
> 8. modern it rendszerek
> 9. növekvő követelmény a temrékkel szemben
>
> **1. ártatlanság kora**: elfogadja a rossz minőséget is
> **2. eszmélés időszaka**: minőség fontosságát felismerik, de szükséges rosszként kezelik
> **3. elkötelezettség kora**: amikor a minőség gazdasági szükségszerűség, a gyártási folyamatok erre optimalizálva.
> **4. világszínvonal elérése**: minőség mindenek felett, a hibás termék megelőzése a cél
>
> **szoftverminőség kezelése**:
> - minőségbiztosítás
>   - szabályok felállítása
> - minőségtervezés
>   - kiválasztjuk, hogy az összes előírásból mi az ami nekünk fontos
> - minsőségtervezés
>   - garantálja, hogy használják az alkalmazottak az előírásokat


