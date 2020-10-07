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
