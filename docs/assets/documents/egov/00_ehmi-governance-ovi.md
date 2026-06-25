<style>
/* Gælder kun i HTML-browser – GitHub ignorerer dette blok */
details {
  margin: 1.2em 0;
  padding: 0.5em 0.75em;
  border-left: 3px solid #d0d7de;
  border-radius: 0 4px 4px 0;
}
details[open] {
  border-left-color: #0969da;
  background: #f8faff;
}
details > summary {
  cursor: pointer;
  padding: 0.3em 0;
  line-height: 1.5;
  list-style: disclosure-closed;
}
details[open] > summary {
  list-style: disclosure-open;
  margin-bottom: 0.6em;
}
details > summary:hover {
  color: #0969da;
}
details p, details li {
  line-height: 1.65;
  margin: 0.7em 0;
}
details details {
  margin-top: 0.8em;
  border-left: 2px solid #c0cad4;
  background: transparent;
}
h1, h2 {
  margin-top: 1.8em;
}
table {
  border-collapse: collapse;
  width: 100%;
  margin: 1em 0;
}
th, td {
  border: 1px solid #d0d7de;
  padding: 0.5em 0.75em;
  vertical-align: top;
}
th {
  background: #f0f4f8;
}
</style>

<h1>Startpakke for EHMI – pilotprojekt</h1>

<p>EHMI (Enhanced Healthcare Messaging Infrastructure) har til formål at etablere, udvikle og drive en infrastruktur til udveksling af kliniske meddelelser inden for sundhedssektoren samt til og fra andre domæner uden for sundhedsområdet.</p>

<p>Denne startpakke er etableret i forbindelse med eDelivery-pilotprojektet til deltagerne heri. Samtidig er startpakken udformet med henblik på, at den – efter nødvendige tilpasninger – kan videreføres, når eDelivery Sundhedsdomænet overgår til normal drift.</p>

<p>Hvis en aktør ønsker at tilslutte sig EHMI, er første skridt at tage kontakt til MedCom. Nogle af de indledende spørgsmål, der kan drøftes, er:</p>

<ol>
<li>Hvad skal EHMI tilslutningen anvendes til?</li>
<li>Hvilken rolle forventer aktøren at have:
  <ol>
    <li>Organisation, der skal sende og modtage kliniske meddelelser via eDelivery Sundhedsdomænet</li>
    <li>End User Application (EUA) – leverandør af fagsystem/klinisk system</li>
    <li>Message Service Handler (MSH)</li>
    <li>Access Point (AP)</li>
  </ol>
</li>
<li>Hvad er de praktiske trin frem mod tilslutning til EHMI – både aftalemæssigt og teknisk?</li>
</ol>

<p>I det følgende beskrives de aftalemæssige og tekniske trin for tilslutning til EHMI.</p>

<p>Beskrivelsen indledes med en kort introduktion til EHMI med fokus på de forskellige roller, en aktør kan have. Herefter følger en kort introduktion til de infrastrukturkomponenter, der indgår i eDelivery Sundhedsdomænet.</p>

<h2>Introduktion til EHMI, med fokus på roller og infrastruktur komponenter.</h2>

<p>(Klik på pilen ud for hver introduktion.)</p>

<details>
  <summary><strong>Introduktion til EHMI med fokus på de forskellige roller.</strong></summary>

<p>Tag stilling til hvilken rolle eller roller du ønsker at varetage i EHMI.
Figuren nedenfor illustrerer, hvordan en klinisk besked sendes fra en afsenderorganisation (f.eks. en kommune) til en modtagerorganisation (f.eks. en praktiserende læge) via eDelivery Sundhedsdomænet. Beskedens fysiske vej går gennem afsender-økosystemet, over sundhedsdatanettet og op gennem modtager-økosystemet.</p>

<img src="EHMIokosystemet.png" alt="Økosystem" width="500">

<p>(Klik på pilen for beskrivelse af nedenstående begreber.)</p>

<details>
  <summary>End User Application (EUA)</summary>

<p>Det kliniske fagsystem (eller andre fagsystemer), som afsender- og modtagerorganisationen anvender til at registrere og behandle en borgers (patientens) sundhedsoplysninger.</p>

<p>Når der er behov for at sende en klinisk meddelelse til en anden organisation, sikrer det kliniske system, at meddelelsen opsættes i det relevante kliniske format (f.eks. en HomeCareObservation) og fremfinder den ønskede modtager. Meddelelsen og modtageren overdrages herefter til MSH. Det kliniske system kan også modtage kliniske meddelelser fra andre sundhedsorganisationer via MSH.</p>

<p>Det kliniske system sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets "track-and-trace"-system.</p>

</details>

<details>
  <summary>Message Service Handler (MSH)</summary>

<p>MSH er ansvarlig for klargøring og afsendelse af kliniske meddelelser fra EUA til en udpeget modtager. Klargøringen indebærer at indpakke den kliniske meddelelse i den digitale konvolut (ehmiSBDH), der bruges til udveksling af kliniske meddelelser indenfor eDelivery Sundhedsdomænet. MSH håndterer succes- eller fejl-kvitteringer fra modtageren (ehmiSBDH Acknowledgement). Ved fejl gensendes den kliniske meddelelse. Efter succesfuld afsendelse sendes en kopi af meddelelsen til EMR, en tjeneste til arkivering af kliniske meddelelser sendt via eDelivery Sundhedsdomænet.</p>

<p>MSH modtager også kliniske meddelelser fra andre sundhedsorganisationer, udpakker dem fra den digitale konvolut (ehmiSBDH), returnerer en kvittering (ehmiSBDH Acknowledgement) til afsenderen og sender den udpakkede kliniske meddelelse op til EUA.</p>

<p>MSH sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets "track-and-trace"-system.</p>

<p>MSH overlader den fysiske afsendelse og modtagelse af beskeder og kvitteringer til Accesspoint.</p>

</details>

<details>
  <summary>Accesspoint (AP)</summary>

<p>AP håndterer den fysiske digitale udveksling af kliniske meddelelser sendt via eDelivery Sundhedsdomænet. Den digitale adresse på modtageren hentes via Erhversstyrelsens SMP-service. Meddelelser og kvitteringer indpakkes og krypteres i henhold til EU's eDelivery protokol og sendes derefter til modtagerens AP via Sundhedsdatanettet.</p>

<p>Når AP modtager en besked fra en anden AP via Sundhedsdatanettet, står AP for dekryptering og udpakning, før beskeden leveres op til MSH.</p>

<p>AP sikrer, at afsendte og modtagne meddelelser kan spores ved at registrere afsendelse og modtagelse i EDS-servicen (EHMI Delivery Status), som er eDelivery Sundhedsdomænets "track-and-trace"-system.</p>

</details>

<details>
  <summary>Sundhedsdatanettet (SDN)</summary>

<p>Et lukket og sikret net til udveksling af sundhedsdata.</p>

<p>EUA, MSH og AP kan kombineres på forskellige måder, f.eks. en sammenbygning af EUA og MSH eller en sammenbygning af MSH og AP.</p>

</details>

<p>Anvendte protokoller og standarder i EHMI findes her: https://ehmi.dk</p>

</details>

<br>

<details>
  <summary><strong>Introduktion til de services som indgår i EHMI.</strong></summary>

<p>EHMI anviser en række tekniske service, som den tilsluttede part skal integrere til og anvende, afhængigt af den rolle, parten varetager. Tabellen nedenfor oplister services, deres systemforvalter samt de roller i EHMI-økosystemet, der skal benytte den enkelte service.</p>

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
<td>EHMI Meddelelses Registrering<br><br>Service til deling af kliniske meddelelser sendt via EHMI. Delingen sker via NSP's dokumentdelingsinfrastruktur</td>
<td>Digital Sundhed Danmark (i 2026: SDS) via NSP</td>
<td>MSH</td>
</tr>
<tr>
<td>SMP/SML</td>
<td>Service Metadata Publisher/Service Metadata Locator<br><br>
SML fungerer som en central adressebog. SMP indeholder en organisations metadata. SML bruges til at pege på den rigtige SMP, mens SMP indeholder de konkrete metadata for organisationens understøttede dokumenttyper samt organisationens endpoint-adresse.
</td>
<td>Digital Sundhed Danmark (i 2026: Med-Com)</td>
<td>AP</td>
</tr>
<tr>
<td>SDN</td>
<td>Sundhedsdatanettet<br><br>Et sikkert og lukket netværk, der forbinder IT-systemer i den danske sundhedssektor. Alle "klient til service" forbindelser via SDN skal registreres i SDN-aftalesystemet</td>
<td>Digital Sundhed Danmark (i 2026: Med-Com)</td>
<td>1) EUA<br>2) MSH<br>3) AP</td>
</tr>
</tbody>
</table>

</details>

<h2>Trin for tilslutning til EHMI</h2>

<details>
  <summary>Trin 1 - Indgå tilslutningsaftale til EHMI</summary>

<p>Aftalen giver den tilsluttede part adgang til EHMI med det formål at sende og modtage meddelelser i henhold til den eller de rolle(r), som parten varetager i EHMI-økosystemet (Enhanced Healthcare Messaging Infrastructure).</p>

<p><a href="tilslutningsaftale_edelivery.docx">Tilslutningsaftale</a></p>

<p>Tilslutningsaftalen skal udfyldes og underskrives. Herefter sendes tilslutningsaftalen elektronisk til Digital Sundhed Danmark (i 2026: MedCom) på ehmi@medcom.dk.</p>

<p>Efter modtagelse underskriver Digital Sundhed Danmark (i 2026: MedCom) en kopi og tilbagesender kopien til den tilsluttede part som bekræftelse på tilslutningen.</p>

</details>

<br>

<details>
  <summary>Trin 2 - Sikre at nødvendige databehandleraftaler er på plads</summary>

<p>Som det fremgår af figuren for EHMI-økosystemet, så findes der 5 roller i EHMI-økosystemet.</p>

<ol>
<li>Afsender- eller modtagerorganisation.</li>
<li>EUA (End-User-Application - også omtalt fagsystem/klinisk system)</li>
<li>MSH (Message-Service-Handler)</li>
<li>AP (Access-Point)</li>
<li>SDN (Sundheds-Data-Nettet)</li>
</ol>

<p>En afsender- eller modtagerorganisation er i sidste ende den dataansvarlige og skal sikre, at der er etableret de nødvendige databehandleraftaler gennem hele kæden af øvrige roller i EHMI-økosystemet. Dette kan håndteres som en traditionel kæde-databehandler-model, hvor afsender- eller modtagerorganisationen indgår en databehandleraftale med EUA samt sikrer, at EUA har indgået en underdatabehandleraftale med MSH, og at MSH tilsvarende har indgået en underdatabehandleraftale med AP, osv. Alternativt kan afsender- eller modtagerorganisationen indgå databehandleraftaler direkte med flere led i kæden.</p>

<p>Det er op til den enkelte part selv at vælge databehandlermodel i samarbejde med sine underleverandører.</p>

<p>Ved tilslutning til EHMI vil den tilsluttede part blive spurgt, om der foreligger gyldige databehandleraftaler med de relevante parter i overensstemmelse med gældende databeskyttelseslovgivning – eller alternativt, hvad den tilsluttede part har af planer for at sikre dette.</p>

<p>EHMI har udarbejdet et eksempel på en databehandleraftale mellem en kommune og et access point, som kan anvendes til inspiration. Vær opmærksom på:</p>

<ol>
<li>at en databehandleraftale altid er kontekstafhængig, og at eksemplet derfor ikke kan anvendes direkte.</li>
<li>at en databehandleraftale kan formuleres på mange forskellige måder, og at databehandlerforholdet muligvis allerede er dækket af eksisterende databehandleraftaler med underleverandører.</li>
<li>at eksemplet viser en databehandleraftale fra en kommune direkte til et access point. Dette kunne alternativt være håndteret via underdatabehandleraftaler fra kommunens leverandør af fagsystem til MSH og AP.</li>
</ol>

<p>Eksemplet tager udgangspunkt i en standard skabelon for databehandleraftaler, hvor en stor del af teksten stammer fra skabelonen. De dele af teksten, der specifikt vedrører eDelivery-sundhedsdomænet, er markeret med gult.</p>

<p><a href="Databehandleraftale_eksempel.docx">Eksempel på databehandleraftale</a></p>

</details>

<br>

<details>
  <summary>Trin 3 - Indgå tilslutningsaftaler til benyttede EHMI-services</summary>

<p>Ovenfor (jf. Introduktion til de Infrastruktur-komponenter som indgår i EHMI) beskrives de tekniske infrastrukturkomponenter, som den tilsluttede part skal integrere til og anvende afhængigt af den rolle, parten varetager.</p>

<p>Det fremgår desuden at infrastrukturkomponenterne systemforvaltes hos to forskellige organisationer:</p>

<ol>
<li>Den Nationale Service Platform (NSP) er systemforvalter på Keycloak, EAS og EMR.</li>
<li>Digital Sundhed Danmark (2026: MedCom) er systemforvalter på EER, EDS, SDN og SMP/SML</li>
</ol>

<p>Nedenfor beskrives hvordan der indgås en aftale med hver af de to systemforvaltere.</p>

<br>

<details>
  <summary><strong>Adgang Keycloak, EAS og EMR – NSP er systemforvalter</strong></summary>

<p>Keycloak, EAS og EMR driftes på Den Nationale Serviceplatform (NSP). Anvenderen skal dels indgå en central aftale med Sundhedsdatastyrelsen (SDS) for at få adgang til NSP og dels whitelistes til de services, der ønskes anvendt.</p>

<p><strong>Adgang til NSP</strong><br>
Vejledning vedrørende indgåelse af den centrale aftale med SDS om adgang til NSP findes her: https://www.nspop.dk/spaces/Web3/pages/29987467/Aftaler+for+Anvenderleverandør+og+Serviceaftager</p>

<p><strong>Adgang til Keycloak</strong><br>
Adgang til Keycloak Authorization Server forudsætter, at anvenderapplikationen tilsluttes til Keycloak via metadata, som blandt andet indeholder applikationens certifikat. Til denne tilslutning anvendes et MitID Erhverv systemcertifikat.</p>

<p>Anvenderen anmoder om tilslutning af anvenderapplikationen til Keycloak ved oprettelse af supportsag på nspop.dk. Der skal vedhæftes en json-fil med anvendersystemets metadata til sagen.</p>

<p>Om en anvenderapplikation må få adgang til en service (her EER, EDS, EAS) autoriseres centralt i Keycloak. Den kaldende anvenderapplikation skal derfor være forhåndskonfigureret i Keycloak til at kunne få udstedt et access token til den pågældende service.
Servicen vedligeholder ikke en særskilt whitelist over tilladte anvenderapplikationer, men skal ved hvert kald validere det modtagne access token, herunder issuer, audience, scope/permissions, udløbstid og sender-binding i overensstemmelse med FAPI 2.0-sikkerhedsprofilen.</p>

<p><strong>Adgang til EAS</strong><br>
Whitelistningen er forhåndskonfigureret i KeyCloak - se ovenfor.<br>
En anvenderapplikation kan opnå adgang til EAS med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.</p>

<p><strong>Adgang til EMR</strong><br>
EMR fungerer som Access Point i eDelivery-infrastrukturen og kan modtage meddelelser fra andre Access Points.
Der kræves ikke en særskilt tilslutningsaftale for den MSH, der skal arkivere en kopi af meddelelsen i EMR. Det skal dog sikres, at det Access Point, som MSH'en er tilsluttet, har en gyldig SDN-aftale med EMR registreret via SDN-aftalesystemet.</p>

</details>

<br>

<details>
  <summary><strong>Adgang EER, EDS og SDN – Digital Sundhed Danmark (2026: MedCom) er systemforvalter</strong></summary>

<p><strong>Adgang til EER</strong><br>
Whitelistningen er forhåndskonfigureret i KeyCloak - se ovenfor.<br>
En anvenderapplikation kan opnå adgang til EER med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.</p>

<p><strong>Adgang til EDS</strong><br>
Whitelistningen er forhåndskonfigureret i KeyCloak - se ovenfor.<br>
En anvenderapplikation kan opnå adgang til EDS med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.</p>

<p><strong>Adgang til SDN</strong><br>
SDN er et sikret netværk til datakommunikation i den danske sundhedssektor for både offentlige og private parter. SDN binder lokale, sikrede net sammen i en fælles infrastruktur – og gør det muligt for de tilsluttede parter både at udstille egne services og indgå aftaler om netværksmæssig adgang til andres services.</p>

<p>Ved tilslutning til SDN indgås både en tilslutningsaftale om brug af SDN samt en databehandleraftale.
Vejledning vedrørende dette findes her: https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/startpakke/</p>

<p><strong>SDN-aftalesystemet</strong><br>
Alle "klient til service" forbindelser via SDN skal registreres og godkendes via SDN-aftalesystemet.</p>

<ol>
<li>En ny AP skal registreres som en service på SDN-aftalesystemet. Derudover fungerer en AP som klient til andre AP'er samt til Keycloak og EDS og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. EMR udstilles som en AP. Ved etablering af en ny AP skal det derfor sikres, at EMR er omfattet af de AP'er, hvortil der anmodes om adgang.</li>
<li>En ny MSH fungerer som klient til Keycloak og EDS og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. Adgang mellem MSH og AP behøver ikke at gå via SDN. Hvis forbindelsen etableres via SDN, skal der dog ligeledes indsendes en anmodning om adgang gennem SDN-aftalesystemet.</li>
<li>En ny EUA fungerer som klient til Keycloak, EDS og eventuelt EAS og EER og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. Adgang mellem EUA og MSH behøver ikke at gå via SDN. Hvis forbindelsen etableres via SDN, skal der tilsvarende indsendes en anmodning om adgang gennem SDN's aftalesystem.
For alle ovennævnte anmodninger via SDN-aftalesystemet gælder, at de relevante serviceejere skal godkende anmodningerne, før SDN kan åbne den ønskede adgang.</li>
</ol>

<p><strong>SMP/SML</strong><br>
Digital Sundhed Danmark (2026: MedCom) håndterer oprettelse i SML/SMP når en ny AP indgår en EHMI-tilslutningsaftale.</p>

<p><em>SMI: der mangler noget udretning her i forhold til processen for oprettelse af adresseringsmetadata og publicering af disse til EER og SMP/SML. Herunder hvilke metadata der er behov for for den enkelte service.</em></p>

</details>

</details>

<br>

<details>
  <summary>Trin 4 - Test og certificering</summary>

<p>Den tilsluttede part skal certificeres af Digital Sundhed Danmark (i 2026: MedCom), før partens løsning kan tilsluttes EHMI. Certificeringen baseres på testprotokoller udviklet af Digital Sundhed Danmark (i 2026: MedCom). De til enhver tid gældende testprotokoller fremgår af ehmi.dk/assets/documents/test/.</p>

<p>Til testformål er følgende etableret:</p>

<ol>
<li>Digital Sundhed Danmark (i 2026: MedCom) og NSP har etableret testmiljøer for følgende EHMI-services: EAS, EMR, SMP/SML, Keycloak, EER og EDS.</li>
<li>Digital Sundhed Danmark (i 2026: MedCom) har desuden etableret en test-AP og en test-MSH (NB. Test-MSH er ikke tilgængelig i pilotprojektet), som tilsluttede parter med rollen AP og MSH kan anvende til at sende og modtage meddelelser via deres egen test-AP eller test-MSH.</li>
<li>Digital Sundhed Danmark (i 2026: MedCom) stiller endvidere testplatform til rådighed, som kan anvendes til at teste overholdelse af gældende standarder og profiler.</li>
</ol>

</details>

<br>

<details>
  <summary>Trin 5 - Etabler testmiljø</summary>

<p>Det er ikke tilladt at teste i EHMI's produktionsmiljøer. Al test i forbindelse med tilslutning, opsætning af nye kunder samt ændringer i software foranlediget af egne behov eller krav fra EHMI skal gennemføres i testmiljøer og med anvendelse af testdata.</p>

<p>Krav til testmiljø fremgår af tilslutningsaftalen.</p>

</details>

<br>

<details>
  <summary>Trin 6 - Etabler supportorganisation</summary>

<p>Den tilsluttede part skal etablere og opretholde en bemandet supportfunktion med dertilhørende kontaktkanaler i form af telefonnummer og e-mailadresse, som kan anvendes til indmelding af supporthenvendelser.</p>

<p>Krav til supportfunktionen fremgår af tilslutningsaftalen.</p>

</details>

<br>

<details>
  <summary>Trin 7 - Etabler produktionsmiljø</summary>

<p>I det produktionsmiljø som den tilsluttede part etablerer skal det sikres, at meddelelser ikke går tabt i perioden fra de er modtaget og kvitteret for af partens løsning, og indtil meddelelsen er videreformidlet til modtager, og modtageren har kvitteret for modtagelsen.</p>

<p>Krav til produktionsmiljø fremgår af tilslutningsaftalen.</p>

</details>

<h2>Kontakt ved spørgsmål om tilslutning</h2>

<p>MedCom</p>

<p>Mail: ehmi@medcom.dk</p>

<p>Telefon: (+45) xxxx xxxx</p>
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

Anvendte protokoller og standarder i EHMI findes her: https://ehmi.dk

<br>
</details>

<details>
  <summary><strong>Introduktion til de services som indgår i EHMI.</strong></summary>

EHMI anviser en række tekniske service, som den tilsluttede part skal integrere til og anvende, afhængigt af den rolle, parten varetager. Tabellen nedenfor oplister services, deres systemforvalter samt de roller i EHMI-økosystemet, der skal benytte den enkelte service.

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
<td>EHMI Meddelelses Registrering<br><br>Service til deling af kliniske meddelelser sendt via EHMI. Delingen sker via NSP’s dokumentde-lingsinfrastruktur</td>
<td>Digital Sundhed Danmark (i 2026: SDS) via NSP</td>
<td>MSH</td>
</tr>
<tr>
<td>SMP/SML</td>
<td>Service Metadata Publisher/Service Metadata Locator<br><br>
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

</details>

<h2>Trin for tilslutning til EHMI</h2>

<details>
  <summary>Trin 1 - Indgå tilslutningsaftale til EHMI</summary>

Aftalen giver den tilsluttede part adgang til EHMI med det formål at sende og modtage meddelelser i henhold til den eller de rolle(r), som parten varetager i EHMI-økosystemet (Enhanced Healthcare Messaging Infrastructure).

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
Ved tilslutning til EHMI vil den tilsluttede part blive spurgt, om der foreligger gyldige databehandleraftaler med de relevante parter i overensstemmelse med gældende databeskyttelseslovgivning – eller alternativt, hvad den tilsluttede part har af planer for at sikre dette.

EHMI har udarbejdet et eksempel på en databehandleraftale mellem en kommune og et access point, som kan anvendes til inspiration. Vær opmærksom på:

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
  <summary>Trin 3 - Indgå tilslutningsaftaler til benyttede EHMI-services</summary>

Ovenfor (jf. Introduktion til de Infrastruktur-komponenter som indgår i EHMI) beskrives de tekniske infrastrukturkomponenter, som den tilsluttede part skal integrere til og anvende afhængigt af den rolle, parten varetager.

Det fremgår desunden at infrastrukturkomponenterne systemforvaltes hos to forskellige organisationer:

<ol>
<li>Den Nationale Service Platform (NSP) er systemforvalter på Keycloak, EAS og EMR.</li>
<li>Digital Sundhed Danmark (2026: MedCom) er systemforvalter på EER, EDS, SDN og SMP/SML</li>
</ol>

Nedenfor beskriver hvordan der indgåes en aftale med hver af de tre systemforvaltere.

<details>
  <summary><strong>Adgang Keycloak, EAS og EMR – NSP er systemforvalter</strong></summary>

Keycloak, EAS og EMR driftes på Den Nationale Serviceplatform (NSP). Anvenderen skal dels indgå en central aftale med Sundhedsdatastyrelsen (SDS) for at få adgang til NSP og dels whitelistes til de services, der ønskes anvendt.

<br><strong>Adgang til NSP</strong><br>
Vejledning vedrørende indgåelse af den centrale aftale med SDS om adgang til NSP findes her: https://www.nspop.dk/spaces/Web3/pages/29987467/Aftaler+for+Anvenderleverandør+og+Serviceaftager

<strong>Adgang til Keycloak</strong><br>
Adgang til Keycloak Authorization Server forudsætter, at anvenderapplikationen tilsluttes til Keycloak via metadata, som blandt andet indeholder applikationens certifikat. Til denne tilslutning anvendes et MitID Erhverv systemcertifikat.
Anvenderen anmoder om tilslutning af anvenderapplikationen til Keycloak ved oprettelse af supportsag på nspop.dk. Der skal vedhæftes en json-fil med anvendersystemets metadata til sagen.

Om en anvenderapplikation må få adgang til en service (her EER, EDS, EAS) autoriseres centralt i Keycloak. Den kaldende anvenderapplikation skal derfor være forhånds-konfigureret i Keycloak til at kunne få udstedt et access token til den pågældende service .
Servicen vedligeholder ikke en særskilt whitelist over tilladte anvenderapplikation, men skal ved hvert kald validere det modtagne access token, herunder issuer, audience, scope/permissions, udløbstid og sender-binding i overensstemmelse med FAPI 2.0-sikkerhedsprofilen.

<br><strong>Adgang til EAS</strong><br>
Whitelistningen er forhåndskonfigureret i KeyCloak - se længere oppe.<br>
En anvenderapplikation kan opnå adgang til EAS med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.

<br><strong>Adgang til EMR</strong><br>
EMR fungerer som Access Point i eDelivery-infrastrukturen og kan modtage meddelelser fra andre Access Points.
Der kræves ikke en særskilt tilslutningsaftale for den MSH, der skal arkivere en kopi af meddelelsen i EMR. Det skal dog sikres, at det Access Point, som MSH'en er tilsluttet, har en gyldig SDN-aftale med EMR registreret via SDN-aftalesystemet.

</details>

<details>
  <summary><strong>Adgang EER, EDS og SDN – Digital Sundhed Danmark (2026: MedCom) er systemforvalter</strong></summary>

<br><strong>Adgang til EER</strong><br>
Whitelistningen er forhåndskonfigureret i KeyCloak - se længere oppe.<br>
En anvenderapplikation kan opnå adgang til EER med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.

<br><strong>Adgang til EDS</strong><br>
Whitelistningen er forhåndskonfigureret i KeyCloak - se længere oppe.<br>
En anvenderapplikation kan opnå adgang til EDS med en gyldig adgangsbillet (access token) udstedt af NSP Keycloak. Adgangsbilletten gælder i en periode og kan anvendes hen over flere opslag.
For at kunne få udstedt en adgangsbillet i NSP Keycloak, er det en forudsætning at anvenderapplikationen er tilsluttet til NSP Keycloak.

<br><strong>Adgang til SDN</strong><br>
SDN er et sikret netværk til datakommunikation i den danske sundhedssektor for både offentlige og private parter. SDN binder lokale, sikrede net sammen i en fælles infrastruktur – og gør det muligt for de tilsluttede parter både at udstille egne services og indgå aftaler om netværksmæssig adgang til andres services.

Ved tilslutning til SDN indgås både en tilslutningsaftale om brug af SDN samt en databehandleraftale.
Vejledning vedrørende dette findes her: https://medcom.dk/systemforvaltning/sundhedsdatanettet-sdn/startpakke/

<br><strong>SDN-aftalesystemet</strong><br>
Alle ”klient til service” forbindelser via SDN skal registreres og godkendes via SDN-aftalesystemet.<br>
<ol>
<li>En ny AP skal registreres som en service på SDN-aftalesystemet. Derudover fungerer en AP som klient til andre AP'er samt til Keycloak og EDS og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. EMR udstilles som en AP. Ved etablering af en ny AP skal det derfor sikres, at EMR er omfattet af de AP'er, hvortil der anmodes om adgang.</li>
<li>En ny MSH fungerer som klient til Keycloak og EDS og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. Adgang mellem MSH og AP behøver ikke at gå via SDN. Hvis forbindelsen etableres via SDN, skal der dog ligeledes indsendes en anmodning om adgang gennem SDN-aftalesystemet.</li>
<li>En ny EUA fungerer som klient til Keycloak, EDS og eventuelt EAS og EER og skal derfor anmode om adgang til disse services via SDN-aftalesystemet. Adgang mellem EUA og MSH behøver ikke at gå via SDN. Hvis forbindelsen etableres via SDN, skal der tilsvarende ind-sendes en anmodning om adgang gennem SDN's aftalesystem.
For alle ovennævnte anmodninger via SDN-aftalesystemet gælder, at de relevante serviceejere skal godkende anmodningerne, før SDN kan åbne den ønskede adgang.</li>
</ol>

<br><strong>SMP/SML</strong><br>
Digital Sundhed Danmark (2026: MedCom) håndtere oprettelse oprettelse i SML/SMP når en ny AP indgår en EHMI-tilslutnngsaftale.
SMI: der mangler noget udretning her i forhold processen for oprettelse af addreseringsmetadata og publisering af disse til EER og SMP/SML. Herunder hvilke metadata der er behov for for den enkelte service.

</details>
</details>

<details>
    <summary>Trin 4 - Test og certificering</summary>

Den tilsluttede part skal certificeres af Digital Sundhed Danmark (i 2026: MedCom), før partens løsning kan tilsluttes EHMI. Certificeringen baseres på testprotokoller udviklet af Digital Sundhed Dan-mark (i 2026: MedCom). De til enhver tid gældende testprotokoller fremgår af ehmi.dk/assets/documents/test/.

Til testformål er følgende etableret:
<ol>
<li>Digital Sundhed Danmark (i 2026: MedCom) og NSP har etableret testmiljøer for følgende EHMI-services: EAS, EMR, SMP/SML, Keycloak, EER og EDS.</li>

<li>Digital Sundhed Danmark (i 2026: MedCom) har desuden etableret en test-AP og en test-MSH (NB. Test-MSH er ikke tilgængelig i pilotprojektet), som tilsluttede parter med rollen AP og MSH kan an-vende til at sende og modtage meddelelser via deres egen test-AP eller test-MSH.</li>

<li>Digital Sundhed Danmark (i 2026: MedCom) stiller endvidere testplatform til rådighed, som kan anvendes til at teste overholdelse af gældende standarder og profiler.</li>
</ol>
</details>

<details>
    <summary>Trin 5 - Etabler testmiljø</summary>
Det er ikke tilladt at teste i EHMI’s produktionsmiljøer. Al test i forbindelse med tilslutning, opsætning af nye kunder samt ændringer i software foranlediget af egne behov eller krav fra EHMI skal gennemføres i testmiljøer og med anvendelse af testdata.<br>
Krav til testmiljø fremgår af tilslutningsaftalen.
</details>

<details>
    <summary>Trin 6 - Etabler supportorganisation</summary>
Den tilsluttede part skal etablere og opretholde en bemandet supportfunktion med dertilhøren-de kontaktkanaler i form af telefonnummer og e-mailadresse, som kan anvendes til indmelding af supporthenvendelser.<br>
Krav til supportfunktionen fremgår af tilslutningsaftalen.
</details>

<details>
    <summary>Trin 7 - Etabler produktionsmiljø</summary>
I det produktion miljø som den tilsluttede part etablere skal det sikres, at meddelelser ikke går tabt i perioden fra de er modtaget og kvitteret for af Partens løsning, og indtil meddelelsen er videreformidlet til modtager, og modtageren har kvitteret for modtagelsen.<br>
Krav til produktionsmiljø fremgår af tilslutningsaftalen.
</details>

<h2>Kontakt ved spørgsmål om tilslutning</h2>

MedCom

Mail: ehmi@medcom.dk

Telefon: (+45) xxxx xxxx
