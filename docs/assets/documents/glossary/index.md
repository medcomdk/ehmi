# Acronyms

***

    **Disclaimer** 
    
    **The menu items above marked with a star are yet not specified**
       
<br/> 

| Acronym | Acronym for | Description | Domain |
| --- | --- | --- | --- |
| AP       | Access Point | The eDelivery component responsible for exchanging data between Corner 2 and 3 in the 4 Corner model | eDelivery |
| EDS      | EHMI Delivery Status | [TBD] | EHMI |
| EER      | EHMI Endpoint Register | [TBD] | EHMI |
| ehmiAck  | EHMI Envelope Receipt | [TBD] | EHMI |
| ehmiSBDH | The EHMI Profile of Standard Business Document Header | [TBD] | EHMI |
| EUA      | End User Application | [TBD] | EHMI |
| GS1      | Originally "EAN International" now just GS1 | The organisation responsible for GLN numbers and the original SBDH specification. [Website](https://www.gs1.org/) | GS1 |
| IHE      | Integrating the Healthcare Enterprise | International organization which creates interoperability in health care systems | EHMI |
| MSH      | Message Service Handler | The functionality who is responsible for wrapping messages into the ehmiSBDH. Can be a module in an EUA or AP, or it can be a stand-alone application | EHMI |
| OASIS    | [TBD] | The Standardisation Organisation responsible for the specifications of AS4, SML, SMP, ebXML [Website](https://www.oasis-open.org/) | EHMI |
| PEPPOL   | [TBD] | [TBD] | PEPPOL |
| SBD      | Standard Business Document | The wrapper around the SBDH and the Binary content of ehmiSBDH | PEPPOL |
| SBDH     | Standard Business Document Header | [TBD] | PEPPOL |
| SMP      | Service Metadata Provider | [TBD] | eDelivery |
| SML      | Service Metadata Locator | [TBD] | eDelivery |
| 4-corner-model | eDelivery 4-corner-model | 1. Sender system Corner 1 sends a message through a Service Handler to Access Point Corner 2. <br/> 2. Access Point Corner 2 looks up in SML/DNS to find the address of the SMP in which the receiving system's Corner 4 receiver-capabilities are registered. <br/> 3. Access Point Corner 2 looks up in SMP to test whether the receiver system Corner 4 has receiver-capabilities corresponding to what is to be sent, as well as to find the address of the Access Point Corner 3 to which the message is to be sent. <br/> 4. Access Point Corner 2 sends the message to Access Point Corner 3. <br/> 5. Access Point Corner 3 sends the message through the Service Handler to the receiver system Corner 4. | eDelivery |
 


