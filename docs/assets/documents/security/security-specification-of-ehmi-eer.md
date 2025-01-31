# Specification of security regarding EHMI services 



## Table of context

- [General information regarding security for components in EHMI](#general-information-regarding-security-for-components-in-ehmi)

- [General security definitions for components in the message chain](#general-security-definitions-for-components-in-the-message-chain)

- [Security specifications regarding EHMI Delivery Status of messages](#security-specifications-regarding-ehmi-delivery-status-of-messages)

- [Registration calls  to EHMI Delivery Status repository](#submission-to-ehmi-delivery-service-repository)

- [Client security for EHMI Delivery Status - submission](#client-security-for-ehmi-delivery-status---submission)

- [Exhibition via service](#exhibition-via-service)

- [Client security for EHMI Delivery Status – search](#client-security-for-ehmi-delivery-status---search)

- [Security specifications regarding EHMI Addressing Service](#security-specifications-regarding-ehmi-addressing-service)

- [Decentral regarding EHMI Addressing Service](#decentral-regarding-ehmi-addressing-service)

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
