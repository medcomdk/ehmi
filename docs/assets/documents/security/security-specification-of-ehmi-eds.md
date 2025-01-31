# Specification of security regarding central EHMI Delivery Status

## Table of context

- [Security specifications regarding EHMI Delivery Status of messages](#security-specifications-regarding-ehmi-delivery-status-of-messages)

- [Registration calls  to EHMI Delivery Status repository](#submission-to-ehmi-delivery-service-repository)

- [Client security for Registration calls  to EHMI Delivery Status repository](#client-security-for-ehmi-delivery-status---submission)

- [Search and lookup via service](#search-and-lookup-via-services)

- [Client security for EHMI Delivery Status – the specific technical details](#client-security-for-ehmi-delivery-status--the-specific-technical-details)

<br/> 

## Security specifications regarding EHMI Delivery Status of messages

Security in relation to delivery status is divided into these different steps: 

1. EHMI Delivery Status is collected and posted to a repository.
2. EHMI Delivery Status is retrieved by users via search and lookup services.

<br/> 

### Registration calls  to EHMI Delivery Status repository

From the Architecture Vision, we know that security around this is necessary partly so that the users will consider the service based on the collected data to be trustworthy, and partly because personal data is collected, since unique citizen identification (most often the CPR number) is part of the collected information: 

-   **Authenticity:** A component that stores EHMI Delivery Status for messages must authenticate itself when accessing the repository. 
-   **Availability:** Agreed uptime and response must be ensured via standard operating mechanisms. This is particularly important, as EHMI Delivery Status, cf. section 5.2.8, must be updated close to real-time. 
-   **Integrity:** Ensured by the protocol through which the collection is implemented.
-   **Non-repudiation:** A component, that stores EHMI Delivery Status, must audit log the collection in a standardized way.
-   **Confidentiality:** When the collected EHMI Delivery Status is communicated to the repository, it is secured either via explicit encryption or implicit encryption in the underlying infrastructure level.

<br/> 

#### Client security for Registration calls  to EHMI Delivery Status repository

| **EHMI components**                                                         | **Subtask**                                                                                                                       | **Who**                                                                    |
|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| EHMI Delivery Status-component                                                 | **Authenticity:** A component, that stores EHMI Delivery Status for messages must authenticate itself when accessing the repository.  | Sending system (EUA/MSH/AP)                             |
| Sending system (EUA/MSH/AP)                              | **Authenticity management:** Implementation of signing Registration calls                                                            | Sending system (EUA/MSH/AP)                             |
| EHMI Delivery Status-component                                                 | **Authenticity management:** Verification of signature upon receipt.                                                              | EHMI Delivery Statuscomponent                                                 |
| Sending system (EUA/MSH/AP) EHMI Delivery Status-component | **Integrity protection and confidentiality protection:** Communication via secured transport protocol, e.g. TLS                              | Sending system (EUA/MSH/AP) EHMI Delivery Status-component |
| Sending system (EUA/MSH/AP) EHMI Delivery Status-component | **Availability:** Implementation of queue mechanism to handle that a connection may be down                                  | Sending system (EUA/MSH/AP) EHMI Delivery Status-component |

<br/> 

### Search and Lookup via services

From the Architecture Vision, we know that the service, who exhibit EHMI Delivery Status on messages, must comply to the same security requirements and rules as other services in the health area, cf. the Architecture Vision’s principle PT6. Therefore, several of the same already existing security mechanisms from other services should be used:

-   **Authenticity:** The service must be presented as a DGWS/IDWS service or a similar level, and the users (both systems, health professionals and citizens) must use digital certificates when calling the service in the same way as for other services on the healthcare area. Again, it is a requirement, that the certificates used are at user credentials level. For systems, however, the certificates must be at system credentials level.
-   **Availability:** Agreed uptime and response time are ensured via the platform on which the service is carried out.
-   **Integrity:** Secured by the protocol with which the service is implemented.
-   **Non-repudiation:** The service implements a standardized audit log. Logging to MinLog is required in cases where a citizen retrieves the EHMI Delivery Status for messages concerning a citizen other than himself, and where a healthcare professional retrieves EHMI Delivery Status specifically for a citizen.
-   **Confidentiality:** The service must actively use the identification of the user (system, healthcare professional or citizen) as well as the search parameters, that are part of the call for the service.

Since the service is exhibited and performed on a platform, that may have its own and more strict security politics than the general security politics in the healthcare area, these must also be observed if necessary.

<br/> 

### Client security for EHMI Delivery Status – the specific technical details

After having crunched the general description of the security mdel in "Sikkerhedsarkitektur EHMI services/Security architechture regarding EHMI central services" the nitty gritty technical details can also be found in English in the <a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/security-EDS-english.html" target="_blank">EDS IG (opens in a new window)</a>