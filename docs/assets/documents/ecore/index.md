# EHMI Core

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
       
<br/> 


**Table of contents** ([CHG]: Fjernes når siden ikke indeholder mere end den gør?)
- [EHMI Core Description](#ehmi-core-description)
    - [EHMI Core Message Delivery and Document Sharing](#ehmi-core-message-delivery-and-document-sharing)
    - [EHMI Core Specifications](#ehmi-core-specifications)

<br/> 

***

<br/> 

## EHMI Core Description

([CHG]: Det er ikke særlig klart hvad der menes præcis med 'EHMI Core'. Er det processerne for meddelelsesforsendelse eller infrastrukturen som understøtter det? Sæt lidt flere ord på. Måske kunne man starte med grafikken og forklare koncepterne ud fra den.)

EHMI Core is defined as 
- the primary message delivering from a sender system to a receiver system concerning 
    - End User Applications (EUA)
    - Message Service Handlers (MSH)
    - eDelivery Access Points (AP)
    - eDelivery SML and SMP
- the secondary message delivering from a sender system to the national XDS Document Sharing platform with an index on NSP also concerning 
    - Sender's End User Application (EUA)
    - Message Service Handlers (MSH)
    - eDelivery Access Points (AP)
    - eDelivery SML and SMP

<br/> 


EHMI Core specifies ([CHG]: Der er noget mismatch mellem denne liste som har to 'specifikationer' (ehmiAP og ehmiSBDH) og nedenstående 'EHMI Core specifications' afsnit. Kan det konsolideres i et afsnit?)

- ehmiAP, how the AP **SHALL** conform to EU eDelivery Requirements, [see here](http://127.0.0.1:4000/assets/documents/ecore/ehmiAP/)
- ehmiSBDH, the envelope that is used between the MSHs
- how ehmiSBDH in addition to its primary purpose of carrying metadata for eDelivery Messaging can carry the metadata used for: ([CHG] Bør formål ikke beskrives som en del af ehmiSBDH? Dvs. skulle man ikke flytte punktet og underpunkterne til ehmiSBDH spec'en?)
    - Reliable Messaging embedded in ehmiSBDH BusinessScopes
    - XDS Document Sharing through the FHIR DocumentReference profile for each messagetype and how it is embedded in an ehmiSBDH BusinessScope
    - EHMI Delivery Status embedded in ehmiSBDH BusinessScopes

<br/> 

### EHMI Core Message Delivery and Document Sharing

<br/> 

The graphic shows and explains in plain text how the primary flow of a MedCom Message is from the Sender to the Receiver.

In addition to the primary flow, ehmiEnvelopeReceipt will be sent from the Receiver's MSH to Sender's MSH and FHIR Acknowledgements will be sent from the Receiver's EUA to the Original Sender's EUA. ([CHG] Har vi ikke en figur som illustrerer at der er tre slags kvitteringer i spil?)

<br/> 

![EHMI Core Message Delivery and Document Sharing](http://127.0.0.1:4000/assets/images/EHMI%20Pixi%20-%20Message%20delivery.png)

<br/> 

### EHMI Core specifications
([CHG]: Til hver af de nævnte spec's bør der tilføjes et par om hvor i flowet spec'en er i spil)

<br/> 

EHMI Core specifies two profiles, one for ehmiSBDH and one for ehmiSMP: ([CHG]: Tilføj ehmiAP? Se ovenstående kommentar.)

- [EHMI Profile of SBDH (ehmiSBDH)](http://127.0.0.1:4000/assets/documents/ecore/ehmiSBDH/)
- [EHMI Profile of Service Metadata Publisher (ehmiSMP)](http://127.0.0.1:4000/assets/documents/ecore/ehmiSMP/)

<br/> 

- EHMI Reliable Messaging follows <a href="https://medcomdk.github.io/MedCom-FHIR-Communication/assets/documents/020_Governance-for-Reliable-Messaging-in-general.html" target="_blank">Governance for Reliable Messaging in general</a> as specified in MedCom's Governance for FHIR Messaging. A similar description for Reliable Messaging for <a href="https://medcomdk.github.io/MedCom-FHIR-Communication/assets/documents/032_Reliable_Messaging-VANSEnvelope.html" target="_blank">Reliable Messaging using VANSEnvelope</a> will be produced for ehmiSDBH.

<br/> 

- [EHMI Core Security is specified here](../security/security-specification-of-ehmi-core.md)

<br/> 

## References

<br/>

<table>
<tr><td><b>Reference</b></td><td><b>Name</b></td><td><b>Filename</b></td></tr>
<tr><td><b>
Policy_identifiers
</b></td><td>
PEPPOL Transport Infrastructure  ICT - Models  Policy for use of Identifiers, Version: 4.2.0
</td><td>
<a href="https://docs.peppol.eu/edelivery/policies/PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf" target="_blank">PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf</a>
</td></tr>
<tr><td><b>
DKEDEL_PIV_CodeList
</b></td><td>
DK_EDEL Code Lists - Participant identifier schemes v7.2
</td><td>
<a href="../../documents/ecore/eDelivery/DK_EDEL Code Lists - Participant identifier schemes v7.2.xlsx" target="_blank">DK_EDEL Code Lists - Participant identifier schemes v7.2.xlsx</a>
</td></tr>
<tr><td><b>
DKEDEL_TP_CodeList
</b></td><td>
Danish eDelivery Code Lists - Transport profiles v7.2
</td><td>
<a href="../../documents/ecore/eDelivery/DK_EDEL Code Lists - Transport profiles v7.2.xlsx" target="_blank">Danish eDelivery Code Lists - Transport profiles v7.2</a>
</td></tr>
<tr><td><b>
PEPPOL_SBDH12
</b></td><td>
PEPPOL Business Message Envelope (SBDH) 1.2
</td><td>
<a href="https://github.com/OpenPEPPOL/documentation/blob/master/TransportInfrastructure/PEPPOL-EDN-Business-Message-Envelope-1.2-2019-02-01.pdf" target="_blank">PEPPOL-EDN-Business-Message-Envelope-1.2-2019-02-01.pdf</a>
</td></tr>
<tr><td><b>
XDS Metadata
</b></td><td>
XDS Metadata-v1.0.0
</td><td>
<a href="https://svn.medcom.dk/svn/releases/Standarder/IHE/DK_profil_metadata/XDS%20Metadata%20for%20Document%20Sharing.%20Danish%20profile%20v.1.0.0.pdf" target="_blank">XDS Metadata for Document Sharing Danish profile v.1.0.0.pdf</a>
</td></tr>
<tr><td><b>
XDS_Metadata- ValueSets
</b></td><td>
DK-IHE_Metadata-Common_Code_systems-Value_sets
</td><td>
<a href="https://svn.medcom.dk/svn/releases/Standarder/IHE/OID/DK-IHE_Metadata-Common_Code_systems-Value_sets.xlsx" target="_blank">DK-IHE_Metadata-Common_Code_systems-Value_sets.xlsx</a>
</td></tr>

</table>

<br/>
