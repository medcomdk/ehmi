# Specificering af sikkerhed ifm centrale og decentrale EHMI-services

## Indholdsfortegnelse

- [2 Introduktion](#introduktion)

- [3 Generelt omkring sikkerhed for nye komponenter i EHMI](#generelt-omkring-sikkerhed-for-nye-komponenter-i-ehmi)

- [3.1 Generelle sikkerhedsmæssige forudsætninger for komponenter i forsendelseskæden](#generelle-sikkerhedsmæssige-forudsætninger-for-komponenter-i-forsendelseskæden)

- [4 Opgavespecificeringer - sikkerhed vedrørende meddelelseskommunikation](#opgavespecificeringer---sikkerhed-vedrørende-punkt-til-punkt-meddelelseskommunikation)

- [4.1 Decentralt vedrørende sikkerhed](#decentralt-vedrørende-sikkerhed)

- [4.2 Alle komponenter stand-alone - implementeret på forskellige servere](#alle-komponenter-stand-alone---implementeret-på-forskellige-servere)

- [4.3 Alle komponenter stand-alone - grupperet sammen på samme server](#alle-komponenter-stand-alone---grupperet-sammen-på-samme-server)

- [4.4 Alle komponenter stand-alone - afsendende fagsystem og MSH grupperet sammen på samme server](#alle-komponenter-stand-alone---afsendende-fagsystem-og-msh-grupperet-sammen-på-samme-server)

- [4.5 Alle komponenter stand-alone, MSH og AP grupperet sammen på samme server](#alle-komponenter-stand-alone-msh-og-ap-grupperet-sammen-på-samme-server)

- [4.6 Afsendende fagsystem stand-alone - MSH/AP sammenbygget - implementeret på forskellige servere](#afsendende-fagsystem-stand-alone---mshap-sammenbygget---implementeret-på-forskellige-servere)

- [4.7 Afsendende fagsystem stand-alone - MSH/AP sammenbygget – alle grupperet sammen på samme server](#afsendende-fagsystem-stand-alone---mshap-sammenbygget--alle-grupperet-sammen-på-samme-server)

- [4.8 Afsendende fagsystem/MSH sammenbygget – AP stand-alone - implementeret på forskellige servere](#afsendende-fagsystemmsh-sammenbygget--ap-stand-alone---implementeret-på-forskellige-servere)

- [4.9 Afsendende fagsystem/MSH sammenbygget – AP stand-alone – alle grupperet sammen på samme server](#afsendende-fagsystemmsh-sammenbygget--ap-stand-alone--alle-grupperet-sammen-på-samme-server)

- [4.10 Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget - implementeret på forskellige servere](#afsendende-fagsystemmsh-sammenbygget--mshap-sammenbygget---implementeret-på-forskellige-servere)

- [4.11 Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget – alle grupperet sammen på samme server](#afsendende-fagsystemmsh-sammenbygget--mshap-sammenbygget--alle-grupperet-sammen-på-samme-server)

- [4.12 Alle komponenter sammenbyggede](#alle-komponenter-sammenbyggede)

- [4.13 Modtagersiden](#_Toc150964819)

***


## Introduktion

I MedCom13 har MedCom et fælles afprøvningsprojekt ’Kommunale prøvesvar på ny infrastruktur’, hvor MedComs to centrale moderniseringsspor kobles: FHIR og EHMI, hvor såvel meddelelseskommunikationen som infrastrukturen moderniseres. Moderniseringen sker grundet behov for kvalitetsløft af bl.a. sikkerhed, gennemsigtighed, robusthed og effektiv, international digital meddelelseskommunikation.

I projektet gennemføres en afprøvning i drift fra d. 1. marts til d. 31. maj 2025.

I afprøvningen skal den nye FHIR-standard for kommunale prøvesvar sendes fra kommunale akutfunktioner (EOJ) til almen lægepraksis (LPS) via den nye infrastruktur EHMI (Enhanced Healthcare Messaging Infrastructure).

Forsendelsen af standarden skal ske via den nye underliggende eDelivery infrastruktur, og der skal ligeledes ske en afprøvning af EHMI-funktionaliteter så som dokumentdeling og forsendelsesstatus (Track’n’Trace).

***


## Generelt omkring sikkerhed for nye komponenter i EHMI

Det er muligt at indrapportere og tilgå data via et FHIR API. Web-services/RESTful-services, der udstilles via et sådant interface, skal, præcis ligesom øvrige nationale web-services på sundhedsområdet, overholde national arkitektur og nationale standarder.

Det betyder bl.a., at ved personhenførbare oplysninger:

Der skal ske en stærk autentifikation af brugere (svarende til NIST niveau 3-4 eller NSIS niveau ”betydeligt”)

1.  Der skal foretages adgangskontrol baseret på nationalt standardiseret information (attributter)
2.  Samtykke/frabedelse og behandlingsrelation skal tjekkes op mod den nationale samtykkeservice og den nationale behandlingsrelationsservice
3.  Oplysninger om sundhedspersoners adgang til persondata skal kunne ses af borgeren via MinLog

***


## Generelle sikkerhedsmæssige definitioner for komponenter i forsendelseskæden

Følgende definitioner for alle systemer/komponenter i EHMI er gældende:

-   Systemer/komponenter kan være en stand-alone applikation eller **sammenbygget** med en eller flere andre systemer/komponenter i meddelelsesflowet.
-   Systemer/komponenter kan være en stand-alone applikation **grupperet sammen** med en eller flere andre systemer/komponenter i meddelelsesflowet på samme server.

***


## Opgavespecificeringer - sikkerhed vedrørende punkt til punkt meddelelseskommunikation

***


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

***


### Alle komponenter stand-alone - implementeret på forskellige servere

***


![](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**                              | **Delopgave**                                                                                                                 | **Hvem**                    |
|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Afsendende fagsystem stand-alone                  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem        |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH                         |
| Afsendende fagsystem stand-alone MSH stand-alone  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem og MSH |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | MSH                         |
| AP stand-alone                                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                          |
| MSH stand-alone AP stand-alone                    | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | MSH og AP                   |

***


### Alle komponenter stand-alone - grupperet sammen på samme server

***


![Et billede, der indeholder tekst, skærmbillede, gul Automatisk genereret beskrivelse](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**              | **Delopgave**                                                          | **Hvem**             |
|-----------------------------------|------------------------------------------------------------------------|----------------------|
| Afsendende fagsystem stand-alone  | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem |
| MSH stand-alone                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | MSH                  |
| MSH stand-alone                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse | MSH                  |
| AP stand-alone                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | AP                   |

***


### Alle komponenter stand-alone - afsendende fagsystem og MSH grupperet sammen på samme server

***


![Et billede, der indeholder tekst, skærmbillede, gul Automatisk genereret beskrivelse](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**              | **Delopgave**                                                                                                                 | **Hvem**             |
|-----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Afsendende fagsystem stand-alone  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem |
| MSH stand-alone                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH                  |
| MSH stand-alone                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | MSH                  |
| AP stand-alone                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                   |
| MSH stand-alone AP stand-alone    | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | MSH og AP            |

***


### Alle komponenter stand-alone, MSH og AP grupperet sammen på samme server

![Et billede, der indeholder tekst, skærmbillede, gul Automatisk genereret beskrivelse](media/5d46ee72c0eb16cfc1d678185c7baa53.png)


| **EHMI Komponenter**                              | **Delopgave**                                                                                                                 | **Hvem**                     |
|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| Afsendende fagsystem stand-alone                  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem         |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH                          |
| Afsendende fagsystem stand-alone MSH stand-alone  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem og MSH  |
| MSH stand-alone                                   | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | MSH                          |
| AP stand-alone                                    | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                           |

***


### Afsendende fagsystem stand-alone - MSH/AP sammenbygget - implementeret på forskellige servere

![](media/584f59d0d6bb7e4f94aea46de8eb249c.png)

| **EHMI Komponenter**                    | **Delopgave**                                                                                                                 | **Hvem**                       |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| Afsendende fagsystem stand-alone        | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem           |
| MSH/AP                                  | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH/AP                         |
| Afsendende fagsystem stand-alone MSH/AP | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem og MSH/AP |

***


### Afsendende fagsystem stand-alone - MSH/AP sammenbygget – alle grupperet sammen på samme server

![Et billede, der indeholder tekst, skærmbillede, Rektangel, linje/række Automatisk genereret beskrivelse](media/584f59d0d6bb7e4f94aea46de8eb249c.png)

| **EHMI Komponenter**              | **Delopgave**                                                          | **Hvem**             |
|-----------------------------------|------------------------------------------------------------------------|----------------------|
| Afsendende fagsystem stand-alone  | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem |
| MSH/AP                            | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | MSH/AP               |

***


### Afsendende fagsystem/MSH sammenbygget – AP stand-alone - implementeret på forskellige servere


![Et billede, der indeholder tekst, skærmbillede, gul, design Automatisk genereret beskrivelse](media/be1c6e9b30bae64a8f5738170ef00b20.png)

| **EHMI Komponenter**                      | **Delopgave**                                                                                                                 | **Hvem**                       |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| Afsendende fagsystem/MSH                  | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem/MSH       |
| AP Stand-alone                            | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | AP                             |
| Afsendende fagsystem/MSH  AP Stand-alone  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem/MSH og AP |

***


### Afsendende fagsystem/MSH sammenbygget – AP stand-alone – alle grupperet sammen på samme server


![](media/be1c6e9b30bae64a8f5738170ef00b20.png)

| **EHMI Komponenter**     | **Delopgave**                                                          | **Hvem**                 |
|--------------------------|------------------------------------------------------------------------|--------------------------|
| Afsendende fagsystem/MSH | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem/MSH |
| AP Stand-alone           | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | AP                       |

***


### Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget - implementeret på forskellige servere

Vi har erfaret gennem samtaler med de deltagende parter, at et scenarie som dette kan være muligt. I så fald er det vigtigt at parter med et sådant setup aftaler, hvilken MSH, der er primær med udfyldelse af MSH forpligtelserne og hvilken MSH, der blot viderestiller informationer til næste led i kæden. Når dette er på plads, vil følgende sikkerhedsanvisninger være gældende.


![](media/dc36c10735cb86a5499e120b23a83c79.png)

| **EHMI Komponenter**                | **Delopgave**                                                                                                                 | **Hvem**                           |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| Afsendende fagsystem/MSH            | **Autenticitetshåndtering:** Implementering af signering af meddelelse                                                        | Afsendende fagsystem/MSH           |
| Afsendende MSH/AP                   | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | MSH/AP                             |
| Afsendende fagsystem/MSH og MSH/AP  | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende fagsystem/MSH og MSH/AP |

***


### Afsendende fagsystem/MSH sammenbygget – MSH/AP sammenbygget – alle grupperet sammen på samme server

Som for 4.10.


![Et billede, der indeholder skærmbillede, linje/række, Rektangel, diagram Automatisk genereret beskrivelse](media/dc36c10735cb86a5499e120b23a83c79.png)

| **EHMI Komponenter**     | **Delopgave**                                                          | **Hvem**                 |
|--------------------------|------------------------------------------------------------------------|--------------------------|
| Afsendende fagsystem/MSH | **Autenticitetshåndtering:** Implementering af signering af meddelelse | Afsendende fagsystem/MSH |
| Afsendende MSH/AP        | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse. | MSH/AP                   |

***


### Alle komponenter sammenbyggede


![](media/5d46ee72c0eb16cfc1d678185c7baa53.png)

Da alle komponenter her er sammenbyggede, håndteres al sikkerhed internt i sammenbygningen, og der er derfor ikke behov for eksplicit at udtrykke noget om sikkerheden her.

***


### Modtagersiden

Ovenstående er kun beskrevet, hvordan sikkerheden ser ud på afsendersiden. De tilsvarende mekanismer implementeres naturligvis også på modtagersider, hvor de så bare anvendes i den modsatte rækkefølge og med de tilsvarende aktører i modsat rækkefølge.

***


### Indberetninger ift. scenarierne i afsnit 4.

I det følgende antages begge sider af afsender- og modtagerøkosystemerne at have samme setup til hinanden som det afsendende økosystem. I praksis er dette naturligvis meget forskelligt, og der skal i så fald kombineres

| **Scenarier**                        | **Skabende/Indgående indberetning**                                                                                             | **Afsluttende/udgående indberetning**                                                                                          |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| Kap. 4.2 Kap. 4.3 Kap. 4.4 Kap. 4.5  | Afsendende fagsystem  Afsendende MSH  Afsendende AP ------------------------------------------- Modtagende AP  Modtagende MSH   |  Afsendende MSH  Afsendende AP ------------------------------------------- Modtagende AP  Modtagende MSH  Modtagende fagsystem |
| Kap. 4.6 Kap. 4.7                    | Afsendende fagsystem  Afsendende MSH/AP ------------------------------------------- Modtagende MSH/AP                           |  Afsendende MSH/AP  ------------------------------------------- Modtagende MSH/AP Modtagende fagsystem                         |
| Kap. 4.8 Kap. 4.9                    | Afsendende fagsystem/MSH Afsendende AP ------------------------------------------- Modtagende AP                                |  Afsendende AP  ------------------------------------------- Modtagende AP Modtagende fagsystem/MSH                             |
| Kap. 4.10 Kap. 4.11                  | Afsendende fagsystem/MSH Afsendende AP/MSH ------------------------------------------- Modtagende AP/MSH                        |  Afsendende AP/MSH ------------------------------------------- Modtagende AP/MSH Modtagende fagsystem/MSH                      |
| Kap. 4.12                            | Afsendende fagsystem/MSH/AP                                                                                                     | Modtagende fagsystem/MSH/AP                                                                                                    |

