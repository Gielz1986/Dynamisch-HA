# Dynamisch Energiebeheer - Home Assistant
**Om in 2️⃣ stappen de dynamische tarieven visueel te krijgen in Home Assistant**.

Dit project bevat de configuratie voor het dynamisch aansturen van thuisbatterijen, op basis van Nordpool energieprijzen (HACS) binnen Home Assistant. Visueel aantrekkelijk met een gemakkelijke JA of NEE voor je eigen laad en ontlaad automatiseringen.

Vind je dit project leuk en wil je mij steunen? Trakteer mij dan op een kopje koffie ☕️ – ik codeer beter met cafeïne!

<a href="https://www.buymeacoffee.com/gielz" target="_blank">
  <img src="https://github.com/Gielz1986/Zendure-HA-zenSDK/blob/main/Images/bmc.png?raw=true" width="180" alt="Buy Me a Coffee">
</a><br>

## 1️⃣ Configuration.yaml

1. Maak eerst een **backup** van je `configuration.yaml`.
2. Pas daarna je `configuration.yaml` aan door gebruik te maken van de Github `configuration.yaml`.
3. Herstart Home Assistant.
4. Vul nu bij de onderstaande entiteiten de juiste gegevens in en herstart Home Assistant nogmaals.

| Configuratie| Extra info|
|-|-|
| `input_text.dynamisch_nordpool_sensor`      |  de sensor van Nordpool HACS toevoegen |
| `input_text.dynamisch_handmatige_periode`    | Verwijder **unknown** |
| `input_text.dynamisch_handmatige_periode_morgen` | Verwijder **unknown** |

![Preview](Images/Nordpool.png)

*Zelf toe te voegen entiteiten op een dashboard.
![Preview](Images/Preview.gif)

| Categorie              | Entiteiten                              | State                                                       |
| ---------------------- | -------------------------------------- | ------------------------------------------------------------ |
| Configuratie           | Dynamisch Nordpool Sensor              | bijv. sensor.nordpool_kwh_nl_eur_3_09_0                      |
| Dynamische Aansturing  | Dynamisch Nordpool                     | Nordpool prijzen in 15min en 1uur                            |
|                        | Dynamisch 15 Minuten                   | Prijzen in 15 minuten                                        |
|                        | Dynamisch Handmatige Periode           | bijvoorbeeld **G11:00;D12:00;G15:00** , **G03:00-07:00;D12:00-15:00;D18:00** of **Geen**                   |
|                        | Dynamisch Handmatige Periode Morgen    | bijvoorbeeld **G11:00;D12:00;G15:00** , **G03:00-07:00;D12:00-15:00;D18:00** of **Geen**                   |
|                        | Dynamisch Spread Indicatie             | Berekening spread                                            |
|                        | Dynamisch Spread Indicatie NOM         | Berekening spread NOM, duurste na eerste laadactie           |
|                        | Dynamisch Spread Indicatie Morgen      | Berekening spread                                            |
|                        | Dynamisch Spread Indicatie NOM Morgen  | Berekening spread NOM, duurste na eerste laadactie           |
|                        | Dynamisch Goedkoopste Periode          | Ja of Nee                                                    |
|                        | Dynamisch Duurste Periode              | Ja of Nee                                                    |
|                        | Dynamisch Goedkoopste X Periode        | 1-96                                                        |
|                        | Dynamisch Duurste X Periode            | 1-96                                                         |
|                        | Dynamisch Goedkoopste X Periode Morgen | 1-96                                                        |
|                        | Dynamisch Duurste X Periode Morgen     | 1-96                                                         |

---

#### ✅ Resultaat
Je krijgt twee sensoren die aangeven of een periode **JA** (goedkoop) of **NEE** (duur) is. Op basis hiervan kun je automatisch bijvoorbeeld een batterij aansturen via je eigen automatiseringen.

![Preview](Images/Janee.JPG)

#### ✅ Attributen bekijken
Je kunt op de indicatie-sensoren klikken om de volledige berekeningen en attributen in te zien. Hier staat ook de code voor de handmatige periode die je vervolgens kunt knippen en plakken om zelf een beetje aan te passen en te gebruiken in het handmatige periode veld.

![Preview](Images/Spread.JPG)

<br><br>

## 2️⃣ Automatisering toevoegen

Voeg de automatisering toe. deze zorgt ervoor dat hij de forecast (morgen) en ingestelde periodes over zal zetten naar vandaag om 00:00. 

<br><br>

## #️⃣ Apexcharts
Je kunt om het visueel aantrekkelijk te maken de Apexcharts `Nordpool_Apexcharts_Vandaag` en `Nordpool_Apexcharts_Morgen` gebruiken `(zie Github bestanden)`.
