# Směrování, směrovací tabulky, směrovací protokoly

`Směrovací tabulky – záznamy, statické směrování, dynamické směrovací protokoly (RIP, RIPv2, RIPng, EIGRP, OSPF, BGP), směrovací protokoly postavené na principu vzdáleného vektoru (distance-vector) v porovnání s link-state. Výhody a nevýhody statického směrování oproti dynamického směrování. Příklad vytvoření směrovacích tabulek staticky a pomocí směrovacího protokolu (např. RIP)`

## Směrování

- L3 vrstva (síťová)
- Určení, kam se má paket dostat
- Router posílá pakety do cizí sítě
- pro přesun z naší sítě do jiné potřebujeme router
  - přesouvá pakety mezi sítěmi
  - router ovšem taky vidí pouze sítě, do kterých patří
- tento problém řeší směrování
  - data, která nemůžeme doručit přímo, doručíme někomu jinému:
    - tomu, kdo je blíže k cíli (next-hop)
    - tomu, kdo má větší šanci najít správnou cestu (default-route)
      - 0.0.0.0/0
      - shoda se všemi adresami → nejméně specifická → vyhodnocení jako poslední
- směrování = proces hledání nejlepší cesty pro data, která nelze doručit přímo přes síť

## Směrovací tabulka (Routing table)

- routing table
- uložení?
  - v RAM routeru (ty dynamické?)
  - v NVRAM (ty statické?)
- udržuje informace, jak doručit data do neznámých sítí
- každý záznam obsahuje:
  - adresu cílové sítě + masku
  - gateway sítě - název odchozího rozhraní
  - IP adresu dalšího routeru
  - metrika (výhodnost cesty)
    - čím menší, tím lepší
    - počítá se počtem hopů, rychlostí, stabilitou a zatížeností
    - jelikož se v tabulce můžou nacházet duplicity, router postupně hledá shodu s nejvýhodnější cestou

### Statické směrování vs dynamické směrování

#### statické

- ručně přidané
- bezpečnější
- méně výpočetně náročné
- pro malé sítě

#### dynamické

- automaticky přidané záznamy
- router se učí cestu k sítím, které nezná
- u dynamického směrování nemusí administrátor znát topologii sítě
- je málo flexibilní a nemůže se dostatečně konfigurovat
- jednodušší administrace, protokol dělá část práce za admina
- jakékoliv změny se okamžitě šíří díky směrovacím protokolům
- přizpůsobují se topologii sítě

## Směrovací protokoly

- záznamy se do směrovací tabulky přidávají buď ručně, nebo automaticky
  - ručně přidané záznamy = **statické routy**
  - rychlé, bezpečné
  - nevhodné pro velké sítě
- automaticky přidané záznamy = **dynamické routy**
  - pomocí směrovacích protokolů
  - router se naučí cestu k sítím, které nezná
  - stačí nastavit pouze jednou a poté fungují samy
  - přizpůsobují se topologii sítě (při výpadku hledají alternativu)

### Dynamické směrovací protokoly

#### Link-state protokoly

- pro správu sítě v rámci jedné domény (např. firma)
- router zjišťuje, zda má v síti další routery a testuje jejich dostupnost
- poté routery informuje o jejich sousedech
- každý router ví o všech ostatních
- takto zmapuje celou síť
- podle toho pro packet určuje nejlepší cestu
- pro rozlehlejší sítě nutno rozdělit na části kvůli zatěžování sítě
- **ospf**

#### Distance-vector protokoly

- routery neznají strukturu sítě, pouze své nejbližší sousedy
- vyměňují si kompletní kopii směrovacích tabulek
- routery periodicky vysílají a díky grafovému algoritmu vypočítají vzdálenost do ostatních uzlů
- vzniká riziko zacyklení
- **rip**

#### RIP

- `Routing Information Protocol`
- distance-vektor protokol
- nejjednodušší protokol s jednoduchou konfigurací
- malé sítě (max. 15 skoků)
- hloupá metrika
- první verze (RIP)
  - posílal směrovací tabulky broadcastem
  - což zatěžovalo síť
- druhá verze (RIPv2)
  - posílá směrovací tabulky multicastem
  - navíc umí pracovat s podsítěmi a maskami sítě (CIDR)
- nejnovější verze (RIPng)
  - má podporu IPv6
  - lepší autentizace

#### EIGRP

- `Enhanced Interior Gateway Routing Protocol`
- hybridní protokol
- pravidelně kontroluje, zda je trasa k dispozici
- místo směrovací tabulky posílá změny topologie
- podpora pro CIDR a proměnnou délku podsítí
  - `Classless Inter-Domain Routing`
  - maska je určena počtem bitů, nikoliv třídou IP adres
- MD5 autentizace

#### OSPF

- `Open Shortest Path Find`
- link-state protokol
- provádí změny v tabulce na základě změn v síti
- velké sítě
- nejpoužívanější v samosprávých (autonomních) systémech
- routery kontrolují okolní routery
- je velmi paměťově náročný

#### BGP

- `Border Gateway Protocol`
- distance-vektor
- používají ho provideři (ISP)
- směrovací tabulky obsahují stovky tisíc záznamů
- vyměňují se pouze informace o změnách, nikoliv celé tabulky

## Windows route print

- Cílová adresa
- Maska sítě
- Brána – IP adresa směrovače (pokud není síť přímo dostupná)
- Rozhraní, přes které se lze dostat na bránu
- Metric je "výhodnost" cesty, preferují se nižší čísla
- V distance-vector protokolech znamená počet skoků
- Jestliže adresa není v tabulce, použije se defaultní routa neboli žolík
  - Adresa 0.0.0.0 s maskou 0.0.0.0

<image src="./images/route.png">
