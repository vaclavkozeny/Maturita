# Vyšší programovací jazyky

- Omezení a rozdíly vůči programování pro PC
  - absance OS
  - přímí přístup k HW
  - někdy je nutno softwarově implementovat zásobník (přes ukazatel)

## Požadavky vyšších programovacích jazyků na mcu

- důvody HLL:
  - snížení kódové nadbytečnosti
  - efektivní implementace typických konstrukcí
    - pole, větvené, podprogramy...
- **požadavky**:
  - více pracovních registrů
    - u ATMega64 je jich 32
  - krátký instrukční cyklus
    - co nejméně taktů
    - splňuje RISC
    - pipelining
  - rozšířené podpora ukazatelů
    - PRE/POST increment/decrement
    - 8/16/24 bit
  - indexování polí
    - přístup pomocí relativních adres
    - **offset**
  - pamětové ukazatele
    - alespoň 4
  - šíření příznaku nuly
    - efektivnější práce s výce bytovými čísly
    - `compare`, `add`, `sub`
    - zahrnuje příznak z předchozí operace
    - příkladem jsou instrukce "... with carry"
  - bitové proměné
    - práce s jednotlivými bity registů/portů
    - `set`
    - `clear`
    - `test`
  - kódy instrukcí delší než 8bit
    - vejde se celá do jedné buňky paměti
    - dokáže přečíst instrukci v jednom taktu
  - registry v normální oblasti paměti
    - přístu k registům přes ukazatel paměti
  - stack pointer
    - ATMega64 SP
      - 16bit
      - SW přístupny
  - podpora 16/32bit bitových dat
    - `ADW`
    - práce se 16bit konstantou

## Optimalizace kompilátoru

- **HW závislé**
  - registrové proměné
    - proměnné a parametry funkcí se umisťují do registrů místo do RAM
  - optimalizace jednoduchým přístupem
    - bytové operace nahrazujeme bitovými
  - reorganizace kódu
    - změna typu smyčky (kompilátor použije FOR místo WHILE, je-li to efektivnější)
    - někdy je efektivnější čítat z druhé strany a testovat na 0, místo testování na vrchní hodnotu
- **HW nezávislé**
  - zpracování konstant
    - výpočty s konstantami se vypočtou při kompilaci
  - vyloučení opakujících se výpočtů
  - kompilátor si může uložit hodnotu když zjistí, že se používá znovu
    - do registru
  - optimalizace skokových výrazů
  - vyloučení mrtvého kódu
  - náhrada opakujícího se kódu
    - vytvoří se podprogram
  - negaece skoků
    - jednu větev podmínky lze odstranit negací podmínky
  - překrývání dat
  - optimalizace plnění
    - při inicializaci proměnných lze nastavit nějakou počáteční hodnotu
  - optimalizace jednoduchých smyček
    - místo použití cyklů lze kód nakopírovat za sebou
    - zvyšuje velikost paměti programu, ovšem zrychluje ho
  - rotace smyček
    - lze zaměnit pořadí provádění instrukcí
    - pokud na sobě nejsou závislé
  - optimalizace řídícího toku
    - náhrada za switch-case
    - switch-case se převádí na if
    - pokud jednotlivé podmínky tvoří kaskádu, lze skočit přímo na správnou větev
