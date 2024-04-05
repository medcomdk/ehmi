# EHMI Core

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
    
    ***Shifts of languages between English and Danish will occur in this version - that will change completely to English in the next upcoming version***
    
<br/> 


**Table of contents**
- [EHMI Core Description](#ehmi-core-description)
    - [EHMI Core Message Delivery and Document Sharing](#ehmi-core-message-delivery-and-document-sharing)
    - [EHMI Core Specifications](#ehmi-core-specifications)

<br/> 

***

<br/> 

## EHMI Core Description

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

EHMI Core specifies 
- ehmiSBDH, the envelope that is used between the MSHs
- how ehmiSBDH in addition to its primary purpose of carrying metadata for eDelivery Messaging can carry the metadata used for:
    - Reliable Messaging embedded in ehmiSBDH BusinessScopes
    - XDS Document Sharing through the FHIR DocumentReference profile for each messagetype and how it is embedded in an ehmiSBDH BusinessScope
    - EHMI Delivery Status embedded in ehmiSBDH BusinessScopes

<br/> 

### EHMI Core Message Delivery and Document Sharing

<br/> 

The graphic shows and explains in plain text how the primary flow of a MedCom Message is from the Sender to the Receiver.

In addition to the primary flow, ehmiEnvelopeReceipt will be send from the Receiver's MSH to Sender's MSH and FHIR Acknowledgements will be send from the Receiver's EUA to the Original Sender's EUA.

<br/> 

![EHMI Core Message Delivery and Document Sharing](/ehmi/assets/images/1_EHMI_Meddelelsesforsendelse_og_dokumentdeling_1315x563.png)

<br/> 

### EHMI Core specifications

<br/> 

EHMI Core specifies two profile, 1 for ehmiSBDH and 1 for ehmiSMP

- [EHMI Profile of SBDH (ehmiSBDH)](/ehmiSBDH/index.md)
- [EHMI Profile of Service Metadata Publisher (ehmiSMP)](/ehmiSMP/index.md)

<br/> 

- EHMI Reliable Messaging follows <a href="https://medcomdk.github.io/MedCom-FHIR-Communication/assets/documents/020_Governance-for-Reliable-Messaging-in-general.html" target="_blank">Governance for Reliable Messaging in general</a> as specified in MedCom's Governance for FHIR Messaging. A similar description for Reliable Messaging for <a href="https://medcomdk.github.io/MedCom-FHIR-Communication/assets/documents/032_Reliable_Messaging-VANSEnvelope.html" target="_blank">Reliable Messaging using VANSEnvelope</a> will be produced for ehmiSDBH.

<br/> 

- [EHMI Core Security is specified here](../security/security-specification-of-ehmi-core.md)

<br/> 

## Referencer

<br/>

<table>
<tr><bold><td>Reference</td><td>Name</td><td>Filename</td></bold></tr>
<tr>
<td><bold>Policy_identifiers<bold></td>
<td>PEPPOL Transport Infrastructure  ICT - Models  Policy for use of Identifiers, Version: 4.2.0</td><td><a href="https://docs.peppol.eu/edelivery/policies/PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf" target="_blank">PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf</a></td>
</tr>
<tr><td>
<bold>DKEDEL_PIV_CodeList<bold>
</td><td>
DK_EDEL Code Lists - Participant identifier schemes v7.2
 </td><td>
 <a href="../../documents/ecore/eDelivery/DK_EDEL%20Code%20Lists%20-%20Participant%20identifier%20schemes%20v7.2.xlsx" target="_blank">DK_EDEL Code Lists - Participant identifier schemes v7.2.xlsx</a></td>
</tr>
</table>

<br/>

| **Reference**             | **Navn**                                                                                   | **Filnavn**                                                   | **Placering**                                                                                                                                                                                                                                                   |
|---------------------------|--------------------------------------------------------------------------------------------|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Policy_identifiers]      | PEPPOL Transport Infrastructure  ICT - Models  Policy for use of Identifiers, Version: 42..0 | PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf   | <a href="https://docs.peppol.eu/edelivery/policies/PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf target="_blank">PEPPOL-EDN-Policy-for-use-of-identifiers-4.2.0-2023-06-19.pdf</a> |

| [DKEDEL_PIV_CodeList]     | DK_EDEL Code Lists - Participant identifier schemes v7.2                                   | DK_EDEL Code Lists - Participant identifier schemes v7.2.xlsx | [DK_EDEL Code Lists - Participant identifier schemes v7.2.xlsx](../../documents/ecore/eDelivery/DK_EDEL%20Code%20Lists%20-%20Participant%20identifier%20schemes%20v7.2.xlsx) |

| [DKEDEL_TP_CodeList]      | Dansk eDelivery Code Lists - Transport profiles v7.2                                       | Dansk eDelivery Code Lists - Transport profiles v7.2.xlsx     | <https://medcomtest.sharepoint.com/:x:/s/MedComModerniseringsPilot2020/EdlEjIlLDadJuy7RjD926bkB0X5X-0m1JuQG_VF8Je2f-g?e=4b7jF8>                                                                                                                                 |
| [DKEDEL_DT_CodeList]      | Dansk eDelivery Code Lists - Document types v7.2. (MedCom meddelelser)                     | Dansk eDelivery Code Lists - Document types v7.2.xlsx         | <https://medcomtest.sharepoint.com/:x:/r/sites/MedComModerniseringsPilot2020/Delte%20dokumenter/eDelivery/Dansk%20eDelivery/DK_EDEL%20Code%20Lists%20-%20Document%20types%20v7.2%20-%2020211122.xlsx?d=wf68cc9cce4594eae8b8c8d26c828280c&csf=1&web=1&e=H5LYNJ>  |
| [PEPPOL_SBDH12]           | PEPPOL Business Message Envelope (SBDH) 1.2                                                | PEPPOL-EDN-Business-Message-Envelope-1.2-2019-02-01.pdf       | <https://medcomtest.sharepoint.com/:b:/s/MedComModerniseringsPilot2020/EeWbN0HnqcZMhel_56f8tCcB7G-boIwnP5PeoMAsDU5lCQ?e=gXR3cY>                                                                                                                                 |
| [DDS Metadata]            | DDS Metadata-v096                                                                          | DDS Metadata-v096.docx                                        | <http://svn.medcom.dk/svn/drafts/Standarder/IHE/DK_profil_metadata/Metadata-v096.docx>                                                                                                                                                                          |
| [DDS_Metadata- ValueSets] | DK-IHE_Metadata-Common_Code_systems-Value_sets                                             | DK-IHE_Metadata-Common_Code_systems-Value_sets.xlsx           | <http://svn.medcom.dk/svn/drafts/Standarder/IHE/OID/DK-IHE_Metadata-Common_Code_systems-Value_sets.xlsx>                                                                                                                                                        |
| [ebxmlbp]                 | ebxmlbp-v2.0.4-Spec-os-en                                                                  | ebxmlbp-v2.0.4-Spec-os-en.pdf                                 | <https://docs.oasis-open.org/ebxml-bp/2.0.4/OS/spec/ebxmlbp-v2.0.4-Spec-os-en.pdf>                                                                                                                                                                              |
| [SBDHschema]              | Standard Business Document Header Schema for pilot                                         | MedComStandardBusinessDocumentHeader_20210217.xsd             | <https://medcomtest.sharepoint.com/:u:/s/MedComModerniseringsPilot2020/EdudZoIaoXtAgC_PhWGKvCwBscQxkP54bYLqWQPx86SxuQ?e=bITgGk>                                                                                                                                 |
| EER                       | EHMI Endpoint Register                                                                     |                                                               |                                                                                                                                                                                                                                                                 |
| EDS                       | EHMI Delivery Status                                                                       |                                                               |                                                                                                                                                                                                                                                                 |

