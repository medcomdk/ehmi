# EHMI Production Pilot

***

    **Disclaimer - The menu items above marked with a star are yet not specified**
    
<br/> 

## EHMI Production Pilot Description


<br/> 

### Introduction

*The production pilot for EHMI involves a new FHIR standard for municipal test responses, HomeCareObservation, which is sent via the new underlying EHMI infrastructure on the Health Data Network (DA: Sundhedsdatanettet, SDN). In the production pilot, a test will be carried out in operation in parts of Q1 and Q2 2026 with a limited set of participants, where the HomeCareObservation will be sent from municipal emergency services (EOJ) to general medical practice (LPS) via EHMI. The HomeCareObservation is based on MedCom's existing standard for laboratory responses, and aims to ensure digital and structured exchange of municipal test responses.* 

*In the production pilot, the following EHMI functionalities and services (and more) will be tested:*
- *document sharing of sent messages and subsequent exposure of the messages in the national infrastructure for both healthcare professionals and citizens for the benefit of the citizens/patients safety.*
- *collecting delivery status of messages (Track’n’Trace) at selected points along the delivery path and subsequently exposing the delivery status via a service to both healthcare professionals and citizens, allowing them to follow the status of a message in close to real-time.*
- *addressing via the EHMI Addressing Service*
- *the EHMI Endpoint Register, a central and independent organizational register of endpoints related to the national SOR*

*The testing of the EHMI architecture and configuration of the involved components with various message flows will be carried out in operation in parts of Q1 and Q2 2026.* 
Overall the EHMI Production Pilot is described in the Project Description as part of MedCom13 <a href="https://medcom.dk/projekter/kommunale-proevesvar-paa-ny-infrastruktur/" target="_blank">here</a>.

The project has a number of deliverables of specifications, which can be seen below in [EHMI Production Pilot specification schema](#ehmi-production-pilot-specification-schema)

<br/> 


**Table of content**

- [Project Time schedule](#project-time-schedule)
- [EHMI Core Description](#ehmi-core-description)
    - [EHMI Core Security Description](#ehmi-core-security-description)
- [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - [EHMI Delivery Status Security Description](#ehmi-delivery-status-security-description)
- [EHMI Production Pilot specification schema](#ehmi-production-pilot-specification-schema)
- [Changes that EHMI causes on MedCom FHIR IGs and FHIR Profiles (by 2024.04.01)](#changes-that-ehmi-causes-on-medcom-fhir-igs-and-fhir-profiles-by-20240401)
- [Relevant Links](#relevant-links)

<br/> 


### Project Time schedule

![EHMI Pixi time schedule](https://medcomdk.github.io/ehmi/assets/images/EHMI%20Pixi%20-%20tidslinje.png)

<br/> 


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

EHMI Core specification is further described [here](../ecore/index.md)

<br/> 


#### EHMI Core Security Description

EHMI Core Security is defined as
- the needed security implementation to serve message delivering as described in [EHMI Core Description](#ehmi-core-description)
    - this part of EHMI Core Security is described [here](../security/security-specification-of-ehmi-core.md)
- the already established security implementation regarding XDS Document Sharing on NSP
    - this part of EHMI Core Security is described <a href="https://www.nspop.dk/display/Web3/E.+Sikkerhed+og+Logning" target="_blank">here (Link to NSP opens in a new window)</a>
    
<br/> 


### EHMI Delivery Status Description
    
EHMI Delivery Status is defined as 
- the registration of EHMI Delivery Status (FHIR AuditEvents) from each "station" in the primary message delivering from a sender system to a receiver system 
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP

EHMI Delivery Status is further described [here](../eds/index.md)

<br/> 


#### EHMI Delivery Status Security Description

EHMI Delivery Status Security is defined as
- the needed security implementation to serve EHMI Delivery Status as described in [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - this part of EHMI Core Security is described [here](../security/security-specification-of-ehmi-eds.md)
    
<br/> 


### EHMI Production Pilot specification schema

| **EHMI Specification**           | **Q1 2024** | **Q2 2024** |<i>**Q3 & Q4 2024** |
|---                               |---          |---          |---          |
|<i>**EHMI Core** <br/> [read more...](../ecore/index.md) <br/>      | ehmiSMP Spec for AP <br/> ehmiSBDH Spec for MSH & AP <br/> | | |
|---                               |---          |---          |
|<i>**EHMI Core Security**</i> <br/> [read more...](../security/security-specification-of-ehmi-core.md) | EHMI Security for EHMI Core <br/> <br/> | | |
|---                               |---          |---          |---          |
|<i>**EHMI EDS**</i> <br/> [read more...](../eds/index.md) <br/> <br/> <br/> <br/> | EHMI Spec for EDS Client write operation <br/> - EUA <br/> - MSH <br/> - AP <br/> [read more...](../security/security-specification-of-ehmi-eds.md)| EHMI Specs for EDS Server operations <br/> EHMI Spec for other EDS Client operations <br/> <br/> <br/> <br/> | |
|---                               |---          |---          |---          |
|<i>**EHMI Servers**</i> <br/> <br/> <br/> <br/> | | EHMI Specs for all EHMI Server operations: <br/> - EDS <br/> - EAS <br/> - EER|Tenders for: <br/> - EHMI EDS Server <br/> - EHMI EAS Server <br/> - EHMI EER Server |
|---                               |---          |---          |---          |
|<i>**EHMI Server & API Security**</i> <br/> <br/> <br/> <br/> | EHMI API Security for: <br/> - EDS <br/> EDS Security is handled as described in: <br/> <a href="../security/media/Sikkerhedsarkitektur EHMI services v05.pdf" target="_blank">Sikkerhedsarkitektur EHMI services v05 (opens in new window)</a> <br/> | EHMI Server & API Security for: <br/> - EDS <br/> - EAS <br/> - EER|Tenders for: <br/> - EHMI Security Server <br/> <br/> <br/> |
|---                               |---          |---          |---          |

<br/> 

## Changes that EHMI causes on MedCom FHIR IGs and FHIR Profiles (by 2024.04.01)

| **EHMI Domain**           | **FHIR Profile(s)**  | **FHIR IG(s)**              | **Change/New** |**Comments** |
|---                        |---                   |---                          |---             |---          |
| EHMI Core                 | MessageDefinition    | MedComMessaging IG          | *New*          | A new basic profile, that will be inherited in all concrete Message Profiles. Is used to define Version among other things |
| EHMI Core                 | All concrete message profiles will have a MessageDefinition. In the production pilot especially HomeCareObservationMessageDefinition | All Concrete Message IGs. In the production pilot especially HomeCareObservation IG | *New*          | Is used to define Version among other things |
| EHMI Core                 | All Concrete Message Profiles | All Concrete Message IGs | *Change* | Message Profiles are going to reference MessageDefinition |
| EHMI Core                 | DocumentReference    | *MedComDocumentSharing IG?* | *New*          | A new basic profile, that will be inherited in *all?* concrete Message Profiles. Is used to transmit XDS Metadata to XDS. Could be part of a new MedComDocumentSharing IG, that serve as the base of DocumentSharing in MedCom's FHIR hierarchi of IGs |
| EHMI Core                 | All concrete message profiles will have a DocumentReference. In the production pilot especially HomeCareObservationDocumentReference | *All Concrete Message IGs. In the production pilot especially HomeCareObservation IG? Or maybe a special DocumentRefernce IG* | *New*          | Is used to transmit XDS Metadata to XDS for a concrete Message Profile |
| EHMI Endpoint Register    | Device               | EHMI Endpoint Register IG   | *New*          | Is used to define applications. Will have relations to Endpoints and MessageDefinitions |
| EHMI Delivery Status      | Device               | EHMI Delivery Status IG     | *New*          | Is used to define source for EDS DeliveryStatus services |


<br/> 

## Relevant links:

<br/> 

<bold><i>Note! All links opens in a new window.</i></bold>

- Danish:
    - MedCom: <a href="https://medcom.dk/projekter/kommunale-proevesvar-paa-ny-infrastruktur/" target="_blank">MedCom13 projektbesksrivelse af ’Kommunale prøvesvar på ny infrastruktur’</a>
    - SDS: <a href="https://sundhedsdatastyrelsen.dk/-/media/sds/filer/rammer-og-retningslinjer/referenceaktitektur-og-it-standarder/referencearkitektur/maalbillede-for-meddelelseskommunikation.pdf" target="_blank">Målbillede for meddelelseskommunikation på sundhedsområdet</a>
    - MedCom: <a href="https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/" target="_blank">Sundhedsdatanettet (SDN)</a>
- English:
    - <a href="" target="_blank"></a>
    - Digital Europe, eDelivery <a href="https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/eDelivery" target="_blank">eDelivery</a>
    - Digital Europe, eDelivery <a href="https://ec.europa.eu/digital-building-blocks/wikis/display/DIGITAL/Access+Point+specifications" target="_blank">AP specifikationer</a>
    - Digital Europe, PEPPOL <a href="https://docs.peppol.eu/edelivery/envelope/Peppol-EDN-Business-Message-Envelope-2.0.1-2023-08-17.pdf" target="_blank">SBDH envelope</a>
