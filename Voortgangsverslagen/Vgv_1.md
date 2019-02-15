# Voortgangsverslag #1
# (Voorlopige) Titel onderwerp: Een mini bedrijf van A to Z opzetten
## Promotors
<!--Zet hier alle namen+email van je verschillende promotors (stagebegeleider,
stagementor). Zeker in vet zetten indien er veranderingen hebben
plaatsgevonden-->

#### Stagebegeleider
Serge Horsmans
Serge.horsmans@ap.be

#### stagementors
Wesley Swartele
Wesley.Swartele@silta-ict.be

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
Gegeven hardware: 3 servers, 1 firewall, 1 L3 switch\
Technologieën die verwerkt moeten worden: Aure, Printserver, Hyper-V, Fileserver, Domaincontroller, DNS, DHCP, Office 365, SCCM, SQL, Citrix, OMS, VEEAM

#### Planning
Eerst dient te worden ingewerkt via een studiefase in het onderwerp. Het maken van een netwerk- en infrastructuur design is hierbij essentieel. In deze studiefase moet er ook worden nagedacht hoe deze functionalteiten verdeeld zullen worden over de 3 beschikbare servers. De servers worden geconfigureerd in RAID om gegevensverlies te vermijden, ook hier moet rekening mee gehouden worden.

Na de studiefase zullen de servers opgebouwd worden met het juiste geheugen, met voorkeur dat de servers ongeveer evenveel geheugen hebben mits ze geclusterd worden. Wanneer deze zijn opgebouwd zal het netwerk gedeelte opgebouwd worden.

Als volgende stap naar een flexibele en snelle implementatie wordt gevraagd een virtuele serveromgeving te ontwikkelen gebruik makende van Azure, Hyper-V, fileserver, printserver, domaincontroller, DNS, DHCP & Office 365. Vervolgens komen patch management, applicaties installeren & antivirus, SQL, Citrix XenApp.

Tot slot kan er worden nagedacht over beveiliging, wie heeft toegang tot welke functionaliteiten.


## Keywords
<!--Noteer hier enkele relevante keywords van het onderwerp-->
<!--Minimum 5 keywords-->
DELL\
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
