# sort-in-PowerPC
<h1 align="center"> Programa duotai architektūrai asemblerio kalba </h1>

*Pasirinktas Burbulinis rikiavimas, nes jis lengvai įgivendinamas.*

<ins>**Burbulo rikiavimo metodas**</ins> – vienas iš paprastų, bet nelabai efektyvių rikiavimo algoritmų.
**Algoritmo principas** – nuosekliai iš eilės peržiūrėti gretimų elementų poras, prireikus elementus sukeisti, perkeliant mažesnį arčiau pradžios. 
Tokiu būdu per pirmą iteraciją mažiausias elementas perkeliamas į pirmą poziciją, vėliau tas pats principas taikomas posekiui be pirmo elemento ir t. t.

*Burbulo algoritmas N elementų masyvo rikiavimui naudoja apie N²/2 lyginimų ir N²/2 keitimų vietomis, tiek laukiamu, tiek ir blogiausiu atveju. 
Algoritmas nenaudoja papildomos atminties.*

![Bubble_sort_animation](https://github.com/user-attachments/assets/79fd3bad-edcf-4e89-ad51-bdaba033252c)

## Failų struktūra

Projektas susideda iš šių failų:
- **`SortPowerPC.s`**: Programa asemblerio kalba, skirta PowerPC architektūrai.
- **`Makefile`**: Komandinės eilutės įrankis, skirtas automatizuoti kodo vertimą ir testavimą.

---

## Reikalavimai
Projekto paleidimui reikalingi šie įrankiai:
1. **PowerPC toolchain**: Kompiliatorius ir surinkėjas PowerPC architektūrai (pvz., `powerpc-linux-gnu-as`).
2. **QEMU**: PowerPC emuliatorius, skirtas programos vykdymui ir testavimui.
3. **GNU Make**: Automatizuotas build ir testavimo įrankis.
4. **MSYS2**: Aplinkos emuliatorius ir paketų tvarkyklė.

---

## Naudojimas

### 1. Projekto paruošimas
Įsitikinkite, kad visi reikiami įrankiai yra įdiegti jūsų sistemoje. Jei ne, įdiekite juos naudodami jūsų naudojamą paketų tvarkyklę (pvz., `pacman`, `apt`, arba `brew`).

### 2. Kompiliavimas
Naudodami `Makefile` galite sukompiliuoti programą.

Testavimo metu bus sugeneruotas failas results.log, kuriame nurodoma, ar rezultatai sutampa su `expected_output.bin`.
Paleiskite testus, kurie naudoja pateiktą `test_input.bin` ir patikrina programos rezultatą:

> test_input.bin: 
> 5, 2, 9, 1, 5, 6
>
> expected_output.bin
> 1, 2, 5, 5, 6, 9
>
> realus rezultatas:
> 1, 2, 5, 5, 6, 9

---

### Paleidimui naudotos komandos

Kompiliuti, sulinkinti, paleisti QEMU
> powerpc-linux-gnu-as SortPowerPC.s -o SortPowerPC.o
> 
> powerpc-linux-gnu-ld SortPowerPC.o -o SortPowerPC
> 
> qemu-ppc ./SortPowerPC

---

## Dydis ir greitis:
Rašant šią programą prioritetas buvo jos paprastumas.
Tolimesnis programos optimizavimas galėtų padidinti jos greitį, bet kompromituotų aiškumą.

---
### Šaltiniai

Wikipedia Contributors (2019). Bubble sort. [online] Wikipedia. Available at: https://en.wikipedia.org/wiki/Bubble_sort.

Wikipedia. (2021). PowerPC. [online] Available at: https://en.wikipedia.org/wiki/PowerPC.

Chibialiens.com. (2021). Learn Multi platform PowerPC Assembly Programming... And feel the POWER! [online] Available at: https://www.chibialiens.com/powerpc/

www.ibm.com. (n.d.). POWER® family and PowerPC® architecture overview. [online] Available at: https://www.ibm.com/docs/en/aix/7.1?topic=storage-power-family-powerpc-architecture-overview.



‌

‌






