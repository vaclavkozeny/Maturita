# Normalizace databáze

`OLAP, OLTP, normalizace, optimalizace, nultá normální forma, první normální forma, druhá normální forma, třetí normální forma, BCNF`

## OLAP

- `Online Analytical Processing​`
- uspořádává velké objemy dat tak, aby byla data přístupná a srozumitelná všem uživatelům​
- získat souhrnná data​
- důležitá je **rychlost**

## OLTP

- `Online Transaction Processing`
- nejsnazší a nejbezpečnější modifikace dat​
- ukládat a organizovat nová data​
- důležitá je **integrita​**

## Normalizace a optimalizace

- způsob, jak navrhnout ideální databázi​
- když je tabulka ve vyšší normální formě, tím kvalitněji je tabulka navržena => **menší šance porušení integrity dat​**
- vzrůstá zátěž na databázi => **pomalejší výsledky​**
- sada pravidel
- proces při kterém se relace rozkládají za účelem:
  - jednodušší práce s daty​
  - lepší manipulace s daty​
  - zabránění opakování dat​
  - lepší konzistence dat​
- řešení závislostí jednotlivých atributů - 0.NF, 1.NF, 2.NF, 3.NF, BCNF​
- řešení vztahů složených primárních klíčů - 4.NF, 5.NF, 6.NF​

## 0.NF

- tabulka obsahuje alespoň jedno pole, které obsahuje více než jednu hodnotu

## 1.NF

- atributy nelze dále dělit, a jsou tudíž **atomické​**

<image src="./images/1nf.PNG">

## 2.NF

- databáze je v 2. NF, když je v 1. NF a ​všechny (neklíčové) atributy **závisí na složeném klíči**.

<image src="./images/2nf.PNG">

- u Octavia by teoreticky mohla být jiná země, což by porušilo integritu dat

## 3.NF

- databáze je ve 3.NF, pokud je ve 2.NF, a všechny **neklíčové atributy jsou navzájem nezávislé** (Jsou závislé pouze na klíči, ne navzájem)

<image src="./images/3nf.PNG">

- základní mzda se váže k pozici, neměla by být různá dle lidí

## BCNF

- atributy, které jsou součástí primárního klíče musí být vzájemně nezávislé​

<image src="./images/bcnf.PNG">

- Škoda je Fabia nebo Kamiq a Fabia je modrá nebo červená, ale je Škoda modrá nebo červená? To je jedno, není tam vztah
