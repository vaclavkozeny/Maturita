# Testování SW

`Sémantická chyba, syntaktická chyba, chyba, debugging, ladění aplikace, výjimka, testování, jednotkové testy`

## Chyba

- nedostatek v kódu
- program nefunguje správně
- **hardwarová**
  - způsobené selháním hardwaru
- **uživatelská**
  - způsobené nekorektním užíváním aplikace uživatelem
  - některé věci se dají oštřit (string místo int)
  - něco se ovšem ošetřit nedá (m místo cm)
- **programátorské**
  - **syntaktické**
    - špatně zapsaný kód
    - chyba v zápisu
    - nelze zkompilovat
  - **sémantické**
    - jíné chování než bylo očekáváno
    - program lze zkompilovat (syntakticky je správně)

## Ladění (debugging)

- postup pro nalezení chyb, popř. snižování jejich množství
- autor nalezne problém, který poté izoluje a opraví ho
- pomáhá nám IDE (samo chyby detekuje a navrhuje řešení)
- **breakpoint** (zarážka)
  - zastavení běhu aplikace
  - lze poté krokovat po řádcích kódu

## Vyjímky

- SW přerušení programu při jeho běhu

### Ošetření

- **try catch**
- používají se jako ochrana před chybným vstupem uživatele
- provedou blok kódu
  - při chybě se vrátí a pokračují v běhu programu
- lze se jim vyhnout pomocí kontroly vstupu

## Testování

- proces ověření integrity kódu
- chování na určité případy
- prevence chyb a zlepšení kvality kódu
- **jednotkové testování**
  - testuje se pouze jedna určitá komponenta / metoda
