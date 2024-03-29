# Specificering af sikkerhed ifm centrale og decentrale EHMI-services

## Indholdsfortegnelse

- [Generelt omkring sikkerhed for komponenter i EHMI](#generelt-omkring-sikkerhed-for-komponenter-i-ehmi)

- [Generelle sikkerhedsmæssige definitioner for komponenter i forsendelseskæden](#generelle-sikkerhedsmæssige-definitioner-for-komponenter-i-forsendelseskæden)

- [Sikkerhedsspecificeringer vedrørende EHMI Delivery Status af meddelelser](#sikkerhedsspecificeringer-vedrørende-Delivery Status-af-meddelelser)

- [Opsamling til repositorie](#opsamling-til-ehmi-delivery-service-repository)

- [Klient sikkerhed for EHMI Delivery Status - indberetning](#decentralt-vedrørende-sikkerhed-for-ehmi-komponent-Delivery Status---indberetning)

- [Udstilling via service](#udstilling-via-service)

- [Klient sikkerhed for EHMI Delivery Status - udsøgning](#klient-sikkerhed-ehmi-delivery-status---indberetning)

- [Sikkerhedsspecificeringer vedrørende EHMI AdressingService]()

- [Decentral vedrørende EHMI Adressing Service](#decentral-vedrørende-ehmi-komponent-ehmi-adressing-service)


## Generelt omkring sikkerhed for komponenter i EHMI

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


## Sikkerhedsspecificeringer vedrørende EHMI Delivery Status af meddelelser

Sikkerhed i forhold til forsendelses-status opdeles i de forskellige trin:

1. EHMI Delivery Status opsamles og gemmes i et repositorie
2. EHMI Delivery Status hentes af anvendere via udstillede services

***


### Opsamling til EHMI Delivery Service repository

Fra målbilledet ved vi, at sikkerhed omkring dette er nødvendigt dels for, at anvenderne vil anse servicen baseret på de opsamlede data for troværdig, og dels fordi der opsamles personoplysninger, da unik borgeridentifikation (oftest CPR-nummeret), for den borger meddelelsen omhandler, er en del af den opsamlede information:

-   **Autenticitet:** En komponent, der gemmer EHMI Delivery Status for meddelelser, skal autentificere sig når den tilgår repositoriet.
-   **Tilgængelighed:** Aftalt oppetid og svartid skal sikres via standard driftsmekanismer. Dette er særlig vigtigt her, da EHMI Delivery Status, jf. afsnit 5.2.8, skal være tæt på realtidsopdateret.
-   **Integritet:** Sikres af den protokol, som opsamlingen implementeres via.
-   **Uafviselighed:** En komponent, der gemmer EHMI Delivery Status, skal audit logge opsamlingen på en standardiseret måde.
-   **Fortrolighed:** Når den opsamlede EHMI Delivery Status kommunikeres til repositoriet, sikres den enten via eksplicit kryptering eller implicit kryptering på det underliggende infrastruktur niveau.

***


#### Klient sikkerhed EHMI Delivery Status - indberetning

| **EHMI Komponenter**                                                         | **Delopgave**                                                                                                                       | **Hvem**                                                                    |
|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| EHMI Delivery Status-komponent                                                 | **Autenticitet:** En komponent, der gemmer EHMI Delivery Status for meddelelser, skal autentificere sig når den tilgår repositoriet.  | Afsendende system (Afsendende fagsystem/MSH/AP)                             |
| Afsendende system (Afsendende fagsystem/MSH/AP)                              | **Autenticitetshåndtering:** Implementering af signering af indberetning                                                            | Afsendende system (Afsendende fagsystem/MSH/AP)                             |
| EHMI Delivery Status-komponent                                                 | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                              | EHMI Delivery Statuskomponent                                                 |
| Afsendende system (Afsendende fagsystem/MSH/AP) EHMI Delivery Status-komponent | **Integritetssikring og fortrolighedssikring:** Kommunikation via sikret transportprotokol, f.eks. TLS                              | Afsendende system (Afsendende fagsystem/MSH/AP) EHMI Delivery Statuskomponent |
| Afsendende system (Afsendende fagsystem/MSH/AP) EHMI Delivery Status-komponent | **Tilgængelighed:** Implementering af kø mekanisme til at håndtere at en forbindelse kan være nede                                  | Afsendende system (Afsendende fagsystem/MSH/AP) EHMI Delivery Statuskomponent |

***


### Indberetninger ift. scenarierne i afsnit 4.

I det følgende antages begge sider af afsender- og modtagerøkosystemerne at have samme setup til hinanden som det afsendende økosystem. I praksis er dette naturligvis meget forskelligt, og der skal i så fald kombineres

| **Scenarier**                        | **Skabende/Indgående indberetning**                                                                                             | **Afsluttende/udgående indberetning**                                                                                          |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| [Kap. 4.2 Alle komponenter stand-alone - implementeret på forskellige servere](./security-specification-of-ehmi-core.md#alle-komponenter-stand-alone---implementeret-på-forskellige-servere) 
[Kap. 4.3 Alle komponenter stand-alone - grupperet sammen på samme server](./security-specification-of-ehmi-core.md#alle-komponenter-stand-alone---grupperet-sammen-på-samme-server) 
Kap. 4.4 Kap. 4.5  | Afsendende fagsystem  Afsendende MSH  Afsendende AP ------------------------------------------- Modtagende AP  Modtagende MSH   |  Afsendende MSH  Afsendende AP ------------------------------------------- Modtagende AP  Modtagende MSH  Modtagende fagsystem |
| Kap. 4.6 Kap. 4.7                    | Afsendende fagsystem  Afsendende MSH/AP ------------------------------------------- Modtagende MSH/AP                           |  Afsendende MSH/AP  ------------------------------------------- Modtagende MSH/AP Modtagende fagsystem                         |
| Kap. 4.8 Kap. 4.9                    | Afsendende fagsystem/MSH Afsendende AP ------------------------------------------- Modtagende AP                                |  Afsendende AP  ------------------------------------------- Modtagende AP Modtagende fagsystem/MSH                             |
| Kap. 4.10 Kap. 4.11                  | Afsendende fagsystem/MSH Afsendende AP/MSH ------------------------------------------- Modtagende AP/MSH                        |  Afsendende AP/MSH ------------------------------------------- Modtagende AP/MSH Modtagende fagsystem/MSH                      |
| Kap. 4.12                            | Afsendende fagsystem/MSH/AP                                                                                                     | Modtagende fagsystem/MSH/AP                                                                                                    |

***


### Udstilling via service

Fra målbilledet ved vi, at servicen, der udstiller EHMI Delivery Status for meddelelser, skal overholde de samme sikkerhedskrav og -regler som øvrige services på sundhedsområdet, jf. målbilledets princip PT6. Derfor bør flere af de samme allerede eksisterende sikkerhedsmekanismer fra disse andre services anvendes:

-   **Autenticitet:** Servicen skal udstilles som en DGWS/IDWS service eller lignende niveau, og anvenderne (både systemer, sundhedspersoner og borgere) skal anvende digitale certifikater i forbindelse med kald til servicen på samme måde som for andre services på sundhedsområdet, og det er (igen) et krav, at de anvendte certifikater er på personbevisniveau. For systemer dog systembevisniveau.
-   **Tilgængelighed:** Aftalt oppetid og svartid sikres via den platform, som servicen afvikles på
-   **Integritet:** Sikres af den protokol, som servicen er implementeret med.
-   **Uafviselighed:** Servicen implementerer standardiseret audit log. Logning til MinLog er påkrævet i tilfældene hvor en borger henter EHMI Delivery Status for meddelelser angående en anden borger end sig selv, og hvor en sundhedsperson henter EHMI Delivery Status specifikt for en borger.
-   **Fortrolighed:** Servicen skal aktivt anvende den identifikation af anvenderen (system, sundhedsperson eller borger) samt de søgeparametre, der er en del af kaldet af servicen.

Da servicen udstilles og afvikles på en platform, der kan have sine egne mere strikse sikkerhedspolitikker end de generelle på sundhedsområdet, skal disse i givet fald også overholdes.

***


#### Klient sikkerhed for EHMI Delivery Status - udsøgning

Det vil blive baseret på et OAuth-sikret REST-interface og SMART-on-FHIR eller lignende.

For opsamling af EHMI Delivery Status stilles der krav om, at der jf. målbilledets afsnit 6.3.1 eksplicit signeres mellem EHMI Delivery Status ”klienten” og ”serveren” (med tilhørende verifikation) på systembevisniveau (VOCES/FOCES/Niveau 3).

For søgning af EHMI Delivery Status stilles der krav om, at der mellem EHMI Delivery Status ”klienten” og ”serveren” anvendes identifikation på systembevisniveau (VOCES/FOCES/Niveau 3).

For søgning af EHMI Delivery Status stilles der derudover krav om, at der ved borgers egen adgang og en klinikers specifikke adgang via borgerens/patientens journal anvendes identifikation på personbevisniveau (MOCES/MitID/Niveau 4).

| **EHMI Komponenter**                                                 | **Delopgave**                                                                                                                 | **Hvem**                                                             |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Afsendende system (Afsendende fagsystem/MSH/AP)                      | **Autenticitetshåndtering:** Implementering af signering af indberetning                                                      | Afsendende system (Afsendende fagsystem/MSH/AP)                      |
| Modtagende komponent                                                 | **Autenticitetshåndtering:** Verifikation af signering ved modtagelse.                                                        | Modtagende komponent                                                 |
| Afsendende system (Afsendende fagsystem/MSH/AP) Modtagende komponent | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse/konvolut via sikret transportprotokol, f.eks. TLS | Afsendende system (Afsendende fagsystem/MSH/AP) Modtagende komponent |

***


## Sikkerhedsspecificeringer vedrørende EHMI Adressing Service

Fra målbilledet ved vi, at EHMI Adressing Servicen skal overholde de samme sikkerhedskrav og -regler som tilsvarende services på sundhedsområdet, og derfor bør flere af de samme allerede eksisterende sikkerhedsmekanismer anvendes:

-   **Autenticitet:** Servicen skal udstilles som en DGWS/IDWS service, og anvenderne skal anvende digitale certifikater i forbindelse med kald til servicen på samme måde som for tilsvarende services på sundhedsområdet. På grund af denne service’ natur er det imidlertid i dette tilfælde tilstrækkeligt, at de anvendte certifikater er på systembevisniveau.
-   **Tilgængelighed:** Aftalt oppetid og svartid skal sikres via den platform, som servicen afvikles på – f.eks. via standard driftsmekanismer som fail-over og load-balancere.
-   **Integritet:** Sikres af den protokol, som servicen er implementeret med.
-   **Uafviselighed:** Servicen skal implementere standardiseret audit log.
-   **Fortrolighed:** Servicen skal anvende den identifikation af anvenderen samt de søgeparametre, der er en del af kaldet af servicen, men en egentlig brugerstyring i forhold til hvem, der kalder servicen, antages håndhævet af de kaldende systemer, så når et anvendersystem er korrekt autentificeret, er der adgang til servicen.

Da servicen udstilles og afvikles på en platform, der kan have sine egne mere strikse sikkerhedspolitikker end de generelle på sundhedsområdet, skal disse i givet fald også overholdes.

***


### Decentral vedrørende EHMI-komponent: EHMI Adressing Service

| **EHMI Komponenter**                                       | **Delopgave**                                                                                                                                                                                                                        | **Hvem**                                                  |
|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Afsendende system (Fagsystem)                              | **Autenticitetshåndtering:** Implementering af signering af søgning (VOCES/FOCES)                                                                                                                                                    | Afsendende system (Fagsystem)                             |
| EHMI Adressing Service                               | **Autenticitetshåndtering:** Verifikation af signering (VOCES/FOCES)                                                                                                                                                                 | EHMI Adressing Service                               |
| Afsendende system (Fagsystem) EHMI Adressing Service | **Integritetssikring og fortrolighedssikring:** Kommunikation sikret via transportprotokol, f.eks. TLS                                                                                                                               | Afsendende system (Fagsystem) EHMI Adressing Service |
| Afsendende system (Fagsystem) EHMI Adressing Service | **Tilgængelighed:** Implementering af faste søgninger, som evt. kan gemmes lokalt til at håndtere at en forbindelse kan være nede.  Hvis servicen er online bør altid søges online. Faste søgninger bør opdateres udenfor peaktimes. | Afsendende system (Fagsystem) EHMI Adressing Service |

***
