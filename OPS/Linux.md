# Linux

`Výběr operačního systému (vhodné distribuce Linuxu)
Instalace operačního systému, připojení uživatelů
Druhy souborových systémů používaných v současných verzích OS
Koncepce souborového systému, stromová struktura, druhy souborů
Práva a oprávnění, nastavení oprávnění pro soubory (rwx), databáze uživatelů a hesel,
Změna vlastníka a oprávnění
`

## Popis

- svobodný a otevřený operační systém
- založen na **linux kernel**

## Výběr operačního systému

- podle potřeb uživatele
- různé distribuce
  - Kali
  - Ubuntu
  - Linux mint
- různé Desktop enviroment
  - Gnome
  - KDE
  - XFCE

## Instalace operačního systému

- většinou si lze vybrat mezi textovou a grafickou verzí
- kromě OS se nainstaluje i potřebný software k ovládání
  - terminal
  - prohlížeč
  - ...

## Připojení uživatelů

- konzole -> připojení přes Telnet / SSH (i lokálně)

## Souborový systém

- zajišťuje ukládání a čtení dat

<image src="./images/filesystem.webp">

- hierarchicky se ukládají v podobě souborů a adresářů
- nepoužívá disky (C:\, D:\ ) jako základ struktury
- základem je root (/)
- honorable mentions
  - /bin - binární soubory, zaručují chod systému (C:\Program Files)
  - /lib - knihovny pro chod systému
  - /proc - informace o běžících procesech
  - /home - domovský adresář všech uživatelů (C:\Users)
  - /media (CD mechanika) a /mnt (disky) - další úložiště

<image src="./images/linuxfiles.png">

### Druhy souborových systémů

- Linux: hlavně ext...
- **EXT2**
  - second extended file system
  - lze vytvářet speciální druhy souborů, adresáře
- **EXT3**
  - third extended filesystem
  - zpětně kompatibilní
  - komplexní datové struktury, implementace stromů, lze měnit velikost za běhu
- **EXT4**
  - fourth extended filesystem
  - zvýšen limit maximální velikosti
  - nanosekundová časová razítka
  - pre-alokace
- **NTFS**
  - pro Windows
  - Linux je umožňuje číst
  - nezmiňovat před Prokešem pokud se nezeptá!

### Druhy souborů

- **soubor**
  - obsahuje data
  - jméno + atributy
- **adresář**
  - directory
  - obsahuje jména souborů a adresářů
  - . odkaz sám na sebe
  - .. odkaz na rodiče
- **odkaz**
  - symbolický
    - odakz na jméno souboru
  - pevný
    - jiné jméno pro stejný soubor
- **pipe**
  - propojení dvou programů

### Práva a oprávnění

- každý soubor i adresář mají vlastníka
- vlastník
  - vytvořil soubor
  - převzal vlastnictví souboru
- práva
  - tři skupiny
    - **Owner** (první trojice bitů)
    - **Group** (druhý trojice bitů)
    - **Other** (třetí trojice bitů)
  - tři druhy
    - **Read**
    - **Write**
    - **Execute** (u directory možnost vstupu)

<image src="./images/prava1.PNG">

- d
  - typ souboru (složka)
- rwxr-xr-x
  - oprávnění
- čísla - 4, 34
  - počet pevných odkazů
- první root
  - vlastník
- druhý root
  - skupina vlastníků
- velikost v bytech
- datum poslední úpravy
- název složky

<image src="./images/prava.png">

- **SUID**
  - bežný uživatel získá oprávnění vlastníka
- **SGID**
  - soubory a adresáře uvnitř rodiče přebírají oprávnění (SAMBA)
- **Sticky bit**
  - všichni mají přístup
  - sticky bit zakazuje mazání a přepisování

### Databáze uživatelů a hesel

- informace o uživatelských účtech jsou uloženy v konfiguračních souborech:
  - `/etc/passwd`
  - `/etc/group`
  - `/etc/shadow`
  - `/etc/sudoers`

### Změna vlastníka a oprávnění

- může provádět pouze administrátor (root)
- příkaz `chown`
