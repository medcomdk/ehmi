# Acronyms

| Acronym | Abbreviation for | Description | Domain |
| --- | --- | --- | --- |
| AP       | Access Point | The eDelivery component responsible for exchanging data between Corner 2 and 3 in the 4 Corner model | eDelivery |
| EDS      | EHMI Delivery Status | [TBD] | EHMI |
| EER      | EHMI Endpoint Register | [TBD] | EHMI |
| ehmiAck  | EHMI Envelope Receipt | [TBD] | EHMI |
| ehmiSBDH | The EHMI Profile of Standard Business Document Header | [TBD] | EHMI |
| EUA      | End User Application | [TBD] | EHMI |
| GS1      | [TBD] | The organisation responsible for GLN numbers and the original SBDH specification | GS1 |
| IHE      | Integrating the Healthcare Enterprise | International organisation som arbejder for at skabe interoperability i sundhedssystemer | EHMI |
| MSH      | Message Service Handler | The functionality who is responsible for wrapping messages into the ehmiSBDH. Can be a module in an EUA or AP, or it can be a stand-alone application | EHMI |
| OASIS    | [TBD] | The Standardisation Organisation responsible for the specifications of AS4, SML, SMP, ebbs | EHMI |
| PEPPOL   | [TBD] | [TBD] | PEPPOL |
| SBD      | Standard Business Document | The wrapper around the SBDH and the Binary content of ehmiSBDH | PEPPOL |
| SBDH     | Standard Business Document Header | [TBD] | PEPPOL |
| SMP      | Service Metadata Provider | [TBD] | eDelivery |
| SML      | Service Metadata Locator | [TBD] | eDelivery |

| 4-corner-model | eDelivery 4-corner-model | 1. Fagsystem Corner 1 sender en meddelelse gennem en servicehandling til Access Point Corner 2. <br/> 2. Access Point Corner 2 slår op i SML/DNS for at finde adressen på den SMP, som det modtagende fagsystems Corner 4 modtager-kapabiliteter er registreret i. <br/> 3. Access Point Corner 2 slår op i SMP for at teste, om det modtagende Fagsystem Corner 4 har modtager-kapabiliteter svarende til det, der skal sendes, samt at finde adressen på det Access Point Corner 3, som meddelelsen skal sendes til. <br/> 4. Access Point Corner 2 sender meddelelsen til Access Point Corner 3. <br/> 5. Access Point Corner 3 sender meddelelsen gennem en servicehandling til det modtagende Fagsystem Corner 4. | eDelivery |
 


