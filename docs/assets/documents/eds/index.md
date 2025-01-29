# EHMI Delivery Status (EDS)

## EHMI Delivery Status is defined as 

EHMI Delivery Status is defined as 
- The registration of EHMI Delivery Status (FHIR AuditEvents) from each EDS Client in the primary message delivering from a sender's End User Application (EUA) to a receiver's End User Application (EUA)
- The registration of EHMI Delivery Status (FHIR AuditEvents) from each "station" in the secondary message delivering from a sender's Message Service Handler to the national XDS Document Sharing platform on NSP or a similar decentral system 
- The EDS Server component implemented as a FHIR server that will host the registered data coming in from the clients at each station of EUAs, MSHs and APs in the primary and secondary messaging flow. The server will expose two FHIR APIs for the clients to registrate their status:
    - <a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/StructureDefinition-EdsBasicDeliveryStatus.html" target="_blank">EdsBasicDeliveryStatus</a> for registrations of message status without patient data, eg. Acknowledgments (opens in a new window)
    - <a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/StructureDefinition-EdsPatientDeliveryStatus.html" target="_blank">EdsPatientDeliveryStatus</a> for registrations of message status containing patient data (opens in a new window)
- The source for the future statistical database for EHMI

In general EDS clients can be either an EUA, a MSH or an AP and throughout the documentation the term "EDS Client(s)" will be used whenever it's not important whether it's one of them particularly. EDS Clients are like stations a train is arriving and leaving at, in this case just software applications.

In FHIR this kind of software is called a Device, which is a term that in fact covers a lot of different types of software and other patient support devices as well. EDS implements a EDS Client as a Device, which will be found in EER's set of profiled FHIR resources.

## What is registred in EDS

Registration is made on certain message-events happening in a message's journay from the sender EUA to the receiver EUA.
- whenever a messaged is created and sent from the sender's EUA to it is being received and has been sent from another EDS Client until it's received in the receivers EUA, the kind of event is being recorded as type and subtypes
- who is involved in the message exchange is also being recorded, ie. a limited set of the sender's and the receiver's SOR-data is being recorded as agents (name, SOR-Id, GLN-Id)
- the source of the registration, ie. the EDS Client's Device-data
- the patient involved (not in acknowledgemnet registrations though)
- date and time of the registration
- data-codes of entities being delivered
  - message identifier
  - message type and version
  - envelope identifier
  - envelope type and version
  - message details relevant for statistical analysis like a category of a CareCommunication Message 

The EDS Server and EDS Clients are expected to implement the user stories outlined [here](./userstories/index.md)

<br/> 
  
## Querying EDS

Besides EDS registrations, EDS also supports querying the registrations on the EDS Server.

Access for these queries is limited to delivery status registrations for messages which include registrations created by the EDS Client. That is, an EDS Client can access all registrations for a given message it has been involved in transferring from one EDS Client to another.

Senders EUA and receivers EUA can access all registrations around messages they have beden involved in as a sender or a receiver defined by their SOR-ID

Patients can access all registrations of messages which they have been the subject for.

<br/> 
  
## An outline of the components of the EHMI Delivery Status can be seen here:
    
<br/> 

![EHMI Delivery Status (EDS)](../../images/EHMI_Pixi_EDS.jpg)

<br/> 
  
**The whole specification for EHMI Delivery Status can be found** 
<a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/" target="_blank">here</a>
    
