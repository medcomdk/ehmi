# EHMI Message Service Handler (MSH) Responsibility Specification

The following prerequisites for the Message Service Handler (MSH) apply:

-   MSH is a component that can be a stand-alone application, integrated with an End User Application (EUA), integrated with an EHMI AP or integrated with both (both End User Application (EUA)  and EHMI Access Point (AP).
-   MSH must be able to communicate via a secured interface with the End User Application (EUA). As well as be able to receive a MedCom message or the data content for a MedCom message via the interface to MSH from the End User Application (EUA).
-   MSH must be able to make any mappings between the End User Application (EUA)'s format and a correctly formatted MedCom message.
-   MSH must be able to handle SBDH envelopes at PEPPOL level, i.e. be able to wrap a MedCom message and transfer metadata from it to the SBDH envelope, as well as apply metadata to the correct BusinessScope/Scopes in the SBDH envelope. How the SBDH envelope is to be filled in is being defined by MedCom but complies with the basic PEPPOL specification, so the SBDH data will be usable for a PEPPOL-compliant AP.
-   MSH must be able to receive sufficient metadata from the End User Application (EUA)  to be able to create an SBDH envelope for both the primary recipient and the secondary recipient in the form of XDS metadata to DDS (Document Sharing Service, in Danish Dokument Delings Service (DDS)).
-   MSH must be able to control which messages are sent directly to the primary recipient and which are sent in copy with XDS metadata to DDS.
-   MSH must be able to communicate the SBDH envelope via a secured interface with EHMI AP.
-   EHMI MSH must be able to handle SBDH acknowledgement in both the sender and receiver ecosystems. The SBDH acknowledgement is an embedded ebXML Business SignalMessage, similar to AS4 acknowledgements.
-   MSH must be subject to high uptime requirements in line with other central critical components in the healthcare system, and like these, it must also comply with common requirements for the operation of critical systems such as logging and backup.


## EHMI Delivery Status - MSH responsibility description:

As an additional task, EHMI MSH must be able to communicate with the EHMI Delivery Status (EDS) repository (track’n’trace).

The EHMI Delivery Status (EDS) repository has a reporting API that the AP must communicate via. 

For the collection of delivery status, it is required that, according to section 6.3.1 of the Architectural Vision, the delivery status is explicitly signed between the “client” and the “server” (with associated verification) at system evidence level (VOCES/FOCES/Level 3).

Furthermore, in this context, there is a requirement that the collection is carried out via an asynchronous decoupling mechanism (queue), so that it is ensured that no delivery status data is lost.


## EHMI MSH's responsibility for communicating with the XDS infrastructure

EHMI MSH must be able to handle XDS Metadata formatted as the FHIR DocumentReference resource. MedCom is profiling the FHIR DocumentReference resource. The MSH must be able to create the MedCom FHIR DocumentReference profile with the correct data. EHMI MSH must be able to insert the extra metadata in the MedCom FHIR DocumentReference resource into the designated BusinessScope/Scope in the SBDH envelope.

