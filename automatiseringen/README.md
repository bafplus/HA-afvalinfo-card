# Automatiseringen

Hier vindt je handige automatiseringen.

## Pushmelding de dag voor de ophaaldag

![alt text](https://github.com/bafplus/HA-afvalinfo-card/blob/main/screenshots/pushbericht.jpg)

Deze automatisering stuurt de dag voor de ophaaldag op een vast tijdstip een pushmelding naar alle apparaten.
### installatie
Kopieer de yaml code uit de [pushbericht.yaml](../automatiseringen/pushbericht.yaml) direct in een automatisering. LET OP! Controleer goed of de naam van de sensor klopt!
### Configuratie
Deze automatisering stuurt een pushbericht naar ALLE apparaten (die dat ondersteunen). Maar je kunt ook het bericht naar 1 apparaat sturen, bijvoorbeeld je eigen gsm. Pas hiervoor de entiteit aan naar die van de gsm door in het action blok de notify aan te passen van
```yaml
service: notify.notify
```
naar (bijvoorbeeld)
```yaml
service: notify.mobile_app_gsm_bart
```
Deze automatisering ondersteund meerdere afvalsoorten op 1 en dezelfde dag in 1 melding. Wil je voor elke afvalsoort een eigen melding dan moet je per afvalsoort een automatisering maken met de sensor van die afvalsoort in plaats van de "tomorrow" sensor.
## Een slimme speaker een melding geven de dag voordat het afval naar buiten moet
Deze automatisering laat een slimme speaker een gesproken bericht geven met welke soort(en) afval naar buiten moet.
### installatie
Kopieer de yaml code uit de [melding-tts.yaml](../automatiseringen/melding-tts.yaml) direct in een automatisering. LET OP! Controleer goed of de naam van de sensor klopt!
### Configuratie
Zorg ervoor dat TTS goed is ingesteld en werkt. Zie https://www.home-assistant.io/integrations/tts/ . Pas de nodige sensoren aan, zie YAMl

Deze automatisering ondersteund meerdere afvalsoorten op 1 en dezelfde dag in 1 melding. Wil je voor elke afvalsoort een eigen melding dan moet je per afvalsoort een automatisering maken met de sensor van die afvalsoort in plaats van de "tomorrow" sensor.
