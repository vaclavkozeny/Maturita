# ASP.NET

`Razor Pages, MVC, Page, PageModel, Razor syntaxe, Startup.cs, služba, databáze, Entity Framework, Identity`

## ASP.NET

- `Active Server Pages`
- Běží na serveru a umožňuje vytvářet dynamické webové stránky
- Jazyky – C#, F#, VB.NET

### Razor Pages

- multiplatformní, serverový webový framework
- využívá:
  - C# pro server-side kód
  - Razor syntaxi s HTML kódem, do kterého lze vkládat C# kód
- Razor Pages modifikují MVC
  - spojuje se Controller a Model -> Page Model
  - View -> Page
- Integrovaný routing, lze snadno vytvořit přehledné adresy URL pro webové stránky
- Podpora Dependency Injection, což umožňuje vývojářům snadno spravovat závislosti v aplikaci

### MVC
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

#### PageModel

<image src="./images/pm.png">

#### Startup.cs

- Klíčový soubor frameworku
- Probíhá v něm veškerá konfigurace
- V nejnovější verzi obsažen v rámci **Program.cs**

#### Služba

- poskytují přístup k dalším funkcionalitám a nástrojům
- Příklady:
  - **ILogger**: Služba pro zaznamenávání logovacích informací
  - **IEmailSender**: Služba pro odesílání e-mailů
  - **IViewRenderService**: Služba pro vykreslování Razor views do řetězců
  - **IUrlHelper**: Služba pro generování URL adres
  - **IHttpContextAccessor**: Služba pro přístup k aktuálnímu HttpContextu

#### Databáze

- strukturovaná sbírka dat - ukládání permanentních dat
- ASP.NET podporuje zároveň několik databázových platforem -> Microsoft SQL Server, Oracle, MySQL
- Několik způsobů připojení databáze do ASP.NET aplikace
  - Vytvořená jako objekt přímo v hierarchii projektu
  - Přes connection string v **appsettings.json**
- Velkou roli hraje Entity Framework

#### Entity framework

- objektově relační mapovací framework
- umožňuje programátorům pracovat s databázovými tabulkami jako s objekty v kódu
- Poskytuje abstraktní vrstvu mezi aplikací a databází
  - vývojáři nemusí přímo pracovat s SQL dotazy
- Podporuje dotazy LINQ, sledování změn, aktualizace a migrace schémat
- Pracuje databázemi jako SQL Database, SQLite, MySQL, PostgreSQL, Oracle..

#### Identity

- sada balíčků
- umožňuje vývojářům implementovat autentizaci a autorizaci pro své webové aplikace
- poskytuje způsob, jak ověřit totožnost uživatele a zkontrolovat, zda má oprávnění přistupovat k určitým funkcím a datům v aplikaci
- podporuje různé způsoby autentizace (ověření pomocí hesla, externích poskytovatelů (GOOGLE, FACEBOOK, nebo pomocí certifikátů)
- Rozšiřuje databázi – potřeba Entity Framework (ukládání loginu, hesla, tokenu, ...)
- Rozšiřuje původní DbContext o několik dalších tabulek – Users, Roles, ...
- Umožňuje **scaffoldovat** (generovat) stránky pro identitu
