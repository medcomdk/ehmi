# EHMI Endpoint Register (EER)

The EHMI Endpoint Register (EER) is an organizational register of Endpoints related to the public SOR.

As SOR will be developed to host only the regular physical locations of an organizational unit, EER will take over the role of SOR-EDI, 
which hosts the GLN number of a SOR unit and its supported messagetypes. 
GLN is the actual foreign key to SOR in SOR-EDI. In EER the foreign key to SOR will be the SORID. 
Thereby the SOR Unit will be able to have more Endpoints expressed by GLN. 
Until the transition of SOR to be able to handle this, EER will be limited to have only one GLN per SOR unit.

EER will in the first version serve the following purposes:

- EER will be the authoritative register for FHIR messaging endpoints, EerMessagingEndpoints
- EER will hold the relation between SOR units and EER endpoints as EerMessagingOrganizations
- EER will be the master register for SMP registrations (EHMI Core) for the above
- EER will be the authoritative register for FHIR document sharing endpoints for FHIR messages
- EER will serve EHMI Addressing Service (EAS) in EAS's effort to deliver the correct receiverdata for a messaging sender as EasMessagingOrganizations.
- EER will contain Devices that serves as EDS Clients in the message flow (EHMI Core)
- EER will hold the relation between EDS Clients (Devices) and EerMessagingOrganizations

<br/>

## An outline of the components of the EHMI Endpoint Register (EER) can be seen here:
    
<br/> 

<figure style="margin-left: 0px; margin-right: 0px; width: 100%;">
<a href="https://medcomdk.github.io/ehmi/assets/images/ehmi-eas-and-eer.png" target="_blank"> <img src="https://medcomdk.github.io/ehmi/assets/images/ehmi-eas-and-eer.png" alt="EHMI Endpoint Register (EER)" style="width:80%; height:auto; margin-left:1%; margin-right:19%; margin-top:5px; margin-bottom:5px;" id="Fig1"></a>
<figcaption text-align="left"><b>Figure 1: EHMI Endpoint Register (EER) </b></figcaption>
</figure>

![EHMI Delivery Status (EDS)](/ehmi/assets/images/ehmi-eas-and-eer.png )

<br/> 
  
**The whole specification for EHMI Endpoint Register (EER) can be found** 
<a href="https://build.fhir.org/ig/medcomdk/dk-ehmi-eer/" target="_blank">here</a>
    
