# EHMI Message Service Handler (MSH) Responsibility Specification

The following prerequisites for the Message Service Handler (MSH) apply:

-   MSH is a component that can be a stand-alone application, integrated with an End User Application (EUA) , integrated with an EHMI AP or integrated with both (both End User Application (EUA)  and EHMI AP).
-   MSH must already be selected and implemented.
-   MSH must be able to communicate via interface with the End User Application (EUA). As well as be able to receive a MedCom message or the data content for a MedCom message via interface to MSH from the End User Application (EUA).
-   MSH must be able to make any mappings between the End User Application (EUA)'s format and a correctly formatted MedCom message.
-   MSH must be able to handle SBDH envelopes at PEPPOL level, i.e. be able to wrap a MedCom message and transfer metadata from it to the SBDH envelope, as well as apply metadata to the correct BusinessScope/Scopes in the SBDH envelope. How the SBDH envelope is to be filled in is being finalized by MedCom but complies with the basic PEPPOL specification, so the SBDH data will be usable for a PEPPOL-compliant AP.
-   MSH must be able to receive sufficient metadata from the End User Application (EUA)  to be able to create an SBDH envelope for both the primary recipient and the secondary recipient in the form of XDS metadata to DDS.
-   MSH must be able to control which messages are sent directly to the primary recipient and which are sent in copy with XDS metadata to DDS.
-   MSH must be able to communicate the SBDH envelope via interface with EHMI AP.

•	MSH er en komponent, som kan være en stand-alone applikation, sammenbygget med et fagsystem, sammenbygget med et EHMI AP eller sammenbygget med begge dele (både fagsystem og EHMI AP).
•	MSH skal allerede være valgt og implementeret. 
•	MSH skal være i stand til at kommunikere via snitflade med fagsystemet. Samt kunne modtage en MedCom-meddelelse eller dataindholdet for en MedCom-meddelelse via snitflade til MSH fra fagsystemet.
•	MSH skal kunne lave evt. mapninger mellem fagsystemets format og en korrekt formateret MedCom-meddelelse.
•	MSH skal være i stand til at håndtere SBDH-kuvert på PEPPOL-niveau, dvs. bl.a. kunne indpakke en MedCom-meddelelse og overføre metadata herfra til SBDH-kuverten, samt påføre metadata til de rette BusinessScope/Scopes i SBDH-kuverten. Hvordan SBDH-kuverten skal udfyldes er under færdigspecificering af MedCom men overholder grundlæggende PEPPOL-specifikation, så SBDH’ens data vil være brugbare for et PEPPOL-compliant AP.
•	MSH skal kunne modtage tilstrækkelige metadata fra fagsystemet til at kunne danne en SBDH-kuvert til både primær modtager og sekundær modtager i form af XDS-metadata til DDS.
•	MSH skal kunne styre hvilke meddelelser der sendes hhv. direkte til primær modtager, og hvilke der sendes i kopi med XDS-metadata til DDS.
•	MSH skal være i stand til at kommunikere SBDH-kuvert via snitflade med EHMI AP. 

Decentralt vedrørende eDelivery og DDS (Dokumentdelingsservicen)

EHMI Komponent	Delopgave	Hvem
Decentralt MSH	Integration til centralt AP og fagsystem	MSH
Kort beskrivelse:

EHMI MSH skal i EHMI-produktionspiloten desuden kunne håndtere XDS Metadata formateret som FHIR DocumentReference ressource. MedCom profilering af FHIR DocumentReference ressource er under specificering. MSH’en skal kunne danne MedCom FHIR DocumentReference profilen med de rette data. EHMI MSH skal kunne indsætte MedCom FHIR DocumentReference ressourcen i den anviste BusinessScope/Scope i SBDH-kuverten.
EHMI MSH tager sig desuden af at håndtere SBDH-kvittering i både afsender og modtager økosystemerne. SBDH-kvitteringen er en indlejret ebXML Business SignalMessage, der minder om AS4-kvitteringer. 
MSH’en skal være underlagt høje oppetidskrav på linje med andre centrale kritiske komponenter i sundhedsvæsenet, og det skal i lighed med disse også overholde gængse krav for drift af kritiske systemer som ex. logning og backup.


## EHMI Delivery Status - MSH responsability description:

The following prerequisites for the End User Application (EUA) apply:
