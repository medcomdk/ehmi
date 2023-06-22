# 7.1 Punkt til punkt kommunikation med eDelivery

## 7.1.1 Niveauer

Med udgangspunkt i hvordan meddelelseskommunikation i eDelivery fungerer, som beskrevet i MB afsnit 5.2, samt den allerede eksisterende og snarligt kommende anvendelse af eDelivery i Danmark (henholdsvis e-handel og næste generation af offentlig digital post), og i overensstemmelse med principperne PF3 og PF6, der omhandler fælles transparent national governance med centrale forankringspunkter og lokalt ansvar for det, som logisk hører til lokalt, og dermed en tydelig ansvarsfordeling, er fire forskellige ansvarsområder identificeret, hvorpå governance skal håndteres:

- eDelivery netværk (fællesoffentligt på tværs af domæner)
- eDelivery sundhedsdomæne
- Access-punkt (C2/C3)
- System (C1/C4 i bred forstand)

Disse ansvarsområder vil igennem hele dette governance afsnit blive omtalt som niveauer, og de er helt centrale omdrejningspunkter for diskussionen i resten af dette afsnit.

Et målbillede på sundhedsområdet (et domæne) kan selvfølgelig ikke bestemme, hvordan governance på det fællesoffentlige niveau på tværs af domænerne skal være, men dette afsnit
beskriver de forslag, der var enighed om i målbillede-workshoparbejdet, hvor der også deltog repræsentanter for det fællesoffentlige niveau. I det kommende arkitektur- og implementeringsarbejde og produktionspilotprojektet, skal det afklares, hvor meget af det foreslåede for eDelivery netværk niveauet, som skal realiseres på det niveau. Såfremt det bliver mindre end det foreslåede, vil noget af det, der ellers var tiltænkt eDelivery netværk niveauet, skulle varetages af eDelivery sundhedsdomæne niveauet. For et stort domæne, som sundhedsdomænet, vil dette godt kunne løftes, og i en vis forstand giver det også lidt større frihedsgrader for domænet.

## 7.1.2 Fora

Der er flere forskellige fora i forhold til governance:

Forum Beskrivelse
Forretningsstyregruppe En sådan bør eksistere både på eDelivery netværk niveauet og på
domæneniveau (i vores tilfælde sundhedsdomænet).
Forretningsstyregruppen på et givet niveau er det øverste beslutningsorgan
på dette niveau i forhold til funktionalitet, anvendelse,
og økonomi, og det ejer strategien for det pågældende niveau,
og agerer derfor også strategiforum.
Deltagerne på sundhedsdomæne niveau er repræsentanter for
parterne på sundhedsområdet, der anvender meddelelseskommunikation.
Faglig referencegruppe En sådan bør ligeledes eksistere både på eDelivery netværk niveauet
og på domæneniveau, og på sundhedsdomæne niveau er
deltagerne igen repræsentanter for parterne på sundhedsområdet,
som anvender meddelelseskommunikation.
Den faglige referencegruppe på et givet niveau har til opgave at
fagligt kvalitetssikre og teknisk vurdere vedligeholdelses- og udviklingstiltag
for meddelelseskommunikation via eDelivery på det
givne niveau.
Brugerforum 

Der findes dels et EU brugerforum, hvori der bør være deltagere fra både eDelivery netværk niveauet og sundhedsdomæne niveauet.
Endvidere bør der være et brugerforum på sundhedsdomæne niveau, hvor der er deltagere fra både access-punktleverandører (C2/C3) og systembrugere (C1/C4), hvor emner og problemstillinger som brugerne finder vigtige skal diskuteres.

Hvorvidt et tilsvarende brugerforum skal etableres på eDelivery netværk niveauet er ikke op til dette sundhedsdomæne målbillede at afgøre.

Disse fora er vigtige, da det er her, repræsentanter for de enkelte parter, der anvender meddelelseskommunikation bliver sat om samme bord for at diskutere og videreudvikle forskellige aspekter ved meddelelseskommunikationen, og det således er her, at de enkelte parter har mulighed for at præge udviklingen af meddelelseskommunikation på sundhedsområdet. 

Præcis hvordan sammensætningen af disse fora skal være og hvilke sammenhænge, der skal være mellem dem og de allerede eksisterende governance fora, skal besluttes i forbindelse med det videre implementeringsarbejde og produktionspilotprojektet.

## 7.1.3 Temaer

Der er mange temaer under governance som tydeligt illustreret i følgende figur, der stammer fra [EDELDIGSTANRAP]:


## 7.1.5 Aftaler

Aftaler er et helt centralt begreb i forhold til governance og taget i betragtning af, hvordan meddelelseskommunikation i eDelivery er, er de fleste af de centrale tilslutningsaftaler desangående
imellem to på hinanden følgende niveauer. Dvs. imellem eDelivery netværket og sundhedsdomænet, imellem sundhedsdomænet og access-punktet (C2/C3), og endelig imellem accesspunktet og systemet (C1/C4 i bred forstand). Den eneste undtagelse for dette er, at der også eksisterer en aftale imellem eDelivery netværket og access-punktet, som illustreret ved følgende figur:

![Figur 22: Governance aftaler imellem de forskellige niveauer for punkt til punkt meddelelseskommunikation.](/ehmi/assets/images/MB_Figur-22-Governance-aftaler-imellem-de-forskellige-niveauer-for-punkt-til-punkt-meddelelseskommunikation.png)
Figur 22: Governance aftaler imellem de forskellige niveauer for punkt til punkt meddelelseskommunikation.

Bemærk at i figuren anvendes det generelle begreb eDelivery domæne, velvidende at i vores kontekst er det sundhedsdomænet, der er tale om.

At der er to tilslutningsaftaler for access-punktet (til henholdsvis netværket og domænet) skyldes, at der dels er nogle krav fra eDelivery netværket, f.eks. anvendelse af SMP, og dels er nogle krav fra sundhedsdomænet, f.eks. skærpede krav til tilgængelighed, overvågning og kvitteringer.

Da der er meget store forskelle i størrelsen af de organisationer, der ejer et system (alt fra en hel region til en enkelt lægepraksis), er det vigtigt, at tilslutningsaftalen for et system, jf. princip PF5, tager højde for dette og ikke reelt umuliggør tilslutning af systemer fra de mindre organisationer.

Nogle dele af en aftale vedrører alene de to niveauer aftalen er indgået mellem, som f.eks. i domænetilslutningsaftalen for et access-punkt hvor det skal angives at et access-punkt med aftalte mellemrum skal udføre sikkerhedsaudits og afrapportere resultatet af disse audits til rette instans på sundhedsdomæne niveauet. Andre dele kan være krav til det nederste niveau i aftalen om at stille krav til det næstfølgende niveau, som f.eks. at der i tilslutningsaftalen for et access-punkt stilles krav om, at der i tilslutningsaftalen for et system skal stå, at systemets supportfunktion skal arbejde konstruktivt sammen med access-punktets supportfunktion, når udfordringer skal løses.

Der kan også være overordnede krav, der gør sig gældende på alle niveauer, som f.eks. at der på et givet niveau skal eksistere en supportfunktion med en nærmere specificeret minimumsåbningstid for henvendelser. Disse overordnede krav kan med fordel formuleres som politikker, så man i tilslutningsaftalerne kan skrive at den pågældende politik skal overholdes/implementeres – på denne måde behøver man ikke gentage den samme lange tekst i alle aftalerne, og såfremt der kommer ændringer skal man kun ændre et sted (nemlig i politikken) fremfor i samtlige aftaler.

Hovedoverskrifterne for de fire tilslutningsaftaler er som følger, hvor dog specielt netværkstilslutningsaftalen for access-punktet kun er indikativ, da indholdet af dette ikke er noget et målbillede på sundhedsområdet kan diktere:

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


Aftale Beskrivelse
Tilslutningsaftale for domæne Vedligehold af meddelelsestyper inden for domæne
vedligehold af standarder for meddelelser inden for
domæne
supportfunktion (kontaktdata, åbningstid, responstid,
etc.)
SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid,
servicevinduer, transaktionsmængder)
miljøer
varslingsfrister for ændringer
eksistens af domænestartpakke
domænekrav over for access-punkter formuleret
(SLA, sikkerhed, supportfunktion, etc.)
Netværkstilslutningsaftale for
access-punkt
Supportfunktion (kontaktdata, åbningstid, responstid,
etc.)
SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid,
servicevinduer, transaktionsmængder)
miljøer
varslingsfrister for ændringer
basale eDelivery meddelelseskommunikationskrav
basale eDelivery sikkerhedskrav
konstruktivt supportsamarbejde imellem accesspunkter
når nødvendigt
krav om passus angående konstruktivt supportsamarbejde
imellem access-punkt og system når nødvendigt
indgår i tilslutningsaftale for system
Domænetilslutningsaftale for
access-punkt
Domænespecifikke krav til supportfunktion (kontaktdata,
åbningstid, responstid, etc.)
krav om passus angående supporterede meddelelsestyper
indgår i tilslutningsaftale for system
domænespecifikke krav til miljøer
varslingsfrister for ændringer
pålidelig meddelelseskommunikation
supplerende domænespecifikke krav til sikkerhed og
performance
sikkerhedsaudit
SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid,
servicevinduer, transaktionsmængder)

Til gengæld introducerer det også større omkostninger og risiko, der skal mitigeres, for domænet, og det er derfor en vigtig afklaring.

Tilslutningsaftale for system Supportfunktion (kontaktdata, åbningstid, responstid,
etc.)
konstruktivt supportsamarbejde imellem accesspunkt
og system når nødvendigt
SLA (svartider, oppetid, driftstid (f.eks. 24/7), reetableringstid,
servicevinduer, transaktionsmængder)
supporterede meddelelsestyper
miljøer
varslingsfrister for ændringer
sikkerhedsmæssige aspekter (kryptering og autentifikation)
ved kommunikationen imellem access-punkt
og system
håndtering af opsamling af forsendelsesstatus for
meddelelser i system
Det er vigtigt at understrege, at de indgåede aftaler naturligvis er forpligtende, og at der fra de
overordnede niveauers side følges løbende op på deres overholdelse, f.eks. jf. SLA-processen i
afsnit ## 7.1.4., i overensstemmelse med dele af diskussionen i afsnit 2.4.

## 7.1.6 Afprøvningsdomæner

Ud over selve sundhedsdomænet som er blevet omtalt indtil nu, vil det også kunne være relevant parallelt hermed at have et sundhedsafprøvningsdomæne. De ansvarlige instanser for afprøvningsdomænet er de samme som for selve det rigtige ”sundhedsproduktionsdomæne”, og afprøvningsdomænet er, naturligvis, også underlagt eDelivery netværket og de krav, som følger
heraf. Men da det, som navnet indikerer, er tænkt som et domæne, hvor et begrænset antal udvalgte anvendere kan prøve ting af, f.eks. en ny meddelelsestype, er der ikke behov for at
have alle de yderligere skærpede krav, som sundhedsdomænet stiller til access-punkterne i sit rigtige produktionsdomæne. På den måde vil man have mulighed for at prøve forskellige ting af i et produktionslignende set-up, og for succesfuldt afprøvede features, som nye meddelelsestyper, vil det efterfølgende være nemmere at etablere det tilsvarende feature i det rigtige sundhedsproduktionsdomæne, end hvis man ikke havde afprøvningsdomænet.
Dette kan betragtes som et eksempel på, at governance for meddelelseskommunikation på sundhedsområdet ikke alene handler om kontrol og forvaltning,