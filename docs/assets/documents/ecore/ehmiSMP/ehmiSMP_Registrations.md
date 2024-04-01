# EHMI SMP (Service Metadata Provider) – konfiguration

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
    
    ***Shifts of languages between English and Danish will occur in this version - that will change completely to English in the next upcoming version***
    
<br/> 

# EHMI Delivery Status User stories

- [EHMI Delivery Status Sender User stories](#ehmi-delivery-status-sender-user-stories)
- [EHMI Delivery Status Receiver User stories](#ehmi-delivery-status-receiver-user-stories)
    
- [4.1 BusinessScope for generel eDelivery meddelelseskommunikation](#businessscope-for-generel-edelivery-meddelelseskommunikation)

- [4.1.1 Sammenhæng til SMP](#sammenhæng-til-smp)

- [*4.1.2* DOCUMENTID](#smpdocumentid)

- [*4.1.2.1* DOCUMENTID for MedCom FHIR Meddelelser](#documentid-for-medcom-fhir-meddelelser)

- [*4.1.2.2* DOCUMENTID for MedCom kvitteringer](#documentid-for-medcom-kvitteringer)

- [4.1.2.3 DOCUMENTID Kvitterings Eksempler](#documentid-kvitterings-eksempler)

- [4.1.3 PROCESSID](#smpprocessid)

- [4.1.3.1 PROCESSID Eksempel: Brug i 4-corner model](#processid-eksempel-brug-i-4-corner-model)

<br/> 

# eDelivery SMP profile

The eDelivery SMP profile is an open specification for publishing service metadata within a 4-corner network. To successfully send a business document in a 4-corner network, an entity must be able to discover critical metadata about the recipient (Access Point) of the business document, such as types of documents the Access Point is capable of receiving and methods of transport supported. The recipient makes this metadata available to other entities in the network through a Service Metadata Publisher service. The eDelivery SMP profile describes the request/response exchanges between a Service Metadata Publisher and a client wishing to discover Access Point metadata. The profile is based on the OASIS Service Metadata Publishing (SMP) Version 1.0 standard.

# SBDH BusinessScopes

## BusinessScope for generel eDelivery meddelelseskommunikation

### Sammenhæng til SBDH

i eDelivery kommunikationen udgør SBDH’ens Scope struktur med de to typer, DOCUMENTID og PROCESSID, foruden værdierne i elementerne Sender og Receiver, den direkte sammenhæng til SMP’ens DocumentIdentifier og ProcessIdentifier. I det følgende beskrives disse 2 Type elementer i SMP.

Scopene DOCUMENTID og PROCESSID er i PEPPOL fast definerede scopes, som sikrer en unik relation til SBDH. DOCUMENTID og PROCESSID anvendes i EHMI med samme præcision som i PEPPOL, så der sikres en vis ensartethed i, hvordan man udtrykker værdierne på tværs af PEPPOL og EHMI. DOCUMENTID og PROCESSID bruges af AP’erne sammen med modtagers ReceiverId til at slå modtagers eDelivery adresse op i SMP med et unikt respons som resultat.

### SMP:DocumentIdentifier

Værdien i DocumentIdentifier  er identisk med den tilsvarende ehmiSBDH-registrering for BusinessScope/Scope[DOCUMENTID]:

    SMP ServiceInformation/DocumentIdentifier
    
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:homecareobservation\#urn:dk:medcom:fhir:homecareobservation:3.0
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:acknowledgement\#urn:dk:medcom:fhir:acknowledgement:2.0
    urn:dk:healthcare:prod:messaging:oasis:ebxml:schema:xsd:sbdhreceiptacknowledgement\#urn:oasis:ebxml:sbdhreceiptacknowledgement:ebbp-signals-2.0


Værdierne hentes fra MedComs standardkatalog og er her repræsenteret ved de værdier, som de har i MedCom meddelelserne. Se bogmærke: [DKEDEL_DT_CodeList]

Ift. det oprindeligt intentionerede fjernes dobbelt ”\#\#” og ”::” fra konstruktionen af InstanceIdentifier, da den aktuelle konfiguration af SMP fra CEF ikke kan håndtere disse så værdierne kan fremsøges igen. Dermed må SBDH’s DOCUMENTID ændres tilsvarende.

<br/>

### SMP:PROCESSID

Værdien i InstanceIdentifier er identisk med den tilsvarende ProcessId SMP-registrering.

Værdien hentes fra nedenstående tabel:

    ProcessList/Process/ProcessIdentifier

    sdn-emergence


**dk-messaging Process Identifier values**

| **Process**   | **Process Identifier value (InstanceIdentifier)** | **Identifier type** |
|---------------|---------------------------------------------------|---------------------|
| sdn-emergence | sdn-emergence                                     | dk-messaging-procid |

