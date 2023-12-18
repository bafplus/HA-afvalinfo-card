## LET OP! Door laatste update is het een en ander veranderd. Alle code in de repo is al aangepast maar door gebrek aan tijd zijn de readme's nog niet hierop aangepast!

# HA-afvalinfo-card
Diverse lovelace cards voor de [Afvalinfo](https://github.com/heyajohnny/afvalinfo "Afvalinfo") integratie voor Home Assistant.

![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afvalkalender.png) ![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afval-vandaag.png) ![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afvalkalender-horizontaal.png)

Afvalinfo ondersteunt verreweg de meeste gemeenten in Nederland (zie [Afvalinfo](https://github.com/heyajohnny/afvalinfo "Afvalinfo") welke).
Maar levert je enkel de nodige sensoren. Je zult dus zelf hier een lovelace card voor moeten maken of een automatisering om bv een push bericht te ontvangen de dag voordat het afval naar buiten moet.
In deze repo probeer ik enkele lovelace cards en automatiseringen te verzamelen om direct te gebruiken of ter inspiratie.
Om alles zo makkelijk mogelijk te maken heb ik ervoor gekozen om alles zodanig te maken dat het meeste door simpelweg te copy/pasten zal werken.
Zo maakt de afvalinfo integratie bijvoorbeeld gebruik van een ID die je in de (optioneel) configuratie kunt opgeven.
Hierdoor krijgen de sensors een niet universele benaming waardoor het veel code en aanpassingen nodig heeft om te functioneren.
Om dit op te vangen wordt gebruik gemaakt van wildcards.
Meer details hierover verder in deze handleiding.

Heb je zelf een mooie card of automatisering of variatie gemaakt maak hier gerust een PR voor aan dan zal ik deze in de lijst opnemen.
Belangrijk hierbij is dat dit zo universeel mogelijk moet werken door gebruik te maken van dezelfde wildcards etc zodat het voor eindgebruikers zo makkelijk mogelijk is om alles werkend te krijgen.

Hieronder een handleiding om alle benodigde zaken te installeren zoals alle integraties, iconen en configuratie. Heb je dit alles al kun je via de volgende links naar de cards, automatiseringen en verder zaken springen. Daar vindt je dan weer meer informatie.

* [Lovelace Cards](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards)
* [Automatiseringen](https://github.com/bafplus/HA-afvalinfo-card/tree/main/automatiseringen)
* [Scripts](https://github.com/bafplus/HA-afvalinfo-card/tree/main/scripts)

## Installatie Afvalinfo Integratie

Om te beginnen is uiteraard de Afvalinfo integratie nodig.
Volg de instructie op [Afvalinfo](https://github.com/heyajohnny/afvalinfo "Afvalinfo").

Hieronder volgt een beknopte installatieinstructie:

1. Installeer HACS als je dat nog niet gedaan hebt. Meer informatie en instructies: [HACS](https://hacs.xyz/docs/setup/prerequisites "HACS").
2. Installeer [Afvalinfo](https://github.com/heyajohnny/afvalinfo "Afvalinfo") in HACS
3. Herstart HA
4. Ga in HA naar instellingen->integraties en voeg Afvalinfo toe. Deze zal de nodige basisgegevens van je vragen zoals naam van je locatie (standaard "home"), je postcode, huisnummer en gemeente en eventuele aanvullende gegevens mocht jouw gemeente dat nodig hebben. Heb je deze gegevens niet, (zoals niet elke gemeente gebruikt de diftar code) laat deze dan simpelweg leeg. Postcode, huisnummer en gemeente zijn vereist.
5. Onderaan kun je alle beschikbare sensoren toevoegen, kies hier welke afvalsoorten je in HA terug wilt zien en vergeet ook zeker de 2 sensoren voor afval-vandaag en afval-morgen niet!
6. Klik op "toevoegen"
7. Herstart HA

Gefeliciteerd! Je hebt nu de afvalintegratie geinstalleerd en heb je diverse sensoren in HA (afhankelijk welke je in stap 5 toegevoegd hebt en de 2 algemene sensoren voor het afval van vandaag en morgen). Let op! Het kan even duren voordat er data binnenkomt.

## Installatie benodigdheden voor de cards in deze repo
### Afbeeldingen, iconen en naam sensoren
Alle sensoren hebben dezelfde icoontjes en hebben als naam de naam van de sensor. Middels deze aanpassing wijzen we voor elke sensor een eigen Friendly name, icoon en afbeelding toe zodat wij deze niet overal hoeven aan te passen in de code maar op 1 centrale plek.
1. In de rootmap van HA (waar configuration.yaml staat) heb je als het goed is een customize.yaml staan. Zo niet maak deze dan aan en open deze in bv File Editor.
2. Copy paste de code van [customize.yaml](https://github.com/bafplus/HA-afvalinfo-card/blob/main/costumize.yaml) in deze repo
3. Controleer goed of alle namen van de sensoren kloppen en pas deze waar nodig aan. Let hier vooral goed op de naam van de sensoren, zo wordt bijvoorbeeld de naam die je tijdens het installeren hebt opgegeven (standaard "home") in elke sensor toegevoegd. Heb je hier wat anders gebruikt moet je dit bij alle sensoren goed aanpassen!
4. Sla het bestand op.
5. Ga naar je configuration.yaml en zet de volgende code helemaal aan het BEGIN van je yaml. Als hier al "Homeassistant:" staat dan hoef je alleen de 2e regel toe te voegen.
```yaml
homeassistant:
  customize: !include customize.yaml
```
6. Sla je configuration.yaml op. Dit zorgt ervoor dat je customize.yaml voortaan gebruikt gaat worden in HA
7. ga naar instellingen->instellingen en klik op "controleer configuratie", als deze ok is herstart HA

### Benodigde iconen
1. Open de map WWW in de root van HA (waar ook je configuration.yaml staat) in bv File Editor
2. Maak een map "images". In deze map zullen alle (icoon) afbeeldingen komen te staan.
3. Plaats alle iconen in de map [icons](https://github.com/bafplus/HA-afvalinfo-card/tree/main/icons "icons") in deze "images" map. Dus dat het pad uiteindelijk /www/images/naamvanicoon.png is. Je kan ook een andere map gebruiken maar dan zul je dit pad ook overal in de code aan moeten passen.
4. Gebruik je een icon image dan is het pad in je card "/local/images/naamvanicoon.png"
Deze plaatjes worden real-time geladen, dus een wijziging van een van deze plaatjes wordt direct gebruikt zonder iets te hoeven herladen (behalve evt je browser).

### Installatie lovelace-auto-entities
Om de cards te laten werken en omdat de afvalinfo integratie geen universele benaming van sensoren gebruikt is gebruik gemaakt van een plugin die wildcards ondersteund in lovelace cards. Dit om de code zo simpel mogelijk te houden zodat het vrijwel copy/paste werkt zonder al te veel aan te hoeven passen. Wel zo makkelijk :-)
1. Open HACS en ga naar Frontend
2. Klik rechtsonder op "explore and download repositories"
3. Zoek naar "lovelace-auto-entities" en installeer deze
4. Thats it! De plugin heeft geen verdere configuratie nodig




