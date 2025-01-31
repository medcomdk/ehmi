# Specification of security regarding EHMI Addressing Service

## Table of context
- [Security specifications regarding EHMI Addressing Service](#security-specifications-regarding-ehmi-addressing-service)

- [Client security for EHMI Addressing Service – the specific technical details](#)

<br/> 

## Security specifications regarding EHMI Addressing Service

From the Architecture Vision it is known, that EHMI Addressing Service must comply to the same security requirements and rules as corresponding services on the healthcare area, and therefore more of the same already existing security mechanisms should be used: 

-   **Authenticity:** The service must be presented as a DGWS/IDWS service, and the users must use digital certificates when calling the service in the same way as for other services on the healthcare area. Due to the nature of the service, it is in this case sufficient, that the used certificates are at system credentials level.
-   **Availability:** Agreed uptime and response time must be ensured via the platform on which the service is carried out, e.g. via standard operating mechanisms such as fail-over and load-balancing.
-   **Integrity:** Secured by the protocol with which the service is implemented.
-   **Non-repudiation:** The service must implement standardized audit log. 
-   **Confidentiality:** The service must use the identification of the user as well as the search parameters, that are part of the call for the service. An actual user management in relation to who calls the service, is assumed to be enforced by the calling systems. So, when a user system is correctly authenticated, there is access to the service.
<br/> 
Since the service is exhibited and performed on a platform, that may have its own and more strict security politics than the general security politics in the healthcare area, these must also be observed if necessary.

<br/> 


<br/> 

### Client security for EHMI Addressing Service – the specific technical details

After having crunched the general description of the security mdel in "Sikkerhedsarkitektur EHMI services/Security architechture regarding EHMI central services" the nitty gritty technical details can also be found in English in the <a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eas/security-eas-english.html" target="_blank">EDS IG (opens in a new window)</a>