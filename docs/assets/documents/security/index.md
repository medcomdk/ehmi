# EHMI Security 

- [General information regarding security for components in EHMI](#general-information-regarding-security-for-components-in-ehmi)

- [General security definitions for components in the message chain](#general-security-definitions-for-components-in-the-message-chain)

- [EHMI Core Security](#ehmi-core-security)

- [EHMI Delivery Status Security](#ehmi-delivery-status-security)

- [EHMI Addressing Service Security](#ehmi-addressing-service-security)

- [EHMI Endpoint Register Security](#ehmi-endpoint-register-security)

## General information regarding security for components in EHMI

It is possible to report and access data via a FHIR API. Web-services/RESTful-services, that are exposed via an interface, must, like other national web-services on the health area, comply with national architecture and national standards.

This means, among other things, that in case of personally identifiable information:

A strong authentication of users must take place (equivalent to NIST level 3-4 or NSIS level “significant”).

1.  Access control must be carried out based on national standardized information (attributes).
2.  Consent/rejection and treatment relation (dansk: behandlingsrelation) must be checked against the national consent service and the national treatment relation service (dansk: behandlingsrelationservice)
3.  Information about healthcare professionals’ access to personal data must be viewable by the citizen via MinLog. 

The general and specific security about this is described in: <a href="./media/Sikkerhedsarkitektur EHMI services v098.pdf" target="_blank">Sikkerhedsarkitektur EHMI services v 0.5/Security architechture regarding EHMI central services v 0.98 (opens in new window)</a>

<br/> 

## General security definitions for components in the message chain

Following definitions for all systems/components in EHMI apply: 

-   Systems/components can be a stand-alone application or **build together** with one or more systems/components in the message flow.
-   Systems/components can be a stand-alone application or **grouped together** with one or more systems/components in the message flow on the same server. 

<br/> 

## EHMI Core Security

EHMI Core Security is defined as
- the needed security implementation to serve message delivering as described in [EHMI Core Description](../ecore/index.md#ehmi-core-description)
- the already established security implementation regarding XDS Document Sharing on NSP
    - this part of EHMI Core Security is described <a href="https://www.nspop.dk/display/Web3/E.+Sikkerhed+og+Logning" target="_blank">here (Link to NSP opens in a new window)</a>

- [EHMI Core Security Description](security-specification-of-ehmi-core.md)

## EHMI Delivery Status Security

EHMI Delivery Status Security is defined as
- the needed security implementation to serve EHMI Delivery Status as described in [EHMI Delivery Status Description](../eds/index.md)
- [Specific EHMI Delivery Status Security Description](security-specification-of-ehmi-eds.md)

## EHMI Addressing Service Security

EHMI Addressing Service Security is defined as
- the needed security implementation to serve EHMI Addressing Service as described in [EHMI Addressing Service Description](../eas/index.md)
- [Specific EHMI Addressing Service Security Description](security-specification-of-ehmi-eas.md)

## EHMI Endpoint Register Security

EHMI Endpoint Register Security is defined as
- the needed security implementation to serve EHMI Endpoint Register as described in [EHMI Endpoint Register Description](../ees/index.md)
- [Specific EHMI Endpoint Register Security Description](security-specification-of-ehmi-eer.md)

<br/> 
