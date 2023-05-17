# Procesory

`Struktura současných procesorů (x86/64). Techniky optimalizace provádění instrukcí, snižování spotřeby. Rozšířené instrukční sady`

## CPU

- `Central Processing Unit`
- provádí instrukce
- s vyšší frekvencí pracuje rychleji
  - ovšem se více zahřívá

### Struktura

- **ALU**
  - `arimeticko-logická jednotka`
  - provádí operace s čísly a logické operace
- **řadič**
  - stará se o řízení ostatních jednotek
- **registry**
  - vnitřní paměť, do kterých se ukládají mezivýsledky
  - velmi rychlé
- **cache**
  - vyrovnávací paměť

### Architektury

- x86-64
  - nejrozšířenejší v PC
  - verze x86 pro 64bit
- ARM
  - nízká spotřeba
  - především pro mobilní telefony a podobná zařízení

## Optimalizace provádění instrukcí

- techniky zvýšení výkonu
  - zvýšení počtu tranzistorů
  - zvýšení taktovacích frekvencí
  - snížení šířky spojů
- rozšíření bitové šířky zpracovávaných dat
  - počet bitů, které cpu dokážou v jedné instrukci zpracovat
- zvýšení počtu pracovních registrů
  - registry jsou nejrychlejší úroveň paměti
- fronta instrukcí
- pipelining
  - současné zpracování většího množství instrukcí
  - každá instrukce se nachází v jiné fázi zpracování
- VLIW
  - `Very Long Instruction Word`
  - explicitní paralelní zpracování instrukcí
  - ALU umístěny paralelně vedle sebe
  - možnost vykonávat operace současně
  - speciální formát operačních kódů
- superskalární architektura
  - v jednom taktu více než jedna instrukce
  - např. dvě ALU, dvě jednotky pro adresaci, dvě jednotky pro provádění skoků
- prediktory skoků
  - odhadování provedení skoku
- SIMD
  - `Single Instruction Multiple Data`
  - jedna instrukce může zpracovat větší množství dat

## Snižování spotřeby

- CPU
  - snížit clockrate
  - 'vypne' nepoužívaná jádra
  - 'vypne' vyrovnávací paměti
  - Intel nově využívá **E core** a **P core**
    - efficieny a power
- GPU
  - použije se integrovaná GPU místo dedikované
- Periferie
  - 'vypnutí' periferií
  - použiji SSD místo HDD
- Monitor
  - vypnu ho sám
- Windows
  - režim spánku

## Rozšířené instrukční sady

- skupina nových instrukcí, které rozšiřují danou instrukční sadu
- MMX (Multi Media Extension)
  - Intel
  - obsahuje SIMD operace
  - pouze integer
- 3DNow!
  - AMD
  - odpověd na MMX
  - umí vše, co MMX
  - navíc podporuje desetinná čísla
  - za účelem rychlých 3D operací s desetinnými čísly
- SSE
  - Intel
  - přidává 128bit registry
  - přidává nové instrukce
- AVX
  - vylepšení SSE
  - namísto 128bit registrů přidává 256bit registry
  - přidává upravené instrukce pro 256bit
