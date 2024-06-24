# EHMI Addressing Service (EAS)

***
    **Disclaimer** 
    
    **To be specified in Q2 2024 and through working groups 2024-2026**

    ***Shifts of languages between English and Danish will occur in this version - that will change completely to English in the next upcoming version***
    
<br/> 

When a user of EHMI wants to send a message, the correct recipient of the message needs to be found somehow unless the user happens to know it by heart. Such a search function already exists to varying degrees in the various user systems, and to make these searches easier, EAS provides useful standardized search services based on relevant authoritative sources (like for example the national register of organizations within the health domain).

When EAS receives a search request from a user system it in turn calls the relevant authoritative sources responsible for the information needed for the particular type of search request, and based on this EAS constructs the response for the user system. In this way EAS decouples the user systems from the authoritative sources and the, sometimes cumbersome, logic to be implemented to support searches for recipients in various different situations only needs to be implemented and maintained in EAS.

Examples of search services EAS support include:
•	Search for a patient’s general practitioner.
•	Search for general practitioners in a delimited geographical area (relevant for patients with no fixed general practitioner).
•	Search for recipients capable of receiving specific types of messages – not just the overall message type (including version), but also more detailed searches concerning specific aspects of the message to be sent (relevant, e.g., in relation to referrals for X-ray examinations that require special equipment not offered by all X-ray departments.

[TBT] EHMI anvender en komponent til at håndtere Sundhedsadressering.

[TBT] En skitse over komponenterne i EHMI netværkets anvendelse af komponenten kan ses her:

![EHMI Addressing Service (EAS)](/ehmi/assets/images/3_EHMI_Sundhedsadresseringsservice_1315x551.png)
