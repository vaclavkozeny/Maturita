# Architektury .NET

`Prostředky architektury .NET pro cílové platformy, MVVM, Binding, Observer, událostmi řízené programování`

## .NET

- open-source cross-platform framework
- podpora C#, F#, C++, VB.NET

### CLI

- `Common Language Infrastructure`
- standardizovaná specifikace popisující vlastnosti kódu a runtime
- možnost spuštění vyšších programovacích jazyků bez závislosti na platformě
- sestavení do platform-independent jazyka CIL (Common Intermediate Language)

### CLR

- `Common Language Runtime`
- spolčené virtuální prostředí pro běh aplikací
- převod CIL na strojový kód
- operace:
  - memory management
  - garbage collection
  - type safety
  - exception handling
  - thread safety

<image src="./images/net.png">

### FCL

- `Framework Class Library`
- soubor knihoven integrovaný do CLR
- poskytuje knihovny pro přistup ke konzoli, souborovému systému a pro síťovou konektivitu
- je v něm velké množství knihoven / frameworků pro tvorbu okenních aplikací (WPF, UWP, WinForms)

## MVVM

- SW architektura
- **Model**
  - logika aplikace a data
  - neví nic o stavu ovládacích prvků
- **ViewModel**
  - poskytuje spojení mezi oběma vrstvami
  - drží stav aplikace
  - ovládací prvky z View jsou pomocí bindingu propojeny s ViewModelem
- **View**
  - obsahuje uživatelské rozhraní
  - okno aplikace / ovládací prvek / stránka

### Binding

- svazuje datové zdroje poskytovatele a konzumenta
- sychnronizovaná data
- vlastnosti ViewModelu (poskytovatel) svázány s vlastnostmi vizálních komponent (konzument)
- mechanismus, který při změně dat upozorňuje konzumenty

### Command

- objekt, který reprezentuje událost
- pracuje s delegáty
- volá delegát, který má v sobě uchovaný, pokud nastane určitá událost (event)

### Converter

- objekt, který přetypovává svázané vlastnosti na jiný typ
- implementuje určité rozhraní (ve WPF IValue Converter)
- příklad - string => image

### Observer

- pozorovatel
- čeká na změnu objektu, poté může reagovat určitým způsobem
- příklad - Binding

### Událostmi řízené programování

- chod programu řídí události
  - uživatelská akce / změna hodnoty na serveru / obdržení zprávy
- využívá naslouchače (event listener) pro detekování určitých akcí
