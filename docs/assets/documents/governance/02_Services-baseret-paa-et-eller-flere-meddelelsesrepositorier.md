# Services baseret på et eller flere meddelelsesrepositorie(r)

7.2.1 Niveauer
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