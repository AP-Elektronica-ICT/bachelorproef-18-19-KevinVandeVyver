# Opdrachtomschrijving

[Een mini bedrijf van A to Z opzetten]

# Bachelor Elektronica-ICT
academiejaar 2017-2018\
jaar 3 semester 1-2

 # Voornaam Naam
Kevin Van de Vyver
 
## Opdrachtomschrijving

### 1	Opdrachtgever
Ferranti (Silta)\
Adres: Romeynsweel 7\
Telefoon: +32 3 540 49 11\
Contactpersoon : Kim Lucas

### 2	Samenvatting
Bedoeling is om alle ICT facetten van een bedrijf te leren kennen door een fictief bedrijf op te zetten in een virtuele omgeving. Deze omgeving zal achteraf gebruikt worden om demo’s te geven bij klanten, producten te testen of situaties te simuleren. 

### 3	Situatie As-Is
De opdracht begint van scratch, er moet een nieuwe physieke en virtuele netwerkomgeving opgebouwd  worden.

### 4	Situatie To-Be
Projectdefinitie

#### 4.1	DoelstellingDe opdracht begint van scratch, er moet een nieuwe physieke en virtuele netwerkomgeving opgebouwd  worden.
Een high performing en high available serveromgeving (DELL) ontwikkelen gebruik makende van Azure, Hyper-V, fileserver, printserver, domaincontroller, DNS, DHCP, Office 365, SCCM (patch management, applicaties installeren & antivirus), SQL, Citrix XenApp & Windows Server 2019. Heel de omgeving dient te worden gemonitord (OMS) + gebackupped (VEEAM) zodat proactief kan worden ingegrepen in geval van calamiteiten. Op het netwerk (CISCO) dient naast een firewall, ook een segmentering (VLAN) te worden aangebracht, waardoor verschillende type omgevingen elkaar niet direct kunnen beïnvloeden.

#### 4.2	Scope
•	Azure: een cloud computing-platform van Microsoft waarmee een aantal internetdiensten aangeboden kan worden via het internet of binnen de omgeving van het eigen bedrijf. Microsoft wil hiermee de concurrentie aangaan met andere cloudsystemen die software as a service (SaaS) aanbieden, zoals Google App Engine van Google en EC2 van Amazon. Deze software hoeft niet geïnstalleerd te worden op de computer van de gebruiker, alles gebeurt via het web. Ook toegang tot bestanden en mappen gebeurt via het web. Het Azure Services Platform gebruikt een aangepast besturingssysteem Microsoft Azure om een cluster van servers te beheren die in het datacenter van Microsoft staan.
•	Printserver : een computer of router met één of meer aangekoppelde printers die d.m.v. een netwerk te bereiken zijn
•	Microsoft Hyper-V, met codenaam Viridian en voorheen bekend als Windows Server-virtualisatie, is een native hypervisor. Het kan virtuele machines maken op x86-64-systemen met Windows. Begonnen met Windows 8, vervangde Hyper-V Windows Virtual PC als onderdeel van hardwarevirtualisatie van de clientedities van Windows NT. Een servercomputer waarop Hyper-V wordt uitgevoerd, kan worden geconfigureerd om afzonderlijke virtuele machines aan een of meer netwerken bloot te stellen.
•	Fileserver: een bestandsserver dient ervoor te zorgen dat bestanden volledig en zonder een enkele fout worden overgebracht naar de client
•	Domaincontroller : 
Een domeincontroller is een server in een computernetwerk van Microsoft Windows die centraal beheert wie er toegang tot welke stukken van het domein mag hebben. Dit in tegenstelling tot het werkgroep-model, waarbij gebruikers en toegang op iedere individuele computer ingesteld moeten worden.
Met de komst van Windows Server 2000 en Active Directory is er hiërarchische structuur in de domeinen mogelijk geworden waarmee meerdere domeinen in een boomstructuur ("tree") georganiseerd kunnen worden, en meerdere "trees" in een "forest". Voor grotere organisaties met meerdere vestigingen biedt dit een grotere flexibiliteit.
•	DNS: Het Domain Name System (DNS) is het systeem en netwerkprotocol dat op het Internet gebruikt wordt om namen van computers naar numerieke adressen (IP-adressen) te vertalen en omgekeerd
•	DHCP: Dynamic Host Configuration Protocol (DHCP) is een computerprotocol dat beschrijft hoe een computer dynamisch zijn netwerkinstelling van een DHCP-server kan verkrijgen
•	Office 365: is een verzameling van internet-diensten, bedoeld voor bedrijven, thuisgebruik en het onderwijs. Deze internetdiensten worden deels aangeboden als online diensten, deels als applicaties op desktop-pc, tablet en telefoon en als combinatie van beide. De applicaties op desktop / pc is vergelijkbaar met het kantoorpakket Microsoft Office met het verschil dat men via Office 365 altijd de beschikking heeft over de meest recente versie.
•	SCCM: een onderdeel van de Microsoft System Center Suite en staat in voor het beheer & inventarisatie van pc's en servers
•	SQL: een gestandaardiseerde taal die gebruikt kan worden voor taken zoals het bevragen en het aanpassen van gegevens in een relationele database
•	Citrix XenApp & Windows Server 2019: een applicatie waarmee windows-applicaties kunnen worden benaderd via individuele apparaten vanaf een gedeelde server of cloud systeem
•	OMS: Operations Management Suite (Microsoft Azure)
•	VEEAM: backup software https://www.veeam.com/nl

#### 4.3	Niet in Scope
•	Alle benodigde hardware, software & licenties worden door de opdrachtgever ter beschikking gesteld.

### 5	Planning
#### 5.1	Hoofdlijnen
Eerst dient te worden ingewerkt via een studiefase in het onderwerp.
Als volgende stap naar een flexibele en snelle implementatie wordt gevraagd virtuele serveromgeving te ontwikkelen gebruik makende van Azure, Hyper-V, fileserver, printserver, domaincontroller, DNS, DHCP & Office 365.
Vervolgens komen patch management, applicaties installeren & antivirus, SQL, Citrix XenApp.
Dit is nog af te stemmen met de opdrachtgever.

#### 5.2	Toelichting fases
Fase 1: opstellen netwerk desgin en infrastructuur design
Fase 2: physieke netwerk opstelling
Fase 3: infrastructuur (servers installeren en VM's werkend krijgen)

### 6	Functioneel design
•	Dit onderdeel geeft een volledig overzicht van alle features van  de opdracht voorzien van de noodzakelijke uitleg
•	Azure: een cloud computing-platform van Microsoft waarmee een aantal internetdiensten aangeboden kan worden via het internet of binnen de omgeving van het eigen bedrijf. Microsoft wil hiermee de concurrentie aangaan met andere cloudsystemen die software as a service (SaaS) aanbieden, zoals Google App Engine van Google en EC2 van Amazon. Deze software hoeft niet geïnstalleerd te worden op de computer van de gebruiker, alles gebeurt via het web. Ook toegang tot bestanden en mappen gebeurt via het web. Het Azure Services Platform gebruikt een aangepast besturingssysteem Microsoft Azure om een cluster van servers te beheren die in het datacenter van Microsoft staan.
•	Printserver : een computer of router met één of meer aangekoppelde printers die d.m.v. een netwerk te bereiken zijn
•	Microsoft Hyper-V, met codenaam Viridian en voorheen bekend als Windows Server-virtualisatie, is een native hypervisor. Het kan virtuele machines maken op x86-64-systemen met Windows. Begonnen met Windows 8, vervangde Hyper-V Windows Virtual PC als onderdeel van hardwarevirtualisatie van de clientedities van Windows NT. Een servercomputer waarop Hyper-V wordt uitgevoerd, kan worden geconfigureerd om afzonderlijke virtuele machines aan een of meer netwerken bloot te stellen.
•	Fileserver: een bestandsserver dient ervoor te zorgen dat bestanden volledig en zonder een enkele fout worden overgebracht naar de client
•	Domaincontroller : 
Een domeincontroller is een server in een computernetwerk van Microsoft Windows die centraal beheert wie er toegang tot welke stukken van het domein mag hebben. Dit in tegenstelling tot het werkgroep-model, waarbij gebruikers en toegang op iedere individuele computer ingesteld moeten worden.
Met de komst van Windows Server 2000 en Active Directory is er hiërarchische structuur in de domeinen mogelijk geworden waarmee meerdere domeinen in een boomstructuur ("tree") georganiseerd kunnen worden, en meerdere "trees" in een "forest". Voor grotere organisaties met meerdere vestigingen biedt dit een grotere flexibiliteit.
•	DNS: Het Domain Name System (DNS) is het systeem en netwerkprotocol dat op het Internet gebruikt wordt om namen van computers naar numerieke adressen (IP-adressen) te vertalen en omgekeerd
•	DHCP: Dynamic Host Configuration Protocol (DHCP) is een computerprotocol dat beschrijft hoe een computer dynamisch zijn netwerkinstelling van een DHCP-server kan verkrijgen
•	Office 365: is een verzameling van internet-diensten, bedoeld voor bedrijven, thuisgebruik en het onderwijs. Deze internetdiensten worden deels aangeboden als online diensten, deels als applicaties op desktop-pc, tablet en telefoon en als combinatie van beide. De applicaties op desktop / pc is vergelijkbaar met het kantoorpakket Microsoft Office met het verschil dat men via Office 365 altijd de beschikking heeft over de meest recente versie.
•	SCCM: een onderdeel van de Microsoft System Center Suite en staat in voor het beheer & inventarisatie van pc's en servers
•	SQL: een gestandaardiseerde taal die gebruikt kan worden voor taken zoals het bevragen en het aanpassen van gegevens in een relationele database
•	Citrix XenApp & Windows Server 2019: een applicatie waarmee windows-applicaties kunnen worden benaderd via individuele apparaten vanaf een gedeelde server of cloud systeem
•	OMS: Operations Management Suite (Microsoft Azure)
•	VEEAM: backup software https://www.veeam.com/nl

### 7	 Technisch design
•	Niet functionele vereisten: performantie, security, continuous integration,… 
•	Wanneer we tot in detail het infrastructuur-gedeelte op het netwerk-gedeelte op vlak van onder meer security wensen af te stemmen, is er toch heel specifieke configuratie vereist (DHCP, DNS, Hyper-V netwerken -> replicatie, livemigration,... laten doorgaan op een apart netwerksegment)
•	Bij pakweg 70% van de installaties kan men gebruik maken van wizard-driven interfaces, maar in het kader van security en best practice worden echter bijna nooit de default instellingen behouden. Indien gewenst kunnen (bijna) alle wizard-driven interfaces gescript worden => PowerShell

### 8	Beschrijving van eventuele impact op de huidige infrastructuur
•	Geen impact op infrastructuur, het draait allemaal in een virtuele omgeving
