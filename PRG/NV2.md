# Návrhové vzory 2

`Návrhové vzory pro skrývání implementace, optimalizaci rozhraní`

## Skrývání implementace

### Proxy (zástupce)

- nahrazení objektu zástupným objektem
- implementace rozhraním nebo abstraktní třídou
- objekt řídí přístup k jinému objektu

#### Remote proxy (vzdálený zástupce)

- řídí objekt umístěný někde jinde
- měla by implementovat kontrolu řízení komunikace
- dbContext (Zastupuje SQL databázi)

#### Protection proxy (ochranný zástupce)

- zakrývá identitu zastupovaného objektu
- většinou nenabízí všechny metody zastupovaného objektu
- implementace přístupových práv
- Identity framework

#### Virtual proxy (virtuální zástupce)

- zastupuje jiný objekt náročný na načtení
- šetří paměť

#### Smart reference (Chytrý odkaz)

- zastupuje objekt a rozšiřuje ho o další funkce

### Command (Příkaz)

- zapouzdření metody do objektu
- jako delegát
- **jako command ve WPF**

### Iterátor

- přístup k objektům uloženým v kolekci
  - možnost procházení (cyklem)

### State

- řešení rozdílů v chování objektu
- reprezentace stavu stavovými třídami
- **jako roboti co jsem dělali**

### Template Method (Šablonová metoda)

- definuje kostru algoritmu
- potomci mohou předefinovat určité kroky algoritmu bez zásahu do kostry

## Optimalizace rozhraní

### Facáda

- zjednodušení komunikace
- redukce počtu tříd, se kterými je potřeba komunikovat
- implementace rozhraním nebo abstraktní třídou
- **když máme bordel v programu tak ho můžeme schovat za fasádu (přístupnou zvenčí), a kód se tváří uklizený**

### Adaptér

- změna aktuálního rozhraní dané třídy
- usnadnění definice nových tříd
- `Chceme aby třída používala specifické rozhraní, ale nechceme ho na ní přímo implementovat -> vytvoříme adaptér, který nám zprostředkuje komunikaci, nemusí implementovat všechny metody rozhraní (naše třída je nepoužívá)`

<image src="./images/adapt.png">

### Composite

- hiearchická struktura objektů
- společný rodič → jednoduché přidávání
- binTree, linkedList
