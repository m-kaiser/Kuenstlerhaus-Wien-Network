# Künstlerhaus Wien Network
This dataset contains information about exhibitor networks gathered by the evaluation of catalogues of the annual exhibitions of the “Association of Fine Artists Vienna, Künstlerhaus”. It includes not only biographical data about Austrian artists but also international participants of these events. Currently, the dataset covers mainly the period from 1869 to 1900 but will be hopefully expanded in the future. Persons, who could be identified, were referenced with identifiers from **Wikidata** and were linked to their **Wikipedia Page**. This has also been done with Institutions and places so far it was possible.

## Dataset
1. Graph File
   - Edges Table
   - Nodes Table
2. Biographical Data
   - person-person-network
   - person-institution-network
   - person-place-network
   - person-source-network

### Edges Table
| column title | definition |
|--------------|------------|
| Id | unique identifier for the edges table |
| source | node id for the network graph, always persons |
| target | node id for the network graph, always exhibitions |
| exhibitor | label of the source node, person name |
| exhibitor_id | database id for biographical data |
| exhibition | label of the target node, exhibition title |
| exhibiton_id | database id for biographical data |
| year | year in which the exhibition was staged |
| name_from_catalogue | original writting of the exhibitor name according to the catalogue |
| place_name | place of residence as stated in the catalogue |

### Nodes Table

| column title | definition |
|--------------|------------|
| Id | unique identifier for the nodes table (prefix p for persons, prefix e for exhibitions)|
| label | name of an exhibitor or exhibition |
| wikidata | identifier of an wikidata entity |
| date of birth| date when an exhibitor was born, based on wikidata |
| date of death | date when an exhibitor has died, based on wikidata |
| place of birth | place where an exhibitor has been born, based on wikidata |
| place of death | place where an exhibitor has died, based on wikidata |
| occupation | one or more occupations of an exhibitor, separated by an semicolon, based on wikidata |
| educated at | listing of educational institutions where an exhibitor has been educated at, separated by a semicolon, based on wikidata |
| gender | male, female or unknown |
| wikipedia | link to english, spanish, german or french wikipedia page of an exhibitor |
| type | two types of nodes “persons” and “exhibitions” |

## Biographical Data

The biographical data for most of the Austrian exhibitors was collected during the APIS project between 2015 and 2019 (about Austrian artists described in the Austrian Biographical Encyclopedia). The relations were then translated into the corresponding Wikidata properties (e.g. was pupil of / student of (P1066)) and the entities were referenced by the matching Wikidata identifiers (QID). This was done to evaluate the existing biographical data from this linked-open-data resource and testing the possibilities for applying more data for the whole dataset. A second data sample, describing the life and careers of German exhibitors (mostly artists from Berlin and Düsseldorf) was compiled in 2020 for comparative purpose. The excerpts of biographical encyclopedia articles for Austrian and German exhibitors were made on the basis of an annotation manual developed in course of the APIS project (see publication section below).

## Interactive Network Graph
The interactive Network Graph is built with [Gephi 0.9](https://gephi.org/) and [Retina beta](https://ouestware.gitlab.io/retina/beta/#/). Nodes represent exhibitors and exhibitions in this two-mode network. Each of the edges is drawn on the basis of a catalogue entry. A wide range of filters can be applied for persons in this network (biographical data from wikidata: gender, type, occupation, places, education etc.). Additional information about an identified exhibitor can be accessed through a link to a wikipedia page.

![image of network node](https://github.com/m-kaiser/Kuenstlerhaus-Wien-Network/blob/ea88a274049c99b50ecb702349ab64669cb5337e/Graph%20File/kuenstlerhaus_wien_network_image1.png)
> Screenshot showing the interactive Network Graph. [Try it out!](https://ouestware.gitlab.io/retina/beta/#/graph/?url=https%3A%2F%2Fgist.githubusercontent.com%2Fm-kaiser%2F10ad8656256ab0af66df00723e171d8a%2Fraw%2F6c3319a38f617dcf8c2356f5021b22ae6a01d3b7%2Fkuenstlerhaus_network.gexf&n=p_1873&sa=r&ca[]=g&ca[]=t&fa[]=dd&fa[]=pb&fa[]=pd&fa[]=o&fa[]=e&fa[]=db&st[]=t&st[]=g&st[]=o&st[]=wd&st[]=db&st[]=pb&st[]=dd&st[]=pd&st[]=e&st[]=wp&st[]=r&ec=o)

## Publications
*  Kaiser, Maximilian: “Was uns Biographien über Künstlernetzwerke sagen. Konzepte für eine historische Netzwerkanalyse auf Basis Biographischer Texte aus dem Österreichischen Biographischen Lexikon (ÖBL)”, in: Christine Gruber, Maximilian Kaiser und Ágoston Zénó Bernád (eds.): Europa Baut auf Biographien. Aspekte, Baustein, Normen und Standards einer Europäischen Biographik, Wien: new academic press, 2018, 383–403. [https://www.oeaw.ac.at/fileadmin/Institute/INZ/Europa_baut_auf_Biographien.pdf](https://www.oeaw.ac.at/fileadmin/Institute/INZ/Europa_baut_auf_Biographien.pdf).
*  Kaiser, Maximilian: “Leitfaden für die Annotation von Named Entities (NE) in Biographien”, in: Christine Gruber, Josef Kohlbacher und Eveline Wandl-Vogt (eds.): The Austrian Prosopographical Information System (APIS). Vom Gedruckten Textkorpus zur Webanwendung für die Forschung, Wien, Hamburg: new academic press, 2020, 82–104. [https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf](https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf).
*  Kaiser, Maximilian: “Künstlerbiographien und historische Netzwerkforschung: Anwendungsbeispiele aus dem Bereich der Digitalen Kunstgeschichte”, in: Christine Gruber, Josef Kohlbacher und Eveline Wandl-Vogt (eds.): The Austrian Prosopographical Information System (APIS). Vom Gedruckten Textkorpus zur Webanwendung für die Forschung, Wien, Hamburg: new academic press, 2020, 201–242. [https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf](https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf).
*  Kaiser, Maximilian: “The ‘Who’s Who?’ Of Künstlerhaus Exhibitors. A Guide to Analyze Entangled Artists Biographies Based on Wikidata”, in: Anne Klammt, Antoine Courtin and Olivier Bonfait (eds.): Humanités Numériques. De Nouveaux Récits En Histoire de l’art?, Histoire de l’art, 87 (January 6, 2021), 125–37. 

## Resources
A complete set of exhibition catalogues are held by the Research Center of the Österreichische Gallerie Belvedere. In autumn 2021, the museum started in cooperation with the archive of the Association of Fine Artists Austria (formerly Association of Fine Artists Vienna) with the digitization of the catalogues. They will be accessible in the future through the [digital library](https://digitale-bibliothek.belvedere.at/viewer/kuenstlerhaus-wien/).
