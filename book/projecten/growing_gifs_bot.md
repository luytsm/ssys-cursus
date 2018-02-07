# Growing Gifs Bot
Dit jaar werken we weer samen de academie voor een project. Op de academie
loopt momenteel het onderzoeksproject *Growing Gifs*. De technische output van
het project is een applicatie die elke pennenstreek op een tekentablet
registreert en hiervan een gif maakt. De gif visualiseert de opbouw van de
tekening. Hieronder kan je een voorbeeld zien van een mogelijke output van de
software.

<img style="display:block; margin: auto;" src="./img/growing_gifs.gif" alt="">

Wij gaan een bijdrage bijleveren aan het onderzoeksproject door de
opbouw van de tekening op een andere manier te visualiseren.
**Wij gaan dit doen door elke pennenstreek te visualiseren met een robot**


## Line Dancer

Een eerste vereiste van het project is het aanpassen van de bestaande
applicatie. De applicatie noemt Line Dancer. Dit is een opensource project, dus
we hebben toegang tot de broncode. Er zijn echter 2 moeilijkheden die we eerst
moeten overkomen. De eerste is dat de code is geschreven in C/C++. De tweede
moeilijkheid is dat de applicatie voor de moment Mac only is.  Aan het
functionele van de applicatie is er zeker een feature dat we moeten
aanpassen/aanmaken. De applicatie maakt rechstreeks een gif aan. Deze gif is
moeilijk om te vervormen naar een coördinaten stelsel en het extraheren van de
druk op de pen zal nog moeilijker zijn. Daarom is het sneller om de applicatie
aan te passen. We vormen de applicatie als volgt om:

<img style="display:block; margin: auto;" src="./img/ssys-blokdiagram-software.png" alt="">

Je kan de code hier vinden: [Line Dancer GitHub
Repository](https://github.com/lab101/LineDancer)


**Het belangrijkste aan deze vereiste is de opbouw van het teksdocument. Dit is
de interface tussen de het tekentablet en de robot. Deze interface moet vanaf
dag 1 bekend zijn.**

## GG Bot

*gg easy* zal het niet zijn. Het maken van de feitelijke robot zal het
moeilijkste zijn aan heel het project. Dit is niks voor niks de focus voor het
vak Smart Systems. De meeste resources zullen gewijd zijn aan het creëren van
de robot.

Op het einde van het project is de robot instaat de complexe vormen na tekenen.
Het ultieme doel is live de complexe vormen kunnen nateken.

Om deze robot te bouwen krijg je als groep een basiskit die  bestaat uit:
- Robotchassis
- Powerbank
- Motordriver
- Draadloze module
- Servo motor
- ...

Deze componenten gecombineerd met de microcontroller kits die je groep reeds
bevatten kan je een basis prototype bouwen van de robot.

Vooraleer dat je aan je prototype(s) begint moet je een grondige analyse maken.
Wat er juist in deze analyse moet staan kan je terugvinden onder
*Deliverables / Analyse* in de cursus van Smart Systems.






