# DPC-Centri-Storici-Rischio-Sismico
Progetto PON - Itinerari digitali - Collaborazione con ICCD per il censimento dei centri storici delle Regioni Basilicata, Calabria, Campania e Puglia

[![GitHub license](https://img.shields.io/badge/License-Creative%20Commons%20Attribution%204.0%20International-blue)](https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/blob/master/LICENSE)
[![GitHub commit](https://img.shields.io/github/last-commit/pcm-dpc/DPC-Aggregati-Strutturali-ITC-NordOvest)](https://github.com/pcm-dpc/DPC-Centri-Storici-Rischio-Sismico/commits/master)

## Avvisi
Il 2022-11-21 viene aperto il Repository.

## Sommario
[Struttura del Repository](#Struttura-del-repository)

[CENTRI STORICI](#CENTRI-STORICI)

[Introduzione](#Introduzione)

[Formato](#Formato)

[Sistema di riferimento](#Sistema-di-riferimento)

[Procedura per la generazione](#Procedura-per-la-generazione)

[Verifica di qualità](#Verifica-di-qualità)

[AREE AD ALTA CONCENTRAZIONE DI EDIFICATO ANTE 1945](#AREE-AD-ALTA-CONCENTRAZIONE-DI-EDIFICATO-ANTE-1945)

[Introduzione](#Introduzione)

[Sistema di riferimento](#Sistema-di-riferimento)

[Procedura per la generazione](#Procedura-per-la-generazione)

[Verifica di qualità](#Verifica-di-qualità)

[Verifica di qualità](#Verifica-di-qualità)

## Introduzione
Ad oggi l’unico censimento complessivo dei centri storici italiani è quello effettuata dall’ICCD agli inizi degli anni ’90 in applicazione della Legge n.84/90. L’ICCD, infatti, elaborò un progetto per realizzare un censimento dei centri storici presenti sul territorio nazionale (esclusa la Regione Sicilia, che ha una propria autonomia in materia di beni culturali), secondo lo standard e i criteri omogenei individuati in una specifica metodologia sperimentale. La parte relativa alla Regione Sicilia fu realizzata nel 1996 attraverso il Piano territoriale paesistico regionale, adottando la medesima metodologia sperimentale.
Nel frattempo erano stati avviati dei rapporti di collaborazione tra DPC e MIC nel cui ambito era stato individuato il centro storico come “unità di aggregazione elementare” più adatta a compiere valutazioni sull’esposizione al rischio del patrimonio storico di interesse comune alle due Amministrazioni. In tale contesto sono state messe a confronto le informazioni tratte dalle rispettive banche dati e verso la fine degli anni ’90, il DPC condivise anche il lavoro intrapreso dall’ICCD e dalla Regione Siciliana. integrandolo in un proprio modello schedografico per generare una specifica banca dati in cui la documentazione geografica dei centri storici venne approfondita rendendola più accurata e mantenendola aggiornata ai più recenti censimenti nazionali della popolazione e delle abitazioni effettuati dall’ISTAT. È stato così realizzato il sistema Centri Storici e Rischio Sismico (CSRS) in cui i centri storici in cui la caratterizzazione geografica riveste una particolare importanza, mediante una localizzazione puntuale e in forma poligonale. Inoltre, tramite un insieme di relazioni con altre informazioni territoriali, nel sistema CSRS è consentita anche una valutazione della dimensione territoriale dei centri stessi secondo una molteplicità di “scale di lettura”, dal livello specifico del centro e della località abitata che lo ospita, fino ai livelli territoriali superiori: comunali, provinciali e regionali.

## Formato
ll formato dei file di dati è shapefile. Ogni shapefile è formato da 4 file con le seguenti estensioni: .dbf, .prj, .shp, .shx.
La struttura dei file è la seguente:

| Nome campo                  | Definizione                       | Descrizione                           | 
|-----------------------------|-----------------------------------|---------------------------------------|
| **NOME**                        | Denominazione del centro storico | Nome attribuito nel censimento ICCD/Regione Sicilia oppure dal sistema CSRS |
| **ID_CS**                        | Identificativo del centro storico | Identificativo del centro storico ereditato dal censimento ICCD/Regione o attribuito dal sistema CSRS |
| **ISTATL**                        | Codice ISTAT completo della località abitata | Codifica creata nel sistema CSRS, riferita al censimento 2011 che compone i codici ISTAT della regione, provincia, comune e località abitata in cui ricade il centro storico (2 cifre: codice ISTAT Regione; 3 cifre: codice ISTAT Provincia; 3 cifre: codice ISTAT Comune;5 cifre codice ISTAT Località). Nel codice della Località la prima cifra indica la tipologia di località (1=centro, 2=nucleo, 3= località speciali, 4=case sparse) |
| **TOPONIMO_IGM**                        | Nome geografico | Nome geografico estratto dalla serie cartografica 25V (vecchia serie delle Tavolette IGM alla scala 1:25000) corrispondente al centro storico (ove associato per definirne la posizione) |
| **LONGITUDINE**                        |  | Coordinata X nel sistema di riferimento adottato |
| **LATITUDINE**                        |  | Coordinata y nel sistema di riferimento adottato |
| **IC(vedi nota)**                        | Interesse Culturale | Indicatore sintetico che prende in considerazione molteplici fattori, tutti concorrenti a determinare l’interesse di un centro storico dal punto di vista artistico, storico, ambientale e socio-antropologico. Per orientarsi rispetto ai valori numerici osservati, si riporta la suddivisione nelle classi di “valore” progressive adottata nel sistema CSRS per le rappresentazioni tematiche, secondo il seguente schema: 
| | |IC = 0                     Indicatore nullo |
| | |0 < IC < 2.41         Classe E |
| | |2.41 < IC < 9.5      Classe D |
| | |9.5 < IC < 31.37    Classe C |
| | |31.37 < IC <= 100 Classe B |
| | |IC > 100                 Classe A |
| **EC(vedi nota)**                        | Esposizione Culturale | Indicatore sintetico, che mette in relazione l’Interesse Culturale di un centro storico con il numero di edifici ante 1945 del medesimo centro storico rispetto al numero massimo di edifici ante 1945 in Italia |

(nota) Questi attributi non vengono riportati nel file scaricabile da Github in quanto indicatori “dinamici”, ovvero soggetti a variazioni in base ai fattori che li determinano e che sono calcolati in base alla valorizzazione delle schede relative ai vari centri storici nel sistema CSRS. Sono pertanto disponibili nei Servizi di rete WMS e WFS. Per i dettagli si rimanda alla Relazione Finale e in particolare ai documenti [1], [2] e [7] della Bibliografia.

## Sistema di riferimento
Il sistema di riferimento ufficiale per l’Italia è il sistema ETRF2000 (all’epoca in cui venne definito 2008.0) ed è un obbligo per le Pubbliche Amministrazioni adottarlo in base a quanto stabilito dal DM 10 novembre 2011 “Adozione del Sistema di riferimento geodetico nazionale” (https://www.gazzettaufficiale.it/eli/id/2012/02/27/12A01799/sg).
Per facilitare il corretto utilizzo dei sistemi di riferimento all’interno dei software GIS, l’Istituto Geografico Militare (IGM) ha pubblicato una apposita Nota (https://www.igmi.org/++theme++igm/pdf/nuova_nota_EPSG.pdf), nella quale – in particolare – viene consigliato l’uso dei sistemi proiettati dell’RDN2008. Nel caso della Carta Nazionale degli Aggregati Strutturali pertanto è stato adottato il sistema proiettato RDN2008 / Italy zone (E-N) (EPSG7794).
Per facilitare e standardizzare le procedure di conversione tra i sistemi di riferimenti, infine, l’IGM ha reso disponibili (https://www.igmi.org/++theme++igm/pdf/nuovi_PRJ.zip) i file .prj da associare ai file cartografici e il Comitato Permanente Sistemi Geografici (CPSG) del Centro Interregionale per i Sistemi Informatici Geografici e Statistici (CISIS) ha messo a disposizione di tutti gli utenti il Programma ConveRgo (Il software (realizzato dall’Ing. V. Cima e disponibile in https://www.cisis.it/?page_id=3214 ) consente di eseguire le trasformazioni di coordinate fra i vari sistemi di riferimento in cui sono espressi i dati geografici (ROMA40, ED50, ETRS89 nelle due realizzazioni ETRF89 e ETRF2000), considerando anche i rispettivi sistemi cartografici (Gauss-Boaga, UTM-ED50, UTM-ETRF89 e UTM-ETRF2000).).
Pertanto, utilizzando il software ConveRgo e adottando il ,prj corrispondente al sistema prima nominato RDN2008 / Italy zone (E-N), ovvero l’EPSG 7794, sono stati trasformati i dati estratti dal sistema CSRS dai loro sistema di riferimento originale (WGS84) in quello di destinazione sopraindicato.

## Procedura per la generazione
La metodologia inizialmente adottata dall’ICCD è basata sul confronto delle località abitate presenti nel primo censimento nazionale disponibile del 1881 con quello del 1981. Tale confronto è stato poi integrato con i dati disponibili del censimento del 1936 e, per i territori ancora extranazionali al 1881, con quelli del censimento del 1921. Successivamente il DPC ha lavorato sull’affinamento del posizionamento geografico basandosi in particolare sull’associazione dei singoli centri con le località abitate ISTAT e con i toponimi dell’Istituto Geografico Militare, tratti dalla vecchia serie della cartografia topografica alla scala 1:25000. Tale affinamento è consistito anche nel progressivo allineamento dei dati cartografici alle varie edizioni del censimento della popolazione e delle abitazioni effettuato da ISTAT (1991, 2001 e 2011).

## Verifica di qualità
A livello di primo inserimento, è stata mantenuta la posizione assegnata dall’ICCD. Nel sistema CSRS è possibile modificare la posizione associandola ad un toponimo IGM oppure ad una posizione stabilita dall’utente con riferimento all’ortofoto del Ministero dell’Ambiente. Una speciale occasione di verifica complessiva è stata offerta dalla collaborazione avviata tra il DPC e l’ICCD per il Progetto PON “Itinerari Digitali” nelle Regioni Basilicata, Calabria, Campania e Puglia. In questa occasione, l’applicazione della metodologia per la generazione delle aree ad elevata concentrazione di edificato storico (ante 1945) in corrispondenza dei centri storici presenti nel sistema CSRS ha consentito una loro più accurata revisione mediante cancellazione, inserimento, modifica posizionale dei centri storici presenti in quelle regioni. Analogamente, in precedenza, una collaborazione con la Soprintendenza per i beni culturali della Provincia Autonoma di Trento aveva consentito una ampia revisione anche in quell’area. Così pure nell’area vulcanica dei Campi Flegrei e del Vesuvio, in occasione dell’avvio delle attività per la pianificazione di emergenza per rischio vulcanico della zona rossa nel settore beni culturali. Nelle restanti porzioni del territorio le verifiche sono state fatte con livelli differenti di dettaglio, dando priorità alle aree a più elevato rischio sismico.
