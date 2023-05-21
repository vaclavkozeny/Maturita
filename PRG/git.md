# Verzovací systémy

`Verzovací systémy, Git, repozitář, commit, větev`

## Verzovací systémy

- používán pro správu změn v kódu během vývoje
- zachovávání historie (a evidence změn) celého projektu
- možnost vrátit se ke starší verzi
- umožnění spolupráce více osob na jednom projektu

- **centralizovaný**
  - historie změn uložena na serveru
  - pro práci se systémem je potřeba online komunikace se serverem
- **distribuovaný**
  - každý může mít historii změn uloženou lokálně
  - umožňuje práci na různých větvích
  - Git, Mercurial

### Git

- distibuovaný verzovací systém
- při commitu neukládá seznam změn, ale snapshot
  - snímek nových a změněných souborů a odkazy na ně
  - pokud se soubor nezměnil, tak použije Git odkaz na soubor z předchozí verze

### Repozitář

- datové uložiště verzovacího systému
- dělění:
  - lokální - na PC uživatele
  - vzdálený - na web. poskytovateli (GitHub / GitLab)
- do repozitáře se ukládá kód
- pro vzdálený repozitář se většinou používá název "origin" a pro hlavní větev název "master" / "main"

<image src="./images/reop.png">

#### Commit

- uložení změn
- příkaz **git commit** uloží změny lokálně

- stavy souboru
  - Untracked
    - Git o něm neví a neřídí ho
  - Staged
    - příkaz **git add**
    - soubor se připravuje k zahrnutí v následujícím commitu
  - Modified
    - Git ví o změně
    - soubor musí aktualizovat v následujícím commitu
  - Deleted
    - pokud byl soubor odebrán
    - Git si toho všimne a soubor bude odebrán ze sledovaných souborů při následujícím commitu

### Větev

- posloupnost commitů daného projektu
- každý vzdálený repozitář má min. 1 větev, může jich mít víc
- větve lze spojovat dohromady (merge)
  - díky tomu lze vytvářet různé verze projektu a oddělovat je

#### Kolize

- Sloučení větví (Merging Branches)
  - provádí se změny provedené v každé z nich a vytváří se nová větev
  - pokud jsou v konfliktu, vrací se chybové hlášení
  - v případech, kdy jsou změny relativněmalé a navzájem kompatibilní
- Přepisování větví (Branch Rebase)
  - změny z jedné větve se aplikují na druhou větev
  - v případech, kdy jsou změny relativněrozsáhlé

### Příkazy

- **git init**
  - vytvoří v aktuální složce lokální repozitář
- **git add --all**
  - přidá vybrané soubory (. = všechno) do tzv. staging area
- **git commit -m „název commitu“**
  - vytvoří lokální commit ze souborů ve staging area
- **git remote add origin {adresa.git}**
  - přidá k lokálnímu repozitáři odkaz na repozitář vzdálený, lokálně pojmenovaný origin
- **git push origin main**
  - nahraje lokální stav do vzdáleného repozitáře
- **git fetch**
  - stáhne data z remote
- **git merge**
- **git pull**
  - fetch + merge
- **git clone {adresa.git}**
  - naklonuje remote
