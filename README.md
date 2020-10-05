# Stappenplan voor de praktijktoets

## Korte beschrijving
Het stappenplan beschrijft de globale activiteiten die moeten worden uitgevoerd voor de praktijktoets. Een onderzoeker met een onderzoeksvraag implementeert een algoritme waarmee een dataset onderzocht kan worden. Het onderzoeksresultaat is versleuteld door middel van homomorphic encryptie. Het resultaat kan de onderzoeker downloaden en gebruiken voor zijn of haar onderzoek.

## Randvoorwaarden vooraf:
- De onderzoeker heeft een onderzoeksvraag geformuleerd en de datasets gekozen. 
- De wijze waarop het algoritme en de resultaatset beschikbaar worden gesteld moeten zijn gecommuniceerd met de onderzoeker. Mogelijke opties zijn: een portaal, via e-mail of via Github/Gitlab

## Basisstappen

1. De onderzoeker implementeert een algoritme voor de onderzoeksvraag. Hiervoor gebruikt hij of zij een technologiestack (Python, R, C++ of Rust). Het algoritme wordt opgenomen in een docker container. 
2. De onderzoeker maakt een dockerfile waarmee een container kan worden aangemaakt waarin het algoritmeis opgenomen. De onderzoeker hanteert als base image voor de dockerfile <nog in te vullen>. Uitgangspunt is een vertrouwd image waarvoor bekend is wat in het image is opgenomen. Het image moet de technologiestack ondersteunen van het algoritme.

    __Environment variabelen__
    
    Bekend moet zijn welke environment variabelen gebruikt moeten worden, bijvoorbeeld de URL voor het SPARQL-endpoint.
    Voorstel: ENV_SPARQLENDPOINT

    __Testdata__

    De onderzoeker heeft testdata nodig om tegen te ontwikkelen. Dit moet in RDF-formaat zijn.

3. De onderzoeker verzendt de code van het algoritme. Hierin is de dockerfile voor de build van de container in opgenomen. Met de dockerfile moet een werkende omgeving gerealiseerd kunnen worden, dus inclusief installatie van dependancies.
4. De datahouder verifieert dat het algoritme een analyse uitvoert overeenkomstig de onderzoeksvraag en geen datalek veroorzaakt.
5. De datahouder doet een build van de container. Docker moet hiervoor vooraf zijn geïnstalleerd.
6. De datahouder plaatst de container in de omgeving voor het uitvoeren van de analyse	Omgeving
    De datahouder moet een omgeving hebben ingericht waar de analyse kan worden uitgevoerd. Deze omgeving bestaat uit de volgende onderdelen:
    1.	RDF-data voor de onderzoeksvraag
    2.	Triplestore – database zoals OpenLink Virtuoso
    3.	RDF-data geladen in triplestore
    4.	Sparql-endpoint – de meeste triplestores leveren ook een Sparql-endpoint erbij
    5.	Docker waarmee de container kan draaien.
    6.	Mount volume naar disk voor bestand met resultaatset

7. De datahouder verifieert dat de resultaatset geen datalek bevat.
8. De datahouder stelt de resultaatset beschikbaar aan de onderzoeker. 
9. De onderzoeker ontvangt de resultaatset.

Hiermee stopt het stappenplan	


