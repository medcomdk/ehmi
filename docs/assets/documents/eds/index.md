# EHMI Delivery Status (EDS)

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
    
    ***There will occur shifts of languages between English and Danish in this version - that will change completely to English in the next upcoming version***
    
***

EHMI Delivery Status is defined as 
- a server component implemented as a FHIR server that will host the registred data coming in from the clients at each station of EUAs, MSHs and APs in the primary and secondary messaging flow. The server will expose two APIs for the client to registrate their status:
    - [EdsBasicDeliveryStatus](https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/StructureDefinition-EdsBasicDeliveryStatus.html) for registrations of message status without patient data, eg. Acknowledgments
    - [EdsPatientDeliveryStatus](https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/StructureDefinition-EdsPatientDeliveryStatus.html) for registrations of message status containing patient data
- clients that handle the registration of EHMI Delivery Status (FHIR AuditEvents) from each "station" in the primary message delivering from a sender system to a receiver system 

The specification for EHMI Delivery Status can be found 
<a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eds/" target="_blank">here</a>
    
***
  
An outline of the components of the EHMI network's reporting to the component can be seen here:
    
***

![EHMI Delivery Status (EDS)](https://medcomdk.github.io/ehmi/assets/images/2_EHMI_Forsendelsesstatus_1315x551.png)
