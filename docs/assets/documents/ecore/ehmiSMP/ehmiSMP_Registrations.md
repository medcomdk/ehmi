([CHG]: Denne side bliver der ikke linket til fra sitet, er den stadig relevante eller skal den slettes?)

# ehmiSMP (EHMI Service Metadata Provider) – konfiguration

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
       
<br/> 

## ehmiSMP
    
<br/> 

EHMIs SMP, ehmiSMP, vil følge den generelle eDelivery funktionalitet for SMP.

ehmiSMP vil med tiden blive populeret fra EHMI Endpoint Register (EER), men vil i Produktionspiloten blive populeret via scripts styret af MedCom.
    
<br/> 

### eDelivery SMP profile
    
<br/> 

The eDelivery SMP profile is an open specification for publishing service metadata within a 4-corner network. To successfully send a business document in a 4-corner network, an entity must be able to discover critical metadata about the recipient (Access Point) of the business document, such as types of documents the Access Point is capable of receiving and methods of transport supported. The recipient makes this metadata available to other entities in the network through a Service Metadata Publisher service. The eDelivery SMP profile describes the request/response exchanges between a Service Metadata Publisher and a client wishing to discover Access Point metadata. The profile is based on the OASIS Service Metadata Publishing (SMP) Version 1.0 standard.

<br/>

# SMP 

<br/>

## SMP ServiceMetadata i generel eDelivery meddelelseskommunikation

<br/>

### Sammenhæng til SBDH

<br/>

I eDelivery kommunikationen udgør SBDH’ens Scope struktur med de to typer, DOCUMENTID og PROCESSID, foruden værdierne i elementerne Sender og Receiver, den direkte sammenhæng til SMP’ens DocumentIdentifier og ProcessIdentifier i ServiceMetadata-strukturen. I det følgende beskrives disse 2 Type elementer i SMP.

Scopene DOCUMENTID og PROCESSID er i PEPPOL fast definerede scopes, som sikrer en unik relation til SBDH. DOCUMENTID og PROCESSID anvendes i EHMI med samme præcision som i PEPPOL, så der sikres en vis ensartethed i, hvordan man udtrykker værdierne på tværs af PEPPOL og EHMI. DOCUMENTID og PROCESSID bruges af AP’erne sammen med modtagers ReceiverId til at slå modtagers eDelivery adresse op i SMP med et unikt respons som resultat.

<br/>

### SMP:DocumentIdentifier

<br/>

Værdien i DocumentIdentifier er identisk med den tilsvarende ehmiSBDH-registrering for BusinessScope/Scope[DOCUMENTID]:

    SMP ServiceInformation/DocumentIdentifier
    
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:homecareobservation\#urn:dk:medcom:fhir:homecareobservation:3.0
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:acknowledgement\#urn:dk:medcom:fhir:acknowledgement:2.0
    urn:dk:healthcare:prod:messaging:oasis:ebxml:schema:xsd:sbdhreceiptacknowledgement\#urn:oasis:ebxml:sbdhreceiptacknowledgement:ebbp-signals-2.0


Værdierne hentes fra MedComs standardkatalog og er her repræsenteret ved de værdier, som de har i MedCom meddelelserne. Se bogmærke: [DKEDEL_DT_CodeList]

Ift. det oprindeligt intentionerede fjernes dobbelt ”\#\#” og ”::” fra konstruktionen af InstanceIdentifier, da den aktuelle konfiguration af SMP fra CEF ikke kan håndtere disse så værdierne kan fremsøges igen. Dermed må SBDH’s DOCUMENTID ændres tilsvarende.

<br/>

### SMP:ProcessIdentifier


<br/>

Værdien i ProcessIdentifier er identisk med den tilsvarende ehmiSBDH-registrering for BusinessScope/Scope[PROCESSID]:

Værdien hentes fra nedenstående:

    ProcessList/Process/ProcessIdentifier

    sdn-emergence


Umiddelbart er værdien af statisk karakter. Dette vil ændre sig, når der kommunikeres ind og ud af sundhedsområdet. Udtrykket "sdn-emergence" står for en meddelelses "opkomst" på sundhedsdomænet/sundhedsdatanettet "sdn"

