<p>

# Indholdsfortegnelse

[2 Introduktion](<p>

#introduktion)

[3 Generelt omkring sikkerhed for nye komponenter i EHMI](<p>

#generelt-omkring-sikkerhed-for-nye-komponenter-i-ehmi)

[3.1 Generelle sikkerhedsmæssige forudsætninger for komponenter i forsendelseskæden](<p>

#generelle-sikkerhedsmæssige-forudsætninger-for-komponenter-i-forsendelseskæden)

[4 Opgavespecificeringer - sikkerhed vedrørende meddelelseskommunikation](<p>

#opgavespecificeringer---sikkerhed-vedrørende-punkt-til-punkt-meddelelseskommunikation)

[4.1 Decentralt vedrørende sikkerhed](<p>

#decentralt-vedrørende-sikkerhed)

[4.2 Alle komponenter stand-alone - implementeret på forskellige servere](<p>

#alle-komponenter-stand-alone---implementeret-på-forskellige-servere)

[4.3 Alle komponenter stand-alone - grupperet sammen på samme server](<p>

#alle-komponenter-stand-alone---grupperet-sammen-på-samme-server)

[4.4 Alle komponenter stand-alone - afsendende fagsystem og MSH grupperet sammen på samme server](<p>

#alle-komponenter-stand-alone---afsendende-fagsystem-og-msh-grupperet-sammen-på-samme-server)

[4.5 Alle komponenter stand-alone, MSH og AP grupperet sammen på samme server](<p>

#alle-komponenter-stand-alone-msh-og-ap-grupperet-sammen-på-samme-server)

[4.6 Afsendende fagsystem stand-alone - MSH/AP sammenbygget - implementeret på forskellige servere](<p>

#afsendende-fagsystem-stand-alone---mshap-sammenbygget---implementeret-på-forskellige-servere)

[4.7 Afsendende fagsystem stand-alone - MSH/AP sammenbygget – alle grupperet sammen på samme server](<p>

#afsendende-fagsystem-stand-alone---mshap-sammenbygget--alle-grupperet-sammen-på-samme-server)

[4.8 Afsendende fagsystem/MSH sammenbygget – AP stand-alone - implementeret på forskellige servere](<p>

#afsendende-fagsystemmsh-sammenbygget--ap-stand-alone---implementeret-på-forskellige-servere)

[4.9 Afsendende fagsystem/MSH sammenbygget – AP stand-alone – alle grupperet sammen på samme server](<p>

#afsendende-fagsystemmsh-sammenbygget--ap-stand-alone--alle-grupperet-sammen-på-samme-server)

[4.10 Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget - implementeret på forskellige servere](<p>

#afsendende-fagsystemmsh-sammenbygget--mshap-sammenbygget---implementeret-på-forskellige-servere)

[4.11 Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget – alle grupperet sammen på samme server](<p>

#afsendende-fagsystemmsh-sammenbygget--mshap-sammenbygget--alle-grupperet-sammen-på-samme-server)

[4.12 Alle komponenter sammenbyggede](<p>

#alle-komponenter-sammenbyggede)

[4.13 Modtagersiden](<p>

#_Toc150964819)

[5 Sikkerhedsspecificeringer vedrørende forsendelsesstatus af meddelelser](<p>

#_Toc150964820)

[5.1 Opsamling til repositorie](<p>

#opsamling-til-repositorie)

[5.1.1 Decentralt vedrørende sikkerhed for EHMI-komponent: Forsendelsesstatus - indberetning](<p>

#decentralt-vedrørende-sikkerhed-for-ehmi-komponent-forsendelsesstatus---indberetning)

[5.2 Udstilling via service](<p>

#_Toc150964823)

[5.2.1 Decentralt vedrørende sikkerhed for EHMI-komponent: Forsendelsesstatus - udsøgning](<p>

#_Toc150964824)

[6 Sikkerhedsspecificeringer vedrørende Sundhedsadressering](<p>

#_Toc150964825)

[6.1 Decentral vedrørende EHMI-komponent: Sundhedsadresseringsservice](<p>

#_Toc150964826)

[7 Relevante links:](<p>

#relevante-links)

<p>

## Introduktion

I MedCom13 har MedCom et fælles afprøvningsprojekt ’Kommunale prøvesvar på ny infrastruktur’, hvor MedComs to centrale moderniseringsspor kobles: FHIR og EHMI, hvor såvel meddelelseskommunikationen som infrastrukturen moderniseres. Moderniseringen sker grundet behov for kvalitetsløft af bl.a. sikkerhed, gennemsigtighed, robusthed og effektiv, international digital meddelelseskommunikation.

I projektet gennemføres en afprøvning i drift fra d. 1. marts til d. 31. maj 2025.

I afprøvningen skal den nye FHIR-standard for kommunale prøvesvar sendes fra kommunale akutfunktioner (EOJ) til almen lægepraksis (LPS) via den nye infrastruktur EHMI (Enhanced Healthcare Messaging Infrastructure).

Forsendelsen af standarden skal ske via den nye underliggende eDelivery infrastruktur, og der skal ligeledes ske en afprøvning af EHMI-funktionaliteter så som dokumentdeling og forsendelsesstatus (Track’n’Trace).

<p>

## Generelt omkring sikkerhed for nye komponenter i EHMI

Det er muligt at indrapportere og tilgå data via et FHIR API. Web-services/RESTful-services, der udstilles via et sådant interface, skal, præcis ligesom øvrige nationale web-services på sundhedsområdet, overholde national arkitektur og nationale standarder.

Det betyder bl.a., at ved personhenførbare oplysninger:

Der skal ske en stærk autentifikation af brugere (svarende til NIST niveau 3-4 eller NSIS niveau ”betydeligt”)

1.  Der skal foretages adgangskontrol baseret på nationalt standardiseret information (attributter)
2.  Samtykke/frabedelse og behandlingsrelation skal tjekkes op mod den nationale samtykkeservice og den nationale behandlingsrelationsservice
3.  Oplysninger om sundhedspersoners adgang til persondata skal kunne ses af borgeren via MinLog


<p>

### Generelle sikkerhedsmæssige forudsætninger for komponenter i forsendelseskæden

Følgende definitioner for alle systemer/komponenter i EHMI er gældende:

-   Systemer/komponenter kan være en stand-alone applikation eller **sammenbygget** med en eller flere andre systemer/komponenter i meddelelsesflowet.
-   Systemer/komponenter kan være en stand-alone applikation **grupperet sammen** med en eller flere andre systemer/komponenter i meddelelsesflowet på samme server.


<p>

## Opgavespecificeringer - sikkerhed vedrørende punkt til punkt meddelelseskommunikation


<p>

### Decentralt vedrørende sikkerhed

Følgende tabel illustrerer generelt, hvordan retningslinjerne er vedrørende sikkerhed i meddelelsesflowet i EHMI.

| **EHMI Komponenter**                                              | **Delopgave**                                                                                                                                      | **Hvem**                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|
| Mellem stand-alone komponenter/services.                          | **Autenticitetshåndtering:** Implementering af signering af forsendelse.                                                                           | Afsenderkomponent          |
| Mellem stand-alone komponenter/services.                          | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                                             | Modtagerkomponent          |
| Mellem komponenter/services, der håndteres på forskellige servere | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse / meddelelsesindhold / kuvert via sikret transportprotokol, f.eks. TLS | Afsender/modtagerkomponent |


**Autenticitetshåndtering mellem C1 og C2 (jf. Målbilledets afsnit 6.1.1):**

*På sundhedsområdet stilles krav om, at meddelelse og/eller konvolutten signeres i C1 og at denne signatur efterfølgende verificeres i C2. På denne måde sikres autentifikation af C1 i C2. Denne autentifikation vil være en del af den aftale, der indgås imellem AP’et og det system AP’et agerer på vegne af. Sikres ved* eksplicit signering mellem Afsendende fagsystem/MSH/AP (med tilhørende verifikation) på systembevisniveau (VOCES/FOCES/Niveau 3). Dette kan eksempelvis sikres via DGWS/IDWS eller lignende.


**Integritetssikring mellem C1 og C2 (jf. Målbilledets afsnit 6.1.2):**

*Sikres ud over den under autenticitet (afsnit 6.1.1) beskrevne konvolutsignering via de protokoller, der anvendes imellem AP’erne og de systemer AP’erne agerer på vegne af – f.eks. TLS (Transport Layer Security).*


**Fortrolighedssikring mellem C1 og C2 (jf. Målbilledets afsnit 6.1.4):**

*Da alle meddelelser under sundhedsdomænet som udgangspunkt indeholder følsomme personoplysninger, skal kryptering anvendes, hvor det er muligt. Meddelelsen skal derfor krypteres imellem afsender og afsendende AP via MSH (C1 og C2) samt imellem modtagende AP og modtager via MSH (C3 og C4). Anvendelse af denne kryptering vil være en del af den aftale, der indgås imellem AP’et og det system AP’et agerer på vegne af. Sikres som via Integritetssikring.*

*Ovenstående gælder også for al kommunikation mellem C3 og C4.*


<p>

### Alle komponenter stand-alone - implementeret på forskellige servere

<p>

![](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**                              | **Delopgave**                                                                                                                 | **Hvem**                    |
|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Afsendende fagsystem stand-alone                  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem        |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH                         |
| Afsendende fagsystem stand-alone MSH stand-alone  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem og MSH |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | MSH                         |
| AP stand-alone                                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                          |
| MSH stand-alone AP stand-alone                    | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | MSH og AP                   |


<p>

### Alle komponenter stand-alone - grupperet sammen på samme server


<p>

![Et billede, der indeholder tekst, skærmbillede, gul Automatisk genereret beskrivelse](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**              | **Delopgave**                                                          | **Hvem**             |
|-----------------------------------|------------------------------------------------------------------------|----------------------|
| Afsendende fagsystem stand-alone  | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem |
| MSH stand-alone                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | MSH                  |
| MSH stand-alone                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse | MSH                  |
| AP stand-alone                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | AP                   |


<p>

### Alle komponenter stand-alone - afsendende fagsystem og MSH grupperet sammen på samme server


<p>

![Et billede, der indeholder tekst, skærmbillede, gul Automatisk genereret beskrivelse](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**              | **Delopgave**                                                                                                                 | **Hvem**             |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Afsendende fagsystem stand-alone  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem |
| MSH stand-alone                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH                  |
| MSH stand-alone                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | MSH                  |
| AP stand-alone                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                   |
| MSH stand-alone AP stand-alone    | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | MSH og AP            |


<p>

### Alle komponenter stand-alone, MSH og AP grupperet sammen på samme server

<p>

#

<p>

![Et billede, der indeholder tekst, skærmbillede, gul Automatisk genereret beskrivelse](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**                              | **Delopgave**                                                                                                                 | **Hvem**                     |
|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| Afsendende fagsystem stand-alone                  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem         |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH                          |
| Afsendende fagsystem stand-alone MSH stand-alone  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem og MSH  |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | MSH                          |
| AP stand-alone                                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                           |

<p>

### Afsendende fagsystem stand-alone - MSH/AP sammenbygget - implementeret på forskellige servere

<p>

![](media/584f59d0d6bb7e4f94aea46de8eb249c.png)

| **EHMI Komponenter**                    | **Delopgave**                                                                                                                 | **Hvem**                       |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| Afsendende fagsystem stand-alone        | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem           |
| MSH/AP                                  | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH/AP                         |
| Afsendende fagsystem stand-alone MSH/AP | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem og MSH/AP |

<p>

### Afsendende fagsystem stand-alone - MSH/AP sammenbygget – alle grupperet sammen på samme server

<p>

![Et billede, der indeholder tekst, skærmbillede, Rektangel, linje/række Automatisk genereret beskrivelse](media/584f59d0d6bb7e4f94aea46de8eb249c.png)

| **EHMI Komponenter**              | **Delopgave**                                                          | **Hvem**             |
|-----------------------------------|------------------------------------------------------------------------|----------------------|
| Afsendende fagsystem stand-alone  | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem |
| MSH/AP                            | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | MSH/AP               |

<p>

### Afsendende fagsystem/MSH sammenbygget – AP stand-alone - implementeret på forskellige servere

<p>

![Et billede, der indeholder tekst, skærmbillede, gul, design Automatisk genereret beskrivelse](media/be1c6e9b30bae64a8f5738170ef00b20.png)

| **EHMI Komponenter**                      | **Delopgave**                                                                                                                 | **Hvem**                       |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| Afsendende fagsystem/MSH                  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem/MSH       |
| AP Stand-alone                            | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                             |
| Afsendende fagsystem/MSH  AP Stand-alone  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem/MSH og AP |

<p>

### Afsendende fagsystem/MSH sammenbygget – AP stand-alone – alle grupperet sammen på samme server

<p>

![](media/be1c6e9b30bae64a8f5738170ef00b20.png)

| **EHMI Komponenter**     | **Delopgave**                                                          | **Hvem**                 |
|--------------------------|------------------------------------------------------------------------|--------------------------|
| Afsendende fagsystem/MSH | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem/MSH |
| AP Stand-alone           | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | AP                       |

<p>

### Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget - implementeret på forskellige servere

Vi har erfaret gennem samtaler med de deltagende parter, at et scenarie som dette kan være muligt. I så fald er det vigtigt at parter med et sådant setup aftaler, hvilken MSH, der er primær med udfyldelse af MSH forpligtelserne og hvilken MSH, der blot viderestiller informationer til næste led i kæden. Når dette er på plads, vil følgende sikkerhedsanvisninger være gældende.

<p>

![](media/dc36c10735cb86a5499e120b23a83c79.png)

| **EHMI Komponenter**                | **Delopgave**                                                                                                                 | **Hvem**                           |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| Afsendende fagsystem/MSH            | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem/MSH           |
| Afsendende MSH/AP                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH/AP                             |
| Afsendende fagsystem/MSH og MSH/AP  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem/MSH og MSH/AP |

<p>

### Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget – alle grupperet sammen på samme server

Som for 4.10.

<p>

![Et billede, der indeholder skærmbillede, linje/række, Rektangel, diagram Automatisk genereret beskrivelse](media/dc36c10735cb86a5499e120b23a83c79.png)

| **EHMI Komponenter**     | **Delopgave**                                                          | **Hvem**                 |
|--------------------------|------------------------------------------------------------------------|--------------------------|
| Afsendende fagsystem/MSH | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem/MSH |
| Afsendende MSH/AP        | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | MSH/AP                   |

<p>

### Alle komponenter sammenbyggede

<p>

![](media/5d46ee72c0eb16cfc1d678185c7baa53.png)

Da alle komponenter her er sammenbyggede, håndteres al sikkerhed internt i sammenbygningen, og der er derfor ikke behov for eksplicit at udtrykke noget om sikkerheden her.

<p>

### Modtagersiden

Ovenstående er kun beskrevet, hvordan sikkerheden ser ud på afsendersiden. De tilsvarende mekanismer implementeres naturligvis også på modtagersider, hvor de så bare anvendes i den modsatte rækkefølge og med de tilsvarende aktører i modsat rækkefølge.

<p>

## Sikkerhedsspecificeringer vedrørende forsendelsesstatus af meddelelser

Sikkerhed i forhold til forsendelses-status opdeles i de forskellige trin:

1.  Forsendelsesstatus opsamles og gemmes i et repositorie
    1.  Forsendelsesstatus hentes af anvendere via udstillede services

<p>

### Opsamling til repositorie

Fra målbilledet ved vi, at sikkerhed omkring dette er nødvendigt dels for, at anvenderne vil anse servicen baseret på de opsamlede data for troværdig, og dels fordi der opsamles personoplysninger, da unik borgeridentifikation (oftest CPR-nummeret), for den borger meddelelsen omhandler, er en del af den opsamlede information:

-   **Autenticitet:** En komponent, der gemmer forsendelsesstatus for meddelelser, skal autentificere sig når den tilgår repositoriet.
-   **Tilgængelighed:** Aftalt oppetid og svartid skal sikres via standard driftsmekanismer. Dette er særlig vigtigt her, da forsendelsesstatus, jf. afsnit 5.2.8, skal være tæt på realtidsopdateret.
-   **Integritet:** Sikres af den protokol, som opsamlingen implementeres via.
-   **Uafviselighed:** En komponent, der gemmer forsendelsesstatus, skal audit logge opsamlingen på en standardiseret måde.
-   **Fortrolighed:** Når den opsamlede forsendelsesstatus kommunikeres til repositoriet, sikres den enten via eksplicit kryptering eller implicit kryptering på det underliggende infrastruktur niveau.

<p>

#### Decentralt vedrørende sikkerhed for EHMI-komponent: Forsendelsesstatus - indberetning

| **EHMI Komponenter**                                                         | **Delopgave**                                                                                                                       | **Hvem**                                                                    |
|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| Forsendelsesstatus-komponent                                                 | **Autenticitet:** En komponent, der gemmer forsendelsesstatus for meddelelser, skal autentificere sig når den tilgår repositoriet.  | Afsendende system (Afsendende fagsystem/MSH/AP)                             |
| Afsendende system (Afsendende fagsystem/MSH/AP)                              | **Autenticitetshåndtering:** Implementering af signering af indberetning                                                            | Afsendende system (Afsendende fagsystem/MSH/AP)                             |
| Forsendelsesstatus-komponent                                                 | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                              | Forsendelsesstatuskomponent                                                 |
| Afsendende system (Afsendende fagsystem/MSH/AP) Forsendelsesstatus-komponent | **Integritetssikring og fortrolighedssikring:** Kommunikation via sikret transportprotokol, f.eks. TLS                              | Afsendende system (Afsendende fagsystem/MSH/AP) Forsendelsesstatuskomponent |
| Afsendende system (Afsendende fagsystem/MSH/AP) Forsendelsesstatus-komponent | **Tilgængelighed:** Implementering af kø mekanisme til at håndtere at en forbindelse kan være nede                                  | Afsendende system (Afsendende fagsystem/MSH/AP) Forsendelsesstatuskomponent |

<p>

### Indberetninger ift. scenarierne i afsnit 4.

I det følgende antages begge sider af afsender- og modtagerøkosystemerne at have samme setup til hinanden som det afsendende økosystem. I praksis er dette naturligvis meget forskelligt, og der skal i så fald kombineres

| **Scenarier**                        | **Skabende/Indgående indberetning**                                                                                             | **Afsluttende/udgående indberetning**                                                                                          |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Kap. 4.2 Kap. 4.3 Kap. 4.4 Kap. 4.5  | Afsendende fagsystem  Afsendende MSH  Afsendende AP ------------------------------------------- Modtagende AP  Modtagende MSH   |  Afsendende MSH  Afsendende AP ------------------------------------------- Modtagende AP  Modtagende MSH  Modtagende fagsystem |
| Kap. 4.6 Kap. 4.7                    | Afsendende fagsystem  Afsendende MSH/AP ------------------------------------------- Modtagende MSH/AP                           |  Afsendende MSH/AP  ------------------------------------------- Modtagende MSH/AP Modtagende fagsystem                         |
| Kap. 4.8 Kap. 4.9                    | Afsendende fagsystem/MSH Afsendende AP ------------------------------------------- Modtagende AP                                |  Afsendende AP  ------------------------------------------- Modtagende AP Modtagende fagsystem/MSH                             |
| Kap. 4.10 Kap. 4.11                  | Afsendende fagsystem/MSH Afsendende AP/MSH ------------------------------------------- Modtagende AP/MSH                        |  Afsendende AP/MSH ------------------------------------------- Modtagende AP/MSH Modtagende fagsystem/MSH                      |
| Kap. 4.12                            | Afsendende fagsystem/MSH/AP                                                                                                     | Modtagende fagsystem/MSH/AP                                                                                                    |

<p>

### Udstilling via service

Fra målbilledet ved vi, at servicen, der udstiller forsendelsesstatus for meddelelser, skal overholde de samme sikkerhedskrav og -regler som øvrige services på sundhedsområdet, jf. målbilledets princip PT6. Derfor bør flere af de samme allerede eksisterende sikkerhedsmekanismer fra disse andre services anvendes:

-   **Autenticitet:** Servicen skal udstilles som en DGWS/IDWS service eller lignende niveau, og anvenderne (både systemer, sundhedspersoner og borgere) skal anvende digitale certifikater i forbindelse med kald til servicen på samme måde som for andre services på sundhedsområdet, og det er (igen) et krav, at de anvendte certifikater er på personbevisniveau. For systemer dog systembevisniveau.
-   **Tilgængelighed:** Aftalt oppetid og svartid sikres via den platform, som servicen afvikles på
-   **Integritet:** Sikres af den protokol, som servicen er implementeret med.
-   **Uafviselighed:** Servicen implementerer standardiseret audit log. Logning til MinLog er påkrævet i tilfældene hvor en borger henter forsendelsesstatus for meddelelser angående en anden borger end sig selv, og hvor en sundhedsperson henter forsendelsesstatus specifikt for en borger.
-   **Fortrolighed:** Servicen skal aktivt anvende den identifikation af anvenderen (system, sundhedsperson eller borger) samt de søgeparametre, der er en del af kaldet af servicen.

Da servicen udstilles og afvikles på en platform, der kan have sine egne mere strikse sikkerhedspolitikker end de generelle på sundhedsområdet, skal disse i givet fald også overholdes.

<p>

#### Decentralt vedrørende sikkerhed for EHMI-komponent: Forsendelsesstatus - udsøgning

Det vil blive baseret på et OAuth-sikret REST-interface og SMART-on-FHIR eller lignende.

For opsamling af forsendelsesstatus stilles der krav om, at der jf. målbilledets afsnit 6.3.1 eksplicit signeres mellem forsendelsesstatus ”klienten” og ”serveren” (med tilhørende verifikation) på systembevisniveau (VOCES/FOCES/Niveau 3).

For søgning af forsendelsesstatus stilles der krav om, at der mellem forsendelsesstatus ”klienten” og ”serveren” anvendes identifikation på systembevisniveau (VOCES/FOCES/Niveau 3).

For søgning af forsendelsesstatus stilles der derudover krav om, at der ved borgers egen adgang og en klinikers specifikke adgang via borgerens/patientens journal anvendes identifikation på personbevisniveau (MOCES/MitID/Niveau 4).

| **EHMI Komponenter**                                                 | **Delopgave**                                                                                                                 | **Hvem**                                                             |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Afsendende system (Afsendende fagsystem/MSH/AP)                      | **Autenticitetshåndtering:** Implementering af signering af indberetning                                                      | Afsendende system (Afsendende fagsystem/MSH/AP)                      |
| Modtagende komponent                                                 | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | Modtagende komponent                                                 |
| Afsendende system (Afsendende fagsystem/MSH/AP) Modtagende komponent | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende system (Afsendende fagsystem/MSH/AP) Modtagende komponent |

<p>

## Sikkerhedsspecificeringer vedrørende Sundhedsadressering

Fra målbilledet ved vi, at sundhedsadresseringsservicen skal overholde de samme sikkerhedskrav og -regler som tilsvarende services på sundhedsområdet, og derfor bør flere af de samme allerede eksisterende sikkerhedsmekanismer anvendes:

-   **Autenticitet:** Servicen skal udstilles som en DGWS/IDWS service, og anvenderne skal anvende digitale certifikater i forbindelse med kald til servicen på samme måde som for tilsvarende services på sundhedsområdet. På grund af denne service’ natur er det imidlertid i dette tilfælde tilstrækkeligt, at de anvendte certifikater er på systembevisniveau.
-   **Tilgængelighed:** Aftalt oppetid og svartid skal sikres via den platform, som servicen afvikles på – f.eks. via standard driftsmekanismer som fail-over og load-balancere.
-   **Integritet:** Sikres af den protokol, som servicen er implementeret med.
-   **Uafviselighed:** Servicen skal implementere standardiseret audit log.
-   **Fortrolighed:** Servicen skal anvende den identifikation af anvenderen samt de søgeparametre, der er en del af kaldet af servicen, men en egentlig brugerstyring i forhold til hvem, der kalder servicen, antages håndhævet af de kaldende systemer, så når et anvendersystem er korrekt autentificeret, er der adgang til servicen.

Da servicen udstilles og afvikles på en platform, der kan have sine egne mere strikse sikkerhedspolitikker end de generelle på sundhedsområdet, skal disse i givet fald også overholdes.

<p>

### Decentral vedrørende EHMI-komponent: Sundhedsadresseringsservice

| **EHMI Komponenter**                                       | **Delopgave**                                                                                                                                                                                                                        | **Hvem**                                                  |
|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Afsendende system (Fagsystem)                              | **Autenticitetshåndtering:** Implementering af signering af søgning (VOCES/FOCES)                                                                                                                                                    | Afsendende system (Fagsystem)                             |
| Sundheds-adresseringsservice                               | **Autenticitetshåndtering:** Verifikation af signering (VOCES/FOCES)                                                                                                                                                                 | Sundhedsadresseringsservice                               |
| Afsendende system (Fagsystem) Sundheds-adresseringsservice | **Integritetssikring og fortrolighedssikring:** Kommunikation sikret via transportprotokol, f.eks. TLS                                                                                                                               | Afsendende system (Fagsystem) Sundhedsadresseringsservice |
| Afsendende system (Fagsystem) Sundheds-adresseringsservice | **Tilgængelighed:** Implementering af faste søgninger, som evt. kan gemmes lokalt til at håndtere at en forbindelse kan være nede.  Hvis servicen er online bør altid søges online. Faste søgninger bør opdateres udenfor peaktimes. | Afsendende system (Fagsystem) Sundhedsadresseringsservice |

<p>

## Relevante links:

-   Dansk:
    -   Målbillede for meddelelseskommunikation på sundhedsområdet (<https://sundhedsdatastyrelsen.dk/-/media/sds/filer/rammer-og-retningslinjer/referenceaktitektur-og-it-standarder/referencearkitektur/maalbillede-for-meddelelseskommunikation.pdf>)
    -   SDN (<https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/>)
-   Engelsk:
    -   EU eDelivery (<https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/eDelivery>)
    -   EU AP specifikationer (<https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/Access+Point+specifications>)
    -   EU PEPPOL SBDH envelope (<https://docs.peppol.eu/edelivery/envelope/Peppol-EDN-Business-Message-Envelope-2.0.0-2023-03-13.pdf>)
    -   IHE BALP (<https://profiles.ihe.net/ITI/BALP/index.html>)
