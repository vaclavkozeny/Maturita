# IPv4

## Popis
- 32 bit adresa
    - rozsah 0-255

## Třídy
- **A**
    - první bit 0
    - 1 - 127 => první byte
    - maska /8
    - 2^24 - 2 adres (16 mil)
- **B**
    - první bity 10
    - 128 - 191 => první byte
    - maska /16
    - 2^16 - 2 adres (65 534)
- **C**
    - první bity 110
    - 192-223 => první byte
    - maska /24
    - 2^8 - 2 aderes (254)


## Speciální adresy
- 0.0.0.0 -> nespecifikovaná adresa
- 127.0.0.1 -> Loopback; localhost
- 255.255.255.255 -> Síťový broadcast
