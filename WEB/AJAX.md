# AJAX a REST

`Klasická a asynchronní komunikace, AJAX, promise, fetch API, API, metody http, GET, POST, DELETE, PUT, PATCH, OPTION, REST, chybové kódy a návratové hodnoty`

## AJAX

- `Asynchronous JavaScript and XML`
- asynchronní komunikace klienta se serverem
- aktualizuje se pouze určitá část stránky
- odpadá nutnost refreshe celé stránky (oproti klasickým formulářům)
- stránky mohou být plynulejší
- snižuje se zátěž serveru, protože nemusí odesílat pokaždé celou stránku
- těžší na implementaci
- v případě, že hlavní obsah stránky je načítán AJAXem, jsou možné SEO problémy, protože crawler nenačítá obsah získaný AJAXem v JavaScriptu
- AJAJ – `Asynchronous JavaScript and JSON` (XML je zastaralé)

### Synchrnní komunikace

<image src="./images/noajax.PNG">

### Asynchronní komunikace

<image src="./images/ajax.PNG">

## REST

- způsob, kterým lze číst, vytvářet, editovat a odstraňovat informace pomocí HTTP dotazů (CRUD operace)
- nejčastěji používané HTTP metody: **GET**, **POST**, **PUT**, **DELETE**, **PATCH**
- tělo dotazu je ve formátu JSON, někdy XML nebo plain-text

<image src="./images/rest.PNG">

- **PATCH** slouží k částečné úpravě (nemusí být nastaveny všechny atributy)
- **OPTION** slouží k získání dalších informací a headerů o dané routě, jako třeba “Accept” header atd

## HTTP kódy

- 1XX
  - informační kódy
- 2XX
  - úspěšné kódy
  - **200** - OK
  - **201** – Created
  - **204** – No Content (Akce byla úspěšná a nevrací se žádná data – třeba při odstraňování)
- 3XX
  - přesměrovací kódy
  - **301** – Moved Permanently (Redirect)
- 4XX
  - chyba na straně klienta
  - **400** – Bad Request
  - **401** – Unauthorized (server klienta nezná – není přihlášený)
  - **403** – Forbidden (sever klienta zná, ale nedovolí mu přístup ke zdroji)
  - **404** – Not Found
- 5XX
  - chyba na straně serveru
  - **500** – Internal Server Error

## Fetch API

- posílání asynchronních dotazů v JavaScriptu
- následník XmlHttpRequest – zastaralá třída pro posílání AJAX requestů
  - Axios používá XmlHttpRequest (možná proto, že má podporu na starých browserech?)

```javascript
fetch("http://example.com/source", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
    "Accept": "application/json",
    "Authorization": "Bearer d3b62babddcfae3e285dd",
  },
  body: JSON.stringify(data),
})
  .then((responce) => responce.json())
  .then((data) => console.log(data));
```

- specifikujeme URL a nastavení
- v nastavení metodu, hlavičku a tělo
- “Content-Type” - jaký formát dat posíláme na server
- “Accept” - jaký formát dat očekáváme od severu
- “Authorization” - předáme řetězec s autorizačním tokenem

## Fetch API - Responce

- .fetch() i .json() vrátí Promise, je potřeba použít .then() nebo await pro získání dat
- fetch nevrací přímo data, ale Response, který představuje celou HTTP odpověď
- pro získání dat použijeme funkci .json()
- .json() nevrací opravdovou hodnotu, ale Promise -> je potřeba znovu použít .then()

## Promise

- objekt, který obaluje nějaká data, ze kterých se v budoucnu stane reálná hodnota
- můžeme použít await – počkáme až Promise vrátí hodnotu
- nebo metodu .then() - předáme do ní funkci, která hodnotu získá jako parametr

<image src="./images/fetch.PNG">
