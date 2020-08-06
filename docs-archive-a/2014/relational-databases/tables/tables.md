---
title: Tabelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- tables [SQL Server]
- table components [SQL Server]
ms.assetid: 82d7819c-b801-4309-a849-baa63083e83f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22e417a535454f88d6475a97d2d17ad794404175
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626621"
---
# <a name="tables"></a><span data-ttu-id="2cec8-102">Tabelle</span><span class="sxs-lookup"><span data-stu-id="2cec8-102">Tables</span></span>
  <span data-ttu-id="2cec8-103">Le tabelle sono oggetti di database che contengono tutti i dati presenti in un database.</span><span class="sxs-lookup"><span data-stu-id="2cec8-103">Tables are database objects that contain all the data in a database.</span></span> <span data-ttu-id="2cec8-104">Nelle tabelle, i dati sono organizzati in modo logico in righe e colonne in un formato simile a quello di un foglio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="2cec8-104">In tables, data is logically organized in a row-and-column format similar to a spreadsheet.</span></span> <span data-ttu-id="2cec8-105">Ogni riga rappresenta un record univoco e ogni colonna rappresenta un campo all'interno del record.</span><span class="sxs-lookup"><span data-stu-id="2cec8-105">Each row represents a unique record, and each column represents a field in the record.</span></span> <span data-ttu-id="2cec8-106">Ad esempio, una tabella che include i dati dei dipendenti di un'azienda può contenere una riga per ogni dipendente e colonne che rappresentano i dettagli dei dipendenti quali l'ID, il nome, l'indirizzo, la posizione e il numero di telefono dell'abitazione.</span><span class="sxs-lookup"><span data-stu-id="2cec8-106">For example, a table that contains employee data for a company might contain a row for each employee and columns representing employee information such as employee number, name, address, job title, and home telephone number.</span></span>  
  
-   <span data-ttu-id="2cec8-107">Il numero di tabelle presenti in un database è limitato solo dal numero di oggetti disponibili in un database (2,147,483,647).</span><span class="sxs-lookup"><span data-stu-id="2cec8-107">The number of tables in a database is limited only by the number of objects allowed in a database (2,147,483,647).</span></span> <span data-ttu-id="2cec8-108">Una tabella standard definita dall'utente può avere fino a 1.024 colonne.</span><span class="sxs-lookup"><span data-stu-id="2cec8-108">A standard user-defined table can have up to 1,024 columns.</span></span> <span data-ttu-id="2cec8-109">Il numero di righe nella tabella è limitato solo dalla capacità di archiviazione del server.</span><span class="sxs-lookup"><span data-stu-id="2cec8-109">The number of rows in the table is limited only by the storage capacity of the server.</span></span>  
  
-   <span data-ttu-id="2cec8-110">È possibile assegnare proprietà alla tabella e a ogni colonna nella tabella per controllare i dati consentiti e le altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="2cec8-110">You can assign properties to the table and to each column in the table to control the data that is allowed and other properties.</span></span> <span data-ttu-id="2cec8-111">Ad esempio, è possibile creare vincoli in una colonna per impedire valori null o fornire un valore predefinito se non è specificato un valore oppure è possibile assegnare un vincolo principale sulla tabella che applica l'univocità o definisce una relazione tra tabelle.</span><span class="sxs-lookup"><span data-stu-id="2cec8-111">For example, you can create constraints on a column to disallow null values or provide a default value if a value is not specified, or you can assign a key constraint on the table that enforces uniqueness or defines a relationship between tables.</span></span>  
  
-   <span data-ttu-id="2cec8-112">I dati nella tabella possono essere compressi per riga o per pagina.</span><span class="sxs-lookup"><span data-stu-id="2cec8-112">The data in the table can be compressed either by row or by page.</span></span> <span data-ttu-id="2cec8-113">La compressione dei dati può consentire l'archiviazione di più righe su una pagina.</span><span class="sxs-lookup"><span data-stu-id="2cec8-113">Data compression can allow more rows to be stored on a page.</span></span> <span data-ttu-id="2cec8-114">Per altre informazioni, vedere [Data Compression](../../relational-databases/data-compression/data-compression.md).</span><span class="sxs-lookup"><span data-stu-id="2cec8-114">For more information, see [Data Compression](../../relational-databases/data-compression/data-compression.md).</span></span>  
  
## <a name="types-of-tables"></a><span data-ttu-id="2cec8-115">Tipi di tabelle</span><span class="sxs-lookup"><span data-stu-id="2cec8-115">Types of Tables</span></span>  
 <span data-ttu-id="2cec8-116">Oltre al ruolo standard delle tabelle di base definite dall'utente, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono disponibili i tipi di tabelle seguenti per scopi specifici in un database:</span><span class="sxs-lookup"><span data-stu-id="2cec8-116">Besides the standard role of basic user-defined tables, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following types of tables that serve special purposes in a database.</span></span>  
  
 <span data-ttu-id="2cec8-117">Tabelle partizionate</span><span class="sxs-lookup"><span data-stu-id="2cec8-117">Partitioned Tables</span></span>  
 <span data-ttu-id="2cec8-118">Nelle tabelle partizionate, i dati vengono suddivisi orizzontalmente in unità che possono essere distribuite in più filegroup di un database.</span><span class="sxs-lookup"><span data-stu-id="2cec8-118">Partitioned tables are tables whose data is horizontally divided into units which may be spread across more than one filegroup in a database.</span></span> <span data-ttu-id="2cec8-119">Il partizionamento semplifica la gestione di tabelle o indici di grandi dimensioni in quanto consente di gestire o accedere a subset di dati in modo rapido ed efficace mantenendo l'integrità della raccolta.</span><span class="sxs-lookup"><span data-stu-id="2cec8-119">Partitioning makes large tables or indexes more manageable by letting you access or manage subsets of data quickly and efficiently, while maintaining the integrity of the overall collection.</span></span> <span data-ttu-id="2cec8-120">Per impostazione predefinita, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supporta fino a 15.000 partizioni.</span><span class="sxs-lookup"><span data-stu-id="2cec8-120">By default, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supports up to 15,000 partitions.</span></span> <span data-ttu-id="2cec8-121">Per ulteriori informazioni, vedere [Partitioned Tables and Indexes](../../relational-databases/partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2cec8-121">For more information, see [Partitioned Tables and Indexes](../../relational-databases/partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="2cec8-122">Tabelle temporanee</span><span class="sxs-lookup"><span data-stu-id="2cec8-122">Temporary Tables</span></span>  
 <span data-ttu-id="2cec8-123">Le tabelle temporanee vengono archiviate in `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="2cec8-123">Temporary tables are stored in `tempdb`.</span></span> <span data-ttu-id="2cec8-124">Esistono due tipi di tabelle temporanee, ovvero le tabelle locali e le tabelle globali.</span><span class="sxs-lookup"><span data-stu-id="2cec8-124">There are two types of temporary tables: local and global.</span></span> <span data-ttu-id="2cec8-125">I due tipi differiscono per i nomi, la visibilità e la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="2cec8-125">They differ from each other in their names, their visibility, and their availability.</span></span> <span data-ttu-id="2cec8-126">Le tabelle temporanee locali contengono un solo simbolo di cancelletto (#) come primo carattere del nome, sono visibili solo durante la connessione utente corrente e vengono eliminate quando l'utente chiude la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cec8-126">Local temporary tables have a single number sign (#) as the first character of their names; they are visible only to the current connection for the user, and they are deleted when the user disconnects from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2cec8-127">Le tabelle temporanee globali contengono due simboli di cancelletto (##) come primi caratteri del nome, una volta create sono visibili per tutti gli utenti e vengono eliminate quando tutti gli utenti che fanno riferimento alla tabella chiudono la connessione all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2cec8-127">Global temporary tables have two number signs (##) as the first characters of their names; they are visible to any user after they are created, and they are deleted when all users referencing the table disconnect from the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2cec8-128">Tabelle di sistema</span><span class="sxs-lookup"><span data-stu-id="2cec8-128">System Tables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2cec8-129">archivia i dati che definiscono la configurazione del server e di tutte le relative tabelle in un set di tabelle speciale noto come tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="2cec8-129">stores the data that defines the configuration of the server and all its tables in a special set of tables known as system tables.</span></span> <span data-ttu-id="2cec8-130">Gli utenti non possono eseguire una query direttamente o aggiornare le tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="2cec8-130">Users cannot directly query or update the system tables.</span></span> <span data-ttu-id="2cec8-131">Le informazioni delle tabelle di sistema vengono rese disponibili tramite le viste di sistema.</span><span class="sxs-lookup"><span data-stu-id="2cec8-131">The information in the system tables is made available through the system views.</span></span> <span data-ttu-id="2cec8-132">Per altre informazioni, vedere [Viste di sistema &#40;Transact-SQL&#41;](/sql/t-sql/language-reference).</span><span class="sxs-lookup"><span data-stu-id="2cec8-132">For more information, see [System Views &#40;Transact-SQL&#41;](/sql/t-sql/language-reference).</span></span>  
  
 <span data-ttu-id="2cec8-133">Tabelle estese in larghezza</span><span class="sxs-lookup"><span data-stu-id="2cec8-133">Wide Tables</span></span>  
 <span data-ttu-id="2cec8-134">Le tabelle estese in larghezza usano le [colonne di tipo sparse](use-sparse-columns.md) per aumentare a 30.000 il numero totale di colonne che una tabella può contenere.</span><span class="sxs-lookup"><span data-stu-id="2cec8-134">Wide tables use [sparse columns](use-sparse-columns.md) to increase the total of columns that a table can have to 30,000.</span></span> <span data-ttu-id="2cec8-135">Le colonne di tipo sparse sono colonne comuni che dispongono di archiviazione ottimizzata per i valori Null.</span><span class="sxs-lookup"><span data-stu-id="2cec8-135">Sparse columns are ordinary columns that have an optimized storage for null values.</span></span> <span data-ttu-id="2cec8-136">Tali colonne consentono di ridurre i requisiti di spazio per i valori Null aumentando tuttavia l'overhead per il recupero dei valori non Null.</span><span class="sxs-lookup"><span data-stu-id="2cec8-136">Sparse columns reduce the space requirements for null values at the cost of more overhead to retrieve nonnull values.</span></span> <span data-ttu-id="2cec8-137">Una colonna estesa ha definito un [set di colonne](use-column-sets.md), ovvero una rappresentazione XML non tipizzata che combina tutte le colonne di tipo sparse di una tabella in un output strutturato.</span><span class="sxs-lookup"><span data-stu-id="2cec8-137">A wide table has defined a [column set](use-column-sets.md), which is an untyped XML representation that combines all the sparse columns of a table into a structured output.</span></span> <span data-ttu-id="2cec8-138">Anche il numero degli indici e delle statistiche viene portato rispettivamente a 1.000 e 30.000.</span><span class="sxs-lookup"><span data-stu-id="2cec8-138">The number of indexes and statistics is also increased to 1,000 and 30,000, respectively.</span></span> <span data-ttu-id="2cec8-139">Le dimensioni di una riga di tabella estesa in larghezza non possono superare 8.019 byte.</span><span class="sxs-lookup"><span data-stu-id="2cec8-139">The maximum size of a wide table row is 8,019 bytes.</span></span> <span data-ttu-id="2cec8-140">Pertanto, la maggior parte dei dati di qualsiasi riga deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="2cec8-140">Therefore, most of the data in any particular row should be NULL.</span></span> <span data-ttu-id="2cec8-141">Il numero massimo di colonne di tipo nonsparse più le colonne calcolate di una tabella estesa in larghezza rimane 1.024.</span><span class="sxs-lookup"><span data-stu-id="2cec8-141">The maximum number of nonsparse columns plus computed columns in a wide table remains 1,024.</span></span>  
  
 <span data-ttu-id="2cec8-142">Le tabelle estese in larghezza hanno le seguenti implicazioni sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2cec8-142">Wide tables have the following performance implications.</span></span>  
  
-   <span data-ttu-id="2cec8-143">Le tabelle estese in larghezza possono aumentare i costi di gestione degli indici nella tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-143">Wide tables can increase the cost to maintain indexes on the table.</span></span> <span data-ttu-id="2cec8-144">È consigliabile limitare il numero di indici di una tabella estesa in larghezza agli indici richiesti dalla logica di business.</span><span class="sxs-lookup"><span data-stu-id="2cec8-144">We recommend that the number of indexes on a wide table be limited to the indexes that are required by the business logic.</span></span> <span data-ttu-id="2cec8-145">All'aumento del numero di indici corrisponde infatti un aumento dei requisiti di memoria e dei tempi di compilazione DML.</span><span class="sxs-lookup"><span data-stu-id="2cec8-145">As the number of indexes increases, so does the DML compile-time and memory requirement.</span></span> <span data-ttu-id="2cec8-146">Gli indici non cluster devono essere indici filtrati applicati a subset di dati.</span><span class="sxs-lookup"><span data-stu-id="2cec8-146">Nonclustered indexes should be filtered indexes that are applied to data subsets.</span></span> <span data-ttu-id="2cec8-147">Per altre informazioni, vedere [Create Filtered Indexes](../../relational-databases/indexes/create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="2cec8-147">For more information, see [Create Filtered Indexes](../../relational-databases/indexes/create-filtered-indexes.md).</span></span>  
  
-   <span data-ttu-id="2cec8-148">Tramite applicazioni è possibile aggiungere e rimuovere in modo dinamico le colonne dalle tabelle estese in larghezza.</span><span class="sxs-lookup"><span data-stu-id="2cec8-148">Applications can dynamically add and remove columns from wide tables.</span></span> <span data-ttu-id="2cec8-149">Quando si aggiungono o rimuovono colonne, i piani di query compilati perdono validità.</span><span class="sxs-lookup"><span data-stu-id="2cec8-149">When columns are added or removed, compiled query plans are also invalidated.</span></span> <span data-ttu-id="2cec8-150">È pertanto consigliabile progettare un'applicazione in base al carico di lavoro previsto in modo che le modifiche allo schema siano minime.</span><span class="sxs-lookup"><span data-stu-id="2cec8-150">We recommend that you design an application to match the projected workload so that schema changes are minimized.</span></span>  
  
-   <span data-ttu-id="2cec8-151">L'aggiunta e la rimozione di dati da una tabella estesa in larghezza possono incidere negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2cec8-151">When data is added and removed from a wide table, performance can be affected.</span></span> <span data-ttu-id="2cec8-152">È necessario progettare le applicazioni per il carico di lavoro previsto in modo che le modifiche ai dati della tabella siano minime.</span><span class="sxs-lookup"><span data-stu-id="2cec8-152">Applications must be designed for the projected workload so that changes to the table data is minimized.</span></span>  
  
-   <span data-ttu-id="2cec8-153">Limitare l'esecuzione di istruzioni DML in una tabella estesa in larghezza che comportino l'aggiornamento di più righe di una chiave di clustering.</span><span class="sxs-lookup"><span data-stu-id="2cec8-153">Limit the execution of DML statements on a wide table that update multiple rows of a clustering key.</span></span> <span data-ttu-id="2cec8-154">La compilazione e l'esecuzione di queste istruzioni possono richiedere una notevole quantità di memoria.</span><span class="sxs-lookup"><span data-stu-id="2cec8-154">These statements can require significant memory resources to compile and execute.</span></span>  
  
-   <span data-ttu-id="2cec8-155">Il passaggio tra partizioni nelle tabelle estese in larghezza può essere lento e richiedere grandi quantità di memoria di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2cec8-155">Switch partition operations on wide tables can be slow and might require large amounts of memory to process.</span></span> <span data-ttu-id="2cec8-156">Le prestazioni e i requisiti di memoria sono proporzionali al numero totale di colonne sia nella partizione di origine sia in quella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2cec8-156">The performance and memory requirements are proportional to the total number of columns in both the source and target partitions.</span></span>  
  
-   <span data-ttu-id="2cec8-157">I cursori di aggiornamento di colonne specifiche di una tabella estesa in larghezza dovrebbero elencare le colonne in modo esplicito per la clausola FOR UPDATE.</span><span class="sxs-lookup"><span data-stu-id="2cec8-157">Update cursors that update specific columns in a wide table should list the columns explicitly in the FOR UPDATE clause.</span></span> <span data-ttu-id="2cec8-158">In questo modo, è possibile ottimizzare le prestazioni quando si utilizzano i cursori.</span><span class="sxs-lookup"><span data-stu-id="2cec8-158">This will help optimize performance when you use cursors.</span></span>  
  
## <a name="common-table-tasks"></a><span data-ttu-id="2cec8-159">Attività comuni della tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-159">Common Table Tasks</span></span>  
 <span data-ttu-id="2cec8-160">Nella tabella riportata di seguito vengono forniti i collegamenti a attività comuni associate alla creazione o alla modifica di una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-160">The following table provides links to common tasks associated with creating or modifying a table.</span></span>  
  
|<span data-ttu-id="2cec8-161">Attività tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-161">Table Tasks</span></span>|<span data-ttu-id="2cec8-162">Argomento</span><span class="sxs-lookup"><span data-stu-id="2cec8-162">Topic</span></span>|  
|-----------------|-----------|  
|<span data-ttu-id="2cec8-163">Viene illustrato come creare una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-163">Describes how to create a table.</span></span>|[<span data-ttu-id="2cec8-164">Creare tabelle &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-164">Create Tables &#40;Database Engine&#41;</span></span>](create-tables-database-engine.md)|  
|<span data-ttu-id="2cec8-165">Viene illustrato come eliminare una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-165">Describes how to delete a table.</span></span>|[<span data-ttu-id="2cec8-166">Eliminare tabelle &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-166">Delete Tables &#40;Database Engine&#41;</span></span>](delete-tables-database-engine.md)|  
|<span data-ttu-id="2cec8-167">Viene illustrato come creare una nuova tabella che contiene alcune o tutte le colonne in una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="2cec8-167">Describes how to create a new table that contains some or all of the columns in an existing table.</span></span>|[<span data-ttu-id="2cec8-168">Duplicare le tabelle</span><span class="sxs-lookup"><span data-stu-id="2cec8-168">Duplicate Tables</span></span>](duplicate-tables.md)|  
|<span data-ttu-id="2cec8-169">Viene illustrato come ridenominare una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-169">Describes how to rename a table.</span></span>|[<span data-ttu-id="2cec8-170">Rinominare tabelle &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-170">Rename Tables &#40;Database Engine&#41;</span></span>](rename-tables-database-engine.md)|  
|<span data-ttu-id="2cec8-171">Viene illustrata la procedura per visualizzare le proprietà della tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-171">Describes how to view the properties of the table.</span></span>|[<span data-ttu-id="2cec8-172">Visualizzare la definizione di una tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-172">View the Table Definition</span></span>](view-the-table-definition.md)|  
|<span data-ttu-id="2cec8-173">Viene illustrato come determinare se altri oggetti quali una vista o una stored procedure dipende da una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-173">Describes how to determine whether other objects such as a view or stored procedure depend on a table.</span></span>|[<span data-ttu-id="2cec8-174">Visualizzare le dipendenze di una tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-174">View the Dependencies of a Table</span></span>](view-the-dependencies-of-a-table.md)|  
  
 <span data-ttu-id="2cec8-175">Nella tabella riportata di seguito vengono forniti i collegamenti a attività comuni associate alla creazione o alla modifica di colonne in una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-175">The following table provides links to common tasks associated with creating or modifying columns in a table.</span></span>  
  
|<span data-ttu-id="2cec8-176">Attività colonne</span><span class="sxs-lookup"><span data-stu-id="2cec8-176">Column Tasks</span></span>|<span data-ttu-id="2cec8-177">Argomento</span><span class="sxs-lookup"><span data-stu-id="2cec8-177">Topic</span></span>|  
|------------------|-----------|  
|<span data-ttu-id="2cec8-178">Viene illustrato come aggiungere colonne a una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="2cec8-178">Describes how to add columns to an existing table.</span></span>|[<span data-ttu-id="2cec8-179">Aggiungere colonne a una tabella &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-179">Add Columns to a Table &#40;Database Engine&#41;</span></span>](add-columns-to-a-table-database-engine.md)|  
|<span data-ttu-id="2cec8-180">Viene illustrato come eliminare colonne da una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-180">Describes how to delete columns from a table.</span></span>|[<span data-ttu-id="2cec8-181">Eliminare le colonne da una tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-181">Delete Columns from a Table</span></span>](delete-columns-from-a-table.md)|  
|<span data-ttu-id="2cec8-182">Viene illustrato come modificare il nome di una colonna.</span><span class="sxs-lookup"><span data-stu-id="2cec8-182">Describes how to change the name of a column.</span></span>|[<span data-ttu-id="2cec8-183">Rinominare colonne &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-183">Rename Columns &#40;Database Engine&#41;</span></span>](rename-columns-database-engine.md)|  
|<span data-ttu-id="2cec8-184">Viene illustrato come copiare colonne da una tabella a un'altra copiando solo la definizione di colonna oppure la definizione e i dati.</span><span class="sxs-lookup"><span data-stu-id="2cec8-184">Describes how to copy columns from one table to another, copying either just the column definition, or the definition and data.</span></span>|[<span data-ttu-id="2cec8-185">Copiare colonne da una tabella a un'altra &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-185">Copy Columns from One Table to Another &#40;Database Engine&#41;</span></span>](copy-columns-from-one-table-to-another-database-engine.md)|  
|<span data-ttu-id="2cec8-186">Viene illustrato come modificare una definizione di colonna, modificando il tipo di dati o altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="2cec8-186">Describes how to modify a column definition, by changing the data type or other property.</span></span>|[<span data-ttu-id="2cec8-187">Modificare colonne &#40;Motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="2cec8-187">Modify Columns &#40;Database Engine&#41;</span></span>](modify-columns-database-engine.md)|  
|<span data-ttu-id="2cec8-188">Viene illustrato come modificare l'ordine di visualizzazione delle colonne.</span><span class="sxs-lookup"><span data-stu-id="2cec8-188">Describes how to change the order in which the columns appear.</span></span>|[<span data-ttu-id="2cec8-189">Modificare l'ordine delle colonne in una tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-189">Change Column Order in a Table</span></span>](change-column-order-in-a-table.md)|  
|<span data-ttu-id="2cec8-190">Viene illustrato come creare una colonna calcolata in una tabella.</span><span class="sxs-lookup"><span data-stu-id="2cec8-190">Describes how to create a computed column in a table.</span></span>|[<span data-ttu-id="2cec8-191">Specificare le colonne calcolate in una tabella</span><span class="sxs-lookup"><span data-stu-id="2cec8-191">Specify Computed Columns in a Table</span></span>](specify-computed-columns-in-a-table.md)|  
|<span data-ttu-id="2cec8-192">Viene illustrato come specificare un valore predefinito per una colonna.</span><span class="sxs-lookup"><span data-stu-id="2cec8-192">Describes how to specify a default value for a column.</span></span> <span data-ttu-id="2cec8-193">Questo valore viene utilizzato nel caso non venga fornito alcun altro valore.</span><span class="sxs-lookup"><span data-stu-id="2cec8-193">This value is used if another value is not supplied.</span></span>|[<span data-ttu-id="2cec8-194">Specificare i valori predefiniti per le colonne</span><span class="sxs-lookup"><span data-stu-id="2cec8-194">Specify Default Values for Columns</span></span>](specify-default-values-for-columns.md)|  
  
## <a name="see-also"></a><span data-ttu-id="2cec8-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cec8-195">See Also</span></span>  
 <span data-ttu-id="2cec8-196">[Vincoli di chiave primaria ed esterna](primary-and-foreign-key-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="2cec8-196">[Primary and Foreign Key Constraints](primary-and-foreign-key-constraints.md) </span></span>  
 [<span data-ttu-id="2cec8-197">Vincoli UNIQUE e CHECK</span><span class="sxs-lookup"><span data-stu-id="2cec8-197">Unique Constraints and Check Constraints</span></span>](unique-constraints-and-check-constraints.md)  
  
  