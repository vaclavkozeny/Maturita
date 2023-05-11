# Možnosti pozicování

`Blokové a inline prvky, absolutní a relativní pozicování, obtékání, grid, flex, tabulka, margin, padding`

## Blokové prvky

- vždy začínají na novém řádku
- využívají plnou šířku, kterou mají k dispozici
- příklad - `<div>...</div>`

## Inline prvky

- nezačínají na novém řádku - lze jich na jednom řádku mít více vedle sebe
- zabírá pouze takovou šířku, jakou potřebuje
  - neroztahuje se více, než je potřeba
- příklad - `<span>...</span>`

## Inline-block prvky

- kombinace inline a blokových prvků
- chová se jako inline, ale dá se u něj nastavit výška a šířka

<image src="./images/display.png">

## Pozicování

### Absolutní

- astavení přesné hodnoty pozice prvku
  - pomocí souřadnic
- souřadnice v levém horním rohu jsou 0,0
- prvek je umístěn staticky

### Relativní

- pozice prvku se odvozuje z jiného prvku
- prvek zůstává v dokumentu
- lepší pro respoznivní stránky

<image src="./images/pozice.png">

## Obtékání (float)

- prvek obtéká text z určité strany
- již se nepoužívá (na moderních webech)
- obtékaný prvek musí mít danou šířku
- špatné zobrazení na menších displejích

```CSS
div {
  margin: 5px;
  width: 50px;
  height: 150px;
}

.left {
  float: left;
  background: pink;
}
```

<image src="./images/float.png">

## Tabulka

- nejstarší a nejvíce zastaralá metoda
- není responzivní
- vymyká se účelu tabulky (zobrazení dat)
- jednoduché na použití

- `tr` - tabular row
- `th` - tabular head
- `td` - tabualr data

```html
<table>
  <tr>
    <th>Person 1</th>
    <th>Person 2</th>
    <th>Person 3</th>
  </tr>
  <tr>
    <td>Emil</td>
    <td>Tobias</td>
    <td>Linus</td>
  </tr>
  <tr>
    <td>16</td>
    <td>14</td>
    <td>10</td>
  </tr>
</table>
```

## Flexbox

- všechny prvky uvnitř využívají celé volné místo
- lze nastavit hodně atributů (směr, pozadí, způsob zarovnání)
- vysoká responzivita
- příklad - galerie obrázků
- <a href="https://css-tricks.com/snippets/css/a-guide-to-flexbox/">ukázky</a>

## Grid

- container definován pomocí display: grid
- pro celou stránku vytvoří pomyslnou mřížku
- definice počtu sloupců a řádků → vytvoření prázdných prostorů, kam můžeme dávat prvky
- <a href="https://css-tricks.com/snippets/css/complete-guide-grid/">ukázky</a>

## Margin, Padding

- margin - venkovní odsazení
- padding - vnitřní odsazení

<image src="./images/margin.png">
