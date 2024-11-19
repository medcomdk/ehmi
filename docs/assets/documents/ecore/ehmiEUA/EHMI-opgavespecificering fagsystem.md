# EHMI-opgavespecificering for fagsystem

## Introduktion og status

I MedCom13 har MedCom et fælles afprøvningsprojekt ’Kommunale prøvesvar på ny infrastruktur’, hvor MedComs to centrale moderniseringsspor kobles: FHIR og EHMI, hvor såvel meddelelseskommunikationen som infrastrukturen moderniseres. Moderniseringen sker grundet behov for kvalitetsløft af bl.a. sikkerhed, gennemsigtighed, robusthed og effektiv, international digital meddelelseskommunikation. I projektet gennemføres en afprøvning i drift fra d. 1. marts til d. 31. maj 2025. I afprøvningen skal den nye FHIR-standard for kommunale prøvesvar sendes fra kommunale akutfunktioner (EOJ) til almen lægepraksis (LPS) via den nye infrastruktur EHMI (Enhanced Healthcare Messaging Infrastructure). Forsendelsen af standarden skal ske via eDelivery, og der skal ligeledes ske en afprøvning af EHMI-funktionaliteter så som dokumentdeling og forsendelsesstatus (Track’n’Trace).

Dette dokument beskriver de påkrævede EHMI-opgaver for fagsystemet. Relevante links findes sidst i dokumentet.

## Baggrundsinfo - illustration og forklaring af komponenter

Der er 3 komponenter involveret ved afsendelse af en meddelelse:

1\. Afsendersystem  
2\. MSH (Message Service Handler)  
3\. Access Point (AP)

![Automatisk genereret beskrivelse](./media/Billede1.png)Disse komponenter kan kombineres på forskellig vis af leverandørerne. Uanset kombinationen, skal leverandørerne overholde opgavespecifikationen.

## Forudsætning for fagsystemet (uden MedCom-støttemidler)

Følgende forudsætninger for fagsystemet er gældende uden MedCom-støttemidler:

-   Fagsystemet er en komponent, som forudsættes at være relevant ift. de kliniske brugere i et sundhedsdomæne. Det kan være en stand-alone applikation, sammenbygget med MSH, sammenbygget med et EHMI AP eller sammenbygget med begge dele (både MSH og EHMI AP).
-   Fagsystemet skal være i stand til at danne MedCom-meddelelser eller data-indhold svarende til en MedCom-meddelelse. Det skal kunne videregive en MedCom-meddelelse eller dataindholdet for en MedCom-meddelelse via snitflade til MSH.
-   Fagsystemet skal kunne give MSH tilstrækkelige metadata til at kunne danne en SBDH-kuvert til både primær modtager og sekundær modtager i form af XDS-metadata til dokumentdeling via snitflade til MSH.

## Opgavespecificeringer (med MedCom-støttemidler)

### Decentralt vedrørende sikkerhed

| **EHMI Komponent**                             | **Delopgave**                                                                                                                                     | **Hvem**           | **Optionel ift. afprøvningen af EHMI** |
|------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|----------------------------------------|
| Fagsystem standalone                           | **Autenticitetshåndtering:** Implementering af signering af meddelelse/meddelelsesindhold i fagsystem                                             | Fagsystemet        |                                        |
| Fagsystem standalone                           | **Integritetssikring og fortrolighedssikring:** Kommunikation af meddelelse / meddelelsesindhold med MSH via sikret transportprotokol, f.eks. TLS | Fagsystemet og MSH |                                        |
| Fagsystem sammen med MSH på samme server       | **Autenticitetshåndtering:** Implementering af signering af i fagsystem                                                                           | Fagsystemet        |                                        |
| Fagsystem sammen med MSH på samme server       | **Integritetssikring og fortrolighedssikring:** Kommunikation af konvolut med AP via sikret transportprotokol, f.eks. TLS                         | Fagsystemet og MSH |                                        |
| Fagsystem sammen med MSH og AP på samme server | **Autenticitetshåndtering:** Implicit da alt hostes på samme server                                                                               | Fagsystemet/MSH/AP |                                        |
| Fagsystem sammen med MSH og AP på samme server | **Integritetssikring og fortrolighedssikring:** Implicit da alt hostes på samme server                                                            | Fagsystemet/MSH/AP |                                        |

**Autenticitetshåndtering mellem C1 og C2 (jf. Målbilledets afsnit 6.1.1):**

*På sundhedsområdet stilles krav om, at meddelelseskonvolutten signeres i C1 og at denne signatur efterfølgende verificeres i C2. På denne måde sikres autentifikation af C1 i C2. Denne autentifikation vil være en del af den aftale, der indgås imellem AP’et og det system AP’et agerer på vegne af. Sikres ved* eksplicit signering mellem Fagsystem/MSH/AP (med tilhørende verifikation) på systembevisniveau (VOCES/FOCES/Niveau 3)

**Integritetssikring mellem C1 og C2 (jf. Målbilledets afsnit 6.1.2):**

*Sikres ud over den under autenticitet (afsnit 6.1.1) beskrevne konvolutsignering via de protokoller, der anvendes imellem AP’erne og de systemer AP’erne agerer på vegne af – f.eks. TLS (Transport Layer Security).*

**Fortrolighedssikring mellem C1 og C2 (jf. Målbilledets afsnit 6.1.4):**

*Da alle meddelelser under sundhedsdomænet som udgangspunkt indeholder følsomme personoplysninger, skal kryptering anvendes, hvor det er muligt. Meddelelsen skal derfor krypteres imellem afsender og afsendende AP via MSH (C1 og C2) samt imellem modtagende AP og modtager via MSH (C3 og C4). Anvendelse af denne kryptering vil være en del af den aftale, der indgås imellem AP’et og det system AP’et agerer på vegne af.* Sikres som via Integritetssikring

### Decentralt vedrørende EHMI-komponent: Forsendelsesstatus

| **EHMI Komponent**                       | **Delopgave**              | **Hvem**    | **Optionel ift. afprøvningen af EHMI** |
|------------------------------------------|----------------------------|-------------|----------------------------------------|
| Forsendelsesstatus: Indrapporterings-API | Implementering i fagsystem | Fagsystemet |                                        |
| Forsendelsesstatus: Visnings-API         | Implementering i fagsystem | Fagsystemet | Optionel – mulighed                    |
| Forsendelsesstatus: Visningsskærmbillede | Implementering i fagsystem | Fagsystemet | Optionel – mulighed                    |

**Kort beskrivelse:**  
Fagsystemet skal som en ekstra opgave kunne kommunikere med et forsendelsesstatus repository (track’n’trace).

Forsendelsesstatus repositoriet har et indrapporterings-API, som fagsystemet skal kommunikere via. Det vil med stor sandsynlighed være baseret på et OAuth-sikret REST-interface og SMART-on-FHIR. Repositoriet og dets interface er pt. under specifikation. Det vil med meget stor sandsynlighed blive baseret på IHE BALP. Der vil være MedCom-støttemidler til implementering af interfacet til dette repository.

For opsamling af forsendelsesstatus stilles der krav om, at der jf. målbilledets afsnit 6.3.1 eksplicit signeres mellem forsendelsesstatus ”klienten” og ”serveren” (med tilhørende verifikation) på systembevisniveau (VOCES/FOCES/Niveau 3).

Desuden er der i denne forbindelse krav om, at opsamlingen foretages via en asynkron afkoblingsmekanisme (kø), så det sikres at der ikke går forsendelsesstatusdata tabt.

I afprøvningen forventes visningen af forsendelsesstatus at ske via en central løsning men der er mulighed for at fagsystemet kan implementere en lokal visning i fagsystemet.

### Decentral vedrørende EHMI-komponent: Sundhedsadresseringsservice

| **EHMI Komponent**                              | **Delopgave**                                | **Hvem**    |
|-------------------------------------------------|----------------------------------------------|-------------|
| Sundheds-adresseringsservice: API for anvendere | Integration til Sundheds-adresseringsservice | Fagsystemet |

**Kort beskrivelse:**  
Fagsystemet skal kunne integrere til EHMI Sundhedsadresseringsservicen. EHMI Sundhedsadresseringsservicen vil tilbyde en søgefunktionalitet, der i første version kan hente forsendelsesdata til egen praktiserende læge. EHMI Sundhedsadresseringsservicen er pt. under specificering.

Der vil være MedCom-støttemidler til implementering af interfacet til EHMI Sundhedsadresseringsservicen.

## Relevante links:

-   Dansk:
    -   Målbillede for meddelelseskommunikation på sundhedsområdet (<https://sundhedsdatastyrelsen.dk/-/media/sds/filer/rammer-og-retningslinjer/referenceaktitektur-og-it-standarder/referencearkitektur/maalbillede-for-meddelelseskommunikation.pdf>)
    -   SDN (<https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/>)
-   Engelsk:
    -   EU eDelivery (<https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/eDelivery>)
    -   EU AP specifikationer (<https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/Access+Point+specifications>)
    -   EU PEPPOL SBDH envelope (<https://docs.peppol.eu/edelivery/envelope/Peppol-EDN-Business-Message-Envelope-2.0.0-2023-03-13.pdf>)
    -   IHE BALP (<https://profiles.ihe.net/ITI/BALP/index.html>)
