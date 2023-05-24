# ASP.NET

`Razor Pages, MVC, Page, PageModel, Razor syntaxe, Startup.cs, služba, databáze, Entity Framework, Identity`


- `Active Server Pages`
- Běží na serveru a umožňuje vytvářet dynamické webové stránky
- Jazyky – C#, F#, VB.NET

## Razor Pages

- multiplatformní, serverový webový framework
- využívá:
  - C# pro server-side kód
  - Razor syntaxi s HTML kódem, do kterého lze vkládat C# kód
- Razor Pages modifikují MVC
  - spojuje se Controller a Model -> Page Model
  - View -> Page
- Integrovaný routing, lze snadno vytvořit přehledné adresy URL pro webové stránky
- Podpora Dependency Injection, což umožňuje vývojářům snadno spravovat závislosti v aplikaci

## MVC
- `Model – View – Controller`
- architektura pro vývoj aplikací
- vznikla pro zanesení řádu do vývoje aplikací
- základem je **model**, **view** a **controller**
- je základem pro další architektury

#### Controler

- řídící jednotka celé architektury
- drží celou aplikaci pohromadě
- od uživatele dostává dotazy na data
- propojuje view a model
- volá metody
- získaná data dále předávána view

### View

- zobrazuej data uživateli

### Model

- struktura dat
- funkcionalita aplikace
- návrh DB

## PageModel

- ASP.NET Razor pages

### Page

- view

### PageModel

- spojení controlleru a modelu
- stará se o data, stav aplikace a komunikuje s view

## Startup.cs

- Klíčový soubor frameworku
- Probíhá v něm veškerá konfigurace
- V nejnovější verzi obsažen v rámci **Program.cs**

## Služba

- poskytují přístup k dalším funkcionalitám a nástrojům
- Příklady:
  - **ILogger**: Služba pro zaznamenávání logovacích informací
  - **IEmailSender**: Služba pro odesílání e-mailů
  - **IViewRenderService**: Služba pro vykreslování Razor views do řetězců
  - **IUrlHelper**: Služba pro generování URL adres
  - **IHttpContextAccessor**: Služba pro přístup k aktuálnímu HttpContextu

## Databáze

- místo, kde jsou uložena data
- k datům se přistupuje přes "SQL dotazy"
- v ASP.NET typicky používan LINQ pro přehlednější dotazy
- Velkou roli hraje Entity Framework

## Entity framework

- objektově relační mapovací framework
- práce s tabulkami jako s objekty
- vývojáři nemusí přímo pracovat s SQL dotazy => LINQ
- podporuje velké množství databázových systémů (SQL, SQLite, MySQL, Oracle ... )

## Identity

- sada balíčků
- umožňuje vývojářům implementovat autentizaci a autorizaci pro své webové aplikace
- ověření pomocí hesla nebo externích poskytovatelů
- Rozšiřuje databázi – přidávají tabulky (Users, Roles ... )
- Umožňuje **scaffoldovat** (generovat) stránky pro identitu
