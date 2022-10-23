# Künstlerhaus Wien Network
This dataset contains information about exhibitor networks gathered by the evaluation of catalogues of the annual exhibitions of the “Association of Fine Artists Vienna, Künstlerhaus”. It includes not only biographical data about Austrian artists but also international participants of these events. Currently, the dataset covers mainly the period from 1869 to 1900 but will be hopefully expanded in the future. Persons, who could be identified, were referenced with identifiers from linked-open-data-resources such as **Wikidata, GND, ULAN, RKDartistsID**. This has been done with Institutions (GND, Wikidata) and places (Wikidata, GeoNames) so far it was possible.

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
*  Kaiser, Maximilian. “Was Uns Biographien Über Künstlernetzwerke Sagen. Konzepte Für Eine Historische Netzwerkanalyse Auf Basis Biographischer Texte Aus Dem Österreichischen Biographischen Lexikon (ÖBL).” In Europa Baut Auf Biographien. Aspekte, Baustein, Normen Und Standards Einer Europäischen Biographik, edited by Christine Gruber, Maximilian Kaiser, and Ágoston Zénó Bernád, 383–403. Wien: new academic press, 2018. [https://www.oeaw.ac.at/fileadmin/Institute/INZ/Europa_baut_auf_Biographien.pdf](https://www.oeaw.ac.at/fileadmin/Institute/INZ/Europa_baut_auf_Biographien.pdf).
*  Kaiser, Maximilian. “Leitfaden Für Die Annotation von Named Entities (NE) in Biographien.” In The Austrian Prosopographical Information System (APIS).  Vom Gedruckten Textkorpus Zur Webanwendung Für Die Forschung, edited by Christine Gruber, Josef Kohlbacher, and Eveline Wandl-Vogt, 82–104. Wien, Hamburg: new academic press, 2020. [https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf](https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf).
*  Kaiser, Maximilian. “Künstlerbiographien Und Historische Netzwerkforschung: Anwendungsbeispiele Aus Dem Bereich Der Digitalen Kunstgeschichte.” In The Austrian Prosopographical Information System (APIS).  Vom Gedruckten Textkorpus Zur Webanwendung Für Die Forschung, edited by Christine Gruber, Josef Kohlbacher, and Eveline Wandl-Vogt, 201–42. Wien, Hamburg: new academic press, 2020. [https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf](https://www.oeaw.ac.at/fileadmin/Institute/ACDH/OEBL/pdf/_apis_Buch_WEB.pdf).
*  Kaiser, Maximilian. “The ‘Who’s Who?’ Of Künstlerhaus Exhibitors. A Guide to Analyze Entangled Artists Biographies Based on Wikidata.” Edited by Anne Klammt, Antoine Courtin, and Olivier Bonfait. Humanités Numériques : De Nouveaux Récits En Histoire de l’art ?, Histoire de l’art, 87 (January 6, 2021): 125–37. 

## Resources
- [Katalog Der Internationalen Jubiläums-Kunst-Ausstellung Im Künstlerhause](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110120850004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1888.
- [Katalog Der XI. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219920060004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1880.
- [Katalog Der XII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110093900004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1881.
- [Katalog Der XIII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218099890004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1883.
- [Katalog Der XIV. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219527000004510), Künstlerhaus, hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1884.
- [Katalog Der XIX. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110134150004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1890.
- [Katalog Der XV. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110388430004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1885.
- [Katalog Der XVI. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110848720004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1886.
- [Katalog Der XVII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218245070004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1887.
- [Katalog Der XVIII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219897280004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1889.
- [Katalog Jubiläums-Kunstausstellung 1898](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218852490004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1898.
- [Katalog Der I. Grossen Internationalen Kunstausstellung Im Künstlerhause in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110523620004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1869.
- [Katalog Der II. Grossen Internationalen Kunstausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110649880004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1870.
- [Katalog Der IV. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110381400004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1872..
- [Katalog Der IX. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219313620004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1878.
- [Katalog Der V. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218202510004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1874.
- [Katalog Der VI. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218759000004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1875.
- [Katalog Der VII. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218915650004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1876.
- [Katalog Der VIII. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218174890004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1877.
- [Katalog Der X. Grossen Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218134930004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1879.
- [Katalog Der XX. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110678510004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1891.
- [Katalog Der XXI. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219178770004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1892.
- [Katalog Der XXII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110147410004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1893.
- [Katalog Der XXIII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110010940004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1895.
- [Katalog Der XXIV. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219733720004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1896.
- [Katalog Der XXV. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma219654820004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1897.
- [Katalog Der XXVI. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma218426490004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1899.
- [Katalog Der XXVII. Jahres-Ausstellung in Wien](https://belvedere-primo.hosted.exlibrisgroup.com/permalink/f/1vb66sb/43OGB_Alma2110592110004510), hrsg. v. Genossenschaft der bildenden Künstler Wien, Wien 1900.
