# UWB Indoor Lokalisatie

## Beschrijving

Voor dit project ontwikkeld je een een prototype voor een UWB indoor lokalisatie oplossingen. Met deze RF tech kan je op basis van ranging de positie van een object tot op 2 cm bepalen. Vorig jaren is er ook al onderzoek naar gedaan. Hierop gaan we verderbouwen. De kritieke componenten van dit prototype zijn:

* DWM1000 
* SAMD21
* PoE  

De architectuur van het prototype werkte niet. De fout in de ontwikkeling zat dat we individuele blokken van het architectuur niet apart hebben getest vooraleer dat we ze combineren. 

Parallel integreren we een bestaande UWB oplossing op de AGV van AP. Data van de UWB oplossingen gaan we vergelijken met de navigatie data van de AGV. Voor dit gedeelte maken we gebruik van het Pozyx systeem. 



## Teamleden 

Dit project wordt uitgevoerd door het Smart Robotics team

## Verwachte output

* Anker
  * Individueel prototypebord / blok in de architectuur
  * Eerste prototype van alle componenten samen 
* Tag
  * Individueel prototypebord / blok in de architectuur
  * Eerste prototype van alle componenten samen
* Demo van werkend product