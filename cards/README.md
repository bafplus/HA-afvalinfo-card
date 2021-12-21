# Lovelace Cards
Hieronder een lijst van alle Lovelace cards. Deze kun je los op je dashboard plaatsen of bv samen een "Verticale stapel". 

Inhoud:
* [Afvalkalender](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards#afvalkalender)
* [Afvalkalender 2](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards#afvalkalender-2)
* [Eerstvolgende afvalsoort(en)](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards#eerstvolgende-afvalsoorten)
* [Afval vandaag](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards#afval-vandaag)
* [Afval morgen](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards#afval-morgen)
* [Afval vandaag en morgen Picture card](https://github.com/bafplus/HA-afvalinfo-card/tree/main/cards#afval-vandaag-en-morgen-picture-card)

## Afvalkalender
![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afvalkalender-horizontaal.png)

Geeft een simpel maar overzichtelijke lijst van alle sensoren die een datum bevatten met hun eerstvolgende datum. Sensoren met geen data worden automatisch verborgen. De lijst wordt gesorteerd zodat altijd de eerstvolgende als eerste in de lijst staat.
### installatie
Kopieer de yaml code uit de [afvalkalender.yaml](../cards/afvalkalender.yaml) direct in een card.
### Configuratie
Geen. Zie eventueleopmerkingen in de yaml

![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afvalkalender.png)

Idem als afvalkalender maar geeft een verticale lijst. Gebruik [afvalkalender-lijst.yaml](../cards/afvalkalender-lijst.yaml) voor deze lijst.

## Eerstvolgende afvalsoort(en)
![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afval-eerstvolgend.png)

Geeft de afvalsoorten weer voor de aankomende week. Ondersteund meerdere afvalsoorten op 1 en dezelfde dag.
### installatie
Kopieer de yaml code uit de [eerstvolgende-afvalsoorten.yaml](../cards/eerstvolgende-afvalsoorten.yaml) direct in een card.
### Configuratie
Geen. Zie eventuele opmerkingen in de yaml

## Afval vandaag
![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afval-vandaag.png)

Geeft alle afvalsoorten die vandaag opgehaald worden. De gehele card is alleen zichtbaar op ophaaldag zelf. Ondersteund meerdere afvalsoorten op 1 en dezelfde dag.
### installatie
Kopieer de yaml code uit de [afval-vandaag.yaml](../cards/afval-vandaag.yaml) direct in een card.
### Configuratie
Geen. Zie opmerkingen in de yaml

## Afval morgen
![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/afval-morgen.png)

Geeft alle afvalsoorten die morgen opgehaald worden. De gehele card is alleen zichtbaar de dag voor de ophaaldag zelf. Ondersteund meerdere afvalsoorten op 1 en dezelfde dag.
### installatie
Kopieer de yaml code uit de [afval-morgen.yaml](../cards/afval-morgen.yaml) direct in een card.
### Configuratie
Geen. Zie opmerkingen in de yaml

## Afvalkalender 2  TODO
* (screenshot)
Afvalkalender met vaste sensoren
### installatie
Kopieer de yaml code uit de afvalkalender-2.yaml direct in een card.
### Configuratie
Geen. Zie opmerkingen in de yaml

## Afval vandaag en morgen Picture card TODO
* (screenshot)
* ### installatie
Kopieer de yaml code uit de afval-vandaag-morgen-picturecard.yaml direct in een card.
### Configuratie
Geen. Zie opmerkingen in de yaml

