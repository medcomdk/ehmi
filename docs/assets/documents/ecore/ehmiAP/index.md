# ehmiAP

An eDelivery AP for EHMI is in the following called ehmiAP


![EHMI Meddelelsesforsendelse og dokumentdeling](/ehmi/assets/images/1_EHMI_Meddelelsesforsendelse_og_dokumentdeling_1315x563.png)

## Requirements for ehmiAPs

An ehmiAP **SHALL** be conformant with the EU general requirements for an eDelivery AP.

The general specifications are outlined here:
- <a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/Access+Point+specifications" target="_blank">Access Point specifications</a>
- <a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eDelivery+AS4+-+1.15" target="_blank">eDelivery AS4 - 1.15</a>

These requirements means basically that the ehmiAP **SHALL** be on the list of <a href="https://ec.europa.eu/digital-building-blocks/sites/display/DIGITAL/eDelivery+AS4+conformant+solutions" target="_blank">EU eDelivery AS4 conformant solutions</a>. And on this list **EHMI** require the participating solutions to have done conformance testing in the last 3 years.

Especially the ehmiAP **SHALL** conform to these basic functionalities
- Common Profile
- Four Corner Topology
- Dynamic Discovery
    - Dynamic Sender
    - Dynamic Receiver
- SBDH (Standard Business Document Header)


Furthermore, for being an EHMI AP supplier for the production pilot it is important that you conform to the following requirements:

- The AP supplier has already chosen an EU approved AP and has implemented it in operation for a organization in the healthcare area.
- The AP supplier has implemented support for SBDH compliance with PEPPOL. Therefore, there will be no MedCom funding for implementing this.
- The AP must operate on the health data network (danish: sundhedsdatanettet, SDN) with the necessary approvals required to operate here.
- The AP must communicate with the healthcare area's chosen SMP, regardless if this is placed on SDN or on the open internet.
- The AP supplier must be willing to follow the rules for communication in the healthcare area, which are stated in the Danish Health Data Authority's (danish: Sundhedsdatastyrelsen)  "Architectural Vision for message communication in the healthcare area" (danish: ”Målbillede for meddelelseskommunikation på sundhedsområdet”). Some rules are explicitly expressed in the Architectural Vision, others are clarified subsequently in governance for the production pilot (danish: produktionspiloten).
- The AP supplier must conform to MedComs approval requirements for an AP, i.e. to demonstrate that the AP can communicate with MedComs test AP on SDN via MedComs SMP with delivery status logging. 
