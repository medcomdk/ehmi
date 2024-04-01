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

### Sammenhæng til SMP

i eDelivery kommunikationen udgør SBDH’ens Scope struktur med de to typer, DOCUMENTID og PROCESSID, foruden de allerede gennemgåede elementer i Sender og Receiver, den direkte sammenhæng til SMP’ens DOCUMENTID og PROCESSID. I det følgende beskrives netop disse 2 Type elementer i SBDH’ens overordnede BusinessScope struktur.

Scopene DOCUMENTID og PROCESSID er i PEPPOL fast definerede scopes, som sikrer en unik relation til SMP. DOCUMENTID og PROCESSID anvendes i EHMI med samme præcision som i PEPPOL, så der sikres en vis ensartethed i, hvordan man udtrykker værdierne på tværs af PEPPOL og EHMI. DOCUMENTID og PROCESSID bruges af AP’erne sammen med modtagers ReceiverId til at slå modtagers eDelivery adresse op i SMP med et unikt respons som resultat.

### SMP:DocumentIdentifier

Værdien i DocumentIdentifier  er identisk med den tilsvarende ehmiSBDH-registrering for BusinessScope/Scope[DOCUMENTID]:

    SMP ServiceInformation/DocumentIdentifier
    
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:homecareobservation\#urn:dk:medcom:fhir:homecareobservation:3.0
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:acknowledgement\#urn:dk:medcom:fhir:acknowledgement:2.0
    urn:dk:healthcare:prod:messaging:oasis:ebxml:schema:xsd:sbdhreceiptacknowledgement\#urn:oasis:ebxml:sbdhreceiptacknowledgement:ebbp-signals-2.0



Værdierne hentes fra MedComs standardkatalog og er her repræsenteret ved de værdier, som de har i MedCom meddelelserne. Se bogmærke: [DKEDEL_DT_CodeList]

Ift. det oprindeligt intentionerede fjernes dobbelt ”\#\#” og ”::” fra konstruktionen af InstanceIdentifier, da den aktuelle konfiguration af SMP fra CEF ikke kan håndtere disse så værdierne kan fremsøges igen. Dermed må SBDH’s DOCUMENTID ændres tilsvarende.

#### DOCUMENTID for MedCom FHIR Meddelelser

\<Scope\>

\<Type\>DOCUMENTID\</Type\>

\<InstanceIdentifier\>

urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:[Bundle.MessageHeader.eventCoding.code.value]\#urn:dk:medcom:fhir:[Bundle.MessageHeader.definition.[value of \|]]

\</InstanceIdentifier\>

\<Identifier\>dk-medcom-messaging\</Identifier\>

\</Scope\>

##### DOCUMENTID for MedCom FHIR Meddelelseseksempel

\<Scope\>

\<Type\>DOCUMENTID\</Type\>

\<InstanceIdentifier\>

urn:dk:medcom:prod:messaging:fhir:structuredefinition:homecareobservation-message\#urn:dk:medcom:fhir:homecareobservation:3.0

\</InstanceIdentifier\>

\<Identifier\>dk-medcom-messaging\</Identifier\>

\</Scope\>

#### DOCUMENTID for MedCom kvitteringer

##### DOCUMENTID for MedCom FHIR Kvitteringer:

\<Scope\>

\<Type\>DOCUMENTID\</Type\>

\<InstanceIdentifier\>

urn:dk:healthcare:prod:messaging:medcom:messaging:fhir:structuredefinition:[Bundle/MessageHeader/eventCoding/code.value]\#urn:dk:medcom:fhir:[https://medcomfhir.dk/ig/homecareobservation/2.1.0]

\</InstanceIdentifier\>

\<Identifier\>urn:urn:dk:healthcare:prod:messaging:medcom:messaging \</Identifier\>

\</Scope\>

##### DOCUMENTID for SBDH Kvitteringer:

\<Scope\>

\<Type\>DOCUMENTID\</Type\>

\<InstanceIdentifier\>

urn:dk:healthcare:prod:oasis:messaging:ebxml:schema:xsd:[eMessage/[LetterType]]\#urn:dk:healthcare:prod:messaging:medcom:messaging:oioxml:schema:xsd:[eMessage/[LetterType]]/[Letter/**StatisticalCode**]:[eMessage/[LetterType]]/[Letter/VersionCode]

\</InstanceIdentifier\>

\<Identifier\>urn:dk:healthcare:prod:messaging:medcom:messaging\</Identifier\>

\</Scope\>

#### DOCUMENTID Kvitterings Eksempler

##### DOCUMENTID for MedCom FHIR Kvitteringseksempel:

\<Scope\>

\<Type\>DOCUMENTID\</Type\>

\<InstanceIdentifier\>

urn:dk:healthcare:prod:messaging:medcom:messaging:oioxml:schema:xsd:PositiveReceipt\#urn:dk:healthcare:prod:messaging:medcom:messaging:oioxml:schema:xsd:PositiveReceipt:XCTL03:XC0330Q

\</InstanceIdentifier\>

\<Identifier\>urn:dk:healthcare:prod:messaging:medcom:messaging:oioxml\</Identifier\>

\</Scope\>

##### DOCUMENTID SBDH Kvitteringseksempel:

\<Scope\>

\<Type\>DOCUMENTID\</Type\>

\<InstanceIdentifier\>

urn:urn:dk:healthcare:prod:messaging:medcom:messaging:ebxml:schema:xsd:SBDHReceiptAcknowledgement

\</InstanceIdentifier\>

\<Identifier\>urn:urn:dk:healthcare:prod:messaging:medcom:messaging:ebxml\</Identifier\>

\</Scope\>

### SMP:PROCESSID

Værdien i InstanceIdentifier er identisk med den tilsvarende ProcessId SMP-registrering.

Værdien hentes fra nedenstående tabel:

**dk-messaging Process Identifier values**

| **Process**   | **Process Identifier value (InstanceIdentifier)** | **Identifier type** |
|---------------|---------------------------------------------------|---------------------|
| sdn-emergence | sdn-emergence                                     | dk-messaging-procid |

#### PROCESSID Eksempel: Brug i 4-corner model

I 4-corner modellen sendes emergence-registreringen med til SMP, således at afsenders AP kan slå finalreceipient op korrekt i SMP.

PROCESSID for SDN Eksempel

\<Scope\>

\<Type\>PROCESSID\</Type\>

\<InstanceIdentifier\>sdn-emergence\</InstanceIdentifier\>

\<Identifier\>dk-messaging-procid\</Identifier\>

\</Scope\>
