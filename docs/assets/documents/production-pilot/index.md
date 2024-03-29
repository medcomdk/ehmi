# EHMI Production Pilot Description

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
    

***

**Table of contents**

- EHMI Production Pilot Description
    - [EHMI Core Description](#ehmi-core-description)
    - [EHMI Core Security Description](#ehmi-core-security-description)
    - [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - [EHMI Delivery Status Security Description](#ehmi-delivery-status-security-description)

## EHMI Production Pilot Description

### Introduction

I MedCom13 har MedCom et fælles afprøvningsprojekt ’Kommunale prøvesvar på ny infrastruktur’, hvor MedComs to centrale moderniseringsspor kobles: FHIR og EHMI, hvor såvel meddelelseskommunikationen som infrastrukturen moderniseres. Moderniseringen sker grundet behov for kvalitetsløft af bl.a. sikkerhed, gennemsigtighed, robusthed og effektiv, international digital meddelelseskommunikation. Overall the EHMI Production Pilot is described in the Project Description as part of MedCom13 [here:](https://medcom.dk/projekter/kommunale-proevesvar-paa-ny-infrastruktur/)

I projektet gennemføres en afprøvning i drift i dela af Q1 og Q2 2026.

I afprøvningen skal den nye FHIR-standard for kommunale prøvesvar sendes fra kommunale akutfunktioner (EOJ) til almen lægepraksis (LPS) via EHMI.

Forsendelsen af standarden skal ske via den nye underliggende eDelivery infrastruktur, og der skal ligeledes ske en afprøvning af EHMI-funktionaliteter så som dokumentdeling og forsendelsesstatus (Track’n’Trace).

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

### EHMI Core Security Description

EHMI Core Security is defined as
- the needed security implementation to serve message delivering as described in [EHMI Core Description](#ehmi-core-description)
    - this part of EHMI Core Security is desribed [here](../security/security-specification-of-ehmi-core.md)
- the already established security implementation regarding XDS Document Sharing on NSP
    - this part of EHMI Core Security is desribed [here (Link to NSP)]()
    
### EHMI Delivery Status Description
    
EHMI Delivery Status is defined as 
- the registration of EHMI Delivery Status (FHIR AuditEvents) from each "station" in the primary message delivering from a sender system to a receiver system 
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP

### EHMI Delivery Status Security Description

EHMI Delivery Status Security is defined as
- the needed security implementation to serve EHMI Delivery Status as described in [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - this part of EHMI Core Security is desribed [here](../security/security-specification-of-ehmi-eds.md)
    
