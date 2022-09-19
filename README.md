# Künstlerhaus Wien Network
 This dataset contains information about exhibitor networks gathered by the evaluation of catalogues of the annual exhibitions of the “Association of Fine Artists Vienna, Künstlerhaus”. It includes not only biographical data about Austrian artists but also international participants of these events. Currently, the dataset covers mainly the period from 1869 to 1900 but will be hopefully expanded in the future. Persons, who could be identified, were referenced with identifiers from linked-open-data-resources such as Wikidata, GND, ULAN, RKDartistsID. This has been done with Institutions (GND, Wikidata) and places (Wikidata, GeoNames) so far it was possible.

## Dataset
1. Biographical Data
2. Graph File
   * Edges Table
   * Nodes Table
3. interactive Network Graph

### edges table
| column title | definition |
|--------------|------------|
| Id | unique identifier for the network graph (prefix p for persons, prefix e for exhibitions)|
| source | node id for the network graph, always persons |
| target | node id for the network graph, always exhibitions |
| exhibitor | label of the source node, person name |
| exhibitor_id | database id for biographical data |
| exhibition | label of the target node, exhibition title |
| exhibiton_id | database id for biographical data |
| year | year in which the exhibition was staged |
| name_from_catalogue | original writting of the exhibitor name according to the catalogue |
| place_name | place of residence as stated in the catalogue |

### nodes table

| column title | definition |
|--------------|------------|
| Id | unique identifier for the network graph (prefix p for persons, prefix e for exhibitions)|
| Label | name of an exhibitor or exhibition |
| wikidata | identifier of an wikidata entity |
| date of birth| date when an exhibitor was born, based on wikidata |
| date of death | date when an exhibitor has died, based on wikidata |
| place of birth | place where an exhibitor has been born, based on wikidata |
| place of death | place where an exhibitor has died, based on wikidata |
| occupation | one or more occupations of an exhibitor, separated by an semicolon, based on wikidata |
| educated at | listing of educational institutions where an exhibitor has been educated at , separated by a semicolon, based on wikidata |
| gender | male, female or unknown |
| wikipedia | Link to english, spanish, german or french wikipedia page of an exhibitor |
| type | two types of nodes “persons” and “exhibitions” |

### Interactive Network Graph

![image of network node](https://github.com/m-kaiser/Kuenstlerhaus-Wien-Network/blob/ea88a274049c99b50ecb702349ab64669cb5337e/Graph%20File/kuenstlerhaus_wien_network_image1.png)
> Screenshot of the interactive Network Graph

[Try it out!](https://ouestware.gitlab.io/retina/beta/#/graph/?url=https%3A%2F%2Fgist.githubusercontent.com%2Fm-kaiser%2F10ad8656256ab0af66df00723e171d8a%2Fraw%2F6c3319a38f617dcf8c2356f5021b22ae6a01d3b7%2Fkuenstlerhaus_network.gexf&n=p_1873&sa=r&ca[]=g&ca[]=t&fa[]=dd&fa[]=pb&fa[]=pd&fa[]=o&fa[]=e&fa[]=db&st[]=t&st[]=g&st[]=o&st[]=wd&st[]=db&st[]=pb&st[]=dd&st[]=pd&st[]=e&st[]=wp&st[]=r&ec=o)

