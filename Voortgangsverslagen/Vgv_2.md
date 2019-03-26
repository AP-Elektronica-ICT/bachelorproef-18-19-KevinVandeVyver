# Voortgangsverslag #2
# (Voorlopige) Titel onderwerp: Bedrijf van A tot Z
## Promotors
<!--Zet hier alle namen+email van je verschillende promotors (stagebegeleider, stagementor). Zeker in vet zetten indien er veranderingen hebben plaatsgevonden-->
### Stagebegeleider
Serge Horsmans
serge.horsmans@ap.be

### Stagementors
Wesley Swartele
wesley.swartele@silta-ict.be

Peter De Baerdemaeker
peter.debaerdemaeker@silta-ict.be

## Abstract
<!--Het abstract is een samenvatting van je totale bachelorproef, inclusief reeds gekende resultaten-->
Een high performing en high available serveromgeving (DELL) ontwikkelen gebruik makende van Azure, Hyper-V, fileserver, printserver, domaincontroller, DNS, DHCP, Office 365, SCCM (patch management, applicaties installeren & antivirus), SQL, Citrix XenApp & Windows Server 2019. Heel de omgeving dient te worden gemonitord (OMS) + gebackupped (VEEAM) zodat snel kan worden ingegrepen in geval van noodgevallen. Op het netwerk (CISCO) dient naast een firewall, ook een segmentering (VLAN) te worden aangebracht, waardoor verschillende type omgevingen elkaar niet direct kunnen beïnvloeden.

## Technische omschrijving
<!--Technische omschrijving van de evolutie van het project tijdens de betrokken periode, met aanduiding van de reeds bekomen resultaten en een planning voor de verdere uitwerking, welke problemen zijn ondervonden en hun oplossingen:-->
<!--Minimum 750 woorden-->
### Evolutie/resultaten

Om het project te starten, werd eerst een onderzoek verricht naar de vereiste technologieën. Eens hier een duidelijk beeld van was, kon het infrastructuur design worden opgesteld om de technologieën op te splitsen over de beschikbare servers. Belangrijk hierbij was het geheugen van de harde schijven en de RAID configuratie, omdat de toepassingen in een cluster (groep) komen voor redundantie. Nadat alle opties overwogen waren met elkaar, konden de servers opgebouwd worden. Om een goede balans te creëren, worden er 2 servers gebruikt in RAID 10 voor de VM’s en de 3e server is configureerd met een RAID 5 voor de back-ups en replicaties. Eens de servers waren opgebouwd, werd de remote connection (iDRAC) in orde gebracht zodat er vanop afstand (via webbrowser) aan de servers gewerkt kan worden. Om effectief aan de webbrowser te geraken moet ook het netwerk in orde gebracht worden. Het netwerk opstellen was dan ook de volgende stap.

Met het uitwerken van het netwerk design moest er rekening mee gehouden worden dat de omgeving high available is en dat er eventuele uitbreidingen mogelijk zijn. Nadat het design was opgesteld, kon de hardware worden geconfigureerd. In de omgeving wordt er gebruik gemaakt van een firewall, een layer 3 switch en 3 servers met daarop hun virtuele switches. Deze firewall bracht wel wat complicaties met zich mee doordat dit een nieuw gegeven was. Met het nodige onderzoek hoe deze precies geconfigureerd moest worden, kwam het netwerk op gang. Om het netwerk te testen, werden er pings uitgevoerd naar alle hardware apparaten. Eens alle pings erdoor geraakten en de redundantie toegepast was, konden de VM’s geïnstalleerd worden op de servers.

Als eerste werd het domein opgesteld, zodat er makkelijke toegang is tot alle servers en VM’s in het domein. De volgende stap was internet toegang verkrijgen op de servers en VM’s. Dit werd opgelost door gebruik te maken van DNS. Hiervoor moest het adres van een publieke DNS server, 8.8.8.8 (google) werd in de omgeving toegepast, geforward worden. Eens deze instelling geconfigureerd was, konden de servers en VM’s op het internet.

De volgende virtuele machine die geconfigureerd werd, was de printserver. De reden waarom deze VM als 2e geconfigureerd werd, was om het domein en netwerk te testen. Eens het operating systeem geïnstalleerd was, kon de VM toegevoegd worden aan het domein om zo te weten te komen of deze toegang tot het internet kreeg. Zo ja, dan is de eerste virtuele machine juist geconfigureerd en werkt het netwerk zoals gehoord. Na het herstarten van de VM kreeg de machine toegang tot het internet en kon de printer toegevoegd worden aan het netwerk. Aangezien het een demo-omgeving is en er geen extra printer ter beschikking was, werd er een demo printer ingesteld. Dit kon men bekomen door een driver te downloaden op het internet en deze toe te voegen aan de printer drivers.

De volgende stap was een fileserver aanmaken, omdat dit het werk vergemakkelijkt wegens het kopiëren en plakken van het operating systeem van server naar server. In de demo-omgeving is er gebruik gemaakt van DFS replicatie, wat overeenkomt met een gedeelde map voor heel het domein. Deze kan men echter ook limiteren tot bepaalde gebruikers om extra beveiliging toe te voegen aan de infrastructuur.

Eenmaal de fileserver up en running was, werd het tijd om de citrix te installeren. Deze applicatie moet op 4 verschillende VM’s draaien om high available te kunnen zijn en was dus heel wat makkelijker op te zetten nadat de ISO van de applicatie op het netwerk stond.  Met behulp van citrix kan men applicaties en/of desktops publishen voor domeingebruikers.

Het laatste onderdeel dat geconfigureerd was tijdens de periode, was de back-up server. Deze maakt gebruik van VEEAM om elke dag een incrementele back-up te maken van de VM’s en weekelijks een volledige back-up. Zeer handig moest er iets fout gaan in de demo-omgeving om terug te vallen op een werkende versie.

### Planning

* DMZ zone opstarten voor extra beveiliging
* firewall/netwerk beveiliging verbeteren.
* Voor verdere toepassingen wordt er nog besproken.

### Problemen

Op basis van netwerking zijn er wat complicaties geweest in verband met de firewall configuratie sinds ik hier niet zo bekend mee ben. Vaak lag het probleem bij poorten die niet open stonden, maar wel gebruikt werden of routes toevoegen als er een subnet wordt gebruikt. Na wat opzoekwerk over de gegeven erros, was dit meestal wel opgelost.

Citrix was veruit de moeilijkste configuratie tot nu toe. De ene keer kon ik met de citrix server connecteren, maar had ik geen apps. De andere keer had ik de apps wel, maar kon ze niet openen. Om dit in orde te krijgen, heb ik enorm veel moeten opzoeken wat niet zo evident was sinds er heel veel informatie over te vinden is. Specifiek zoeken naar wat het probleem juist is terwijl de erros niet echt duidelijk zijn, maakte het wel lastig.

Hyper-V (virtual machine manager) met GPT partition was ook een probleem, maar lag eerder aan de versie van windows server 2019. Voor een bepaalde update zat de server vast in een loop van herstarten, omdat Hyper-V niet wou werken op EUFI boot mode. Dit is met een latere versie van windows server 2019 opgelost.


### Realisaties 
<!--Kort oplijsting gedane werk zowel onderzoek, analyse als realisaties.-->
Opzoekwerk naar alle technologieën die verwerkt moeten worden\
Uitwerking netwerk- en infrastructuur design\
Implementeren van de verschillende technologieën

Tot nu toe geïmplementeerde toepassingen:
* VLAN segmentering
* Fileserver
* Printserver
* Domaincontroller
* DNS
* Citrix
* VEEAM


### Huidige werkpunten
<!--Beschrijven wat de huide focus punten zodat er progressie is in de BAP/Stage-->
Debugging\
Best practices\
Testing

### Toekomst
<!--Mogelijk richting naar waar de BAP/Stage kan evolueren in de toekomst-->
Het project is heel omvangrijk, er is zowel de mogelijkheid om diepgaand te werken met bepaalde technologieën als heel veel technologieën te gebruiken, maar dan niet zo gedatailleerd.
## Extra informatie
### Bijscholingen
<!--Bijgewoonde seminaries, presentaties, workshops, bedrijfsbezoeken etc in deze periode (onderwerp, datum, korte samenvatting en beoordeling)-->

### Nieuwe contacten
<!--Nieuwe contacten gemaakt in deze periode (naam, voornaam, e-mail, telefoonnummer, bedrijf, functie, relevantie voor het werk)-->

### Literatuur
<!--Nieuwe contacten gemaakt in deze periode (naam, voornaam, e-mail, telefoonnummer, bedrijf, functie, relevantie voor het onderzoek)-->
