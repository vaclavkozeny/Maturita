# Ověřování identity v prostředí internetu

`Jméno, heslo, dvoufázové ověřování, biometrické ověřování, OAuth2, resource, owner, authorization server, OpenID, poskytovatelé ověření, access_token`

## Jméno a heslo

- nejjednodušší a nejpoužívanější způsob ověřování​
- heslo by mělo splňovat určité bezpečnostní požadavky​
  - velká písmena, číslice, speciální znaky​
- hesla by měla být uložena jako HASH, nikoliv jako šifra​
  - HASH nelze rozluštit zpětně​
  - MD5, SHA-1, SHA-2​

## Dvoufázové oveření

- kromě jména a hesla se oveřuje aplikací z jiného zařízení
  - SMS / autenticator / fyzický klíč
- útočník se případně musí zmocnit navíc uživatelova telefonu​
- bezpečnější než pouze jméno a heslo

## Biometrika

- jedinečné biologické charakteristiky
  - otisk prstu / obličej
- nemusí vždy fungovat
  - špinavé prsty
  - rouška

## OAuth2

- standard pro přihlašování (autorizaci)​
- pro ověřování používá Access Token​
  - náhodný token identifikující klientova oprávnění​

### Role

- **User**
  - člověk snažící se o přístup k **Resource​**
- **Resource**
  - chráněná data
- **Client**
  - aplikace (uživatel), žádající o přístup k datům
- **Resource owner**
  - uživatel umožňující klientovi přístup ke svým datům​
- **Resource Server**
  - API obsahující sdílená data
- **Authorization Server**
  - API poskytující ověření identity a vydávající přístupové tokeny

<image src="./images/oauth.PNG">

### Proces

- uživatel žádá gateway, aby mohl přistoupit k datům na API; gateway pošle token
- uživatel žádá API o data a přikládá token (zpravidla v Authorization headeru)
- API se ptá gatewaye, jestli může uživatel s daným tokenem přistoupit k datům
- jestli gateway potvrdí autorizaci uživatele, tak mu API posílá data

<image src="./images/proces.PNG">

### Authorization Grant

- použit klientem pro získání tokenu

- **Authorization Code**
  - komunikace mezi servery, výměna kódu za token, kód je krátkodobý​
- **Implicit**
  - komunikace s webovou nebo mobilní aplikací, zjednodušený, vyměňuje token za ID a secret​
- **Resource Owner Password Credentials**
  - důvěryhodné (vlastní) aplikace, ID a heslo jsou vyměněny rovnou za token​
- **Client Credentials**
  - API, komunikace bez kontextu uživatele​
- **Device Code**
  - jednoúčelová zařízení​
- **Refresh Token**
  - obnovení platnosti tokenu

## OpenID

- rozšíření OAuth2.0 o identity layer​
- token nese informaci o uživateli
- obvykle JWT token
  - sub = subject = ID uživatele​
  - iss = issuer = kdo token vydal​
  - aud = audience = client, kterému byl token poskytnut

## Poskytovatelé oveření

- Google
- Microsoft
- Facebook
- Apple
