---
title: Trasformazione Estrazione termini | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextractiontrans.f1
helpviewer_keywords:
- word boundaries [Integration Services]
- extracting data [Integration Services]
- sentence boundaries
- word extractions [Integration Services]
- Term Extraction transformation
- tagging words
- normalized data [Integration Services]
- tokenizing text [Integration Services]
- parts of speech [Integration Services]
- text extraction [Integration Services]
- term extractions [Integration Services]
- stemming words [Integration Services]
ms.assetid: d0821526-1603-4ea6-8322-2d901568fbeb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8215b53de7da43bbdbcbe29a9bb7f5ad8edc0d61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722924"
---
# <a name="term-extraction-transformation"></a>Estrazione termini - trasformazione
  La trasformazione Estrazione termini consente di estrarre termini da un testo in una colonna di input di una trasformazione e quindi scrivere tali termini in una colonna di output della trasformazione. La trasformazione è applicabile solo a testo in lingua inglese, utilizza un dizionario inglese interno e le proprie informazioni sulla lingua inglese.  
  
 È possibile utilizzare la trasformazione Estrazione termini per individuare il contenuto di un set di dati. Il testo contenuto nei messaggi di posta elettronica, ad esempio, può fornire utili commenti e suggerimenti sui prodotti. È pertanto possibile utilizzare la trasformazione Estrazione termini per estrarre gli argomenti di discussione dei messaggi al fine di analizzare tali commenti e suggerimenti.  
  
## <a name="extracted-terms-and-data-types"></a>Tipi di dati e termini estratti  
 La trasformazione Estrazione termini può essere configurata in modo da estrarre solo sostantivi, solo sintagmi nominali o entrambi. Un sostantivo è costituito da una sola parola, mentre un sintagma nominale include almeno due parole, di cui una costituita da un sostantivo e l'altra da un sostantivo o da un aggettivo. Ad esempio, se la trasformazione usa l'opzione per i soli sostantivi, estrae termini come *bicicletta* e *paesaggio*. Se la trasformazione usa l'opzione per i sintagmi nominali, estrae termini come *nuova bicicletta blu*, *casco da bicicletta*e *biciclette confezionate*.  
  
 Gli articoli e i pronomi non vengono estratti. Ad esempio, la trasformazione Estrazione termini estrae il termine *bicicletta* da *la bicicletta*, *la mia bicicletta*e *quella bicicletta*.  
  
 Per ogni termine estratto la trasformazione Estrazione termini genera un punteggio, costituito da un valore TFIDF o dalla frequenza della riga, che indica il numero di corrispondenze con il termine normalizzato presenti nell'input. In entrambi i casi, il punteggio viene rappresentato da un numero reale che è maggiore di 0. Ad esempio, il punteggio TFIDF potrebbe avere il valore 0,5 e la frequenza sarebbe un valore come 1,0 o 2,0.  
  
 L'output della trasformazione Estrazione termini include solo due colonne, una con i termini estratti e l'altra con il punteggio. I nomi predefiniti delle colonne sono **termini** e `Score` . Poiché la colonna di testo nell'input può contenere più termini, l'output della trasformazione Estrazione termini include in genere un numero di righe maggiore rispetto all'input.  
  
 Se i termini estratti vengono scritti in una tabella, potranno essere utilizzati da altre trasformazioni di ricerca, ad esempio le trasformazioni Ricerca termini, Ricerca fuzzy e Ricerca.  
  
 La trasformazione Estrazione termini può essere applicata solo a testo contenuto in colonne con tipo di dati DT_WSTR o DT_NTEXT. Se una colonna contiene testo ma non ha uno di questi tipi di dati, sarà possibile utilizzare la trasformazione Conversione dati per aggiungere al flusso di dati una colonna con tipo di dati DT_WSTR o DT_NTEXT e copiare nella nuova colonna i valori della colonna originale. L'output della trasformazione Conversione dati può essere quindi utilizzato come input della trasformazione Estrazione termini. Per altre informazioni, vedere [Trasformazione Conversione dati](data-conversion-transformation.md).  
  
## <a name="exclusion-terms"></a>Termini di esclusione  
 Facoltativamente, la trasformazione Estrazione termini può fare riferimento a una colonna in una tabella che contiene termini di esclusione, ovvero parole che la trasformazione deve ignorare durante l'estrazione dei termini da un set di dati. Ciò è utile quando è già stato identificato un set di termini non rilevanti per un'azienda o un settore specifico, in genere perché si presentano con una frequenza tale da non essere significativi. Durante l'estrazione di termini da un set di dati che contiene informazioni sul servizio di assistenza clienti per una particolare marca di automobili, ad esempio, è possibile escludere la marca stessa, perché viene citata troppo spesso per essere significativa. I valori nell'elenco di esclusione possono essere pertanto personalizzati in base al set di dati che si sta utilizzando.  
  
 Quando si aggiunge un termine all'elenco di esclusioni, vengono esclusi anche tutti i termini, ovvero parole o sintagmi nominali, che contengono tale termine. Ad esempio, se l'elenco di esclusione include la singola parola *dati*, verranno esclusi anche tutti i termini che contengono questa parola, come *dati*, *origine dati* *integrità dei dati*e *convalida dei dati* . Per escludere solo i composti che contengono la parola *dati*, è necessario aggiungerli in modo esplicito all'elenco di esclusione. Ad esempio, per estrarre le incidenze di *dati*escludendo *convalida dei dati*, è necessario aggiungere *convalida dei dati* all'elenco di esclusione e assicurarsi che la parola *dati* venga rimossa dall'elenco.  
  
 La tabella di riferimento deve essere una tabella di un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o di Access. La trasformazione Estrazione termini utilizza una connessione OLE DB distinta per connettersi alla tabella di riferimento. Per altre informazioni, vedere [Gestione connessione OLE DB](../../connection-manager/ole-db-connection-manager.md).  
  
 La trasformazione Estrazione termini funziona in una modalità con pre-memorizzazione nella cache completa. In fase di esecuzione legge i termini di esclusione dalla tabella di riferimento e li archivia nella propria memoria privata, prima di elaborare le righe di input della trasformazione.  
  
## <a name="extraction-of-terms-from-text"></a>Estrazione di termini da un testo  
 Per estrarre termini da un testo, la trasformazione Estrazione termini esegue le operazioni seguenti.  
  
### <a name="identification-of-words"></a>Identificazione di parole  
 La trasformazione Estrazione termini identifica innanzitutto le parole eseguendo le operazioni seguenti:  
  
-   Suddivisione del testo in parole, tramite spazi, interruzioni di riga e altri caratteri di terminazione delle parole utilizzati nella lingua inglese. Ad esempio, segni di punteggiatura come *?* e *:* sono caratteri di word breaking.  
  
-   Mantenimento delle parole legate da segni meno o caratteri di sottolineatura. Le parole *snap-in* e *front-end* , ad esempio, restano come unica parola.  
  
-   Mantenimento come parola unica degli acronimi che includono punti. Ad esempio, l'azienda *A.B.C* Company verrebbe suddivisa in token come **ABC** e **Company**.  
  
-   Suddivisione delle parole in corrispondenza di caratteri speciali. Ad esempio, la parola *data/ora* viene estratta come *data* e *ora*, la parola *(bicicletta)* come *bicicletta*e C# viene considerato C. I caratteri speciali vengono ignorati e non possono essere lessicalizzati.  
  
-   Riconoscimento dei casi in cui i caratteri speciali, come l'apostrofo, non devono essere utilizzati per suddividere le parole. Ad esempio, la parola inglese *bicycle's* non viene suddivisa in due parole e produce il singolo termine *bicycle* (sostantivo).  
  
-   Suddivisione di espressioni di data e ora, espressioni di valuta, indirizzi di posta elettronica e indirizzi postali. Ad esempio, la data *31 gennaio 2004* viene separata in tre token, *31*, *gennaio*e *2004*.  
  
### <a name="tagged-words"></a>Parole con tag  
 La trasformazione Estrazione termini applica un tag a ogni parola in modo da identificarla come una delle parti del discorso seguenti:  
  
-   Sostantivo in forma singolare, ad esempio *bicicletta* e *pomodoro*.  
  
-   Sostantivo in forma plurale, ad esempio *biciclette* e *pomodori*. Tutti i sostantivi in forma plurale non lemmatizzati vengono sottoposti a stemming.  
  
-   Nome proprio in forma singolare, ad esempio *Tintoretto* e *sabato*.  
  
-   Nome proprio in forma plurale, ad esempio *Tintoretti* e *sabati*. È possibile eseguire lo stemming dei soli nomi propri che fanno parte del lessico interno, limitato alle parole italiane standard.  
  
-   Aggettivo, ad esempio *blu*.  
  
-   Aggettivo comparativo per il confronto di due elementi, ad esempio *maggiore* e *migliore*.  
  
-   Aggettivo superlativo che identifica un elemento con una qualità di livello superiore o inferiore a quello di almeno altri due elementi, ad esempio *massimo* e *ottimo*.  
  
-   Numero, ad esempio *62* e *2004*.  
  
 Le parole non identificate come una delle parti del discorso precedenti vengono ignorate. Questo avviene ad esempio per verbi e pronomi.  
  
> [!NOTE]  
>  La classificazione delle parti del discorso è basata su un modello statistico e potrebbe non essere perfettamente accurata.  
  
 Se la trasformazione Estrazione termini è configurata in modo da estrarre solo i sostantivi, verranno estratte solo le parole classificate come forme singolari o plurali di sostantivi e nomi propri.  
  
 Se la trasformazione Estrazione termini è configurata in modo da estrarre solo sintagmi nominali, è possibile che parole classificate come sostantivi, nomi propri, aggettivi e numeri vengano combinate in modo da formare un sintagma nominale, che tuttavia deve includere almeno una parola classificata come forma singolare o plurale di un sostantivo o nome proprio. Ad esempio, il sintagma nominale *altitudine superiore* combina una parola classificata come aggettivo superlativo (*superiore*) e una parola classificata come sostantivo (*altitudine*).  
  
 Se la trasformazione Estrazione termini è configurata in modo da estrarre sia sostantivi che sintagmi nominali, verranno applicate sia le regole relative ai sostantivi che quelle relative ai sintagmi nominali. Ad esempio, dal testo *molte belle biciclette blu* la trasformazione estrae *bicicletta* e *belle biciclette blu*.  
  
> [!NOTE]  
>  I termini estratti sono soggetti alle soglie di lunghezza e frequenza utilizzate dalla trasformazione.  
  
### <a name="stemmed-words"></a>Parole in forma flessiva  
 La trasformazione Estrazione termini esegue lo stemming (ricerca di radici di parole) dei sostantivi in modo da estrarre solo la forma singolare. Ad esempio, la trasformazione estrae *uomo* da *uomini*, *camicia* da *camicie*e *pesca* da *pesche*. Per questo scopo viene utilizzato il dizionario interno. I gerundi vengono trattati come sostantivi, se presenti nel dizionario.  
  
 Utilizzando il dizionario interno la trasformazione Estrazione termini esegue quindi le operazioni di stemming delle parole riportate negli esempi, in modo da ottenere la forma presente nel dizionario.  
  
-   Rimozione della desinenza inglese *s* dai nomi. Ad esempio, *bicycles* diventa *bicycle*.  
  
-   Rimozione della desinenza inglese *es* dai nomi. Ad esempio, *stories* diventa *story*.  
  
-   Recupero dal dizionario della forma singolare per i sostantivi irregolari. Ad esempio, *geese* diventa *goose*.  
  
### <a name="normalized-words"></a>Parole normalizzate  
 La trasformazione Estrazione termini normalizza i termini che hanno iniziale maiuscola solo a causa della propria posizione nella frase, sostituendoli con la forma senza maiuscole. Ad esempio, nelle frasi *Cani che inseguono gatti* e *Montagne con sentieri ripidi*, le parole *Cani* e *Montagne* vengono normalizzate in *cane* e *montagna*.  
  
 La trasformazione Estrazione termini normalizza le parole in modo che le versioni con e senza maiuscole di una stessa parola non vengano considerate come termini diversi. Ad esempio, nei testi *A Milano puoi vedere molte biciclette* e *Biciclette di colore blu*, *biciclette* e *Biciclette* vengono riconosciuti come lo stesso termine e la trasformazione mantiene solo *bicicletta*. Le parole e i nomi propri non elencati nel dizionario interno non vengono normalizzati.  
  
### <a name="case-sensitive-normalization"></a>Normalizzazione con distinzione tra maiuscole e minuscole  
 È possibile configurare la trasformazione Estrazione termini in modo da considerare le parole maiuscole e minuscole come termini diversi o come varianti diverse di uno stesso termine.  
  
-   Se la trasformazione è configurata per riconoscere la distinzione tra maiuscole e minuscole, *Metodo* e *metodo* vengono estratti come due termini diversi. Le parole con iniziale maiuscola che non si trovano all'inizio di una frase non vengono mai normalizzate e vengono classificate come nomi propri.  
  
-   Se la trasformazione è configurata in modo da non distinguere tra maiuscole e minuscole, termini come *Metodo* e *metodo* vengono riconosciuti come varianti di un singolo termine. L'elenco dei termini estratti può includere *Metodo* o *metodo*, a seconda di quale compare per primo nel set di dati di input. Se la parola *Metodo* ha iniziale maiuscola solo perché è la prima parola di una frase, verrà estratta in forma normalizzata.  
  
## <a name="sentence-and-word-boundaries"></a>Delimitatori di parole e frasi  
 Per suddividere il testo in frasi, la trasformazione Estrazione termini utilizza i caratteri seguenti come delimitatori di frase:  
  
-   Caratteri ASCII di interruzione di riga, 0x0d (ritorno a capo) e 0x0a (avanzamento riga). Tali caratteri vengono utilizzati come delimitatori di frase solo se nella riga sono presenti due o più caratteri di interruzione di riga.  
  
-   Segno meno (-). Tale carattere viene utilizzato come delimitatore di frase solo se non è preceduto né seguito da una lettera.  
  
-   Carattere di sottolineatura (_). Tale carattere viene utilizzato come delimitatore di frase solo se non è preceduto né seguito da una lettera.  
  
-   Tutti i caratteri Unicode minori o uguali a 0x19 o maggiori o uguali a 0x7b.  
  
-   Combinazioni di numeri, segni di punteggiatura e caratteri alfabetici. Ad esempio, *A23B#99* restituisce il termine *A23B*.  
  
-   Caratteri %, @, &, $, #, \*, :, ;, ., **,** , !, ?, \<, >, +, =, ^, ~, |, \\, /, (, ), [, ], {, }, " e '.  
  
    > [!NOTE]  
    >  Gli acronimi che includono uno o più punti (.) non vengono suddivisi in più frasi.  
  
 La trasformazione Estrazione termini suddivide quindi le frasi in parole utilizzando i delimitatori di parola seguenti:  
  
-   Space  
  
-   Scheda  
  
-   Carattere ASCII 0x0d (ritorno a capo)  
  
-   Carattere ASCII 0x0a (avanzamento riga)  
  
    > [!NOTE]  
    >  Se un apostrofo si trova in un'espressione costituita da una contrazione, ad esempio *we're* o *it's*, l'espressione verrà suddivisa in corrispondenza dell'apostrofo, altrimenti le lettere che seguono l'apostrofo verranno eliminate. L'espressione inglese *we're* , ad esempio, viene suddivisa in *we* e *'re*, mentre *bicycle's* viene tagliato in modo da ottenere *bicycle*.  
  
## <a name="configuration-of-the-term-extraction-transformation"></a>Configurazione della trasformazione Estrazione termini  
 Per generare i risultati la trasformazione Estrazione termini utilizza algoritmi interni e modelli statistici. Può essere necessario eseguire la trasformazione Estrazione termini più volte ed esaminare i risultati per configurare la trasformazione in modo da generare il tipo di risultati più adatto per la propria soluzione di text mining.  
  
 Questa trasformazione include un input regolare, un output e un output degli errori.  
  
 È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.  
  
 Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Estrazione termini** , fare clic su uno degli argomenti seguenti:  
  
-   [Editor trasformazione Estrazione termini &#40;scheda Estrazione termini&#41;](../../term-extraction-transformation-editor-term-extraction-tab.md)  
  
-   [Editor trasformazione Estrazione termini &#40;scheda Esclusione&#41;](../../term-extraction-transformation-editor-exclusion-tab.md)  
  
-   [Editor trasformazione Estrazione termini &#40;scheda Avanzate&#41;](../../term-extraction-transformation-editor-advanced-tab.md)  
  
 Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:  
  
-   [Proprietà comuni](../../common-properties.md)  
  
-   [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md)  
  
 Per altre informazioni su come impostare le proprietà, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).  
  
  
