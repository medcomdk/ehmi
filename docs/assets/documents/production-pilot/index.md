# EHMI Production Pilot Description

**Table of contents**

- EHMI Production Pilot Description
    - [EHMI Core Description](#ehmi-core-description)
    - [EHMI Core Security Description](#ehmi-core-security-description)
    - [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - [EHMI Delivery Status Security Description](#ehmi-delivery-status-security-description)

## EHMI Production Pilot Description

Overall the EHMI Production Pilot is described in the Projct Description as part of MedCom13 [here:](https://medcom.dk/projekter/kommunale-proevesvar-paa-ny-infrastruktur/)

### EHMI Core Description

EHMI Core is defined as 
- the primary message delivering from a sender system to a receiver system concerning 
    - End USer Applications (EUA)
    - Message Service Handlers (MSH)
    - edelivery Access Points (AP)
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP also concerning 
    - Sender's End USer Applications (EUA)
    - Message Service Handlers (MSH)
    - edelivery Access Points (AP)

### EHMI Core Security Description

EHMI Core Security is defined as
- the needed security implementation to serve message delivering as described in [EHMI Core Description](#ehmi-core-description)
    - this part of EHMI Core Security is desribed [here](../security/security-specification-of-ehmi-core.md)
- the already established security implementation regarding XDS Document Sharing on NSP
    - this part of EHMI Core Security is desribed [here (Link to NSP)]()
    
### EHMI Delivery Status Description
    
EHMI Delivery Status is defined as 
- the registration of EHMI Delivery Status (FHIR AuditEvents) from each "station" in the primary message delivering from a sender system to a receiver system 
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP

### EHMI Delivery Status Security Description

EHMI Delivery Status Security is defined as
- the needed security implementation to serve EHMI Delivery Status as described in [EHMI Delivery Status Description](#ehmi-delivery-status-description)
    - this part of EHMI Core Security is desribed [here](../security/security-specification-of-ehmi-eds.md)
    
