# Counting Towers
A feladat, hogy építsünk egy 2 egység széles és n magas tornyot, ahol n egész szám.
Rendelkezésünkre áll mindenféle szélességű és magasságú építőkocka végtelen mennyiségben.
A szélessége és magassága egész számok. A kérdés, hogy hányféleképpen lehet a tornyot megépíteni?

## Input
Egy N egész szám, ami a toronynak a magassága.

## Ötletelés
Legyen a függvény neve torony, amely vár egy integert.

Rekurzív megvalósításon gondolkodva.
Van egy n magasságig megéptendő tornyunk.
n-1 magaságú tornyot kevesebb lépésben lehet építeni.
Tehát torony(n-1) egy kissebb probléma, mint torony(n).

### Ekkor alapeset a torony(1) = ?
- Első lehetőség, hogy 2 darab 1x1-es építőkockát használunk a megépítésre.
- Másik lehetőség, hogy 1 darab, egész tornyot "lefedő" építőkockát használunk a megépítésre.
- **torony(1) = 2**


### Mi van akkor, ha torony(2)-őt akarom megoldani?
- Ha 1 magas építőkockákkal dolgozunk, akkor torony(1) * torony(1) = 4
- Ha 2 magas építőkockákat használunk, akkor vagy 2 darab 1x2 vagy 1 darab 2x2 jöhet szóba.
    - Összesen 2 lehetőség
- Van 1 darab 1x2 építőkockánk és 2 darab 1x1 az összesen 2 lehetőség.
- **torony(2) = 8**


### Mi van akkor, ha torony(3)-at akarom megoldani?
- Először építünk egy 2 egység magasságú tornyot és ezt egészítjük ki.
    - Ezt összesen torony(2)*torony(1) = **16** féleképpen tehetjük meg.
    - Tehát 3 egység magasságnál kissebb építőkockákat használva ennyi féleképpen építhetünk tornyot.
- Használhatunk 1 darab 2x3-as építőkockát.
- Két darab 1x3-mas építőkockát használunk.
- A baloldalon van egy 1x3-mas építőkockánk. A jobb oldal hány féleképpen tölthető ki?
    - Csak 1x1-es kockákat használunk a jobboldalon.
    - A jobboldalon egy 1x2-es és egy 1x1-es építőkockát használunk. Ezt 2 féleképpen lehet.
    - Más lehetőségünk nincsen.
- A jobboldalon van egy 1x3-mas építőkocka. A bal oldal hány féleképpen tölthető ki?
    - Ezt is 3 féleképpen tehetjük meg.
- **torony(3) = 18 + 2*3 = 24**


### Mi van akkor, ha torony(n)-et akarom megoldani?
- Először építünk egy n-1 egység magasságú tornyot és ezt egészítjük ki.
    - Ezt összesen torony(n-1)*torony(1) féleképpen tehetjük meg.
    - Tehát n egység magasságnál kissebb építőkockákat használva ennyi féleképpen építhetünk tornyot.
    - Mivel torony(n-1)*torony(1) = torony(n-1)*2 = torony(n-2)*2*2 = ...
    - **Tehát torony(n-1)\*torony(1) = 2^(n+1)**
- Használhatunk 1 darab 2xn-as építőkockát.
- A baloldalon van egy 1xn-nes építőkockánk. A jobb oldal hány féleképpen tölthető ki?
    - Csak 1x1-es kockákat használunk a jobboldalon
    - A jobboldalon is egy 1xn-es építőkockát használunk. + 1 eset

    - A jobboldalon egy 1x(n-1)-es és egy 1x1-es építőkockát használunk. Ezt 2 féleképpen lehet.
    - A jobboldalon egy 1x(n-2)-es és két darab 1x1-es építőkockát használunk. Ezt 2 féleképpen lehet.
    - ...
- A jobboldalon van egy 1xn-nes építőkockánk. A bal oldal hány féleképpen tölthető ki?
    - Ezt is ... féleképpen tehetjük meg.






### Mi van akkor, ha torony(4)-at akarom megoldani?
- Először építünk egy 3 egység magasságú tornyot és ezt egészítjük ki.
    - Ezt összesen torony(3)*torony(1) = 48 féleképpen tehetjük meg.
    - Tehát 4 egység magasságnál kissebb építőkockákat használva ennyi féleképpen építhetünk tornyot.
- Használhatunk 1 darab 2x4-as építőkockát.
- Két darab 1x4-es építőkockát használunk.
- A baloldalon van egy 1x4-es építőkockánk. A jobb oldal hány féleképpen tölthető ki?
    - Csak 1x1-es kockákat használunk a jobboldalon. + 1 eset
    - A jobboldalon egy 1x3-as és egy 1x1-es építőkockát használunk. Ezt 2 féleképpen lehet.

- A jobboldalon van egy 1x4-mas építőkocka. A bal oldal hány féleképpen tölthető ki?
    - Ezt is ... féleképpen tehetjük meg.
- **torony(3) = 16 + 1 + 3 = 20**


1. Fogunk egy 2 széles és N magas építőkockát.
2. Fogunk két darab 1 széles és N magas építőkockát.
3. Fogunk egy 2 széles és N-1 magas építőkockát.
   - A kimaradt helyre teszek 2 széles egy magas építőkockát
   - A kimaradt helyre teszek 1 széles és 

