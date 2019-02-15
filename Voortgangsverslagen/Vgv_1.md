# Voortgangsverslag #1
# (Voorlopige) Titel onderwerp: Een mini bedrijf van A to Z opzetten
## Promotors
<!--Zet hier alle namen+email van je verschillende promotors (stagebegeleider,
stagementor). Zeker in vet zetten indien er veranderingen hebben
plaatsgevonden-->

#### Stagebegeleider
Serge Horsmans
serge.horsmans@ap.be

#### stagementors
Wesley Swartele
wesley.swartele@silta-ict.be

Peter De Baerdemaeker
peter.debaerdemaeker@silta-ict.be

## Onderwerp
<!--Beschrijf je onderwerp van je BAP/Stage. Wat is het resultaat dat je wilt
bereiken tegen het eind van de BAP? Maak een analyse van het
onderwerp/resultaat. Geef de mogelijke stappen om je BAP/Stage tot een goed
eind te brengen. --> 
<!--Minimum 5000 tekens-->
#### Doel
De bedoeling is om alle ICT facetten van een bedrijf te leren kennen door een fictief bedrijf op te zetten in een virtuele omgeving. Deze omgeving zal achteraf gebruikt worden om demo’s te geven bij klanten, producten te testen of situaties te simuleren. 

#### Resultaat
Een high performing en high available serveromgeving (DELL) ontwikkelen gebruik makende van Azure, Hyper-V, fileserver, printserver, domaincontroller, DNS, DHCP, Office 365, SCCM (patch management, applicaties installeren & antivirus), SQL, Citrix XenApp & Windows Server 2019. Heel de omgeving dient te worden gemonitord (OMS) + gebackupped (VEEAM) zodat proactief kan worden ingegrepen in geval van calamiteiten. Op het netwerk (CISCO) dient naast een firewall, ook een segmentering (VLAN) te worden aangebracht, waardoor verschillende type omgevingen elkaar niet direct kunnen beïnvloeden.

#### Analyse
Gegeven hardware machines: 3 servers (poweredge R420, poweredge R620, poweredge R720), 1 firewall (ASA-5510-K8), 1 L3 switch (Catalyst 3560G)\
Beschikbare geheugenkaarten: 4x 73 GB, 8x 146 GB, 3x 3TB\
Technologieën die verwerkt moeten worden: Aure, Printserver, Hyper-V, Fileserver, Domaincontroller, DNS, DHCP, Office 365, SCCM, SQL, Citrix, OMS, VEEAM

Server 1 zal dienen als domaincontroller en printserver + zal zorgen voor DHCP en DNS.\
Server 2 zal de SQL en citrix beheren.\
Server 3 zal de algemene opslag worden (fileserver).

Servers 1 en 2 gebruiken elk 2x 73 GB waar het operating systeem zal opkomen en 4x 146 GB waar de virtuele machines opgeslagen zullen worden. Deze servers gaan geconfigureerd worden als een RAID 10 (RAID 1 + 0). Deze kan snel schrijven en lezen wat noodzakelijk is voor de functionaliteiten die deze servers moeten volbrengen. Het nadeel is wel dat je de helft van de geheugencapaciteit ter beschikking hebt sinds deze gemirrored wordt, maar er is voldoende geheugen beschikbaar.

Aangezien server 3 zal dienen als fileserver en dus heel wat data moet gaan opslaan, zal deze gebruik maken van de 3 TB schijven. Deze schijven zullen in een RAID 5 komen sinds een fileserver niet snel moeten functioneren, maar wel zeker een failover nodig, zodat deze alle data nog bevat moest er een schijf kapot gaan.

Voor het opdelen van het netwerk zal er gebruik gemaakt worden van subnets (VLAN's) zodat de omgevingen elkaar niet kunnen beïnvloeden. Er zullen 8 VLAN's voorzien worden:

VLAN 510: Interconnect firewall/switch\
VLAN 520: Physieke servers\
VLAN 530: Virtuele servers\
VLAN 540: Users\
VLAN 550: Nog ter beschikking\
VLAN 560: Nog ter beschikking\
VLAN 570: Management

De physieke en virtuele servers zullen elk een eigen domein hebben voor extra beveiliging/overzicht. Zo kunnen de servers elkaar terug vinden en kan men vanaf één server de andere VM's starten of stop zetten indien nodig, wat zeker een meerwaarde is. Er zullen al een paar users aangemaakt worden in het domein die men later kan gebruiken. Ook zal er een gedeelde virtuele schijf geconfigureerd worden tussen de virtuele machines om makkelijk bestanden te kunnen doorgeven.

De virtuele machines 1 en 2 zullen met elkaar geclustered worden voor failover protectie. De fileserver kan eventueel ook geclustered worden met deze virtuele machines mits deze genoeg geheugen hebben ervoor.

#### Planning
Eerst dient te worden ingewerkt via een studiefase in het onderwerp. Het maken van een netwerk- en infrastructuur design is hierbij essentieel. In deze studiefase moet er ook worden nagedacht hoe deze functionalteiten verdeeld zullen worden over de 3 beschikbare servers. De servers worden geconfigureerd in RAID om gegevensverlies te vermijden, ook hier moet rekening mee gehouden worden.

Na de studiefase zullen de servers opgebouwd worden met het juiste geheugen, met voorkeur dat de servers ongeveer evenveel geheugen hebben mits ze geclusterd worden. Wanneer deze zijn opgebouwd zal het netwerk gedeelte opgebouwd en geconfigureerd worden, extra redundancy is een must. Na het physieke netwerk aan te sluiten zal de remote access in orde gebracht worden zodat er vanop aftstand verbinding gemaakt kan worden met de servers om deze verder te configureren. 

Als volgende stap naar een flexibele en snelle implementatie wordt gevraagd een virtuele serveromgeving te ontwikkelen gebruik makende van Azure, Hyper-V, fileserver, printserver, domaincontroller, DNS, DHCP & Office 365. Vervolgens komen patch management, applicaties installeren & antivirus, SQL, Citrix XenApp.

Tot slot kan er worden nagedacht over beveiliging, wie heeft toegang tot welke functionaliteiten. De beveiliging van het netwerk zal vooral beheerd worden door de firewall door middel van access control lists om bepaalde poorten of IP-adressen door te laten.

Er is nog een extra opdracht voorzien mocht de opdracht klaar geraken voor het einde van de stage. Deze opdracht is een secure wireless omgeving op te starten gebruik makend van CA/NPS. Hiervoor wordt er een access point voorzien die ik mee in hetwerk zou kunnen integregen.

## Keywords
<!--Noteer hier enkele relevante keywords van het onderwerp-->
<!--Minimum 5 keywords-->
DELL\
RAID\
Azure\
Hyper-V\
Citrix\
Domaincontroller\
SCCM\
SQL\
VEEAM

## Milestones
<!--Geef hier kort weer wat te behalen milestones zijn per week-->
week 1: gedetailleerd netwerk design\
week 2: gedetailleerd infrastructuur design\
week 3: Netwerk opstelling + configuratie\
week 4: Servers configureren (RAID, OS, Remote access)\
week 5: VM's op de servers installeren\
week 6: VM's clusteren voor failover\
week 7: Domaincontroller, DNS (VM1)\
week 8: DHCP, printserver (VM1)\
week 9: Citrix, SQL (VM2)\
week 9: Citrix, SQL (VM2)\
week 10: Fileserver (VM3)\
week 11: Backup (VEEAM)\
week 12: monitoring\
week 13-15: afwerking project
