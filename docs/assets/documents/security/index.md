# EHMI Security 

- [General information regarding security for components in EHMI](#general-information-regarding-security-for-components-in-ehmi)

- [General security definitions for components in the message chain](#general-security-definitions-for-components-in-the-message-chain)

## General information regarding security for components in EHMI

It is possible to report and access data via a FHIR API. Web-services/RESTful-services, that are exposed via an interface, must, like other national web-services on the health area, comply with national architecture and national standards.

This means, among other things, that in case of personally identifiable information:

A strong authentication of users must take place (equivalent to NIST level 3-4 or NSIS level “significant”).

1.  Access control must be carried out based on national standardized information (attributes).
2.  Consent/rejection and treatment relation (dansk: behandlingsrelation) must be checked against the national consent service and the national treatment relation service (dansk: behandlingsrelationservice)
3.  Information about healthcare professionals’ access to personal data must be viewable by the citizen via MinLog. 

The general and specific security about this is described in: <a href="../security/media/Sikkerhedsarkitektur EHMI services v098.pdf" target="_blank">Security architecture EHMI support services v05 (opens in new window)</a>

<br/> 


## General security definitions for components in the message chain

Following definitions for all systems/components in EHMI apply: 

-   Systems/components can be a stand-alone application or **build together** with one or more systems/components in the message flow.
-   Systems/components can be a stand-alone application or **grouped together** with one or more systems/components in the message flow on the same server. 

<br/> 


## EHMI Core Security Description

EHMI Core Security is defined as
- the needed security implementation to serve message delivering as described in [EHMI Core Description](../ecore/index.md#ehmi-core-description)
- the already established security implementation regarding XDS Document Sharing on NSP
    - this part of EHMI Core Security is described <a href="https://www.nspop.dk/display/Web3/E.+Sikkerhed+og+Logning" target="_blank">here (Link to NSP opens in a new window)</a>

- [EHMI Core Security Description](security-specification-of-ehmi-core.md)

<br/> 

## EHMI Delivery Status Security Description

EHMI Delivery Status Security is defined as
- the needed security implementation to serve EHMI Delivery Status as described in [EHMI Delivery Status Description](../eds/index.md#ehmi-delivery-status-description)

- [EHMI Delivery Status Security Description](security-specification-of-ehmi-eds.md)

### EHMI Delivery Status Security Description

EHMI Delivery Status Security is handled as described in chapter 1-4 in:
- <a href="./media/Sikkerhedsarkitektur EHMI services v098.pdf" target="_blank">Sikkerhedsarkitektur EHMI services v 0.5/Security architechture regarding EHMI central services v 0.98 (opens in new window)</a>

<b><i>This specification has been updated with security specifications pointed out in the FAPI 2.0 specification.</i></b>
- If you want to read more about FAPI <a href="https://medium.com/@hidebike712/fapi2-explained-8602e52596e5" target="_blank">click here</a> 


In the document EUAs, MSHs and APs are named "stations" in the message flow.

<br/> 
