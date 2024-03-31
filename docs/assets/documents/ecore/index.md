# EHMI Core

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
    
    ***Shifts of languages between English and Danish will occur in this version - that will change completely to English in the next upcoming version***
    
***
***


**Table of contents**
- [EHMI Core Description](#ehmi-core-description)
    - [EHMI Core Message Delivery and Document Sharing](#ehmi-core-message-delivery-and-document-sharing)
    - [EHMI Core Description](#ehmi-core-specifications)

    
***
***

## EHMI Core Description

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

EHMI Core specifies 
- ehmiSBDH, the envelope that is used between the MSH's
- how ehmiSBDH in addition to its primary purpose of carrying metadata for eDelivery Messaging can carry the metadata used for:
    - Reliable Messaging embedded in ehmiSBDH BusinessScopes
    - XDS Document Sharing through the FHIR DocumentReference profile for each messagetype and how it is embedded in an ehmiSBDH BusinessScope
    - EHMI Delivery Status embedded in ehmiSBDH BusinessScopes

***
***

### EHMI Core Message Delivery and Document Sharing


![EHMI Core Message Delivery and Document Sharing](/ehmi/assets/images/1_EHMI_Meddelelsesforsendelse_og_dokumentdeling_1315x563.png)

    
***
***

### EHMI Core specifications

EHMI Core specifies two

- [EHMI Profile of SBDH (ehmiSBDH)](/ehmiSBDH/index.md)
- [Service Metadata Publisher (SMP)](/SMP/index.md)

<br/> Security in relation to EHMI Core is specified [here](../security/security-specification-of-ehmi-core.md)

***
***

