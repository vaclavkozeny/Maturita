# Prostředky pro návrh webových aplikací

`HTML, CSS, Javascript, značka, atribut, sémantický význam značek, písmo v WWW, CSS selektor, příklady selektorů, vlastnosti CSS, media query`

## HTML

- `Hyper Text Markup Language`
- markup language
- tvorba webových stránek
- definujeme obsah stránky a strukturu dokumentu
- tagy ve špičatých závorkách `< >`
- 2 části
  - **head**:
    - jazyk
    - autor
    - charset
  - **body**:
    - samotná stránka
- soubor `.html` / `.htm`

### Značka

- označení různých částí obsahu webové stránky
- 2 druhy
  - párové
    - `<div></div>`
    - `<p></p>`
  - nepárové
    - `<hr/>`
    - `<br/>`
    - `<img/>`

### Atribut

- vstupuje do značky
- umožňují nastavit `id, class, style` a další
- definují charakteristiku tagu
- může s nimi pracovat JavaScript
- `<img src='{cesta}' alt='{popis}'/>`
- `<p class='{název}'></p>`
- `<div id='{id}'></div>`

## CSS

- `Cascading Style Sheets`
- definuje vzhled jednotlivých elementů (tagů)
- oddělení vzhledu a struktury webu
- soubor `.css`

- `    body{
    padding: 0;
    margin: 0;
    }
a{
    color: #FAAA01;
}`

- **Internal CSS**
  - není potřeba nahrávat více souborů
  - zvětšuje načítací dobu stránky
- **External CSS**
  - musí se importovat
  - standard dnešní doby
- **Inline CSS**
  - nepřehledný kód
  - **nedoporučuje** se používat

### Písmo

- lze definovat vlastní fonty
- zátež navíc

### Selektory

- vybírá na který tag aplikovat styl

- `*` – vybere všechny elementy
- `{tag}` - vybere všechny elemety typu {tag}
- `{tag1},{tag2}` - vybere elementy typu {tag1} a {tag2}
- `.class` – vybere elementy s `class="class"`
- `class1.class2` - vybere jenom elemnty které mají jak `class1` tak `class2`
- `{tag}.class` - vybere elmenty {tag} s `class="class"`
- `#id` – vybere elementy s `id="id`
- `{tag1} {tag2}` - vybere `{tag2}` elementy uvnitř `{tag1}`
- `{tag1}>{tag2}` - vybere všechny `{tag2}` elementy kde je parent `{tag1}`
- `{tag1}+{tag2}` - vybere první `{tag2}` umístšn hned za `{tag1}` elementem

### Vlastnosti

- **color** - určuje barvu textu
- **font-size** - určuje velikost písma
- **font-family** - určuje rodinu písma, kterou chcete použít
- **background-color** - určuje barvu pozadí elementu
- **border** - určuje vlastnosti okrajů elementu
- **width** - určuje šířku elementu
- **height** - určuje výšku elementu
- **margin** - určuje okraj elementu
- **padding** - určuje mezery uvnitř elementu
- **text-align** - určuje zarovnání textu
- **display** - určuje způsob zobrazení elementu
- **position** - určuje pozici elementu vůči ostatním elementům
- **float** - určuje, zda se element zarovnává doleva nebo doprava
- **z-index** - určuje vrstvu, na které se element zobrazí vzhledem k ostatním elementům

## Javascript

- interpretovaný programovací jazyk
- tvorba interaktivních webových stránek
- vetšinou běží na straně klienta

- funkce

  - s funkcemi se zachází jako s jinými proměnnými
  - funkci lze předat jako argument jiným funkcím

- přidávání a odebírání prvků ze stránky
- validace formulářů
