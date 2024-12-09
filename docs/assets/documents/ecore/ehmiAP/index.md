# ehmiAP

An eDelivery AP for EHMI is in the following called ehmiAP.

([CHG]: Erstat med den engelske udgave af figuren)

![EHMI Meddelelsesforsendelse og dokumentdeling](/ehmi/assets/images/1_EHMI_Meddelelsesforsendelse_og_dokumentdeling_1315x563.png)

## Requirements for ehmiAPs

An ehmiAP **SHALL** be conformant with the EU general requirements for an eDelivery AP.

The general specifications are outlined here:
- <a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/Access+Point+specifications" target="_blank">Access Point specifications</a>
- <a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eDelivery+AS4+-+1.15" target="_blank">eDelivery AS4 - 1.15</a> ([CHG]: AS4 spec'en står til at blive opdateret til en version 2.0, som løfter sikkerheden. Er der planer for ibrugtagning af 2.0?)

These requirements basically mean that the ehmiAP **SHALL** be on the list of <a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eDelivery+AS4+conformant+solutions" target="_blank">EU eDelivery AS4 conformant solutions</a>. And on this list **EHMI** require the participating solutions to have been EU eDelivery AS4 conformance tested within the last 3 years.

Especially the ehmiAP **SHALL** conform to these basic functionalities ([CHG]: Jeg antager at disse også fremgår af ovenstående AP og AS4 spec's, men de er måske ikke påkrævede siden de nævnes her?)
- Common Profile
- Four Corner Topology
- Dynamic Discovery
    - Dynamic Sender
    - Dynamic Receiver
- SBDH (Standard Business Document Header)

([CHG]: Tilføj overskrift "Requirements for ehmiAP suppliers"?)

Furthermore, for being an EHMI AP supplier for the production pilot it is important that you conform to the following requirements:

- The AP supplier has already chosen an EU approved AP and must be able to implement it in operation for an organization in the healthcare sector.
- The AP supplier has implemented support for SBDH compliance with PEPPOL ([CHG]: Bør PEPPOL compliance ift. til SBDH så ikke angives som krav til ehmiAP længere i ovenstående? Tilføj et link til https://docs.peppol.eu/edelivery/envelope/Peppol-EDN-Business-Message-Envelope-2.0.1-2023-08-17.pdf?) . Therefore, there will be no MedCom funding for implementing this.
- The AP must operate on the health data network (danish: sundhedsdatanettet, SDN) with the necessary approvals required to operate here.
- The AP must communicate with the healthcare sector's chosen SMP, regardless if this is placed on SDN or on the open internet.
- The AP supplier must follow the rules for communication in the healthcare sector, which are stated in the Danish Health Data Authority's (danish: Sundhedsdatastyrelsen)  "Architectural Vision for message communication in the healthcare area" (danish: ”Målbillede for meddelelseskommunikation på sundhedsområdet”) ([CHG]: Tilføj link?) . Some rules are explicitly expressed in the Architectural Vision, others are clarified subsequently in governance for the production pilot (danish: produktionspiloten) ([CHG]: Tilføj en reference).
- The AP supplier must conform to MedComs approval requirements for an AP ([CHG]: Tilføj et link til certificeringskriterierne), i.e. to demonstrate that the AP can communicate with MedComs test AP on SDN via MedComs SMP with delivery status logging. 
