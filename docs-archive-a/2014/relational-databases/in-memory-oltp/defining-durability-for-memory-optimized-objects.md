---
title: Definizione di durabilità per gli oggetti con ottimizzazione per la memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0fe85fbf-8e8d-4983-96fd-d04b3c7d6d65
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 325f50a74ea75270dd62fc3564200c59255dc6cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626083"
---
# <a name="defining-durability-for-memory-optimized-objects"></a><span data-ttu-id="acfe3-102">Definizione di durabilità per gli oggetti con ottimizzazione per la memoria</span><span class="sxs-lookup"><span data-stu-id="acfe3-102">Defining Durability for Memory-Optimized Objects</span></span>
  <span data-ttu-id="acfe3-103">Con OLTP in memoria viene garantita la disponibilità completa di tutte le proprietà di atomicità, coerenza, isolamento e durabilità (ACID, Atomicity, Consistency, Isolation, Durability).</span><span class="sxs-lookup"><span data-stu-id="acfe3-103">In-Memory OLTP guarantees full atomicity, consistency, isolation, and full durability (ACID) properties.</span></span> <span data-ttu-id="acfe3-104">La durabilità, nel contesto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e delle tabelle ottimizzate per la memoria, offre le seguenti garanzie:</span><span class="sxs-lookup"><span data-stu-id="acfe3-104">Durability in the context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and memory-optimized tables provides following guarantees:</span></span>  
  
 <span data-ttu-id="acfe3-105">Durabilità delle transazioni</span><span class="sxs-lookup"><span data-stu-id="acfe3-105">Transactional Durability</span></span>  
 <span data-ttu-id="acfe3-106">Quando si esegue il commit di una transazione completamente durevole che ha apportato modifiche (DML o DDL) a una tabella ottimizzata per la memoria, le modifiche apportate a una tabella durevole ottimizzata per la memoria vengono rese permanenti.</span><span class="sxs-lookup"><span data-stu-id="acfe3-106">When you commit a fully durable transaction that made (DDL or DML) changes to a memory-optimized table, the changes made to a durable memory-optimized table are permanent.</span></span>  
  
 <span data-ttu-id="acfe3-107">Quando si esegue il commit di una transazione durevole posticipata a una tabella ottimizzata per la memoria, la transazione diventa durevole solo dopo che il log delle transazioni in memoria viene salvato su disco.</span><span class="sxs-lookup"><span data-stu-id="acfe3-107">When you commit a delayed durable transaction to a memory-optimized table, the transaction becomes durable only after the in-memory transaction log is saved to disk.</span></span>  
  
 <span data-ttu-id="acfe3-108">Durabilità al riavvio</span><span class="sxs-lookup"><span data-stu-id="acfe3-108">Restart Durability</span></span>  
 <span data-ttu-id="acfe3-109">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene riavviato dopo un arresto anomalo o pianificato, viene ricreata un'istanza delle tabelle durevoli ottimizzate per la memoria per ripristinarne lo stato precedente all'arresto anomalo o pianificato.</span><span class="sxs-lookup"><span data-stu-id="acfe3-109">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restarts after a crash or planned shutdown, the memory-optimized durable tables are reinstantiated to restore them to the state before the shutdown or crash.</span></span>  
  
 <span data-ttu-id="acfe3-110">Durabilità in caso di errori dei supporti</span><span class="sxs-lookup"><span data-stu-id="acfe3-110">Media Failure Durability</span></span>  
 <span data-ttu-id="acfe3-111">Se in un disco guasto o danneggiato sono presenti una o più copie persistenti di oggetti durevoli ottimizzati per la memoria, la funzionalità di backup e ripristino di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di ripristinare le tabelle ottimizzate per la memoria sul nuovo supporto.</span><span class="sxs-lookup"><span data-stu-id="acfe3-111">If a failed or corrupt disk contains one or more persisted copies of durable memory-optimized objects, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore feature restores memory-optimized tables on the new media.</span></span>  
  
 <span data-ttu-id="acfe3-112">Per le tabelle ottimizzate per la memoria sono disponibili due opzioni di durabilità:</span><span class="sxs-lookup"><span data-stu-id="acfe3-112">There are two durability options for memory-optimized tables:</span></span>  
  
 <span data-ttu-id="acfe3-113">SCHEMA_ONLY (tabella non durevole)</span><span class="sxs-lookup"><span data-stu-id="acfe3-113">SCHEMA_ONLY (non-durable table)</span></span>  
 <span data-ttu-id="acfe3-114">Questa opzione assicura la durabilità dello schema della tabella, inclusi gli indici.</span><span class="sxs-lookup"><span data-stu-id="acfe3-114">This option ensures durability of the table schema, including indexes.</span></span> <span data-ttu-id="acfe3-115">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene riavviato, la tabella non durevole viene ricreata, ma inizialmente senza dati.</span><span class="sxs-lookup"><span data-stu-id="acfe3-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is restarted, the non-durable table is recreated, but starts with no data.</span></span> <span data-ttu-id="acfe3-116">Si tratta di un comportamento diverso da una tabella in tempdb, in cui sia la tabella che i dati vengono persi al riavvio. Uno scenario tipico per creare una tabella non durevole consiste nell'archiviare dati temporanei, ad esempio una tabella di staging per un processo ETL.</span><span class="sxs-lookup"><span data-stu-id="acfe3-116">(This is unlike a table in tempdb, where both the table and its data are lost upon restart.) A typical scenario for creating a non-durable table is to store transient data, such as a staging table for an ETL process.</span></span> <span data-ttu-id="acfe3-117">Una durabilità SCHEMA_ONLY evita la registrazione delle transazioni e i checkpoint, con una possibile riduzione significativa delle operazioni di I/O.</span><span class="sxs-lookup"><span data-stu-id="acfe3-117">A SCHEMA_ONLY durability avoids both transaction logging and checkpoint, which can significantly reduce I/O operations.</span></span>  
  
 <span data-ttu-id="acfe3-118">SCHEMA_AND_DATA (tabella durevole)</span><span class="sxs-lookup"><span data-stu-id="acfe3-118">SCHEMA_AND_DATA (durable table)</span></span>  
 <span data-ttu-id="acfe3-119">Questa opzione offre durabilità dello schema e dei dati.</span><span class="sxs-lookup"><span data-stu-id="acfe3-119">This option provides durability of both schema and data.</span></span> <span data-ttu-id="acfe3-120">Il livello di durabilità dei dati dipende dall'eventuale scelta di eseguire il commit di una transazione come completamente durevole o con durabilità posticipata.</span><span class="sxs-lookup"><span data-stu-id="acfe3-120">The level of data durability depends on whether you commit a transaction as fully durable or with delayed durability.</span></span> <span data-ttu-id="acfe3-121">Le transazioni completamente durevoli offrono la stessa garanzia di durabilità dei dati e dello schema, in modo analogo a una tabella basata su disco.</span><span class="sxs-lookup"><span data-stu-id="acfe3-121">Fully durable transactions provide the same durability guarantee for data and schema, similar to a disk-based table.</span></span> <span data-ttu-id="acfe3-122">La durabilità posticipata migliora le prestazioni ma può causare la perdita di dati in caso di un arresto anomalo del server o di failover.</span><span class="sxs-lookup"><span data-stu-id="acfe3-122">Delayed durability will improve performance but can potentially result in data loss in case of a server crash or fail over.</span></span> <span data-ttu-id="acfe3-123">Per altre informazioni sulla durabilità ritardata, vedere [Controllo della durabilità delle transazioni](../logs/control-transaction-durability.md).</span><span class="sxs-lookup"><span data-stu-id="acfe3-123">(For more information about delayed durability, see [Control Transaction Durability](../logs/control-transaction-durability.md).)</span></span>  
  
 <span data-ttu-id="acfe3-124">Lo schema della tabella ottimizzata per la memoria viene reso persistente, in modo analogo alle tabelle basate su disco, nel filegroup primario di un database.</span><span class="sxs-lookup"><span data-stu-id="acfe3-124">The schema of the memory-optimized table is persisted, similar to disk-based tables, in the primary file group of a database.</span></span>  
  
 <span data-ttu-id="acfe3-125">I dati delle tabelle ottimizzate per la memoria vengono salvati in coppie di file di dati e differenziali.</span><span class="sxs-lookup"><span data-stu-id="acfe3-125">Data in durable memory-optimized tables is saved in data and delta file pairs.</span></span>  
  
 <span data-ttu-id="acfe3-126">Gli indici definiti nelle tabelle ottimizzate per la memoria sono persistenti solo nei metadati, non nell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="acfe3-126">The indexes defined in memory-optimized tables persist only in metadata, not in storage.</span></span> <span data-ttu-id="acfe3-127">Le strutture degli indici vengono generate nell'ambito del caricamento di tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="acfe3-127">Index structures are generated as part of loading memory-optimized tables.</span></span>  
  
 <span data-ttu-id="acfe3-128">Le righe vengono eliminate in modo esplicito tramite un'istruzione DELETE o indirettamente tramite un'istruzione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="acfe3-128">Rows are deleted either explicitly by a DELETE statement or indirectly by an UPDATE statement.</span></span> <span data-ttu-id="acfe3-129">Un'operazione UPDATE viene eseguita come un'eliminazione seguita da un inserimento.</span><span class="sxs-lookup"><span data-stu-id="acfe3-129">An UPDATE operation is executed as a delete followed by an insert.</span></span> <span data-ttu-id="acfe3-130">Quando viene eliminata una riga, non viene apportata alcuna modifica a un file di dati, ma al file differenziale corrispondente viene accodata una nuova riga che identifica quella eliminata.</span><span class="sxs-lookup"><span data-stu-id="acfe3-130">When a row is deleted, no change is made to a data file but a new row, identifying the deleted row, is appended to the corresponding delta file.</span></span>  
  
 <span data-ttu-id="acfe3-131">Durante le operazioni di recupero o ripristino, il motore di OLTP in memoria legge i file di dati e differenziali per il caricamento nella memoria fisica.</span><span class="sxs-lookup"><span data-stu-id="acfe3-131">During recovery or restore operations, the In-Memory OLTP engine reads data and delta files for loading into physical memory.</span></span> <span data-ttu-id="acfe3-132">Il tempo di caricamento viene determinato dai seguenti fattori:</span><span class="sxs-lookup"><span data-stu-id="acfe3-132">The load time is determined by:</span></span>  
  
-   <span data-ttu-id="acfe3-133">Quantità di dati da caricare.</span><span class="sxs-lookup"><span data-stu-id="acfe3-133">The amount of data to load.</span></span>  
  
-   <span data-ttu-id="acfe3-134">Larghezza di banda per operazioni di I/O sequenziali.</span><span class="sxs-lookup"><span data-stu-id="acfe3-134">Sequential I/O bandwidth.</span></span>  
  
-   <span data-ttu-id="acfe3-135">Grado di parallelismo, determinato dal numero di file contenitori e di core del processore.</span><span class="sxs-lookup"><span data-stu-id="acfe3-135">Degree of parallelism, determined by number of file containers and processor cores.</span></span>  
  
-   <span data-ttu-id="acfe3-136">Quantità di record di log nella parte attiva del log che devono essere ripetuti.</span><span class="sxs-lookup"><span data-stu-id="acfe3-136">The amount of log records in the active portion of the log that need to be redone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfe3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acfe3-137">See Also</span></span>  
 [<span data-ttu-id="acfe3-138">Creazione e gestione dell'archiviazione per gli oggetti ottimizzati per la memoria</span><span class="sxs-lookup"><span data-stu-id="acfe3-138">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  