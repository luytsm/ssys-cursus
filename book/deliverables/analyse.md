# Analyse

In de analyse vinden we de volgende elementen terug:
- Probleemstelling
- Een mindmap
- Een beschrijving
- Hardware analyse
- Software  analyse 
- Taakverdeling
- Systeem specificaties

## Probleemstelling 

Het doel van Smart Systems is het voorzien van een oplossing voor een probleem.
Als we het probleem gedefinieerd is en neergeschreven is het eenvoudiger om een
oplossing te voorzien. De oplossing voor het probleem kan worden opgedeeld in
verschillende kleine deelproblemen. Door het probleem te zien als een som van
kleine deelproblemen lijkt het minder imposant. Als je systematisch kleine
problemen oplost dan kan je vooruitgang zien en de finish.

**Voor deze sectie van de analyse beschrijf je het hoofdprobleem in maximaal 2
tot 5 zinnen. Daarna deel je het probleem op in minimum 10 delen (Als bulletpoints).**


## Mindmap

Nu dat we het probleem hebben vastgesteld gaan we beginnen aan het formuleren
van een oplossing. De eerste stap hierin is het bundelen van losse ideeën om
het probleem aan te pakken en eventueel nog meer details over het probleem neer
te pennen. Hiervoor gebruiken we een mindmap. Met een mindmap gaan we onze
losse ideeën en gedachten op een visuele manier organiseren en met elkaar te
verbinden. Als we dit hebben gedaan is het startschot van de analyse gegeven 

<img style="display:block; margin: auto;" src="./img/mindmap.jpg" alt="">

**Je voegt de mindmap toe aan de analyse.Je mag dit op papier doen maar je moet
deze wel netjes inscannen, digitaal heeft de voorkeur. (Je kan Google Drawings
gebruiken)**

# Specieke analyse
In de mindmap hebben we alle mogelijke oplossingen gevisualiseerd en
verbindingen gelegd. In deze stap van de analyse gaan we één van deze
oplossingen selecteren en onderbouwen. Dit moet zowel voor hardware als
software gebeuren.


## Hardware analyse
We leggen eerst de focus op de hardware omdat deze mee de mogelijkheden van de
software oplossingen bepaalt. Voor de hardware analyse ga je de connecties van
de subsystemen weergeven en aantonen hoe dat de interface tussen beide
componenten is opgebouwd. Een voorbeeld: 

<img style="display:block; margin: auto;" src="./img/block_diagram_connections.png" alt="">

Een voorbeeld van een volledig systeem

<img style="display:block; margin: auto;" src="./img/basic_blok.png" alt="">

**Stel dit op voor de voorgestelde oplossing en voeg dit toe aan de analyse**

Natuurlijk hoort er bij elke blok ook specificaties en/of elektrische
karakteristieken. Deze worden in het volgende formaat meegeven in de analyse.

| Blok           | Specificatie    | Min  | Nominaal | Max    |
| --             | --              | --   | --       | --     |
| Motor Power    | Werkspanning    | 7V   | 7.2V     | 7.V    |
| (Loodbatterij) | Stroom          |      | 500mA    | 2A     |
|                | Capaciteit      |      | 2700mAh  | &nbsp; |
| ATmega328p     | F<sub>cpu</sub> |      | 16 MHz   |        |
|                | Werkspanning    | 4.8V | 5V       | 5.2V   |
 
**Stel dit op voor gebruikte blokken in de  oplossing en voeg dit toe aan de analyse**

Voor elk blok moet je ook een argumentatie geven waarom deze gebruikt wordt in
de voorgestelde oplossing in de analyse. Geef ook mogelijke alternatieven. Geef
deze informatie in het volgend formaat: 

| Blok            | Argumentatie                                                                                                                                                                                                                                   | Alternatieven           |
| --              | --                                                                                                                                                                                                                                             | --                      |
| Motor Power     | De loodbatterij is oplaadbaar en levert de correcte spanning voor de motorsturing. De LiPo batterij is een betere oplossing vooral door gewicht en beter behoud van capaciteit. De loodbatterij was beschikbaar en moest niet aangkocht worden | LiPo, Powerbank         |
| Wireless Driver | We maken gebruik van een nRF24L01 omdat de simpelste manier van communicatie is, geen protocol en een simpele communicatie voorziet.                                                                                                           | Bluetooth, ZigBee, WiFi |

**Stel dit op voor gebruikte blokken in de  oplossing en voeg dit toe aan de analyse**


## Software analyse

Om onze software te analyseren is een top down methodologie aangeraden. Eerst
moeten we zien wat onze datastromen zijn. Welke data word er genereerd in het
systeem, wat voor data kunnen we injecteren voor het systeem. Deze vraag is
cruciaal om parallel in team te kunnen werken. Dit moet in het begin bepaald
worden zodat je als individu aan aparte blok kunt werken van het systeem. 

Als je bepaalt hebt wat voor data er in en uit een specifieke blok van het
systeem komt, moet je ook nog bepalen in welk formaat dit gebeurt. Om dit
succesvol te doen moet er ook rekening gehouden worden met de hardware
restricties. JSON versturen over I²C met een Arduino is gedoemd om  te falen.

Voor de starten geef je aan welke data er in en/of uit een specifieke blok komt
van de hardware analyse. We geven dit weer in het volgend formaat: 

| Blok         | Data In                               | Data Uit                              |
| --           | --                                    | --                                    |
| Motor Driver | 2x PWM Signaal                        | N.V.T.                                |
| ATMega328P   | Configuratie instellingen, Sensordata | Configuratie instellingen, Sensordata |

Bij de ATMega328p zien we dat de data uit gelijk is aan de data in. Hieruit
kunnen we afleiden dan we data van ons systeem remote kunnen opvragen via de
Wireless Driver. Deze functionaliteit moet in elk project zitten.

**Maak de oplijsting voor de in en uit data van de voorgestelde oplossing in
bovenstaand formaat en voeg deze toe aan de analyse**

De machine die als mogelijke oplossing word aangebodendat we aanbieden kan in
zich in verschillende states vinden en kan transitioneren tussen verschillende
states. Om de embedded code in het project eenvoudig te kunnen debugen moeten
we weten in welke state de code zicht bevindt. Om deze states te defineren
maken we gebruik van een state diagram. Een voorbeeld hiervan kan je hieronder
terugvinden. 

<img style="display:block; margin: auto;" src="./img/state_diagram.png" alt="">

**Voeg aan de analyse een state diagram toe van de voorgestelde oplossing**
*Een goed voorbeeld van een complexer state diagram kan je hier terugvinden:
[State Diagram nRF24L01](http://m8ta.com/images/470_1.png)*

Om te wisselen tussen de verschillende states moeten we de flow hiervan beschrijven in een flowchart 

<img style="display:block; margin: auto;" src="./img/flow_chart.png" alt="">

**Voeg in de analyse voor elke state transition een flowchart. Verduidelijk de
nodige processen met flowchart waar nodig.**

*Op deze manier bouwen we onze software modulair. Dit is een vereiste doorheen
het project. Je werkt met meerde tijdens het project aan aparte blokken om dit
mogelijk te maken moeten de interface tusssen de aparte blokken gekend zijn.*

Als er een grafische interface nodig, dienen hiervoor mock ups gemaakt worden.
<img style="display:block; margin: auto;" src="./img/mockup.png" alt="">

**Als er mock ups nodig zijn voeg deze toe aan de analyse**


## User stories en Engineering Tasks

Voor je analyse moet je minimaal 10 epics uitschrijven zoals gezien tijdens de
lessen van dhr. Luc Peeters. Je breidt deze epics uit met user stories. Deze
user stories zijn dan verbonden aan een specifieke epic. Op deze manier creëren
we meetbare taken die een student kan oplossen.In totaal voorzie je 50 user
stories ter ondersteuning van de Epics.

Voor een voorbeeld en meer info hierover: [klik
hier](http://xp.c2.com/EngineeringTask.html)

Door de user stories te schrijven heb je de functionele analyse van je product
gemaakt.

## Taakverdeling

Om alles tijdig klaar te krijgen zal  het noodzakelijk zijn het werk te
verdelen. Een duidelijke en correcte taakverdeling zal onontbeerlijk zijn. We
gaan gebruik maken van Jira als projectmanagement tool. Hierin moet de
taakverdeling duidelijk worden.

## Systeemspecificaties

Tot slot zal uit de hardware- en softwareanalyse zullen we systeemspecificaties
kunnen opstellen die het mogelijk moeten maken om de juiste
hardwareschakelingen te ontwerpen en de juiste programma's te ontwikkelen.


