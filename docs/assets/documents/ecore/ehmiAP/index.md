# ehmiAP

An eDelivery AP for EHMI is in the following called ehmiAP

**Table of contents**


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

Furthermore, for being an ehmiAP supplier for the production pilot it is important that you conform to the following requirements (in danish):

Følgende forudsætninger for en EHMI AP-leverandør er gældende:
•	AP-leverandøren har allerede valgt et EU-godkendt AP og vil kunne implementere dette i drift for en organisation i sundhedsvæsenet. 
•	AP-leverandøren har implementeret understøttelse for SBDH compliance  med PEPPOL. Der vil derfor ikke være MedCom-støttemidler til implementering af dette.
•	AP’et skal operere på sundhedsdatanettet (SDN) med de godkendelser, det kræves at operere her.
•	AP’et skal kommunikere med sundhedsvæsenets valgte SMP, uanset om dette er placeret på SDN eller på det åbne internet.
•	AP-leverandøren skal være indstillet på at følge de regler for kommunikation i sundhedsvæsenet, som er angivet i Sundhedsdatastyrelsens  ”Målbillede for meddelelseskommunikation på sundhedsområdet”. Nogle regler er eksplicit udtrykt i målbilledet, andre præciseres efterfølgende i governance for afprøvningen (produktionspiloten).
•	AP-leverandøren skal leve op til MedComs godkendelseskrav for et AP, dvs. at demonstrere at AP’et kan kommunikere med MedComs test-AP på SDN via MedComs SMP med logning af forsendelsesstatus. 

