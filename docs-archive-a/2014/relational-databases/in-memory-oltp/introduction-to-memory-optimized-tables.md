---
title: Introduzione alle tabelle con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: ef1cc7de-63be-4fa3-a622-6d93b440e3ac
author: rothja
ms.author: jroth
ms.openlocfilehash: edcdea9d266cf0ef231b1e16be4da7009372dcd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725783"
---
# <a name="introduction-to-memory-optimized-tables"></a>Introduzione alle tabelle con ottimizzazione per la memoria
  Le tabelle con ottimizzazione per la memoria sono tabelle create usando [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).  
  
 Le tabelle con ottimizzazione per la memoria risiedono in memoria. Le righe della tabella vengono lette e scritte in memoria. L'intera tabella risiede in memoria. Una seconda copia dei dati della tabella viene mantenuta su disco, ma solo per motivi di durabilità.  
  
 OLTP in memoria viene integrato con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per fornire un'esperienza senza problemi in tutte le aree, ad esempio sviluppo, distribuzione, gestibilità e supporto. Un database può contenere sia oggetti in memoria che oggetti basati su disco.  
  
 Le righe delle tabelle ottimizzate per la memoria dispongono di versioni. Ciò significa che ogni riga nella tabella dispone potenzialmente di più versioni. Tutte le versioni delle righe vengono mantenute nella stessa struttura dei dati della tabella. Il controllo delle versioni delle righe viene utilizzato per consentire letture e scritture simultanee nella stessa riga. Per ulteriori informazioni sulle letture e scritture simultanee nella stessa riga, vedere [transazioni nelle tabelle ottimizzate per la memoria](memory-optimized-tables.md).  
  
 Nella figura seguente viene illustrato il controllo di più versioni. Nella figura è illustrata una tabella con tre righe e ogni riga ha diverse versioni.  
  
 ![Controllo di più versioni.](../../database-engine/media/hekaton-tables-1.gif "Controllo di più versioni.")  
  
 Nella tabella sono presenti tre righe: r1, r2 e r3. r1 include tre versioni, r2 due versioni e r3 quattro versioni. Si noti che diverse versioni della stessa riga non occupano necessariamente posizioni di memoria consecutive. Le diverse versioni delle righe possono essere presenti in diverse posizioni della struttura dei dati della tabella.  
  
 La struttura dei dati della tabella ottimizzata per la memoria può essere considerata una raccolta di versioni di riga. Le righe nelle tabelle basate su disco sono organizzate in pagine ed extent e alle singole righe viene fatto riferimento utilizzando il numero e l'offset della pagina, alle versioni di riga nelle tabelle ottimizzate per la memoria viene fatto riferimento tramite puntatori alla memoria a 8 byte.  
  
## <a name="durability"></a>Durabilità  
 Le tabelle ottimizzate per la memoria sono completamente durevoli per impostazione predefinita e, come le transazioni in tabelle tradizionali basate su disco, le transazioni completamente durevoli nelle tabelle ottimizzate per la memoria sono completamente ACID (atomicità, coerenza, isolamento e durabilità). Le tabelle con ottimizzazione per la memoria e le stored procedure compilate in modo nativo supportano un subset di [!INCLUDE[tsql](../../../includes/tsql-md.md)].  
  
 La funzionalità OLTP in memoria supporta le tabelle durevoli con transazioni con durabilità ritardata. Le transazioni con durabilità ritardata sono salvate su disco subito dopo il commit della transazione. In cambio di un miglioramento delle prestazioni, le transazioni di cui è stato eseguito il commit non salvate su disco vengono perse in caso di arresto anomalo del server o di failover.  
  
 Oltre alle tabelle ottimizzate per la memoria durevoli predefinite, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supporta anche le tabelle ottimizzate per la memoria non durevoli che non vengono registrate e i cui dati non vengono salvati in modo persistente su disco. Ciò significa che le transazioni in tali tabelle non richiedono alcuna attività di I/O su disco, ma i dati non verranno recuperati in caso di un arresto anomalo o di un failover del server.  
  
## <a name="accessing-data-in-memory-optimized-tables"></a>Accesso ai dati nelle tabelle con ottimizzazione per la memoria  
 Ai dati nelle tabelle ottimizzate per la memoria è possibile accedere in due modi:  
  
-   Tramite codice [!INCLUDE[tsql](../../../includes/tsql-md.md)] interpretato, all'esterno di una stored procedure compilata in modo nativo. Queste istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] possono essere incluse in stored procedure interpretate o essere istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] ad hoc.  
  
-   Tramite stored procedure compilate in modo nativo.  
  
 È possibile accedere alle tabelle con ottimizzazione per la memoria in modo più efficiente da stored procedure compilate in modo nativo ([Stored procedure compilate in modo nativo](natively-compiled-stored-procedures.md)). È inoltre possibile accedere alle tabelle con ottimizzazione per la memoria con codice [!INCLUDE[tsql](../../../includes/tsql-md.md)]tradizionale interpretato. Con [!INCLUDE[tsql](../../../includes/tsql-md.md)] interpretato si fa riferimento all'accesso a tabelle ottimizzate per la memoria senza una stored procedure compilata in modo nativo. Alcuni esempi di accesso [!INCLUDE[tsql](../../../includes/tsql-md.md)] interpretato includono l'accesso a una tabella ottimizzata per la memoria da un trigger DML o un batch, una vista e una funzione con valori di tabella [!INCLUDE[tsql](../../../includes/tsql-md.md)] ad hoc.  
  
 Nella tabella seguente viene riepilogato l'accesso [!INCLUDE[tsql](../../../includes/tsql-md.md)] interpretato e nativo per vari oggetti.  
  
|Funzionalità|Accesso tramite una stored procedure compilata in modo nativo|Accesso [!INCLUDE[tsql](../../../includes/tsql-md.md)] interpretato|Accesso con CLR|  
|-------------|-------------------------------------------------------|-------------------------------------------|----------------|  
|Tabelle ottimizzate per la memoria|Sì|Sì|No <sup>1</sup>|  
|[Variabili di tabella con ottimizzazione per la memoria](../../database-engine/memory-optimized-table-variables.md)|Sì|Sì|No|  
|[Stored procedure compilate in modo nativo](https://msdn.microsoft.com/library/dn133184.aspx)|Non è possibile utilizzare l'istruzione EXECUTE per eseguire una stored procedure qualsiasi da una stored procedure compilata in modo nativo.|Sì|No <sup>1</sup>|  
  
 <sup>1</sup> non è possibile accedere a una tabella ottimizzata per la memoria o a una stored procedure compilata in modo nativo dalla connessione del contesto (la connessione da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] quando si esegue un modulo CLR). È tuttavia possibile creare e aprire un'altra connessione da cui accedere a tabelle ottimizzate per la memoria e stored procedure compilate in modo nativo. Per altre informazioni, vedere [confronto tra normali e connessioni di contesto](../clr-integration/data-access/context-connections-vs-regular-connections.md).  
  
## <a name="performance-and-scalability"></a>Prestazioni e scalabilità  
 I seguenti fattori influiranno sui miglioramenti delle prestazioni che possono essere ottenuti con OLTP in memoria:  
  
 Comunicazione  
 Il miglioramento delle prestazioni per un'applicazione con molte chiamate a stored procedure brevi può risultare inferiore rispetto a un'applicazione con meno chiamate e più funzionalità implementate in ogni stored procedure.  
  
 [!INCLUDE[tsql](../../../includes/tsql-md.md)] Esecuzione  
 In OLTP in memoria si ottengono le migliori prestazioni quando si utilizzano le stored procedure compilate in modo nativo anziché le stored procedure interpretate o l'esecuzione delle query. Le stored procedure che comportano l'esecuzione di altre stored procedure non possono essere compilate in modo nativo, ma l'accesso alle tabelle ottimizzate per la memoria da queste stored procedure può offrire alcuni vantaggi.  
  
 Analisi dell'intervallo e ricerca di punti  
 Gli indici non cluster con ottimizzazione per la memoria supportano le analisi di intervalli e le analisi ordinate. Per le ricerche a punti, gli indici hash ottimizzati per la memoria offrono prestazioni migliori rispetto agli indici non cluster ottimizzati per la memoria. Gli indici non cluster con ottimizzazione per la memoria offrono prestazioni migliori rispetto agli indici basati su disco.  
  
 Le operazioni sugli indici non vengono registrate e sono presenti solo in memoria.  
  
 Concorrenza  
 Le prestazioni di applicazioni interessate dalla concorrenza a livello di motore, ad esempio la contesa di latch o il blocco, migliorano significativamente quando l'applicazione viene spostata in OLTP in memoria.  
  
 Nella tabella seguente sono elencati i problemi relativi a prestazioni e scalabilità presenti in genere nei database relazionali e viene descritto in che modo OLTP in memoria può consentire il miglioramento delle prestazioni.  
  
|Problema|Impatto di OLTP in memoria|  
|-----------|----------------------------|  
|Prestazioni<br /><br /> Utilizzo elevato delle risorse (CPU, I/O, rete o memoria).|CPU<br /> Le stored procedure compilate in modo nativo possono ridurre in modo significativo l'utilizzo della CPU perché richiedono un numero decisamente inferiore di istruzioni per eseguire un'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] rispetto alle stored procedure interpretate.<br /><br /> OLTP in memoria può ridurre l'investimento hardware nei carichi di lavoro con scalabilità orizzontale, in quanto un server può potenzialmente fornire la velocità effettiva di cinque/dieci server.<br /><br /> I/O<br /> Se si verifica un collo di bottiglia a livello di I/O in seguito all'elaborazione di pagine di dati o di indice, in OLTP in memoria il collo di bottiglia potrebbe risultare contenuto. Inoltre, il checkpoint degli oggetti di OLTP in memoria è continuo e non genera aumenti improvvisi nelle operazioni di I/O. Se tuttavia il working set delle tabelle critiche per le prestazioni eccede la memoria disponibile, OLTP in memoria non sarà in grado di migliorare le prestazioni in quanto è necessario che i dati siano residenti in memoria. Se si verifica un collo di bottiglia a livello di I/O durante la registrazione, OLTP in memoria può ridurre il collo di bottiglia perché richiede meno attività di registrazione. Se una o più tabelle ottimizzate per la memoria sono configurate come tabelle non durevoli, è possibile eliminare la registrazione dei dati.<br /><br /> Memoria<br /> Con OLTP in memoria non si ottiene alcun vantaggio in termini di prestazioni. È possibile che OLTP in memoria comporti un utilizzo elevato di memoria, in quando gli oggetti devono essere residenti in memoria.<br /><br /> Rete<br /> Con OLTP in memoria non si ottiene alcun vantaggio in termini di prestazioni. I dati devo essere comunicati dal livello dati al livello applicazione.|  
|Scalabilità<br /><br /> La maggior parte dei problemi di scalabilità nelle applicazioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è causata da problemi di concorrenza, ad esempio la contesa in blocchi, latch e spinlock.|Contesa di latch<br /> Uno scenario tipico riguarda la contesa nell'ultima pagina di un indice quando vengono inserite contemporaneamente righe nell'ordine delle chiavi. Poiché in OLTP in memoria non vengono utilizzati latch per l'accesso ai dati, i problemi di scalabilità correlati alle contese di latch vengono completamente rimossi.<br /><br /> Contesa di spinlock<br /> Poiché in OLTP in memoria non vengono utilizzati latch per l'accesso ai dati, i problemi di scalabilità correlati alle contese di spinlock vengono completamente rimossi.<br /><br /> Contesa correlata al blocco<br /> Se nell'applicazione di database vengono rilevati problemi di blocco tra operazioni di lettura e scrittura, con OLTP in memoria vengono rimossi i problemi che impediscono di proseguire perché è previsto l'utilizzo di una nuova forma di controllo della concorrenza ottimistica per implementare tutti i livelli di isolamento delle transazioni. In OLTP in memoria, TempDB non viene utilizzato per l'archiviazione delle versioni di riga.<br /><br /> Se il problema di scalabilità è determinato dal conflitto tra due operazioni di scrittura, ad esempio due transazioni simultanee che tentano di aggiornare la stessa riga, OLTP in memoria consente il completamento di una transazione e genera un errore per l'altra. La transazione non riuscita deve essere inviata di nuovo in modo esplicito o implicito, ripetendone l'esecuzione. In entrambi i casi è necessario apportare modifiche all'applicazione.<br /><br /> Se nell'applicazione si verificano frequenti conflitti tra due operazioni di scrittura, il valore del blocco ottimistico viene ridotto. L'applicazione non è appropriata per OLTP in memoria. La maggior parte delle applicazioni OLTP non presenta conflitti di scrittura, a meno che il conflitto non venga attivato da escalation blocchi.|  
  
## <a name="see-also"></a>Vedere anche  
 [OLTP in memoria &#40;ottimizzazione per la memoria&#41;](in-memory-oltp-in-memory-optimization.md)  
  
  
