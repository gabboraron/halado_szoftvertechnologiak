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
![spirálmodell vázlat](https://hu.wikipedia.org/wiki/Spir%C3%A1lmodell#/media/Fájl:Spiralmodell.jpeg)
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
