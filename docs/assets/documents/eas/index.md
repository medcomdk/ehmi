# EHMI Addressing Service (EAS)

***
    **Disclaimer - The menu items above marked with a star are yet not specified**
     
<br/> 

When a user of EHMI wants to send a message, the correct recipient of the message needs to be found somehow unless the user happens to know it by heart. Such a search function already exists to varying degrees in the various user systems, and to make these searches easier, EAS provides useful standardized search services based on relevant authoritative sources (like for example the national register of organizations within the health domain (SOR)).

When EAS receives a search request from a user system EAS in turn calls the relevant authoritative sources responsible for the information needed for the particular type of search request, and based on this EAS constructs the response for the user system. In this way EAS decouples the user systems from the authoritative sources and the, sometimes cumbersome, logic to be implemented to support searches for recipients in various different situations only needs to be implemented and maintained in EAS.

Examples of search services EAS support include: 
* Search for a patient’s general practitioner.
* Search for general practitioners in a delimited geographical area (relevant for patients with no fixed general practitioner).
* Search for recipients capable of receiving specific types of messages – not just the overall message type (including version), but also more detailed searches concerning specific aspects of the message to be sent (relevant, e.g., in relation to referrals for X-ray examinations that require special equipment not offered by all X-ray departments).

An outline of the components in the EHMI network's use of the EHMI Adressing Service can be seen here:
<img src="https://medcomdk.github.io/ehmi/assets/images/EHMI%20Pixi%20-%20Addressing%20Service.png" alt="EHMI Addressing Service (EAS) (DA)" width="100%">

**The whole specification for EHMI Addressing Service (EAS) can be found** 
<a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eas/" target="_blank">here</a>
    
