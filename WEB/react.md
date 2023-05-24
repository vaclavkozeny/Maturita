# React

`Component, DOM, Virtual DOM, událost, props, state, hook, propagace stavu`

## React

- JS framework
- native -> mobilní aplikace

## Component

- umožňuje rozdělit UI do částí
- jsou na sobě nezávisle a lze je používat znovu
- každá komponenta může přijímat vstup - props
- do HTML struktury lze vkládat proměnné jako {}

## Props

- props = properties
- objekt, který slouží jako vstup do komponenty
- přenáší se v něm data, která poté lze použít v komponentě

## State

- do statu se ukládají data (proměnné) komponenty
- tato data "přežijí" překreslení komponenty
  - refresh stránky nepřežijí
- když dojde ke změně state překreslí se komponenta

## DOM (Document Object Model)

- stromová struktura aplikace (všechny objekty)
- reprezentuje dokument tak, aby program mohl měnit jeho strukturu a obsah
- **Virtual DOM**
  - eliminuje zbytečné překreslování neměnných komponent
  - vytvořit VDOM s novým stavem aplikace
  - porovnat s předchozím VDOM
  - v pravém DOM aktualizovat pouze ty komponenty, které se změnily

## Událost

- funkce, která se provede při určité akci, např. kliknutí na tlačítko
- předává se ke komponentě jako event handler ve složených závorkách

```JavaScript
<button onclick={HandleClick}>
    Click
</button>
```

## Hook

- umožňují používat funkce Reactu bez použití třídy
  - nefungují uvnitř tříd, pouze uvnitř React funkcí
- nelze je tedy volat ze smyček, podmínek apod
- **useState**
  - pro ukládání proměných komponenty
- **useEffect**
  - první parametr je funkce, která se má zavolat
  - druhý parametr je pole prvků, které funkci při své změně zavolají

```JavaScript
useEffect(()=>{

},[])
```

- **useContext**
  - Umožňuje mít společná globální data, která nemusíme všem komponentám tunelovat pomocí props
  - V kombinaci s hákem **useReducer** lze mít i globální logiku

## Propagace stavu

- pokud v potomkovi chceme změnit hodnotu rodiče
  - předáme mu v props metodu na změnu této hodnoty
