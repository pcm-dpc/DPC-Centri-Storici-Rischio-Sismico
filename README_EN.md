<img src="Documenti/LogoGitHub.PNG" alt="DPC-Centri-Storici-Rischio-Sismico" data-canonical-src="Documenti/LogoGitHub.PNG" width="800" />

# DPC-Centri-Storici-Rischio-Sismico
## Repository containing some datasets of the Historical Centers and Seismic Risk Web System (CSRS)
Collaboration between the Civil Protection Department of the Presidency of the Council of Ministers (DPC) and the Institute for Cataloguing and Documentation of the Ministry of Culture (ICCD), including the one in the context of the PON Project "Digital Paths" on the historical town centers of Regions of Basilicata, Calabria, Campania and Puglia
[![GitHub license](https://img.shields.io/badge/License-Creative%20Commons%20Attribution%204.0%20International-blue)](https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/blob/master/LICENSE)
[![GitHub commit](https://img.shields.io/github/last-commit/pcm-dpc/DPC-Aggregati-Strutturali-ITC-NordOvest)](https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/commits/master)

## Warnings
On 2022-12-05 the Repository is opened.

## Summary

[Repository structure](#Repository structure)

[1 HISTORICAL TOWN CENTERS](#1- HISTORICAL TOWN CENTERS)

[1-1 Introduction](#1-1-Introduction)

[1-2 Format](#1-2-Format)

[1-3 Reference system](#1-3-Reference-syustem)

[1-4 Generation procedure](#1-4-Generation-procedure)

[1-5 Quality checks](#1-5-Quality-checks)

[2 AREAS WITH A HIGH CONCENTRATION OF PRE-1945 BUILT-UP](#2- AREAS-WITH-A-HIGH-CONCENTRATION-OF-PRE-1945-BUILT-UP)

[2-1 Introduction](#2-1-Introduction)

[2-2 Format](#2-2-Format)

[2-3 Reference system](#2-3-Reference-syustem)

[2-4 Generation procedure](#2-4-Generation-procedure)

[2-5 Quality checks](#2-5-Quality-checks)

[NETWORK SERVICES OGC](#NETWORK-SERVICES-OGC)

[METADATA](#METADATA)

[ACTOR INVOLVED](#ACTORS-INVOLVED)

[LICENSE](#LICENSE)



## Repository structure
The repository is organized into two main folders: Data and Documents. The Data are then organized into the various themes present and in the respective formats envisaged for publication. The Documents contain the overall report, and other publications of interest.
```
DPC-Centri-Storici-Rischio-Sismico/
│
├── Dati/
│   ├── CentriStorici/
│   │   ├── Shapefile/
│   │   │   ├── shapefile CS
│   │   ├── Geojson/
│   │   │   ├── geojson CS
│   ├── AreeEdificiAnte1945/
│   │   ├── Shapefile/
│   │   │   ├── shapefile Aree
│   │   ├── Geojson/
│   │   │   ├── geojson Aree
├── Documenti/
│   ├── report & paper/
```
## 1 HISTORICAL TOWN CENTERS.
## 1-1 Introduction
To date, the only comprehensive census of Italy's historical town centers is the one carried out by the ICCD in the early 1990s in application of Law No. 84/90. The ICCD, in fact, developed a project aimed at producing a census of the historical towns present across national territory (excluding the Region of Sicily, which is autonomous in matters of cultural heritage), according to a standard and consistent criteria identified through a specific experimental methodology. The part concerning Sicily was carried out in 1996 through the Regional Landscape Territorial Plan, adopting the same experimental methodology

In the meantime, DPC and MIC established fruitful collaborations in which framework the historical town centers became identified as “elementary aggregation units" most suitable for making risk exposure assessments of the historic heritage of common interest to the two Administrations. In this context, information drawn from the respective databases was compared, and in the late 1990s, the DPC shared the work undertaken by the ICCD and the Sicilian Region, integrating it into its own record model to generate a specific database. In this database the geographic documentation of historical town centers was further analyzed, made more accurate and updated with the most recent national population and housing censuses carried out by ISTAT. Thus, the Historical town centers and Seismic Risk System (CSRS) was created , highlighting  the geographic position of historical town centers identified by means of a location point and in polygonal form. In addition, by a series of comparative studies with other spatial information, the CSRS system also allowed an evaluation of the territorial dimension of the centers themselves according to a range  of "reading scales," from the specific level of the center and its inhabited area, up to higher territorial administrative levels: municipal, provincial and regional.

## 1-2 Format
The format of the data files is shapefile. Each shapefile consists of 4 files with the following extensions: .dbf, .prj, .shp, .shx. The geojson format is also added.
The structure of the files is as follows:
| Field Name                  | Definition                      | Description                   | 
|-----------------------------|-----------------------------------|---------------------------------------|
| **NOMECS**                        | Name of the historical town center | Name given in the ICCD/Region of Sicily census or by the CSRS system |
| **ID_CS**                        | Identifier of the historical town center | I Identifier of the historical town center inherited from the ICCD/Region census or assigned by the CSRS system |
| **ISTATL**                        | ISTAT complete Code of the inhabited area | ISTAT code referring to the 2011 census of the region, province, municipality and inhabited area in which the historical town center falls (2 digits: ISTAT Region code; 3 digits: ISTAT Province code; 3 digits: ISTAT Municipality code; 5 digits ISTAT Inhabited area code). In the Inhabited area code, the first digit indicates the type of locality (1=center, 2=nucleus, 3=special locality, 4=scattered houses) |
| **TOPONIMO_IGM**                        | Geographic name | Geographic name taken from the cartographic series 25V (Old series of the Tables of the Geographical Military Institute – IGM at the scale 1:25000) corresponding to the historical town center (when associated to identify the position) |
| **LONGITUDINE**                        |  | X Coordinate in the reference system |
| **LATITUDINE**                        |  | Y Coordinate in the reference system |
| **IC(vedi nota)**                        | Cultural Interest | A synthetic indicator that takes into consideration multiple factors, all of which contribute to determine the interest of a historical town center from the artistic, historical, environmental and socio-anthropological points of view. To orient oneself with respect to the numerical values observed, the division into the progressive "value" classes adopted in the CSRS system for the thematic representations is reported, according to the following schema: 
| | |IC = 0                     null |
| | |0 < IC < 2.41         Class E |
| | |2.41 < IC < 9.5      Class D |
| | |9.5 < IC < 31.37    Class C |
| | |31.37 < IC <= 100 Class B |
| | |IC > 100                 Class A |
| **EC(see footnote)**                        | Cultural Exposure | Synthetic indicator, which relates the Cultural Interest of a historical town center to the number of pre-1945 buildings in the same historical town center compared to the maximum number of pre-1945 buildings in Italy |
(footnote) These attributes are not reported in the downloadable file from Github because they are "dynamic" indicators, i.e., subject to change based on the factors that determine them and are calculated based on the valorization of the tabs  related to the various historical centers in the CSRS system. They are therefore available in the W*S Network Services. For details, see the Final Report (https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/blob/main/Documenti/CentriStorici_ProgettoPON_Finale.pdf  ) and in particular documents [1], [2] and [7] in the Bibliography. 
## 1-3 Reference system
The official reference system for Italy is the ETRF2000 system (at the time it was defined as 2008.0) and it is an obligation for Public Administrations to adopt it according to the provisions of the November 10, 2011 DM "Adoption of the National Geodetic Reference System" (https://www.gazzettaufficiale.it/eli/id/2012/02/27/12A01799/sg).
To facilitate the correct use of reference systems within GIS software, the Military Geographical Institute (IGM) has published a special Note (https://www.igmi.org/++theme++igm/pdf/new_note_EPSG.pdf), in which - in particular - the use of the projected systems of RDN2008 is recommended. In the case of the Historical Town Centers therefore the projected system RDN2008 / Italy zone (E-N) (EPSG7794) was adopted.
Finally, in order to facilitate and standardize conversion procedures between reference systems, the IGM has made available (https://www.igmi.org/++theme++igm/pdf/new_PRJ.zipper) prj files to be associated with cartographic files. The Geographic Systems Standing Committee (GSCP) of the Interregional Center for Geographic and Statistical Information Systems (CISIS) has made available to all users the ConveRgo Program (The software (created by Eng. V. Cima and available at https://www.cisis.it//page_id=3214 )  makes it possible to perform coordinate transformations between the various reference systems in which geographic data are expressed (ROMA40, ED50, ETRS89 in the two realizations ETRF89 and ETRF2000), while also considering the respective map systems (Gauss-Boaga, UTM-ED50, UTM-ETRF89 and UTM-ETRF2000).)
Therefore, using ConveRgo software and adopting the prj corresponding to the previously named RDN2008 / Italy zone (E-N) system, i.e., EPSG 7794, the data extracted from the CSRS system were transformed from their original reference systems (WGS84) into the target system mentioned above.

## 1-4 Generation procedure
The methodology initially adopted by the ICCD is based on a comparison of the inhabited localities found in the first available national census of 1881 with that of 1981. This comparison was then supplemented with available data from the 1936 census and, for territories still extra-national to 1881, with those from the 1921 census. Subsequently, the DPC worked on the refinement of geographic positioning based in particular on the association of individual centers with ISTAT inhabited localities and with the toponyms of the Military Geographical Institute, taken from the old series of topographic cartography at the scale 1:25000. This refinement also consisted of the gradual alignment of map data with the various editions of the population and housing census conducted by ISTAT (1991, 2001 and 2011).

## 1-5 Quality Checks
At the first entry level, the position assigned by the ICCD was maintained. In the CSRS system, it is possible to change the position by associating it with an IGM toponym or with a position established by the user with reference to the orthophoto of the Ministry of the Environment. A special general assessment opportunity was provided by the collaboration initiated between the DPC and the ICCD for the PON Project "Digital Paths" in the Basilicata, Calabria, Campania and Apulia Regions. On this occasion, the application of the methodology for the generation of areas with a high concentration of historic built-up areas (pre-1945) in correspondence with the historical town centers present in the CSRS system allowed for their more accurate review through deletion, insertion, and positional modification of the historical town centers present in those regions. Similarly, previously, a collaboration with the Superintendence for Cultural Heritage of the Autonomous Province of Trento had enabled extensive revision in that area as well. So, too, in the volcanic area of the Phlegraean Fields and Vesuvius, on the occasion of the start of activities for emergency planning for volcanic risk of the red zone in the cultural heritage sector. In the remaining portions of the territory, checks were conducted at different levels of detail, giving priority to areas of higher seismic risk.


## 2 AREAS WITH A HIGH CONCENTRATION OF PRE-1945 BUILT-UP
## 2-1 Introduction
Following the experimentation on the perimeters of the historical town centers of the Molise Region, carried out using cadastral cartographic data provided by the Agenzia delle Entrate and the subsequent similar elaborations for the purposes of the PON Project "Digital Paths" in the Basilicata, Calabria, Campania and Apulia Regions, the definition of the polygons generated for the historical town centers was better specified. Rather than a perimeter of the center, in fact, these polygons identify areas with a high concentration of pre-1945 built-up area of historical interest, because they are located within historical town centers. The rapid approach adopted by the DPC for the generation of these areas facilitates possible subsequent additions of identifiers, leading thanks to this combination of observations, to a more in-depth and facilitated analysis of Italy’s urban centers.


## 2-2 Format 
The format of the data files is shapefile. Each shapefile consists of 4 files with the following extensions: .dbf, .prj, .shp, .shx. The geojson format is also added.

The structure of the files is as follows:
| Field Name                  | Definition                      | Description                   | 
|-----------------------------|-----------------------------------|---------------------------------------|
| **ID_CS**                        | ID of the historical town center | Identifier of the historical town center originating from the ICCD/Region census or attributed to the CSRS system |
| **ISTATL**                        | Complete ISTAT Code  of the inhabited area | ISTAT code of the 2011 census of the region, province, municipality and inhabited area within the historical town center (2 digits: Regional ISTAT code; 3 digits: ISTAT Province code; 3 digits: ISTAT Municipality code; 5 digits ISTAT Inhabited area code). In the Inhabited area code, the first digit indicates the type of area (1=center, 2=nucleus, 3=special inhabited areas, 4=scattered houses) |

## 2-3 Reference system
The official reference system for Italy is the ETRF2000 system (at the time it was defined as 2008.0) and it is an obligation for Public Administrations to adopt it according to the provisions of the November 10, 2011 DM "Adoption of the National Geodetic Reference System" (https://www.gazzettaufficiale.it/eli/id/2012/02/27/12A01799/sg).
To facilitate the correct use of reference systems within GIS software, the Military Geographical Institute (IGM) has published a special Note (https://www.igmi.org/++theme++igm/pdf/new_note_EPSG.pdf), in which - in particular - the use of the projected systems of RDN2008 is recommended. In the case of the Areas with a high concentration of pre-1945 built-up therefore the projected system RDN2008 / Italy zone (E-N) (EPSG7794) was adopted.
Finally, in order to facilitate and standardize conversion procedures between reference systems, the IGM has made available (https://www.igmi.org/++theme++igm/pdf/new_PRJ.zipper) prj files to be associated with cartographic files. The Geographic Systems Standing Committee (GSCP) of the Interregional Center for Geographic and Statistical Information Systems (CISIS) has made available to all users the ConveRgo Program (The software (created by Eng. V. Cima and available at https://www.cisis.it//page_id=3214 )  makes it possible to perform coordinate transformations between the various reference systems in which geographic data are expressed (ROMA40, ED50, ETRS89 in the two realizations ETRF89 and ETRF2000), while also considering the respective map systems (Gauss-Boaga, UTM-ED50, UTM-ETRF89 and UTM-ETRF2000).)
Therefore, using ConveRgo software and adopting the prj corresponding to the previously named RDN2008 / Italy zone (E-N) system, i.e., EPSG 7794, the data extracted from the CSRS system were transformed from their original reference systems (WGS84) into the target system mentioned above.

## 2-4 Generation procedure
For the methodology adopted, please refer to what is reported in https://www.agenziaentrate.gov.it/portale/documents/20143/4042296/5_Ferrante_interno_OK.pdf/c9481131-6e16-1688-69c5-5e8251341432 , for the general aspects, as well as to the Final Report (https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/blob/main/Documenti/CentriStorici_ProgettoPON_Finale.pdf  ) for details on what was done on the individual provinces of the four regions involved.

## 2-5 Quality checks
Besides the application of the automatic procedures for the generation of the polygons, essentially manual quality checks are subsequently applied to evaluate and, where necessary, modify the geometries generated by the algorithm, as well as to verify and/or integrate the associations with the historical town centers generated automatically.
The experimental phase, however, does not seem to be over yet, especially taking into account the extreme heterogeneity of the Italian built landscape. In regions such as Campania and Calabria, especially in areas subject to greater building development, the work of manual editing (post processing) for validation has been very onerous as well as necessary. This has led to a final rendering of the generated dataset, which in some cases may appear uneven with respect to the same product in different areas. The management and resolution of various cases and unprecedented situations that occurred during construction also contributed - although in a limited way - to adapting and modifying the criteria for using and interpreting the data. An accurate verification of the results achieved so far is therefore considered useful, also through the hoped-for integration with further data, but also the extension (in the future) of the application of the procedure to other areas of the national territory, starting from those at higher seismic risk. For the purposes of the checks mentioned above, the work of comparison, with the delimitations of some historical town centers produced in the various plans available for the area under study,  carried out by Cosmo Mercuri (DPC) and presented at the conference held in June 2022, as well as the activity of compiling the SCAN (cultural heritage data sheet) forms by the ICCD has proved extremely useful.

## NETWORK SERVICES

In the case of territorial data, given the technical rules referred to in the INSPIRE guidelines for the implementation of network services referred to in art. 7 paragraph 1 of Legislative Decree-32-2010, these network services can be considered as APIs in consideration of the fact that within the framework of the Guidelines on technical interoperability of the PAs, accepting the nomenclature in use at European level and more generally in the international context, the generic term API is used to indicate indifferently Web APIs, web services and REST APIs (Open Data Guidelines).

**Download service**

https://servizi.protezionecivile.it/geoserver/CSRS/ows?service=wfs&version=1.1.0&request=GetCapabilities

## METADATA

The two published datasets are documented in compliance with the provisions of the Guidelines Technical rules for defining and updating the
content of the National Spatial Data Directory, Version 2.0.1 adopted with Resolution no. 50/2022 of the DG of AgID pursuant to art. 71 of Legislative Decree 7 March 2005, n. 82 and subsequent amendments (Digital Administration Code).

**Historical town centers:**

https://dati.protezionecivile.it/geoportalDPC/rest/document?id=PCM:111:20221114:100000

**Areas with a hich concentration of pre 1945 build up:**

https://dati.protezionecivile.it/geoportalDPC/rest/document?id=PCM:111bis:20221114:100900

## ACTORS INVOLVED
Attività istituzionale realizzata in collaborazione tra il Servizio Sistemi Informativi e di comunicazione dell’Ufficio Risorse umane e strumentali e servizi generali di funzionamento (RUS) e il Servizio Rilievo del danno dell’Ufficio Attività per il superamento dell’emergenza (POST), entrambi appartenenti al Dipartimento della protezione civile della Presidenza del Consiglio dei Ministri (DPC) e l’Istituto per il Catalogo e la Documentazione del Ministero della Cultura (ICCD).

**Edited by:**

Pierluigi Cara

**Inter-institutional Technical Table for the management and development of databases for post-emergency cultural heritage interventions**

DPC: Pierluigi Cara e Cosmo Mercuri
ICR: Maria Elena Corrado
ICCD: Antonella Negri
DG Sicurezza del Patrimonio: Carlo Cacace

**Acknowledgements:**

Maurizio Ambrosanio (Agenzia delle Entrate - Direzione Centrale Servizi Catastali, Cartografici e di Pubblicità Immobiliare, Carlo Birrozzi (ICCD), Chiara Veninata (ICCD) e Maria Letizia Mancinelli (ICCD).

## LICENSE

[CC-BY-4.0](https://creativecommons.org/licenses/by/4.0/deed.it) - [Visualizza licenza](https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/blob/master/LICENSE.md)

**Historical town centers**

The owner of the dataset relating to historic centers is the Presidency of the Council of Ministers - Department of Civil Protection, the attribution citation must also refer to the Central Institute for Cataloging and Documentation of the Ministry of Culture and the Department of Cultural Heritage and 'Sicilian identity of the Assessorate of Cultural Heritage and Sicilian Identity of the Sicily Region.

**Areas with a hich concentration of pre 1945 build up**

The owner of the dataset relating to areas with a high concentration of buildings before 1945 is the Presidency of the Council of Ministers - Civil Protection Department, the attribution citation must also refer to the Revenue Agency as the source of the processed data. The same Agency must consider itself relieved of any use deriving from the processing of data produced by the Department of Civil Protection.



