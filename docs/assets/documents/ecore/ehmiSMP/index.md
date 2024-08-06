# EHMI Service Metadata Provider – ehmiSMP configuration

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
       
<br/> 

## ehmiSMP

- [eDelivery SMP profile](#edelivery-smp-profile)
- [SMP ServiceMetadata in general eDelivery message communication](#smp-servicemetadata-in-general-edelivery-message-communication)
- [Connection to SBDH](#connection-to-sbdh)
- [SMP DocumentIdentifier](#smpdocumentidentifier)
- [SMP ProcessIdentifier](#smpprocessidentifier)
- [SMP at Digital Europe (EU)](#smp-at-digital-europe-eu)

<br/> 

EHMIs SMP, ehmiSMP, follows the generel eDelivery SMP functionality.

ehmiSMP will eventually be populated from the EHMI Endpoint Register (EER), but will, in the EHMI Production Pilot, be populated via scripts managed by MedCom.
    
<br/> 

### eDelivery SMP profile
    
<br/> 

The eDelivery SMP profile is an open specification for publishing service metadata within a 4-corner network. To successfully send a business document in a 4-corner network, an entity must be able to discover critical metadata about the recipient (Access Point) of the business document, such as types of documents the Access Point is capable of receiving and methods of transport supported. The recipient makes this metadata available to other entities in the network through a Service Metadata Publisher service. The eDelivery SMP profile describes the request/response exchanges between a Service Metadata Publisher and a client wishing to discover Access Point metadata. The profile is based on the OASIS Service Metadata Publishing (SMP) Version 1.0 standard.

<br/>

## SMP ServiceMetadata in general eDelivery message communication

<br/>

### Connection to SBDH

<br/>

In the eDelivery communication, the SBDH Scope structure with the two types, DOCUMENTID and PROCESSID, forms (in addition to the values in the elements Sender and Receiver) a direct connection to the SMP DocumentIdentifier and ProcessIdentifier in the ServiceMetadata structure. In the following, these two types of elements in SMP are described. 

In PEPPOL, the scopes of DOCUMENTID and PROCESSID are permanently defined scopes, which ensure a unique relation to SBDH. DOCUMENTID and PROCESSID is used in EHMI with the same precision as in PEPPOL, which ensure a certain uniformity in how the values across of PEPPOL and EHMI is expressed. DOCUMENTID and PROCESSID is used by the APs together with the recipient’s ReceiverId to look up the recipient’s eDelivery address in SMP with a unique response as result. 

<br/>

### SMP:DocumentIdentifier

<br/>

The value in DocumentIdentifier is identical to the corresponding ehmiSBDH-registration for BusinessScope/Scope[DOCUMENTID]:

    SMP ServiceInformation/DocumentIdentifier
    
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:homecareobservation\#urn:dk:medcom:fhir:homecareobservation:3.0
    urn:dk:healthcare:prod:medcom:messaging:fhir:structuredefinition:acknowledgement\#urn:dk:medcom:fhir:acknowledgement:2.0
    urn:dk:healthcare:prod:messaging:oasis:ebxml:schema:xsd:sbdhreceiptacknowledgement\#urn:oasis:ebxml:sbdhreceiptacknowledgement:ebbp-signals-2.0


The values are taken from MedComs standard catalog and are represented here by the values they have in MedCom messages. See bookmark: [DKEDEL_DT_CodeList]

Regarding the originally intended, double ”##” and ”::” are removed from the construction of InstanceIdentifier, as the current configuration of SMP from CEF cannot handle these, so that the values can be retrieved again. This means that SBDH's DOCUMENTID must be changed accordingly.

<br/>

### SMP:ProcessIdentifier

<br/>

The value in ProcessIdentifier is identical with the corresponding ehmiSBDH-registration for BusinessScope/Scope[DOCUMENTID]:

The value is obtained from the following: 

    ProcessList/Process/ProcessIdentifier

    sdn-emergence


By now, the value is of static character. This will change when communicating in and out of the healthcare area. The term “sdn-emergence” stands for the ”emergence” of a message on the health domain/health data network “sdn”. 

<br/>

### SMP at Digital Europe (EU)

<br/>

<a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/SMP+specifications" target="_blank">SMP at Digital Europe (EU)</a>

