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

