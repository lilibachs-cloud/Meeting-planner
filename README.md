# Fagmøte-planlegger

En app for å planlegge fagmøter med flere foredragsholdere. Tidspunkt oppdateres automatisk ut fra varighet, pause/lunsj-rader får egen farge, og den ferdige planen kan limes rett inn i Word.

Appen kjøres fra nettleseren (Edge) og lagrer alle møteplaner i én delt fil i en intern nettverksmappe — ingen database eller pålogging er nødvendig.

## Oppsett (gjøres én gang av den som administrerer)

1. Last opp `index.html` til dette GitHub-repoet (filen må hete nøyaktig `index.html` for at GitHub Pages skal vise den automatisk på rot-lenken).
2. Gå til **Settings > Pages** i repoet, velg branch og mappe, og lagre. GitHub gir deg en offentlig lenke, i dette tilfellet:

   ```
   https://lilibachs-cloud.github.io/Meeting-planner/
   ```
3. Del denne lenken med alle som skal bruke appen.

## Første gang du (som bruker) åpner appen

1. Åpne lenken i **Edge**.
2. Skriv inn navnet ditt øverst i feltet **«Ditt navn»** — det brukes til å vise hvem som redigerer en plan.
3. Trykk **«📁 Koble til mappe»** og velg denne mappen:

   ```
   K:\Sensitivt\Klinikk\RMF_Kvalitetssikring\Meeting planner
   ```

   (Samme mappe skal velges av alle brukere.)
4. Godkjenn tilgang når Edge spør. Etter dette husker nettleseren valget på din PC, så du slipper å gjøre det på nytt neste gang du åpner lenken.

> Alle må gjøre steg 2–4 hver for seg, på sin egen PC — tilgangen deles ikke automatisk mellom kolleger.

## Personlig mappe eller delt mappe — du velger selv

Appen har ingen fast, innebygd mappe. Hver bruker velger selv hvilken mappe de kobler seg til når de trykker **«📁 Koble til mappe»**, og det kan tilpasses hvordan dere faktisk jobber:

- **Samarbeidsprosjekter**: koble deg til en felles mappe (f.eks. `Meeting planner`-mappen nevnt over) som du og kollegene dine har tilgang til sammen. Da ser og redigerer dere de samme planene.
- **Egne, private prosjekter**: koble deg i stedet til en personlig mappe (f.eks. din egen lokale mappe eller OneDrive-mappe). Da blir planene dine private — ingen andre ser dem.
- **Bytte fram og tilbake**: du kan når som helst trykke «📁 Koble til mappe» igjen og velge en annen mappe. Appen husker alltid kun **den sist tilkoblede mappen** — ikke flere samtidig — så husk å bytte tilbake til riktig mappe før du begynner å jobbe med et annet prosjekt.
- Mappe-indikatoren øverst i appen viser til enhver tid tydelig hvilken mappe du er koblet til akkurat nå, slik at du ikke er i tvil.

> Tips: Hvis en gruppe kolleger ikke har tilgang til den samme mappen som en annen gruppe, kan de rett og slett opprette sin egen felles mappe et sted de *har* tilgang sammen, og koble seg til den i stedet. Det krever ingen endring i selve appen.

## Daglig bruk

- **Ny plan**: trykk «+ Ny plan», fyll inn møtetittel, starttidspunkt og legg til rader for foredrag eller pause/lunsj.
- **Varighet** styrer automatisk tidspunktene i kolonnen til venstre.
- **Dra rader** med ☰-håndtaket for å endre rekkefølgen.
- **Lagre** skriver planen til den delte filen `fagmoteplaner.json` i nettverksmappen — synlig for alle andre med tilgang.
- **Åpne** henter en tidligere lagret plan fra listen.
- **Kopier for Word**: kopierer tabellen til utklippstavlen, klar til å limes inn i et Word-dokument med Ctrl+V. Merknad-kolonnen kan skrus av før kopiering.

## Om samtidig redigering

Når du åpner en plan, merkes den som «opptatt» av deg. Hvis en kollega prøver å åpne samme plan mens du redigerer, får de et varsel om at den er i bruk, med ditt navn og klokkeslett for når du sist var aktiv. Låsen fornyes automatisk hvert 20. sekund mens du har planen åpen, og slippes når du lagrer, bytter plan eller lukker fanen. Blir en fane lukket brått, løser låsen seg selv opp igjen etter 3 minutter.

Dette er en **myk advarsel**, ikke en absolutt sperre — to personer kan i teorien fortsatt lagre over hverandre hvis de velger å ignorere varselet. Snakk sammen internt om det, spesielt hvis flere pleier å redigere samme plan samtidig.

## Feilsøking

- **«Koble til mappe»-knappen dukker opp igjen etter en stund**: Edge har glemt tilgangen — bare trykk knappen og velg mappen på nytt.
- **Andre nettlesere enn Edge/Chrome**: Appen bruker en funksjon (File System Access API) som foreløpig kun støttes av Chromium-baserte nettlesere. Safari og Firefox fungerer ikke.
- **Ser ikke andres planer**: Sjekk at dere har koblet dere til nøyaktig samme mappe (samme sti).
