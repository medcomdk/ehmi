# EHMI Production Pilot

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**

    ***Shifts of languages between English and Danish will occur in this version - that will change completely to English in the next upcoming version***
    
***

## EHMI Production Pilot Description


***

### Introduction

I MedCom13 har MedCom et fælles afprøvningsprojekt ’Kommunale prøvesvar på ny infrastruktur’, hvor MedComs to centrale moderniseringsspor kobles: FHIR og EHMI, hvor såvel meddelelseskommunikationen som infrastrukturen moderniseres. Moderniseringen sker grundet behov for kvalitetsløft af bl.a. sikkerhed, gennemsigtighed, robusthed og effektiv, international digital meddelelseskommunikation. Overall the EHMI Production Pilot is described in the Project Description as part of MedCom13 <a href="https://medcom.dk/projekter/kommunale-proevesvar-paa-ny-infrastruktur/" target="_blank">here</a>

I projektet gennemføres en afprøvning i drift i dela af Q1 og Q2 2026.

I afprøvningen skal den nye FHIR-standard for kommunale prøvesvar sendes fra kommunale akutfunktioner (EOJ) til almen lægepraksis (LPS) via EHMI.

Forsendelsen af standarden skal ske via den nye underliggende eDelivery infrastruktur, og der skal ligeledes ske en afprøvning af EHMI-funktionaliteter så som dokumentdeling og forsendelsesstatus (Track’n’Trace).

***


**Table of contents**

- EHMI Production Pilot Description
    - [EHMI Core Description](#ehmi-core-description)
        - [EHMI Core Security Description](#ehmi-core-security-description)
    - [EHMI Delivery Status Description](#ehmi-delivery-status-description)
        - [EHMI Delivery Status Security Description](#ehmi-delivery-status-security-description)
    - [EHMI Production Pilot specificaion schema](#ehmi-production-pilot-specificaion-schema)
    - [Relevante Links](#relevante-links)

***


### EHMI Core Description

EHMI Core is defined as 
- the primary message delivering from a sender system to a receiver system concerning 
    - End User Applications (EUA)
    - Message Service Handlers (MSH)
    - eDelivery Access Points (AP)
    - eDelivery SML and SMP
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP also concerning 
    - Sender's End User Application (EUA)
    - Message Service Handlers (MSH)
    - eDelivery Access Points (AP)
    - eDelivery SML and SMP

EHMI Core is described further [here](../ecore/index.md)

***


#### EHMI Core Security Description

EHMI Core Security is defined as
- the needed security implementation to serve message delivering as described in [EHMI Core Description](#ehmi-core-description)
    - this part of EHMI Core Security is desribed [here](../security/security-specification-of-ehmi-core.md)
- the already established security implementation regarding XDS Document Sharing on NSP
    - this part of EHMI Core Security is desribed [here (Link to NSP)]()
    
***


### EHMI Delivery Status Description
    
EHMI Delivery Status is defined as 
- the registration of EHMI Delivery Status (FHIR AuditEvents) from each "station" in the primary message delivering from a sender system to a receiver system 
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP

EHMI Delivery Status is described further [here](../eds/index.md)

***


#### EHMI Delivery Status Security Description

EHMI Delivery Status Security is defined as
- the needed security implementation to serve EHMI Delivery Status as described in [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - this part of EHMI Core Security is desribed [here](../security/security-specification-of-ehmi-eds.md)
    
***


### EHMI Production Pilot specificaion schema

| EHMI Specification              | **Q1 2024** | **Q2 2024** |**Q3 & Q4 2024** |
|---                              |---          |---          |---          |
|EHMI Core <br/> <br/>            | ehmiSMP Spec for AP <br/> ehmiSBDH Spec for MSH & AP <br/> | | |
|---                              |---          |---          |
|EHMI Core Security               | EHMI Security for EHMI Core | | |
|---                              |---          |---          |---          |
|EHMI EDS <br/> <br/> <br/> <br/> | EHMI Spec for EDS Client write operation <br/> - EUA <br/> - MSH <br/> - AP | EHMI Spec for EDS Server operations <br/> EHMI Spec for other EDS Client operations <br/> <br/> <br/> | |
|---                              |---          |---          |---          |
|EHMI Servers <br/> <br/> <br/> <br/> | | EHMI Server Specification for: <br/> - EDS <br/> - EAS <br/> - EER|Tenders for: <br/> - EHMI EDS Server <br/> - EHMI EAS Server <br/> - EHMI EER Server |
|---                              |---          |---          |---          |
|EHMI Server & API Security <br/> <br/> <br/> <br/> | EHMI API Security for: <br/> - EDS <br/> <br/> <br/> | EHMI Server & API Security for: <br/> - EDS <br/> - EAS <br/> - EER|Tenders for: <br/> - EHMI Security Server <br/> <br/> <br/> |
|---                              |---          |---          |---          |

***


### Relevante links:


<bold><i>OBS! Alle links åbner i et nyt vindue.</i></bold>

- Dansk:
    - MedCom: <a href="https://medcom.dk/projekter/kommunale-proevesvar-paa-ny-infrastruktur/" target="_blank">MedCom13 projektbesksrivelse af ’Kommunale prøvesvar på ny infrastruktur’</a>
    - SDS: <a href="https://sundhedsdatastyrelsen.dk/-/media/sds/filer/rammer-og-retningslinjer/referenceaktitektur-og-it-standarder/referencearkitektur/maalbillede-for-meddelelseskommunikation.pdf" target="_blank">Målbillede for meddelelseskommunikation på sundhedsområdet</a>
    - MedCom: <a href="https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/" target="_blank">Sundhedsdatanettet (SDN)</a>
- Engelsk:
    - <a href="" target="_blank"></a>
    - Digital Europe, eDelivery <a href="https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/eDelivery" target="_blank">eDelivery</a>
    - Digital Europe, eDelivery <a href="https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/Access+Point+specifications" target="_blank">AP specifikationer</a>
    - Digital Europe, PEPPOL <a href="https://docs.peppol.eu/edelivery/envelope/Peppol-EDN-Business-Message-Envelope-2.0.1-2023-08-17.pdf" target="_blank">SBDH envelope</a>
