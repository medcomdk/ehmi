# Acronyms and glossary

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
       
<br/> 


| Acronym | Acronym for | Description |  Domain | Relevate links |
| --- | --- | --- | --- | --- |
| AP       | Access Point | The eDelivery component responsible for exchanging data between Corner 2 and 3 in the 4 Corner model | eDelivery | [TBD] |
| *DDS*    | *Document Sharing Service* | *A national infrastructure for document sharing with an underlying repository structure based on IHE-XDS already exists on the national service platform for the healthcare sector. Document sharing of sent messages is realized through the collection of sent messages from the senders AP to the DDS, where DDS expose the same messsages in the national infrastructure for both healthcare professionals and citizens.* | *NSP* | [TBD] |
| *EAS*    | *EHMI Addressing Service* | *A health addressing service is developed to solve the wellknown challenges for a sender to find the right recipient. The service will draw necessary information from the proper authoritative sources and present this information to the sender of the message, thereby assisting the sender in finding the proper recipient.* | *EHMI* | [EHMI EAS (IG)]*(https://build.fhir.org/ig/medcomdk/dk-ehmi-eas/)* |
| EDS      | *EHMI Delivery Status (Track’n’Trace)* | *The delivery status component collects the delivery status of a sent message at selected points along the delivery path and subsequently exposing the delivery status via a service to both healthcare professionals and citizens, allowing them to follow the status of a message in close to real-time to the benefit of the citizens/patients’ safety.* | EHMI | [TBD] |
| EER      | EHMI Endpoint Register | [TBD] | EHMI | *[EER (IG)](https://build.fhir.org/ig/medcomdk/dk-ehmi-eer/)* |
| ehmiAck  | EHMI Envelope Receipt | [TBD] | EHMI | [TBD] |
| ehmiSBDH | The EHMI Profile of Standard Business Document Header | *SBDH 'Standard Business Document Header’ is an envelope that can be used in relation to eDelivery and can contain different general message format types, such as EDIFACT, OIO-XML and FHIR. The ehmiSBDH is a customized version of the PEPPOL SBDH. ehmiSBDH is the envelope that is used between the MSHs and ensures the message communication in the EHMI network, so that the EHMI network nodes do not have to deal with anything else than a generic envelope.* | EHMI | *[ehmiSBDH (IG)](https://build.fhir.org/ig/medcomdk/dk-ehmi-sbdh/index.html)* |
| *ehmiSMP*      | *Service Metadata Provider* | [TBD] | *EHMI* | [TBD] |
| EUA      | End User Application | *A message is created in the EUA by the end user/health professional. A message will be sent from the Sender’s EUA to the Receiver’s EUA, and FHIR Acknowledgements will be sent from the Receiver’s EUA to the Original Sender’s EUA. The EUA can be built and hosted together with MSH and AP in various ways.* | EHMI | [TBD] |
| GS1      | Originally "EAN International" now just GS1 | The organisation responsible for GLN numbers and the original SBDH specification. | GS1 | [Website](https://www.gs1.org/) |
| IHE      | Integrating the Healthcare Enterprise | International organization which creates interoperability in health care systems | EHMI | [TBD] |
| MSH      | Message Service Handler | The functionality who is responsible for wrapping messages into the ehmiSBDH. Can be a module in an EUA or AP, or it can be a stand-alone application | EHMI | [TBD] |
| OASIS    | [TBD] | The Standardisation Organisation responsible for the specifications of AS4, SML, SMP, ebXML | EHMI | [Website](https://www.oasis-open.org/) |
| PEPPOL   | [TBD] | [TBD] | PEPPOL | [TBD] |
| SBD      | Standard Business Document | The wrapper around the SBDH and the Binary content of ehmiSBDH | PEPPOL | [TBD] |
| SBDH     | Standard Business Document Header | *PEPPOL SBDH is an envelope that can be used in relation to eDelivery and can contain different general message format types, such as EDIFACT, OIO-XML and FHIR.* | PEPPOL | [TBD] |
| SMP      | Service Metadata Provider | [TBD] | eDelivery | [TBD] |
| SML      | Service Metadata Locator | [TBD] | eDelivery | [TBD] |
| 4-corner-model | eDelivery 4-corner-model | 1. Sender system Corner 1 sends a message through a Service Handler to Access Point Corner 2. <br/> 2. Access Point Corner 2 looks up in SML/DNS to find the address of the SMP in which the receiving system's Corner 4 receiver-capabilities are registered. <br/> 3. Access Point Corner 2 looks up in SMP to test whether the receiver system Corner 4 has receiver-capabilities corresponding to what is to be sent, as well as to find the address of the Access Point Corner 3 to which the message is to be sent. <br/> 4. Access Point Corner 2 sends the message to Access Point Corner 3. <br/> 5. Access Point Corner 3 sends the message through the Service Handler to the receiver system Corner 4. | eDelivery | [TBD] |

<br/>


