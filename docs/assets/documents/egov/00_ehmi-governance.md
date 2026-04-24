# Startpakke for eDelivery Sundhedsdomænet – pilotprojekt
eDelivery Sundhedsdomænet har til formål at etablere, udvikle og drive en infrastruktur til udveksling af kliniske meddelelser inden for sundhedssektoren samt til og fra andre domæner uden for sundhedsområdet.

Denne startpakke er etableret i forbindelse med eDelivery-pilotprojektet til deltagerne heri. Samtidig er startpakken udformet med henblik på, at den – efter nødvendige tilpasninger – kan videreføres, når eDelivery Sundhedsdomænet overgår til normal drift.

Hvis en aktør ønsker at tilslutte sig eDelivery Sundhedsdomænet, er første skridt at tage kontakt til MedCom. Nogle af de indledende spørgsmål, der kan drøftes, er:
1) Hvad skal eDelivery Sundhedsdomænet anvendes til?
2) Hvilken rolle forventer aktøren at have:
    1) Organisation, der skal sende og modtage kliniske meddelelser via eDelivery Sundhedsdomænet
    2) End User Application (EUA) – leverandør af fagsystem/klinisk system
    3) Message Service Handler (MSH)
    4) Access Point (AP)
3) Hvad er de praktiske trin frem mod tilslutning til eDelivery Sundhedsdomænet – både aftalemæssigt og teknisk?

I det følgende beskrives de aftalemæssige og tekniske trin for tilslutning til eDelivery Sundhedsdomænet.

Beskrivelsen indledes med en kort introduktion til eDelivery Sundhedsdomænet i relation til de forskellige roller, en aktør kan have.

# Roller i eDelivery Sundhedsdomænet
Tag stilling til hvilken rolle eller roller du ønsker at varetage i eDelivery domænet.
Figuren nedenfor illustrerer, hvordan en klinisk besked sendes fra en afsenderorganisation (f.eks. en kommune) til en modtagerorganisation (f.eks. en praktiserende læge) via eDelivery Sundhedsdomænet. Beskedens fysiske vej går gennem afsender-økosystemet, over sundhedsdatanettet og op gennem modtager-økosystemet.

<img src="EHMIokosystemet.png" alt="Økosystem" width="500">

(Klik på pilen for beskrivelse af nedenstående begreber.)
<details>
  <summary>End User Application (EUA)</summary>

Det kliniske fagsystem (eller andre fagsystemer), som afsender- og modtagerorganisationen anvender til at registrere og behandle en borgers (patientens) sundhedsoplysninger. 
Når der er behov for at sende en klinisk meddelelse til en anden organisation, sikrer det kliniske system, at meddelelsen opsættes i det relevante kliniske format (f.eks. en HomeCareObservation) og fremfinder den ønskede modtager. Meddelelsen og modtageren overdrages herefter til MSH. Det kliniske system kan også modtage kliniske meddelelser fra andre sundhedsorganisationer via MSH.
Det kliniske system sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets “track-and-trace”-system.
</details>

<details>
  <summary>Message Service Handler (MSH)</summary>

MSH er ansvarlig for klargøring og afsendelse af kliniske meddelelser fra EUA til en udpeget modtager. Klargøringen indebærer at indpakke den kliniske meddelelse i den digitale konvolut (ehmiSBDH), der bruges til udveksling af kliniske meddelelser indenfor eDelivery Sundhedsdomænet. MSH håndterer succes- eller fejl-kvitteringer fra modtageren (ehmiSBDH Acknowledgement). Ved fejl gensendes den kliniske meddelelse. Efter succesfuld afsendelse sendes en kopi af meddelelsen til EMR, en tjeneste til arkivering af kliniske meddelelser sendt via eDelivery Sundhedsdomænet.
MSH modtager også kliniske meddelelser fra andre sundhedsorganisationer, udpakker dem fra den digitale konvolut (ehmiSBDH), returnerer en kvittering (ehmiSBDH Acknowledgement) til afsenderen og sender den udpakkede kliniske meddelelse op til EUA.
MSH sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets “track-and-trace”-system.
MSH overlader den fysiske afsendelse og modtagelse af beskeder og kvitteringer til Accesspoint.
</details>

<details>
  <summary>Accesspoint (AP)</summary>

AP håndterer den fysiske digitale udveksling af kliniske meddelelser sendt via eDelivery Sundhedsdomænet. Den digitale adresse på modtageren hentes via Erhversstyrelsens SMP-service. Meddelelser og kvitteringer indpakkes og krypteres i henhold til EU’s eDelivery protokol og sendes derefter til modtagerens AP via Sundhedsdatanettet. 
Når AP modtager en besked fra en anden AP via Sundhedsdatanettet, står AP for dekryptering og udpakning, før beskeden leveres op til MSH. 
AP sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets “track-and-trace”-system.
</details>

<details>
  <summary>Sundhedsdatanettet (SDN)</summary>

Et lukket og sikret net til udveksling af sundhedsdata.
EUA, MSH og AP kan kombineres på forskellige måder, f.eks. en sammenbygning af EUA og MSH eller en sammenbygning af MSH og AP.
</details>



# EHMI Governance domain level

## Strategi og udvikling

### Strategi

### Roadmap

### EU

### Interessenthåndtering

## Brugersupport og -dialog

### Support

### Dialog via brugergrupper

### Dokumentation

### Tilslutningsaftaler

### Tilslutningsbistand

## Systemforvaltning

### Change management

### Incident management

### Service management

### Standarder

### Administration af certifikater

### Administration af centrale komponenter

### Leverandørstyring (drift/udvikling)
