# Specification of security regarding central EHMI services 

***

    **Disclaimer - The menu items above marked with a star are yet not specified**
    
<br/> 


## Table of context

- [General information regarding security for components in EHMI](#general-information-regarding-security-for-components-in-ehmi)

- [General security definitions for components in the message chain](#general-security-definitions-for-components-in-the-message-chain)

- [Security specifications regarding EHMI Delivery Status of messages](#security-specifications-regarding-ehmi-delivery-status-of-messages)

- [Submission to EHMI Delivery Service repository](#submission-to-ehmi-delivery-service-repository)

- [Client security for EHMI Delivery Status - submission](#client-security-for-ehmi-delivery-status---submission)

- [Exhibition via service](#exhibition-via-service)

- [Client security for EHMI Delivery Status – search](#client-security-for-ehmi-delivery-status---search)

- [Security specifications regarding EHMI Addressing Service](#security-specifications-regarding-ehmi-addressing-service)

- [Decentral regarding EHMI Addressing Service](#decentral-regarding-ehmi-addressing-service)

<br/> 


## Security specifications regarding EHMI Delivery Status of messages

Security in relation to delivery status is divided into these different steps: 

1. EHMI Delivery Status is collected and saved in a repository.
2. EHMI Delivery Status is retrieved by users via displayed services.

<br/> 


### Submission to EHMI Delivery Service repository

From the Architecture Vision, we know that security around this is necessary partly so that the users will consider the service based on the collected data to be trustworthy, and partly because personal data is collected, since unique citizen identification (most often the CPR number) is part of the collected information: 

-   **Authenticity:** A component that stores EHMI Delivery Status for messages must authenticate itself when accessing the repository. 
-   **Availability:** Agreed uptime and response must be ensured via standard operating mechanisms. This is particularly important, as EHMI Delivery Status, cf. section 5.2.8, must be updated close to real-time. 
-   **Integrity:** Ensured by the protocol through which the collection is implemented.
-   **Non-repudiation:** A component, that stores EHMI Delivery Status, must audit log the collection in a standardized way.
-   **Confidentiality:** When the collected EHMI Delivery Status is communicated to the repository, it is secured either via explicit encryption or implicit encryption in the underlying infrastructure level.

<br/> 


#### Client security for EHMI Delivery Status - Submission

| **EHMI components**                                                         | **Subtask**                                                                                                                       | **Who**                                                                    |
|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| EHMI Delivery Status-component                                                 | **Authenticity:** A component, that stores EHMI Delivery Status for messages must authenticate itself when accessing the repository.  | Sending system (Sending system/MSH/AP)                             |
| Sending system (Sending system/MSH/AP)                              | **Authenticity management:** Implementation of signing submission                                                           | Sending system (Sending system/MSH/AP)                             |
| EHMI Delivery Status-component                                                 | **Authenticity management:** Verification of signature upon receipt.                                                              | EHMI Delivery Statuscomponent                                                 |
| Sending system (Sending system/MSH/AP) EHMI Delivery Status-component | **Integrity protection and confidentiality protection:** Communication via secured transport protocol, e.g. TLS                              | Sending system (Sending system/MSH/AP) EHMI Delivery Status-component |
| Sending system (Sending system/MSH/AP) EHMI Delivery Status-component | **Availability:** Implementation of queue mechanism to handle that a connection may be down                                  | Sending system (Sending system/MSH/AP) EHMI Delivery Status-component |

<br/> 


### Submissions in relation to the scenarios in [Specifications – security regarding message communication](./security-specification-of-ehmi-core.md#Specifications---security-regarding-message-communication)

In the following, both sides of the sender and receiver ecosystems are assumed to have the same setup as the sending ecosystem. In practice, Sender and Receiver ecosystems are potentially very different, and in that case the different scenarios must be combined accordingly. 

| **Scenarios** | **Starting/Incoming submission** | **Final/outgoing submission** |
|---|---|---|
| [All components stand-alone – implemented on different servers](./security-specification-of-ehmi-core.md#all-components-stand-alone---implemented-on-different-servers) <br/> [All components stand-alone – grouped together on the same server](./security-specification-of-ehmi-core.md#all-components-stand-alone---grouped-together-on-the-same-server) <br/> [All components stand-alone – sending system and MSH grouped together on the same server](./security-specification-of-ehmi-core.md#all-components-stand-alone---sending-system-and-msh-grouped-together-on-the-same-server) <br/> [All components stand-alone - MSH and AP grouped together on the same server](./security-specification-of-ehmi-core.md#all-components-stand-alone-msh-and-ap-grouped-together-on-the-same-server) <br/> <br/> <br/>  | Sending system  <br/> Sending MSH <br/>  Sending AP <br/> ------------------------------------------- <br/> Receiving AP <br/>  Receiving MSH <br/> | Sending MSH <br/> Sending AP <br/> ------------------------------------------- <br/> Receiving AP <br/>  Receiving MSH <br/>  Receiving system <br/> |
| | | |
| [Sending system stand-alone - MSH/AP build together - implemented on different servers](./security-specification-of-ehmi-core.md#sending-system-stand-alone---mshap-build-together---implemented-on-different-servers) <br/> [Sending system stand-alone - MSH/AP build together - all grouped on the same server](./security-specification-of-ehmi-core.md#sending-system-stand-alone---mshap-build-together---all-grouped-on-the-same-server) <br/> <br/> <br/> | Sending system <br/> Sending MSH/AP <br/> ------------------------------------------- <br/> Receiving MSH/AP <br/> | Sending MSH/AP <br/>  ------------------------------------------- <br/> Receiving MSH/AP <br/> Receiving system <br/> |
| | | |
| [Sending system/MSH build together - AP stand-alone - implemented on different servers](./security-specification-of-ehmi-core.md#sending-systemmsh-build-together--ap-stand-alone---implemented-on-different-servers) <br/> [Sending system/MSH build together - AP stand-alone - all grouped together on the same server](./security-specification-of-ehmi-core.md#sending-systemmsh-build-together---ap-stand-alone--all-grouped-together-on-the-same-server) <br/><br/> | Sending system/MSH <br/> Sending AP <br/> ------------------------------------------- <br/> Receiving AP <br/> | Sending AP <br/> ------------------------------------------- <br/> Receiving AP <br/> Receiving system/MSH <br/> |
| | | |
| [Sending system/MSH build together – MSH/AP build together - implemented on different servers](./security-specification-of-ehmi-core.md#sending-systemmsh-build-together---mshap-build-together---implemented-on-different-servers) <br/> [Sending system/MSH build together – MSH/AP build together - all grouped on the same server](./security-specification-of-ehmi-core.md#sending-systemmsh-build-together---mshap-build-together--all-grouped-on-the-same-server) <br/> <br/> | Sending system/MSH <br/> Sending AP/MSH <br/> ------------------------------------------- <br/> Receiving AP/MSH <br/> | Sending AP/MSH <br/> ------------------------------------------- <br/> Receiving AP/MSH <br/> Receiving system/MSH <br/> |
| | | |
| [All components build together](./security-specification-of-ehmi-core.md#all-components-build-together) <br/> | Sending system/MSH/AP <br/> | Receiving system/MSH/AP <br/> |

<br/> 


### Exhibition via service

From the Architecture Vision, we know that the service, who exhibit EHMI Delivery Status on messages, must comply to the same security requirements and rules as other services in the health area, cf. the Architecture Vision’s principle PT6. Therefore, several of the same already existing security mechanisms from other services should be used:

-   **Authenticity:** The service must be presented as a DGWS/IDWS service or a similar level, and the users (both systems, health professionals and citizens) must use digital certificates when calling the service in the same way as for other services on the healthcare area. Again, it is a requirement, that the certificates used are at user credentials level. For systems, however, the certificates must be at system credentials level.
-   **Availability:** Agreed uptime and response time are ensured via the platform on which the service is carried out.
-   **Integrity:** Secured by the protocol with which the service is implemented.
-   **Non-repudiation:** The service implements a standardized audit log. Logging to MinLog is required in cases where a citizen retrieves the EHMI Delivery Status for messages concerning a citizen other than himself, and where a healthcare professional retrieves EHMI Delivery Status specifically for a citizen.
-   **Confidentiality:** The service must actively use the identification of the user (system, healthcare professional or citizen) as well as the search parameters, that are part of the call for the service.

Since the service is exhibited and performed on a platform, that may have its own and more strict security politics than the general security politics in the healthcare area, these must also be observed if necessary.

<br/> 


#### Client security for EHMI Delivery Status - Search

It will be based on an OAuth-secured REST-interface and SMART-on-FHIR or similar.

For the collection of EHMI Delivery Status, explicit signature between the EHMI Delivery Status “client” and “server” (with associated verification) on system credentials level (VOCES/FOCES/Niveau 3) is required, cf. section 6.3.1 in the Architecture Vision.

To search for EHMI Delivery Status, it is required to use identification on system credentials level (VOCES/FOCES/Niveau 3) between the EHMI Delivery Status “client” and “server”.

To search for EHMI Delivery Status, it is further required to use identification on user credentials level (MOCES/MitID/Niveau 4) for a citizen’s own access as well as a healthcare professional’s specific access via the citizen’s/patient’s record. 

| **EHMI components**                                                 | **Subtask**                                                                                                                 | **Who**                                                             |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Sending system (Sending system/MSH/AP)                      | **Authenticity management:** Implementation of signing submissions                                                      | Sending system (Sending system/MSH/AP)                      |
| Receiving component                                                 | **Authenticity management:** Verification of signing upon receiving.                                                        | Receiving component                                                 |
| Sending system (Sending system/MSH/AP) Receiving component | **Integrity protection and confidentiality protection:** Communication of message/envelope via secured transport protocol, e.g. TLS | Sending system (Sending system/MSH/AP) Receiving component |

<br/> 


## Security specifications regarding EHMI Addressing Service

From the Architecture Vision it is known, that EHMI Addressing Service must comply to the same security requirements and rules as corresponding services on the healthcare area, and therefore more of the same already existing security mechanisms should be used: 

-   **Authenticity:** The service must be presented as a DGWS/IDWS service, and the users must use digital certificates when calling the service in the same way as for other services on the healthcare area. Due to the nature of the service, it is in this case sufficient, that the used certificates are at system credentials level.
-   **Availability:** Agreed uptime and response time must be ensured via the platform on which the service is carried out, e.g. via standard operating mechanisms such as fail-over and load-balancing.
-   **Integrity:** Secured by the protocol with which the service is implemented.
-   **Non-repudiation:** The service must implement standardized audit log. 
-   **Confidentiality:** The service must use the identification of the user as well as the search parameters, that are part of the call for the service. An actual user management in relation to who calls the service, is assumed to be enforced by the calling systems. So, when a user system is correctly authenticated, there is access to the service.

Since the service is exhibited and performed on a platform, that may have its own and more strict security politics than the general security politics in the healthcare area, these must also be observed if necessary.

<br/> 


### Decentral regarding EHMI Addressing Service

| **EHMI components**                                       | **Subtask**                                                                                                                                                                                                                        | **Who**                                                  |
|------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| Sending system (System)                              | **Authenticity management:** Implementation of signing a search (VOCES/FOCES)                                                                                                                                                    | Sending system (System)                             |
| EHMI Addressing Service                               | **Authenticity management:** Verification of signing (VOCES/FOCES)                                                                                                                                                                 | EHMI Addressing Service                               |
| Sending system (System) EHMI Addressing Service | **Integrity protection and confidentiality protection:** Communication secured via transport protocol, e.g. TLS                                                                                                                               | Sending system (System) EHMI Addressing Service |
| Sending system (System) EHMI Addressing Service | **Availability:** Implementation of fixed searches, which may be locally saved to handle if a connection is down. If the service is online, one should always search online. Fixed searches should be updated outside peak hours | Sending system (System) EHMI Addressing Service

<br/> 
