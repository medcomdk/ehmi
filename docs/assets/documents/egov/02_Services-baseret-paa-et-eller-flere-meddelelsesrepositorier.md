# Services baseret på et eller flere meddelelsesrepositorie(r)

## 7.2.1 Niveauer

Deling af meddelelser på sundhedsområdet hører naturligt hjemme under sundhedsdomænet og dermed overordnet set under sundhedsdomænets governance, jf. princip PF3. Forsendelsesstatus
af meddelelser er af så generel karakter, at det egentlig godt kunne høre hjemme under eDelivery netværket, men det er blevet vurderet, at behovet for forsendelsesstatus fra andre
domæner end sundhedsdomænet ikke er stort, så dette kommer også i første omgang til overordnet at høre under sundhedsdomænets governance – hvor det så skal sikres, at det implementeres på en tilpas generisk måde, der vil gøre en eventuel senere generalisering til eDelivery netværk niveauet mulig.

Eftersom access-punkterne spiller en central rolle i opsamlingen af både meddelelser og forsendelsesstatus, så er disse et andet logisk governance niveau. Efter opsamlingen af meddelelserne og forsendelsesstatus gemmes disse i repositorier, hvorfra anvendersystemer henter dem via services, så på denne måde kommer vi frem til følgende fire governance niveauer i forhold til deling og forsendelsesstatus:

- eDelivery sundhedsdomæne
- Access-punkt (C2/C3)
- Repositorie/Service
- Anvendersystem

I forhold til niveauerne for punkt til punkt meddelelseskommunikation er sundhedsdomænet nu det overordnede niveau og det operationelle koblingspunkt er access-punkterne (C2/C3).
Tilsvarende punkt til punkt kommunikation, hvor access-punkter indgik aftaler med både eDelivery netværket og sundhedsdomænet, så indgår repositorie/service her aftaler med både
sundhedsdomænet og access-punktet. 

Specielt i forhold til Repositorie/Service niveauet, så kommer de to typer services til at blive udstillet og afviklet på (ikke her nærmere angivne) platforme, og ligeledes for repositorierne for meddelelser og forsendelsesstatus. Disse platforme kan have sine egne skærpede governance krav og processer i forhold til de generelle på sundhedsområdet, og disse skal i givet fald naturligvis også efterfølges.

Derudover spiller distributionen af repositorier for meddelelser ind i forhold til hvilke databehandlingsaftaler, der skal indgås imellem hvem, i det der aftalemæssigt er forskel på om alle meddelelser fra alle afsendere opsamles i et centralt repositorie eller om meddelelser fra en samling afsendere opsamles i et decentralt repositorie tæt på dem selv eller en kombination af begge modeller anvendes.

## 7.2.2 Fora

Da deling af meddelelser og forsendelsesstatus på sundhedsområdet hører så tæt sammen med punkt til punkt meddelelseskommunikationen som det gør, bør de samme governance fora forankret på sundhedsdomæne niveau anvendes, dvs. den samme forretningsstyregruppe, den samme faglige referencegruppe, og det samme brugerforum.

## 7.2.3 Temaer

De relevante governance temaer er bortset fra EU temaet under gruppen strategi og udvikling de samme som for punkt til punkt meddelelseskommunikation. I det hele taget er den overordnede ansvarsdiskussion for temaerne niveauerne imellem meget lig den for punkt til punkt meddelelseskommunikationen. 

F.eks. ligger ansvaret for temaerne i gruppen strategi og udvikling på sundhedsdomæne niveau og de øvrige niveauer er deltagere, og for de klassiske ITIL temaer
under systemforvaltning gruppen er det enkelte niveau hver især ansvarlig for det, der logisk hører hjemme på niveauet.

## 7.2.4 Processer

De relevante governance processer er ligeledes langt hen ad vejen analoge til de listede ovenfor for punkt til punkt meddelelseskommunikation, hvorfor udvalgte kun listes ganske kort:
Tilslutning: Dette foregår mellem flere niveauer. Der er tilslutning af et anvendersystem til en repositoriebaseret service, tilslutning mellem repositorie og access-punkt, tilslutning af repositorie til sundhedsdomænet, og tilslutning af access-punkt til sundhedsdomænet.

Disse tilslutninger styres af tilsvarende aftaler, som beskrevet i følgende afsnit 7.2.5 ”De klassiske ITIL inspirerede processer” om incident, problem, og change håndtering: På
de enkelte niveauer håndteres de komponenter, hvis ansvar ligger på det pågældende niveau. 

Derudover er man ansvarlig for at holde de interessenter på andre niveauer, der er afhængige af den pågældende komponent, orienteret.

SLA: Monitorering, opfølgning, og afrapportering i forhold til SLA eksisterer også på flere niveauer. Hvor detaljeret der skal monitoreres og hvor ofte, der skal følges op og afrapporteres er igen en del af de tilslutningsaftaler, der indgås på det givne niveau.

## 7.2.5 Aftaler

Aftalestrukturen i forhold til deling af meddelelser og forsendelsesstatus kan illustreres ved:

<p/>
![
Figur 23: Governance aftaler imellem de forskellige niveauer for deling af meddelelser og forsendelsesstatus](/ehmi/assets/images/MB_Figur-23-Governance-aftaler-imellem-de-forskellige-niveauer-for-deling-af-meddelelser-og-forsendelsesstatus.png)

Figur 23: Governance aftaler imellem de forskellige niveauer for deling af meddelelser og forsendelsesstatus.

Da deling af meddelelser og forsendelsesstatus på sundhedsområdet er en integreret del af meddelelseskommunikation på sundhedsområdet og hører tæt sammen med punkt til punkt
meddelelseskommunikationen i dette målbillede, og der allerede i forbindelse med punkt til punkt meddelelseskommunikationen via eDelivery er blevet identificeret en domænetilslutningsaftale imellem sundhedsdomænet og access-punktet, er tilslutningsaftalen for accesspunkt i Figur 23 en del af denne domænetilslutningsaftale fremfor en selvstående aftale. I det følgende er det derfor kun det relateret til opsamling af meddelelser/forsendelsesstatus i denne tilslutningsaftale, der omtales. Tilslutningsaftalen for anvendersystemet vil være meget lig tilsvarende aftaler for anvendersystemer af andre nationale services på sundhedsområdet.

**Indholdet af de fire tilslutningsaftaler på hovedoverskriftniveau er som følger:**


<table style="border:1px solid black">
<thead style="border:1px solid black">
<tr class="header" style="border:1px solid black align:top">
    <th style="border:1px solid black">>Aftale</th>
    <th style="border:1px solid black">>Beskrivelse</th>
</tr>
</thead>
<tbody style="border:1px solid black align:top">
<tr class="odd" style="border:1px solid black">
    <td style="border:1px solid black align:top">
    Tilslutningsaftale for access-punkt
    </td>
    <td style="border:1px solid black">
        <ul>
        <li>
        Krav om opsamling af meddelelse til repositorie og sikkerhedsmæssige aspekter hertil
        </li>
        <li>
        krav om opsamling af forsendelsesstatus til repositorie og sikkerhedsmæssige aspekter hertil
        </li>
        </ul>
    </td>
</tr>
<tr class="even" style="border:1px solid black">
    <td style="border:1px solid black">
    Domænetilslutningsaftale for repositorie/service
    </td>
    <td style="border:1px solid black">
        <ul>
        <li>
        Supportfunktion (kontaktdata, åbningstid, responstid,
        etc.)
        </li>
        <li>
        SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid, servicevinduer, transaktionsmængder)
        </li>
        <li>
        miljøer
        </li>
        <li>
        varslingsfrister for ændringer
        </li>
        <li>
        krav om passus om konstruktivt supportsamarbejde imellem access-punkt og repositorie når nødvendigt
        </li>
        <li>
        krav om passus om kommunikationsprotokol og sikkerhed i forhold til kommunikation imellem repositorie
        og access-punkt 
        </li>
        <li>
        krav om passus om tilslutningsaftale for anvendersystem til service
        </li>
        </ul>
    </td>
</tr>
<tr class="odd" style="border:1px solid black">
    <td style="border:1px solid black">
    Access-punkttilslutningsaftale for repositorie/service
    </td>
    <td style="border:1px solid black">
        <ul>
        <li>
        Supportfunktion (kontaktdata, åbningstid, responstid, etc.)
        </li>
        <li>
        SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid, servicevinduer, transaktionsmængder)
        </li>
        <li>
        miljøer
        </li>
        <li>
        varslingsfrister for ændringer
        </li>
        <li>
        konstruktivt supportsamarbejde imellem accesspunkt og repositorie når nødvendigt
        </li>
        <li>
        protokol for kommunikation af opsamlede data imellem access-punkt og repositorie
        </li>
        <li>
        sikkerhedsmæssige aspekter (kryptering og autentifikation) ved kommunikationen imellem accesspunkt og repositorie
        </li>
        </ul>
    </td>
</tr>
<tr class="even" style="border:1px solid black">
    <td style="border:1px solid black">
    Tilslutningsaftale for anvendersystem
    </td>
    <td style="border:1px solid black">
        <ul>
        <li>
        Supportfunktion (kontaktdata, åbningstid, responstid, etc.)
        </li>
        <li>
        SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid, servicevinduer, transaktionsmængder)
        </li>
        <li>
        miljøer
        </li>
        <li>
        varslingsfrister for ændringer
        </li>
        <li>
        brugeradministration i anvendersystem
        </li>
        <li>
        håndtering af de hentede data herunder personhenførbare data
        </li>
        </ul>
    </td>
</tr>
</tbody>
</table>
