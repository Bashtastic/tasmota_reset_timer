# Tasmota reset-timer

Een interactieve, zelfstandige webtimer voor de **Fast Power Cycle Device Recovery** van Tasmota.

## Gebruiken

Open [index.html](index.html) in een browser en druk op **Start timer**.

De timer begeleidt je door:

1. **30 seconden spanning UIT**
2. **6 keer**: 2 seconden **AAN**, daarna 2 seconden **UIT**
3. **7e keer AAN** en de spanning **aan laten staan**

De interface biedt een grote aftelklok, kleurindicatie, geluidssignalen, voortgang per ronde, pauzeren, opnieuw beginnen en een volledigschermknop. Er is geen installatie of internetverbinding nodig.

> **Belangrijk:** deze methode werkt alleen wanneer `SetOption65 0` is ingesteld. Bij `SetOption65 1` is de reset door stroomonderbrekingen uitgeschakeld.

## Als de stroomcyclus-reset niet werkt

Volgens de Tasmota-documentatie zijn er andere manieren om het apparaat te herstellen:

- Houd **Button1 40 seconden** ingedrukt, mits de knopfunctie niet is uitgeschakeld of gewijzigd. De werkelijke tijd kan afhangen van `SetOption32`.
- Gebruik **6 korte drukken** op Button1 om de WiFi-configuratiemodus te starten, mits multipress niet is uitgeschakeld.
- Gebruik `Reset 1` via de console, MQTT of HTTP als het apparaat nog bereikbaar is.
- Als niets werkt, kan opnieuw flashen via de seriële aansluiting nodig zijn.

## Veiligheid

De timer **schakelt zelf geen elektriciteit**: hij geeft alleen aanwijzingen. Gebruik een veilige stekker of schakelaar en raak nooit blootliggende netspanningsdraden aan. Een fabrieksreset verwijdert instellingen.

## Bron

- [Tasmota Device Recovery](https://tasmota.github.io/docs/Device-Recovery/)
- [Tasmota Buttons and Switches](https://tasmota.github.io/docs/Buttons-and-Switches/)

## Techniek

Eén HTML-bestand met ingebouwde CSS en JavaScript; geen externe afhankelijkheden.
