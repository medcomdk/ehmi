<h1>Startpakke for eDelivery Sundhedsdomænet – pilotprojekt</h1>

eDelivery Sundhedsdomænet har til formål at etablere, udvikle og drive en infrastruktur til udveksling af kliniske meddelelser inden for sundhedssektoren samt til og fra andre domæner uden for sundhedsområdet.

Denne startpakke er etableret i forbindelse med eDelivery-pilotprojektet til deltagerne heri. Samtidig er startpakken udformet med henblik på, at den – efter nødvendige tilpasninger – kan videreføres, når eDelivery Sundhedsdomænet overgår til normal drift.

Hvis en aktør ønsker at tilslutte sig eDelivery Sundhedsdomænet, er første skridt at tage kontakt til MedCom. Nogle af de indledende spørgsmål, der kan drøftes, er:

<ol>
<li>Hvad skal eDelivery Sundhedsdomænet anvendes til?</li>
<li>Hvilken rolle forventer aktøren at have:
  <ol>
    <li>Organisation, der skal sende og modtage kliniske meddelelser via eDelivery Sundhedsdomænet</li>
    <li>End User Application (EUA) – leverandør af fagsystem/klinisk system</li>
    <li>Message Service Handler (MSH)</li>
    <li>Access Point (AP)</li>
  </ol>
</li>
<li>Hvad er de praktiske trin frem mod tilslutning til eDelivery Sundhedsdomænet – både aftalemæssigt og teknisk?</li>
</ol>

I det følgende beskrives de aftalemæssige og tekniske trin for tilslutning til eDelivery Sundhedsdomænet.

Beskrivelsen indledes med en kort introduktion til eDelivery Sundhedsdomænet med fokus på de forskellige roller, en aktør kan have. Herefter følger en kort introduktion til de infrastrukturkomponenter, der indgår i eDelivery Sundhedsdomænet.

<h2>Introduktion til eDelivery Sundhedsdomænet, med fokus på roller og infrastruktur komponenter.</h2>

(Klik på pilen ud for hver introduktion.)

<details>
  <summary><strong>Introduktion til eDelivery Sundhedsdomænet med fokus på de forskellige roller.</strong></summary>

Tag stilling til hvilken rolle eller roller du ønsker at varetage i eDelivery domænet.
Figuren nedenfor illustrerer, hvordan en klinisk besked sendes fra en afsenderorganisation (f.eks. en kommune) til en modtagerorganisation (f.eks. en praktiserende læge) via eDelivery Sundhedsdomænet. Beskedens fysiske vej går gennem afsender-økosystemet, over sundhedsdatanettet og op gennem modtager-økosystemet.

<img src="EHMIokosystemet.png" alt="Økosystem" width="500">

(Klik på pilen for beskrivelse af nedenstående begreber.)
<details>
  <summary>End User Application (EUA)</summary>

Det kliniske fagsystem (eller andre fagsystemer), som afsender- og modtagerorganisationen anvender til at registrere og behandle en borgers (patientens) sundhedsoplysninger.
Når der er behov for at sende en klinisk meddelelse til en anden organisation, sikrer det kliniske system, at meddelelsen opsættes i det relevante kliniske format (f.eks. en HomeCareObservation) og fremfinder den ønskede modtager. Meddelelsen og modtageren overdrages herefter til MSH. Det kliniske system kan også modtage kliniske meddelelser fra andre sundhedsorganisationer via MSH.
Det kliniske system sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets "track-and-trace"-system.
<br>
</details>

<details>
  <summary>Message Service Handler (MSH)</summary>

MSH er ansvarlig for klargøring og afsendelse af kliniske meddelelser fra EUA til en udpeget modtager. Klargøringen indebærer at indpakke den kliniske meddelelse i den digitale konvolut (ehmiSBDH), der bruges til udveksling af kliniske meddelelser indenfor eDelivery Sundhedsdomænet. MSH håndterer succes- eller fejl-kvitteringer fra modtageren (ehmiSBDH Acknowledgement). Ved fejl gensendes den kliniske meddelelse. Efter succesfuld afsendelse sendes en kopi af meddelelsen til EMR, en tjeneste til arkivering af kliniske meddelelser sendt via eDelivery Sundhedsdomænet.
MSH modtager også kliniske meddelelser fra andre sundhedsorganisationer, udpakker dem fra den digitale konvolut (ehmiSBDH), returnerer en kvittering (ehmiSBDH Acknowledgement) til afsenderen og sender den udpakkede kliniske meddelelse op til EUA.
MSH sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets "track-and-trace"-system.
MSH overlader den fysiske afsendelse og modtagelse af beskeder og kvitteringer til Accesspoint.
<br>
</details>

<details>
  <summary>Accesspoint (AP)</summary>

AP håndterer den fysiske digitale udveksling af kliniske meddelelser sendt via eDelivery Sundhedsdomænet. Den digitale adresse på modtageren hentes via Erhversstyrelsens SMP-service. Meddelelser og kvitteringer indpakkes og krypteres i henhold til EU's eDelivery protokol og sendes derefter til modtagerens AP via Sundhedsdatanettet.
Når AP modtager en besked fra en anden AP via Sundhedsdatanettet, står AP for dekryptering og udpakning, før beskeden leveres op til MSH.
AP sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets "track-and-trace"-system.
<br>
</details>

<details>
  <summary>Sundhedsdatanettet (SDN)</summary>

Et lukket og sikret net til udveksling af sundhedsdata.
EUA, MSH og AP kan kombineres på forskellige måder, f.eks. en sammenbygning af EUA og MSH eller en sammenbygning af MSH og AP.
</details>

Anvendte protokoller og standarder i eDelivery Sundhedsdomænet findes her: https://ehmi.dk

<br>
</details>

<details>
  <summary><strong>Introduktion til de Infrastruktur-komponenter som indgår i eDelivery Sundhedsdomænet.</strong></summary>

eDelivery-sundhedsdomænet anviser en række tekniske infrastrukturkomponenter, som den tilsluttede part skal integrere til og anvende, afhængigt af den rolle, parten varetager. Tabellen nedenfor oplister infrastrukturkomponenterne, deres systemforvalter samt de roller i eDelivery-sundhedsdomænet, der skal benytte komponenterne.

<table>
<thead>
<tr>
<th>Infrastruktur-komponent</th>
<th>Beskrivelse</th>
<th>Systemforvalter</th>
<th>Anvender rolle</th>
</tr>
</thead>
<tbody>
<tr>
<td>EER</td>
<td>EHMI Endpoint Register<br><br>Opslag efter endpoint ID (adresse i form af GLN-nummer) for modtager af meddelelse.</td>
<td>Digital Sundhed Danmark (i 2026: Med-Com)</td>
<td>EUA - anvendelse ikke påkrævet.</td>
</tr>
<tr>
<td>EAS</td>
<td>EHMI Addressing Service<br><br>Opslag efter korrekt modtager af en meddelelse</td>
<td>Digital Sundhed Danmark (i 2026: SDS) via NSP</td>
<td>EUA</td>
</tr>
<tr>
<td>EDS</td>
<td>EHMI Delivery Status<br><br>eDelivery Sundhedsdomænets "track-and-trace"-system</td>
<td>Digital Sundhed Danmark (i 2026: Med-Com)</td>
<td>1) EUA<br>2) MSH<br>3) AP</td>
</tr>
<tr>
<td>Keycloak</td>
<td>Sikkerhedskomponent og udsteder de OpenID-adgangsbilletter, som anvendes ved adgang til EDS og EER.</td>
<td>Digital Sundhed Danmark (i 2026: SDS) via NSP</td>
<td>1) EUA<br>2) MSH<br>3) AP</td>
</tr>
<tr>
<td>EMR</td>
<td>Service til deling af kliniske meddelelser sendt via EHMI. Delingen sker via NSP’s dokumentde-lingsinfrastruktur</td>
<td>Digital Sundhed Danmark (i 2026: SDS) via NSP</td>
<td>MSH</td>
</tr>
<tr>
<td>SMP/SML</td>
<td>Service Metadata Publisher/Service Metadata Locator
SML fungerer som en central adresse-bog. SMP indehol-der en organisations metadata. SML bru-ges til at pege på den rigtige SMP, mens SMP indeholder de konkrete metadata for organisationens understøttede doku-menttyper samt or-ganisationens endpo-int-adresse.
</td>
<td>Digital Sundhed Danmark (i 2026: Med-Com)</td>
<td>AP</td>
</tr>
<tr>
<td>SDN</td>
<td>Sundhedsdatanettet<br><br>Et sikkert og lukket netværk, der forbinder IT-systemer i den danske sundhedssektor. Alle ”klient til ser-vice” forbindelser via SDN skal regi-streres i SDN-aftalesystemet </td>
<td>Digital Sundhed Danmark (i 2026: Med-Com)</td>
<td>1) EUA<br>2) MSH<br>3) AP</td>
</tr>
</tbody>
</table>

Snitflader til flere at EHMI-infrastrukturkomponenterne findes her: https://ehmi.dk

</details>

<h2>Trin for tilslutning til eDelivery Sundhedsdomænet</h2>

<details>
  <summary>Trin 1 - Indgå tilslutningsaftale for eDelivery sundhedsdomænet</summary>

Aftalen giver den tilsluttede part adgang til eDelivery-sundhedsdomænet med det formål at sende og modtage meddelelser i henhold til den eller de rolle(r), som parten varetager i EHMI-økosystemet (Enhanced Healthcare Messaging Infrastructure).

[Tilslutningsaftale](tilslutningsaftale_edelivery.docx)

Tilslutningsaftalen skal udfyldes og underskrives. Herefter sendes tilslutningsaftalen elektronisk til Digital Sundhed Danmark (i 2026: MedCom) på ehmi@medcom.dk.

Efter modtagelse underskriver Digital Sundhed Danmark (i 2026: MedCom) en kopi og tilbagesender kopien til den tilsluttede part som bekræftelse på tilslutningen.

<br>
</details>

<details>
    <summary>Trin 2 - Sikre at nødvendige databehandleraftaler er på plads</summary>

Som det fremgår af figuren for EHMI-økosystemet, så findes der 5 roller i EHMI-økosystemet.

<ol>
<li>Afsender- eller modtagerorganisation.</li>
<li>EUA (End-User-Application - også omtalt fagsystem/klinisk system)</li>
<li>MSH (Message-Service-Handler)</li>
<li>AP (Access-Point)</li>
<li>SDN (Sundheds-Data-Nettet)</li>
</ol>

En afsender- eller modtagerorganisation er i sidste ende den dataansvarlige og skal sikre, at der er etableret de nødvendige databehandleraftaler gennem hele kæden af øvrige roller i EHMI-økosystemet. Dette kan håndteres som en traditionel kæde-databehandler-model, hvor afsender- eller modtagerorganisationen indgår en databehandleraftale med EUA samt sikrer, at EUA har indgået en underdatabehandleraftale med MSH, og at MSH tilsvarende har indgået en underdatabehandleraftale med AP, osv. Alternativt kan afsender- eller modtagerorganisationen indgå databehandleraftaler direkte med flere led i kæden.
Det er op til den enkelte part selv at vælge databehandlermodel i samarbejde med sine underleverandører.
Ved tilslutning til eDelivery Sundhedsdomænet vil den tilsluttede part blive spurgt, om der foreligger gyldige databehandleraftaler med de relevante parter i overensstemmelse med gældende databeskyttelseslovgivning – eller alternativt, hvad den tilsluttede part har af planer for at sikre dette.

eDelivery-sundhedsdomænet har udarbejdet et eksempel på en databehandleraftale mellem en kommune og et access point, som kan anvendes til inspiration. Vær opmærksom på:

<ol>
<li>at en databehandleraftale altid er kontekstafhængig, og at eksemplet derfor ikke kan anvendes direkte.</li>
<li>at en databehandleraftale kan formuleres på mange forskellige måder, og at databehandlerforholdet muligvis allerede er dækket af eksisterende databehandleraftaler med underleverandører.</li>
<li>at eksemplet viser en databehandleraftale fra en kommune direkte til et access point. Dette kunne alternativt være håndteret via underdatabehandleraftaler fra kommunens leverandør af fagsystem til MSH og AP.</li>
</ol>

Eksemplet tager udgangspunkt i en standard skabelon for databehandleraftaler, hvor en stor del af teksten stammer fra skabelonen. De dele af teksten, der specifikt vedrører eDelivery-sundhedsdomænet, er markeret med gult.

[Eksempel på databehandleraftale](Databehandleraftale_eksempel.docx)
<br>
</details>

<details>
  <summary>Trin 3 - Indgå tilslutningsaftaler til benyttede EHMI-infrastrukturkomponenter</summary>

Ovenfor (jf. Introduktion til de Infrastruktur-komponenter som indgår i eDelivery Sundhedsdomænet) beskrives de tekniske infrastrukturkomponenter, som den tilsluttede part skal integrere til og anvende afhængigt af den rolle, parten varetager.

Det fremgår desunden at infrastrukturkomponenterne systemforvaltes hos to forskellige organisationer:

<ol>
<li>Den Nationale Service Platform (NSP) er systemforvalter på Keycloak, EAS og EMR.</li>
<li>Digital Sundhed Danmark (2026: MedCom) er systemforvalter på EER, EDS, SDN og SMP/SML</li>
</ol>

Nedenfor beskriver hvordan der indgåes en aftale med hver af de tre systemforvaltere.

<details>
  <summary><strong>Adgang Keycloak, EAS og EMR – NSP er systemforvalter</strong></summary>

Keycloak, EAS og EMR driftes på Den Nationale Serviceplatform (NSP). Anvenderen skal dels indgå en central aftale med Sundhedsdatastyrelsen (SDS) for at få adgang til NSP og dels whitelistes til de services, der ønskes anvendt.

<strong>Adgang til NSP</strong><br>
Vejledning vedrørende indgåelse af den centrale aftale med SDS om adgang til NSP findes her: https://www.nspop.dk/spaces/Web3/pages/29987467/Aftaler+for+Anvenderleverandør+og+Serviceaftager

<br><br><strong>Whitelistning til Keycloak</strong><br>
Adgang til Keycloak Authorization Server forudsætter, at anvenderapplikationen tilsluttes til Keycloak via metadata, som blandt andet indeholder applikationens certifikat. Til denne tilslutning anvendes et MitID Erhverv systemcertifikat.
Anvenderen anmoder om tilslutning af anvenderapplikationen til Keycloak ved oprettelse af supportsag på nspop.dk. Der skal vedhæftes en json-fil med anvendersystemets metadata til sagen.

<br><br><strong>Whitelistning til EAS</strong><br>
En anvenderapplikation kan opnå adgang til EAS med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.

<strong>Whitelistning til EMR</strong><br>EMR fungerer som Access Point i eDelivery-infrastrukturen og kan modtage meddelelser fra andre Access Points.
Der kræves ikke en særskilt tilslutningsaftale for den MSH, der skal arkivere en kopi af meddelelsen i EMR. Det skal dog sikres, at det Access Point, som MSH'en er tilsluttet, har en gyldig SDN-aftale med EMR registreret via SDN-aftalesystemet.
<br>
</details>

<details>
  <summary><strong>Adgang EER, EDS og SDN – Digital Sundhed Danmark (2026: MedCom) er systemforvalter</strong></summary>

<strong>Adgang til EER</strong><br>
En anvenderapplikation kan opnå adgang til EER med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.

<br><br><strong>Adgang til EDS</strong><br>
En anvenderapplikation kan opnå adgang til EDS med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.

<br><br><strong>Adgang til SDN</strong><br>
SDN er et sikret netværk til datakommunikation i den danske sundhedssektor for både offentlige og private parter. SDN binder lokale, sikrede net sammen i en fælles infrastruktur – og gør det muligt for de tilsluttede parter både at udstille egne services og indgå aftaler om netværksmæssig adgang til andres services.

Ved tilslutning til SDN skal indgås både en tilslutningsaftale om brug af SDN samt en databehandleraftale.
Vejledning vedrørende dette findes her: https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/startpakke/

<strong>SDN-aftalesystemet</strong><br>
Alle ”klient til service” forbindelser via SDN skal registreres og godkendes via SDN-aftalesystemet.<br>
En ny AP skal registreres som en service på SDN-aftalesystemet. Derudover fungerer en AP som klient til andre AP'er samt til Keycloak og EDS og skal derfor anmode om adgang til dis-se services via SDN-aftalesystemet. EMR udstilles som en AP. Ved etablering af en ny AP skal det derfor sikres, at EMR er omfattet af de AP'er, hvortil der anmodes om adgang.<br>
En ny MSH fungerer som klient til Keycloak og EDS og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. Adgang mellem MSH og AP behøver ikke at gå via SDN. Hvis forbindelsen etableres via SDN, skal der dog ligeledes indsendes en anmodning om adgang gennem SDN-aftalesystemet.<br>
En ny EUA fungerer som klient til Keycloak, EDS og eventuelt EAS og EER og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. Adgang mellem EUA og MSH behøver ikke at gå via SDN. Hvis forbindelsen etableres via SDN, skal der tilsvarende ind-sendes en anmodning om adgang gennem SDN's aftalesystem.
For alle ovennævnte anmodninger via SDN-aftalesystemet gælder, at de relevante serviceejere skal godkende anmodningerne, før SDN kan åbne den ønskede adgang.<br>
</details>

<details>
  <summary><strong>Adgang SMP/SML – Digital Sundhed Danmark (2026: MedCom) er systemforvalter</strong></summary>
Digital Sundhed Danmark (2026: MedCom) håndtere oprettelse i SML/SMP når en ny AP indgår en EHMI-tilslutnngsaftale.

</details>
</details>

<details>
    <summary>Trin 4 - Test og certificering</summary>

I nedenstående tabel fremgår en blanding af krav og testmuligheder opdelt på de forskellige integrationskomponenter. Det fremgår desuden, hvilke roller i EHMI-økosystemet de enkelte krav og test er relevante for.

<table>
<thead>
<tr>
<th>ID</th>
<th>Krav til produkter, test og testintegrationer</th>
<th>AP</th>
<th>MSH</th>
<th>EUA</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td><strong>Godkendte AP-produkter og brug af SMP/SML</strong><br><br>eDelivery Sundhedsområdet følger det fælles offentlige eDelivery retningslinjer på dette område. Disse retningslinjer kommer blandt andet ind på:<br><br>at det anvendte AP-produkt skal figurere på EU's liste over "eDelivery AS4 v1.x conformant products". Desuden skal AP-produktet:<br>- Have bestået conformance testen indenfor seneste 3 år.<br>- Overholde "(eDel AS4 1.15) eDelivery AS4 Profile v1.15"<br>- Overholde "(eDel AS4 1.15) AS4 Four Corner Topology Profile Enhancement"<br>- Overholde "(eDel AS4 1.15) AS4 SBDH Profile Enhancement"<br><br><a href="https://ec.europa.eu/digital-building-blocks/sites/spaces/DIGITAL/pages/721846393/eDelivery+AS4+v1.x+conformant+products">*eDelivery AS4 v1.x conformant products</a></td>
<td>X</td>
<td></td>
<td></td>
</tr>
<tr>
<td>2</td>
<td><strong>EDS integrationstest</strong><br><br>MedCom stiller en test EDS-service til rådighed.<br><br>MedCom udstiller desuden en testplatform, der kan anvendes til test af, om EDS-klienten kan generere valide AuditEvents.</td>
<td>X</td>
<td>X</td>
<td>X</td>
</tr>
<tr>
<td>3</td>
<td><strong>FAPI 2.0-sikkerhedsprofilen</strong><br><br>Keycloak fungerer som en sikkerhedskomponent og udsteder de OpenID-adgangsbilletter, der anvendes ved adgang til EDS. Overholdelse af FAPI 2.0-sikkerhedsprofilen testes indirekte i forbindelse med EDS- og EAS-integrationstesten.</td>
<td>X</td>
<td>X</td>
<td>X</td>
</tr>
<tr>
<td>4</td>
<td><strong>Accesspoint tilslutningstest</strong><br><br>Da der stilles krav om godkendte AP-produkter, forventes det, at et AP overholder gældende krav til protokoller og formater.<br><br>Formålet med AP-tilslutningstesten er at sikre, at et AP er korrekt konfigureret til at kunne sende og modtage meddelelser via en test-AP i eDelivery Sundhedsdomænet, som MedCom stiller til rådighed. I forbindelse med integrationstesten testes desuden integration til SMP-servicen.</td>
<td>X</td>
<td></td>
<td></td>
</tr>
<tr>
<td>5</td>
<td><strong>MSH test</strong><br><br>MedCom udstiller en testplatform, der kan anvendes til test af, om en MSH overholder de nødvendige protokoller og formater for en MSH-service.<br>Tilslutningstesten dækker følgende hovedområder:<br><br>
<ol>
<li>Overholdelse af ehmiSBDH-profilen.</li>
<li>Succesfuld levering af meddelelser til en MSH-modtager.</li>
<li>Succesfuld modtagelse af meddelelser fra en MSH-afsender.</li>
<li>Håndtering af kvitteringer.</li>
<li>Håndtering af semantiske fejl.</li>
</ol></td>
<td></td>
<td>X</td>
<td></td>
</tr>
<tr>
<td>6</td>
<td><strong>EMR tilslutningstest</strong><br><br>Efter succesfuld levering af en meddelelse til en modtager-MSH skal afsender-MSH uploade meddelelsen til EMR-servicen.<br><br>EMR testes indirekte via MSH test. Der er i princippet ikke forskel på afsendelse af en meddelelse til EMR og afsendelse af en meddelelse enhver anden MSH.<br><br>Det forventes dog at Afsender-MSH har afprøvet og sikret korrekt afsendelse af meddelelser til EMR på NSP-testsystemer før produktionssætning.</td>
<td></td>
<td>X (kun afsender MSH)</td>
<td></td>
</tr>
<tr>
<td>7</td>
<td><strong>Overholdelse af format for kliniske meddelelser (eksempelvis "HomeCareObservation")</strong><br><br>En EUA skal certificeres i forhold til de kliniske meddelelser, som systemet understøtter, og må kun sende/modtage kliniske meddelelser, som det kliniske system er godkendt til.<br>MedCom forestår denne certificering, og efter gennemført certificering vil den tilsluttede parts løsning fremgå af MedComs godkendelsesoversigt.</td>
<td></td>
<td></td>
<td>X</td>
</tr>
<tr>
<td>8</td>
<td><strong>EAS integrationstest</strong><br><br>Sundhedsdatastyrelsen stiller en test EAS-service til rådighed på NSP-testsystemerne. Det forventes, at EUA tester deres løsning op imod EAS på NSP-testsystemerne før produktionssætning.</td>
<td></td>
<td></td>
<td>X</td>
</tr>
<tr>
<td>9</td>
<td><strong>EER integrationstest</strong><br><br>MedCom stiller en test EER-service til rådighed. Det forventes at EUA tester deres løsning op imod test EER-servicen før produktionssætning.</td>
<td></td>
<td>X</td>
<td>(hvis den benyttes)</td>
</tr>
</tbody>
</table>

Den tilsluttede part skal certificeres af MedCom, før partens løsning kan tilsluttes eDelivery-sundhedsdomænet. Certificeringen baseres på en testprotokol udviklet af MedCom. Den til enhver tid gældende testprotokol fremgår af www.medcom.dk.
<br>
</details>

<details>
    <summary>Trin 5 - Etabler testmiljø</summary>

MedCom, Sundhedsdatastyrelsen og Erhvervsstyrelsen har etableret testmiljøer for følgende infrastrukturkomponenter: EAS, EMR, SMP, Keycloak, EER og EDS.

MedCom har desuden etableret en test-AP og en test-MSH, som tilsluttede parter med rollen AP og MSH kan anvende til at sende og modtage meddelelser via deres egen test-AP eller test-MSH.

MedCom stiller endvidere testplatform til rådighed, som kan anvendes til at teste overholdelse af gældende standarder og profiler.

Den tilsluttede part skal etablere og vedligeholde et testmiljø med de produkter, som parten ønsker at tilslutte eDelivery-sundhedsdomænet. Testmiljøet skal integrere de relevante testmiljøer og services hos MedCom, Sundhedsdatastyrelsen og Erhvervsstyrelsen.

Testmiljøet bør desuden være integreret med de underliggende testmiljøer hos de aktører i EHMI-økosystemet, som den tilsluttede part er afhængig af, således at end-to-end-test af funktionalitet og integration kan gennemføres.

Den tilsluttede part skal endvidere stille testgrænseflader (testsnitflader) til rådighed i testmiljøet, som partens kunder kan anvende til egne testformål, herunder integrationstest og validering forud for idriftsættelse i produktionsmiljøet.

<br>
</details>

<details>
    <summary>Trin 6 - Etabler supportorganisation</summary>

Den tilsluttede part skal informere afsenderen om fejlscenarier, såsom meddelelser med semantiske eller adresseringsfejl, der ikke kan leveres til modtageren.

Den tilsluttede part indgår i eDelivery sundhedsdomænets fælles supportflow som skitseret på figuren.

<img src="Supportflow2.png" alt="Supportflow" width="800">

Den tilsluttede part fastlægger selv sit supportniveau i forhold til egne kunder, dvs. aktører, der er placeret over den tilsluttede part i EHMI-økosystemet.

Den tilsluttede part er forpligtet til at modtage, håndtere og medvirke til udredning af supporthenvendelser fra aktører, der er placeret under eller parallelt med den pågældende part i EHMI-økosystemet.

<ol>
<li>En EUA er forpligtet til at udrede supporthenvendelser fra den underliggende MSH samt fra de EUA'er, som der sendes kliniske meddelelser til og modtages kliniske meddelelser fra.</li>
<li>En MSH er forpligtet til at udrede supporthenvendelser fra den underliggende AP samt fra de MSH'er, som der sendes ehmiSBDH-meddelelser til og modtages ehmiSBDH-meddelelser fra.</li>
<li>En AP er forpligtet til at udrede supporthenvendelser fra de AP'er, som der sendes AS4-meddelelser til og modtages AS4-meddelelser fra.</li>
</ol>

Hvis en tilsluttet part har sammenbyggede EUA-, MSH- og/eller AP-komponenter, er parten forpligtet til at håndtere det samlede supportansvar, som de enkelte komponenter hver især er ansvarlige for.

Den tilsluttede part skal etablere og opretholde en bemandet supportfunktion med dertilhørende kontaktkanaler i form af telefonnummer og e-mailadresse, som kan anvendes til indmelding af supporthenvendelser.

Supportfunktionen skal være tilgængelig på hverdage med følgende servicemål:

<ol>
<li><strong>Kvittering for modtagelse:</strong><br>
Modtagelse af en supporthenvendelse skal kvitteres inden for to (2) timer på hverdage inden for normal arbejdstid. Supporthenvendelser, der modtages lørdag, søndag eller på helligdage, skal kvitteres inden for to (2) timer på førstkommende hverdag.</li>
<li><strong>Opstart af udredning:</strong><br>
Udredning og fejlsøgning af supporthenvendelsen skal påbegyndes af kvalificeret personale inden for to (2) timer på hverdage regnet fra tidspunktet for kvittering af henvendelsen.</li>
</ol>

Supporthenvendelser håndteres i overensstemmelse med følgende principper:

<ol>
<li><strong>Lokal afhjælpning:</strong><br>
Supporthenvendelsen skal i videst muligt omfang løses lokalt af den tilsluttede part, såfremt årsagen til problemet kan henføres til den tilsluttede part eget ansvarsområde.</li>
<li><strong>Koordineret udredning:</strong><br>
Såfremt problemet involverer eller mistænkes at involvere en underliggende eller paralleltliggende aktør i EHMI-økosystemet, skal den tilsluttede part aktivt inddrage den relevante aktør i den videre udredning og fejlsøgning.</li>
<li><strong>Eskaleringspligt:</strong><br>
Kan supporthenvendelsen ikke løses lokalt eller gennem koordination med relevante aktører, er den tilsluttede part forpligtet til rettidigt at eskalere henvendelsen til enten MedCom EHMI Support eller NSP Support, afhængigt af problemets karakter og ansvarsplacering.</li>
</ol>

MedCom EHMI support håndterer supporthenvendelser vedrørende EDS, EER, SDN og SMP. NSP Support håndterer supporthenvendelser vedrørende EAS, EMR og Keycloak.

MedCom EHMI support og NSP Support kan efter behov eskalere supporthenvendelser videre til de relevante systemforvaltere (Product Owners) og systemleverandører.

<br>
</details>

<details>
    <summary>Trin 7 - Etabler produktionsmiljø</summary>

I det produktion miljø som den tilsluttede part etablere skal det sikres, at meddelelser ikke går tabt i perioden fra de er modtaget og kvitteret for af Partens løsning, og indtil meddelelsen er videreformidlet til modtager, og modtageren har kvitteret for modtagelsen.

Parten skal etablere og opretholde tekniske og organisatoriske mekanismer, der sikrer, at meddelelser i dette forløb håndteres på en måde, så de kan spores, genoptages og reetableres ved fejl eller nedbrud. Dette omfatter som minimum:

<ol>
<li>vedvarende lagring og sporbarhed af meddelelser samt tilhørende kvitteringer, indtil de er færdigbehandlet.</li>
<li>mekanismer, der sikrer, at en meddelelse først betragtes som endeligt afleveret, når modtagerens kvittering er modtaget og registreret,</li>
<li>automatisk genoptagelse af videreformidling efter nedbrud, herunder genforsøg og håndtering af midlertidige fejltilstande,</li>
<li>procedurer for reetablering, så meddelelser, der er modtaget, ikke bortfalder eller efterlades ubehandlede.</li>
</ol>

Såfremt der konstateres forhold, der medfører risiko for tab af meddelelser, skal Parten uden unødig forsinkelse iværksætte afhjælpende foranstaltninger.

</details>

<h2>Kontakt ved spørgsmål om tilslutning</h2>

MedCom

Mail: ehmi@medcom.dk

Telefon: (+45) xxxx xxxx
