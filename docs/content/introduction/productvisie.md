# ZAKEN Productvisie ZDS

## Inhoud
* [Introductie](#introductie)
* [Productvisie ZDS](#productvisie-zds)
* [Scope](#scope)
* [Uitgangspunten](#uitgangspunten)
* [Realisatie](#realisatie)
* [Transitie](#transitie)
* [Centraal aanbieden](#centraal-aanbieden)
* [Gerelateerde trajecten](#gerelateerde-trajecten)


## Introductie

Om Zaakgericht Werken een stap verder te brengen worden Zaak- en Documentservices (ZDS) versie 2 ontwikkeld. Hierbij wordt een andere vorm van standaardisatie toegepast. Op basis van relevante informatiemodellen (RGBZ 2.0 en ImZTC 2.2) wordt met zowel publieke als private partijen in een agile proces vorm gegeven aan RESTful API's die concreet invulling geven aan de gewenste standaard. De standaard wordt tegelijk met een referentie-implementatie ontwikkeld om de implementeerbaarheid aan te tonen, en als referentie te dienen voor latere implementaties.

Binnen de Gemeentelijke Model Architectuur (GEMMA) versie 2 is het [Katern Zaakgericht Werken](https://www.gemmaonline.nl/index.php/GEMMA_2_Katern_Zaakgericht_Werken) beschikbaar. Hierin wordt uitvoerig beschreven hoe Zaakgericht Werken bedoeld is. Dit is verder uitgewerkt in de GEMMA Informatiearchitectuur in o.a. [referentiecomponenten en Integratiepatronen Zaakgericht werken](https://www.gemmaonline.nl/index.php/ZGW_in_GEMMA_2).

Vanaf mei 2018 wordt met een aantal partijen [samengewerkt](./samenwerking.md) aan realisatie van de "ZDS 2.0".

De naam Zaak- en Documentservices (ZDS) wordt gebruik om duidelijk te maken welke huidige standaard wordt gemoderniseerd. Waarschijnlijk worden uiteindelijk meerdere aparte API's ontwikkeld, waarna ook de naam ZDS veranderd zal moeten worden om verwarring te voorkomen.


## Productvisie ZDS

De visie op de te realiseren Zaak- en Documentservices is als volgt:

- De services worden vormgegeven op basis van heldere user stories ontleend aan de praktijk, dus op basis van daadwerkelijk gebruik in plaats van op basis van een theoretische inschatting van wat nodig is; Hieronder valt ook het uitwerken van  [klantcontacten](https://www.gemmaonline.nl/index.php/Klantcontacten_en_het_RGBZ) in de API.

- Alles rond "zaken" vindt zoveel mogelijk geautomatiseerd en op de achtergrond plaats. Medewerkers zijn bezig met inhoudelijke activiteiten, niet met zaken;

- De inhoud van de zaaktypecatalogus (ZTC) wordt zoveel mogelijk gestandaardiseerd, rekening houdend met de [zaakgerichte selectielijst](https://vng.nl/files/vng/20170706-selectielijst-gemeenten-intergemeentelijke-organen-2017.pdf)(pdf) en GEMMA 2 processen. Gestreefd wordt naar het centraal aanbieden van een ZTC. Deze kan bijv. dienen als repository, waar gemeenten zaaktypen 1 op 1 uit kunnen overnemen of deze voor eigen gebruik wijzigen waar nodig.

- Voor elk gegeven geldt een authentieke bron die wordt ontsloten via API's. Er wordt niet gekopieerd en gesynchroniseerd. Er worden relaties gelegd en doorgeknipt. Bijvoorbeeld: wanneer een informatieobject in meerdere zaken een rol speelt wordt vanuit elke zaak een relatie gelegd naar (een specifieke versie van) betreffend informatieobject. Het informatieobject blijft in de DRC onder verantwoordelijkheid van de opsteller. Dit heeft consequenties voor bijvoorbeeld de logica die besluit tot overbrengen of vernietigen.

- Door te werken met API's die een logische scope hebben binnen de informatiemodellen wordt toegewerkt naar een gegevenslandschap waarbij componenten zonder enige impact kunnen worden vervangen door een component van een andere leverancier. In de huidige praktijk is dit onmogelijk omdat de scope van wat een leverancierspecifieke implementatie van een service afdekt niet uniform is. Hiermee worden (onbedoelde) vendor lockins bestreden.

## Scope

Realisatie van de productvisie valt uiteen in vier delen die niet los van elkaar gezien kunnen worden:

1. Specificeren van Zaak- Documentservices v2.0
2. Beschikbaar maken van Open Source referentieimplementatie
3. Realiseren van toepassingen voor burgers of gemeenten gebruikmakend van de ZDS 2.0 API's
4. Centraal aanbieden van componenten op basis van de nieuwe API's

Delen 1 en 2 worden uitgevoerd door een centraal scrumteam bestaand uit samenwerkende gemeenten.

Deel 3 wordt uitgevoerd door planning af te stemmen tussen dit scrumteam en projecten die tegelijkertijd in gemeenten worden uitgevoerd. Bij deel 3 zorgt het centrale scrumteam voor het tijdig beschikbaar zijn van de relevante delen van de nieuwe API's.

Deel 4 is buiten scope voor het centrale scrumteam. Dit deel van de visie wordt nader uitgewerkt en op een later moment uitgevoerd.



##	Uitgangspunten

Bij de start van dit traject hanteren we de volgende uitgangspunten:

- De [GEMMA 2 Architectuur](https://www.gemmaonline.nl/index.php/GEMMA_Architectuur) en de [GEMMA 2 standaarden](https://www.gemmaonline.nl/index.php/GEMMA_Gegevens-_en_berichtenarchitectuur) (voor zover van toepassing) worden gevolgd

- Daar waar GEMMA 2 niets voorschrijft worden [Open Standaarden](https://www.forumstandaardisatie.nl/open-standaarden) gevolgd

- Daar waar GEMMA 2 nog niet (helemaal) in lijn is met Common Ground, wordt Common Ground gevolgd

- Alle code, documenten en specificaties die ontstaan in dit traject wordt Open Source, gepubliceerd onder de EUPL licentie

- RGBZ 2 en het daarvan afgeleide gegevensmodel UGM GBZ (GEMMA 2) zijn het startpunt voor de uitwerking van services. Wanneer blijkt dat aanpassingen nodig zijn voor goede werking van de Zaak- en Documentservices dan is dit mogelijk. In eerste instantie betreft dat het UGM GBZ. Indien uit de user-storys blijkt dat 'de werkelijkheid' niet correct gemodelleerd is in het RGBZ, dan is aanpassing mogelijk. Met ingang van dit traject komen betrokken standaarden in een toestand, waarbij deze voortdurend op basis van behoefte en consensus worden gewijzigd en frequent nieuwe versies worden vastgesteld.

- Voor de specificatie van API's wordt de onlangs door Forum Standaardisatie op de "Pas toe of leg uit"-lijst geplaatste OpenAPI Specification v3.x gebruikt.

- De principes volgend uit de [Common Ground visie](https://github.com/VNG-Realisatie/common-ground/blob/master/cg-vision.md) (EN) worden als volgt toegepast:
  - Goede scheiding zaakafhandeling en -registratie (ook conform GEMMA 2 met Zaakregistratiecomponent en Zaakafhandelcomponent)
  - Bij eventueel centraal aangeboden voorzieningen worden API's ontsloten via NLX
  - Grote informatiemodellen worden waar nuttig opgesplitst in kleinere informatiemodellen die hoog-frequent kunnen wijzigen
  - De modernste bewezen techniek wordt toegepast, en de toegepaste techniek verandert mee met de ontwikkelingen door de jaren heen. We gaan over in een toestand die kan worden aangeduid als "permanent beta".

- De [API en URI strategie](https://aandeslagmetdeomgevingswet.nl/digitaal-stelsel/documenten/documenten/api-uri-strategie/) zoals opgesteld binnen het programma Digitaal Stelsel Omgevingswet worden waar mogelijk toegepast.

- Eisen rond [Duurzame toegankelijkheid](https://wiki.nationaalarchief.nl/pagina/DUTO:Kwaliteitseisen) worden vanaf het begin in de standaarden verwerkt.

- Archivering speelt een rol bij de uitvoering van elk proces, vanaf de start tot aan [overbrenging](https://wiki.nationaalarchief.nl/pagina/DUTO:Overbrenging) of [vernietiging](https://wiki.nationaalarchief.nl/pagina/DUTO:Vernietigen). De gegevensstandaard voor archiefstukken [TMLO](https://archief2020.nl/nieuws/toepassingsprofiel-metadatering-lokale-overheden)is al geïntegreerd in RGBZ en ImZTC.


## Realisatie

De realisatie gaat van start zonder complete blauwdruk van wat gebouwd moet worden. Door user-stories zo goed mogelijk in te vullen en vanuit oogpunt architectuur in de gaten te houden dat designchoices worden gemaakt die ruimte openlaten voor verdere ontwikkeling in de richting van de visie, komt de nieuwe standaard stukje bij beetje tot stand.

Om een snelle start te maken wordt gestart met alle gemeenten en partijen waarvan de interesse bekend is. Aanhakers zijn nadrukkelijk welkom.

De ontwikkeling gebeurt in de GitHub repository [VNG-Realisatie/gemma-zaken](https://github.com/VNG-Realisatie/gemma-zaken).

Ook de backlog wordt publiek bijgehouden, samengesteld uit GitHub issues op dit open [Scrum bord](https://github.com/VNG-Realisatie/gemma-zaken/projects/1).

Bij de ontwikkeling van de API's wordt gestreefd naar backwards compatibility.

Voor meer informatie over de samenwerking, zie [samenwerking.md](./samenwerking.md)

Naast de (nieuw te ontwikkelen) OpenAPI 3 specificatie wordt een [referentie implementatie](https://nl.wikipedia.org/wiki/Referentie-implementatie) gemaakt. De referentie implementatie heeft de volgende karakteristieken:

* Wordt gelijktijdig ontwikkeld met de specificatie en (geautomatiseerde) test suite;
* Maakt het mogelijk ketentesten uit te voeren, wat vraagt om persistentie van testdata;
* Bewijst dat de specificatie geïmplementeerd kan worden;
* Zorgt er voor dat leveranciers hun eigen implementatie kunnen testen;
* Is de defacto standaard voor andere implementaties;
* Geeft duidelijkheid over de intentie van de specificatie waar deze ruimte biedt voor interpretaties.


## Transitie

Een BIG BANG overgang is onmogelijk. Er zal een geleidelijke transitie moeten plaatsvinden waarbij het nieuwe naast het oude bestaat. De te ontwikkelen ZDS 2.0 (en verder) is de toekomst, rekening moet worden gehouden met de huidige werkelijkheid die daarnaast moet kunnen bestaan. Idealiter in de zelfde achterliggende bronnen die op meerdere manieren worden ontsloten.

In het ZDS Scrumteam ligt de focus op het ontwikkelen van de nieuwe wereld. De rol van architecten in het team bestaat o.a. uit het in de gaten houden of een transitie mogelijk blijft.


## Centraal aanbieden      

Het principe "raadplegen bij de bron" veronderstelt waar mogelijk een enkele bron die wordt bijgehouden door de verantwoordelijke en welke kan worden geraadpleegd door afnemers.

Voorzien wordt dat centraal aanbieden van componenten naast decentraal gebruik van grote waarde kan zijn. Om daar te komen is het volgordelijk nodig eerst de API specificatie uit te werken.

Een centrale *Zaakregistratiecomponent* (ZRC) en *Documentregistratiecomponent* (DRC) is in veel ketensamenwerkingen wellicht een welkome oplossing als alternatief van de hudige praktijk van ketenautomatisering waarbij dossiers steeds worden gekopieerd naar een volgende silo. In de praktijk betekent dit dan dat organisaties afhankelijk van het proces en de ketenpartners het proces koppelen aan een andere ZRC en DRC.
- Binnen het DSO (zie: [Gerelateerde trajecten](#gerelateerde_trajecten)) is hier mogelijk op korte termijn behoefte aan.
- Ook binnen het Sociaal Domein heeft deze constructie potentie.

Een centrale *Zaaktypecatalogus* (ZTC) kan dienen als repository van content die voor veel gemeenten gelijk zal blijken. Voor veel zaken zal het niet nodig blijken af te wijken van de referentie. Ook hier geldt dat organisaties per proces zouden kunnen kiezen welke authoratieve bron voor Zaaktypen wordt geraadpleegd - bijvoorbeeld voor interne processen een intern ZTC en voor ketenprocessen een centrale ZTC.

Wanneer componenten centraal worden aangeboden is een *beheerorganisatie* noodzakelijk.


## Gerelateerde trajecten

- Binnen het [Digitaal Stelsel Omgevingswet](https://www.omgevingswetportaal.nl/wet-en-regelgeving/dso) zijn wellicht kansen om Zaakgericht Werken zoals gemeenten dat kennen te introduceren op basis van de ZDS 2.0 API's. Momenteel wordt samenwerking daar voorzien door middel van een omgeving waar bestanden kunnen worden gedeeld.

- De gemeenten Almere, Amsterdam, Haarlem, Heerenveen, Hoorn, Medemblik (en wellicht nog meer) zijn voornemens gezamelijk een Open Source Mijn Gemeente website te produceren. Daarbij is ZDS 2.0 wellicht een interessante aanvulling, hier liggen kansen om samen op te trekken.

- Dimpact en Atos stellen de Atos e-Suite in de context van Common Ground beschikbaar als platform voor proeven die innovatie en ontwikkeling stimuleren.

- Het project Landelijke Online Diensten (LOD) heeft een landelijke dienst voor aangifte overlijden en aangifte verhuizing gerealiseerd. Voor de koppeling tussen deze dienst (de voorkant) en de verwerkende systemen in de gemeente (de achterkant) worden twee "productaanvragen" API's ontworpen en gerealiseerd.
