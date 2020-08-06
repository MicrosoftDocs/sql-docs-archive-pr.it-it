---
title: Associare un database con tabelle con ottimizzazione per la memoria a un pool di risorse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f222b1d5-d2fa-4269-8294-4575a0e78636
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cd163c5d3bc7a2cd9051b8d37b8127a1cc88c30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638398"
---
# <a name="bind-a-database-with-memory-optimized-tables-to-a-resource-pool"></a><span data-ttu-id="7ef11-102">Associare un database con tabelle con ottimizzazione per la memoria a un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="7ef11-102">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>
  <span data-ttu-id="7ef11-103">Un pool di risorse rappresenta un subset di risorse fisiche che è possibile governare.</span><span class="sxs-lookup"><span data-stu-id="7ef11-103">A resource pool represents a subset of physical resources that can be governed.</span></span> <span data-ttu-id="7ef11-104">Per impostazione predefinita, i database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono associati alle risorse del pool di risorse predefinito e usano queste ultime.</span><span class="sxs-lookup"><span data-stu-id="7ef11-104">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases are bound to and consume the resources of the default resource pool.</span></span> <span data-ttu-id="7ef11-105">Per evitare che in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tutte le risorse vengano usate da una o più tabelle ottimizzate per la memoria e che altri utenti utilizzino la memoria necessaria per le tabelle ottimizzate per la memoria, è consigliabile creare un pool di risorse distinto per gestire l'utilizzo di memoria per il database con tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-105">To protect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from having its resources consumed by one or more memory-optimized tables, and to prevent other memory users from consuming memory needed by memory-optimized tables, you should create a separate resource pool to manage memory consumption for the database with memory-optimized tables.</span></span>  
  
 <span data-ttu-id="7ef11-106">Un database può essere associato a un solo pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-106">A database can be bound on only one resource pool.</span></span> <span data-ttu-id="7ef11-107">Tuttavia, è possibile associare più database allo stesso pool.</span><span class="sxs-lookup"><span data-stu-id="7ef11-107">However, you can bind multiple databases to the same pool.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7ef11-108">consente di associare un database senza tabelle ottimizzate per la memoria a un pool di risorse, ma questa operazione non ha alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="7ef11-108">allows binding a database without memory-optimized tables to a resource pool but it has no effect.</span></span> <span data-ttu-id="7ef11-109">Può essere opportuno associare un database a un pool di risorse denominato se, in futuro, si intende creare tabelle ottimizzate per la memoria nel database.</span><span class="sxs-lookup"><span data-stu-id="7ef11-109">You may want to bind a database to a named resource pool if, in future, you may want to create memory-optimized tables in the database.</span></span>  
  
 <span data-ttu-id="7ef11-110">Prima di poter associare un database a un pool di risorse, è necessario che sia presente sia il database che il pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-110">Before you can bind a database to a resource pool both the database and the resource pool must exist.</span></span> <span data-ttu-id="7ef11-111">L'associazione viene applicata alla successiva connessione del database.</span><span class="sxs-lookup"><span data-stu-id="7ef11-111">The binding takes effect the next time the database is brought online.</span></span> <span data-ttu-id="7ef11-112">Per altre informazioni, vedere [Stati del database](../databases/database-states.md) .</span><span class="sxs-lookup"><span data-stu-id="7ef11-112">See [Database States](../databases/database-states.md) for more information.</span></span>  
  
 <span data-ttu-id="7ef11-113">Per informazioni sui pool di risorse, vedere [Pool di risorse di Resource Governor](../resource-governor/resource-governor-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="7ef11-113">For information about resource pools, see [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span></span>  
  
  
## <a name="create-the-database-and-resource-pool"></a><span data-ttu-id="7ef11-114">Creare il database e il pool di risorse</span><span class="sxs-lookup"><span data-stu-id="7ef11-114">Create the database and resource pool</span></span>  
 <span data-ttu-id="7ef11-115">È possibile creare il database e il pool di risorse in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="7ef11-115">You can create the database and resource pool in any order.</span></span> <span data-ttu-id="7ef11-116">La cosa importante è che entrambi esistano prima di associare il database al pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-116">What matters is that they both exist prior to binding the database to the resource pool.</span></span>  
  
### <a name="create-the-database"></a><span data-ttu-id="7ef11-117">Creare il database</span><span class="sxs-lookup"><span data-stu-id="7ef11-117">Create the database</span></span>  
 <span data-ttu-id="7ef11-118">Con l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene creato un database denominato IMOLTP_DB in cui saranno incluse una o più tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-118">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a database named IMOLTP_DB which will contain one or more memory-optimized tables.</span></span> <span data-ttu-id="7ef11-119">Il percorso \<driveAndPath> deve esistere prima dell'esecuzione del comando.</span><span class="sxs-lookup"><span data-stu-id="7ef11-119">The path \<driveAndPath> must exist prior to running this command.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP_DB  
GO  
ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_fg CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_fg' , FILENAME = 'c:\data\IMOLTP_DB_fg') TO FILEGROUP IMOLTP_DB_fg;  
GO  
```  
  
### <a name="determine-the-minimum-value-for-min_memory_percent-and-max_memory_percent"></a><span data-ttu-id="7ef11-120">Determinare il valore minimo per MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="7ef11-120">Determine the minimum value for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT</span></span>  
 <span data-ttu-id="7ef11-121">Dopo aver determinato la memoria necessaria per le tabelle ottimizzate per la memoria, è necessario determinare la percentuale di memoria disponibile necessaria e impostare le percentuali di memoria su un valore uguale o superiore.</span><span class="sxs-lookup"><span data-stu-id="7ef11-121">Once you determine the memory needs for your memory-optimized tables, you need to determine what percentage of available memory you need, and set the memory percentages to that value or higher.</span></span>  
  
 <span data-ttu-id="7ef11-122">**Esempio:**  </span><span class="sxs-lookup"><span data-stu-id="7ef11-122">**Example:** </span></span>  
<span data-ttu-id="7ef11-123">In questo esempio si suppone che sia stato calcolato che gli indici e le tabelle ottimizzate per la memoria richiedano 16 GB di memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-123">For this example we will assume that from your calculations you determined that your memory-optimized tables and indexes need 16 GB of memory.</span></span> <span data-ttu-id="7ef11-124">Si suppone inoltre che siano stati riservati 32 GB di memoria per l'utilizzo da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7ef11-124">Assume that you have 32 GB of memory committed for your use.</span></span>  
  
 <span data-ttu-id="7ef11-125">A prima vista, si potrebbe ritenere corretto impostare MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT su 50 (16 è il 50% di 32).</span><span class="sxs-lookup"><span data-stu-id="7ef11-125">At first glance it could seem that you need to set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to 50 (16 is 50% of 32).</span></span>  <span data-ttu-id="7ef11-126">Tuttavia, questo valore non garantirebbe memoria sufficiente alle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-126">However, that would not give your memory-optimized tables sufficient memory.</span></span> <span data-ttu-id="7ef11-127">Nella tabella seguente ([la sezione relativa alla percentuale di memoria disponibile per indici e tabelle ottimizzate per la memoria](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) è possibile notare che se si riservano 32 GB di memoria, solo l'80% di tale valore sarà disponibile per gli indici e le tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-127">Looking at the table below ([Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) we see that if there is 32 GB of committed memory, only 80% of that is available for memory-optimized tables and indexes.</span></span>  <span data-ttu-id="7ef11-128">Pertanto, le percentuali minima e massima sono calcolate in base alla memoria disponibile, non alla memoria riservata.</span><span class="sxs-lookup"><span data-stu-id="7ef11-128">Therefore, we calculate the min and max percentages based upon the available memory, not the committed memory.</span></span>  
  
 `memoryNeedeed = 16`   
 `memoryCommitted = 32`   
 `availablePercent = 0.8`   
 `memoryAvailable = memoryCommitted * availablePercent`   
 `percentNeeded = memoryNeeded / memoryAvailable`  
  
 <span data-ttu-id="7ef11-129">Inserimento di numeri reali:</span><span class="sxs-lookup"><span data-stu-id="7ef11-129">Plugging in real numbes:</span></span>   
`percentNeeded = 16 / (32 * 0.8) = 16 / 25.6 = 0.625`  
  
 <span data-ttu-id="7ef11-130">È pertanto necessario almeno il 62,5% della memoria disponibile per soddisfare il requisito di 16 GB degli indici e delle tabelle ottimizzate per la memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-130">Thus you need at least 62.5% of the available memory to meet the 16 GB requirement of your memory-optimized tables and indexes.</span></span>  <span data-ttu-id="7ef11-131">Poiché i valori di MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT devono essere numeri interi, viene impostato un valore pari almeno al 63%.</span><span class="sxs-lookup"><span data-stu-id="7ef11-131">Since the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT must be integers, we set them to at least 63%.</span></span>  
  
### <a name="create-a-resource-pool-and-configure-memory"></a><span data-ttu-id="7ef11-132">Creare un pool di risorse e configurare la memoria</span><span class="sxs-lookup"><span data-stu-id="7ef11-132">Create a resource pool and configure memory</span></span>  
 <span data-ttu-id="7ef11-133">Quando si configura la memoria per le tabelle ottimizzate per la memoria, la pianificazione della capacità deve essere eseguita in base a MIN_MEMORY_PERCENT, non MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="7ef11-133">When configuring memory for memory-optimized tables, the capacity planning should be done based on MIN_MEMORY_PERCENT, not on MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="7ef11-134">Per informazioni su MIN_MEMORY_PERCENT e su MAX_MEMORY_PERCENT, vedere [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ef11-134">See [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) for information on MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="7ef11-135">Ciò rende maggiormente stimabile la disponibilità di memoria per le tabelle ottimizzate per la memoria, poiché MIN_MEMORY_PERCENT causa un utilizzo elevato di memoria per gli altri pool di risorse, al fine di garantire la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="7ef11-135">This provides more predictable memory availability for memory-optimized tables as MIN_MEMORY_PERCENT causes memory pressure to other resource pools to make sure it is honored.</span></span> <span data-ttu-id="7ef11-136">Per garantire che la memoria sia disponibile ed evitare condizioni di memoria insufficiente, i valori di MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT devono essere uguali.</span><span class="sxs-lookup"><span data-stu-id="7ef11-136">To ensure that memory is available and help avoid out-of-memory conditions, the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT should be the same.</span></span> <span data-ttu-id="7ef11-137">Vedere la sezione relativa alla [percentuale di memoria disponibile per indici e tabelle ottimizzate per la memoria](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) per i valori in base alla quantità di memoria riservata.</span><span class="sxs-lookup"><span data-stu-id="7ef11-137">See [Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) below for the percent of memory available for memory-optimized tables based on the amount of committed memory.</span></span>  
  
 <span data-ttu-id="7ef11-138">Per altre informazioni sull'uso di un ambiente di VM, vedere [Procedure consigliate: Uso di OLTP in memoria in un ambiente di VM](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7ef11-138">See [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information when working in a VM environment.</span></span>  
  
 <span data-ttu-id="7ef11-139">Con il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene creato un pool di risorse denominato Pool_IMOLTP con metà della memoria disponibile per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="7ef11-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a resource pool named Pool_IMOLTP with half of the memory available for its use.</span></span>  <span data-ttu-id="7ef11-140">Dopo la creazione del pool, Resource Governor viene riconfigurato in modo da includere Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="7ef11-140">After the pool is created Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
-- set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to the same value  
CREATE RESOURCE POOL Pool_IMOLTP   
  WITH   
    ( MIN_MEMORY_PERCENT = 63,   
    MAX_MEMORY_PERCENT = 63 );  
GO  
  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="bind-the-database-to-the-pool"></a><span data-ttu-id="7ef11-141">Associare il database al pool.</span><span class="sxs-lookup"><span data-stu-id="7ef11-141">Bind the database to the pool</span></span>  
 <span data-ttu-id="7ef11-142">Usare la funzione di sistema `sp_xtp_bind_db_resource_pool` per associare il database al pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-142">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="7ef11-143">La funzione accetta due parametri: il nome del database e il nome del pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-143">The function takes two parameters: the database name and the resource pool name.</span></span>  
  
 <span data-ttu-id="7ef11-144">Con l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene definita un'associazione del database IMOLTP_DB al pool di risorse Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="7ef11-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="7ef11-145">L'associazione non diventa effettiva finché il database non viene portato online.</span><span class="sxs-lookup"><span data-stu-id="7ef11-145">The binding does not become effective until you bring the database online.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
 <span data-ttu-id="7ef11-146">La funzione di sistema sp_xtp_bind_db_resourece_pool accetta due parametri di stringa: database_name e pool_name.</span><span class="sxs-lookup"><span data-stu-id="7ef11-146">The system function sp_xtp_bind_db_resourece_pool takes two string parameters: database_name and pool_name.</span></span>  
  
## <a name="confirm-the-binding"></a><span data-ttu-id="7ef11-147">Verificare l'associazione</span><span class="sxs-lookup"><span data-stu-id="7ef11-147">Confirm the binding</span></span>  
 <span data-ttu-id="7ef11-148">Verificare l'associazione, annotando l'ID del pool di risorse per IMOLTP_DB.</span><span class="sxs-lookup"><span data-stu-id="7ef11-148">Confirm the binding, noting the resource pool id for IMOLTP_DB.</span></span> <span data-ttu-id="7ef11-149">Non deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="7ef11-149">It should not be NULL.</span></span>  
  
```sql  
SELECT d.database_id, d.name, d.resource_pool_id  
FROM sys.databases d  
GO  
```  
  
## <a name="make-the-binding-effective"></a><span data-ttu-id="7ef11-150">Rendere effettiva l'associazione</span><span class="sxs-lookup"><span data-stu-id="7ef11-150">Make the binding effective</span></span>  
 <span data-ttu-id="7ef11-151">Dopo aver associato il database al pool di risorse, è necessario portare il database offline, quindi di nuovo online per rendere effettiva l'associazione.</span><span class="sxs-lookup"><span data-stu-id="7ef11-151">You must take the database offline and back online after binding it to the resource pool for binding to take effect.</span></span> <span data-ttu-id="7ef11-152">Se in precedenza il database era stato associato a un pool diverso, tramite questa operazione la memoria allocata verrà rimossa dal pool di risorse precedente e verranno usate le allocazioni di memoria per gli indici e la tabella ottimizzata per la memoria provenienti dal pool di risorse appena associato al database.</span><span class="sxs-lookup"><span data-stu-id="7ef11-152">If your database was bound to an a different pool earlier, this removes the allocated memory from the previous resource pool and memory allocations for your memory-optimized table and indexes will now come from the resource pool newly bound with the database.</span></span>  
  
```sql  
USE master  
GO  
  
ALTER DATABASE IMOLTP_DB SET OFFLINE  
GO  
ALTER DATABASE IMOLTP_DB SET ONLINE  
GO  
  
USE IMOLTP_DB  
GO  
```  
  
 <span data-ttu-id="7ef11-153">Il database è ora associato al pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-153">And now, the database is bound to the resource pool.</span></span>  
  
## <a name="change-min-memory-percent-and-max-memory-percent-on-an-existing-pool"></a><span data-ttu-id="7ef11-154">Modificare la percentuale minima della memoria e la percentuale massima di memoria in un pool esistente</span><span class="sxs-lookup"><span data-stu-id="7ef11-154">Change MIN MEMORY PERCENT and MAX MEMORY PERCENT on an existing pool</span></span>  
 <span data-ttu-id="7ef11-155">Se si aggiunge altra memoria al server o se cambia la quantità di memoria necessaria per le tabelle ottimizzate per la memoria, può essere necessario modificare il valore di MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="7ef11-155">If you add additional memory to the server or the amount of memory needed for your memory-optimized tables changes, you may need to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="7ef11-156">Nei passaggi seguenti viene illustrato come modificare il valore di MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT in un pool di risorse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-156">The following steps show you how to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on a resource pool.</span></span> <span data-ttu-id="7ef11-157">Per informazioni sui valori da usare per MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT, vedere la sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="7ef11-157">See the section below, for guidance on what values to use for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="7ef11-158">Per altre informazioni, vedere l'argomento [Procedure consigliate: Uso di OLTP in memoria in un ambiente di VM](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7ef11-158">See the topic [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information.</span></span>  
  
1.  <span data-ttu-id="7ef11-159">Usare `ALTER RESOURCE POOL` per modificare il valore di MIN_MEMORY_PERCENT e MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="7ef11-159">Use `ALTER RESOURCE POOL` to change the value of both MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  
  
2.  <span data-ttu-id="7ef11-160">Usare `ALTER RESURCE GOVERNOR` per riconfigurare Resource Governor con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="7ef11-160">Use `ALTER RESURCE GOVERNOR` to reconfigure the Resource Governor with the new values.</span></span>  
  
 <span data-ttu-id="7ef11-161">**Codice di esempio**</span><span class="sxs-lookup"><span data-stu-id="7ef11-161">**Sample Code**</span></span>  
  
```sql  
ALTER RESOURCE POOL Pool_IMOLTP  
WITH  
     ( MIN_MEMORY_PERCENT = 70,  
       MAX_MEMORY_PERCENT = 70 )   
GO  
  
-- reconfigure the Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE  
GO  
```  
  
## <a name="percent-of-memory-available-for-memory-optimized-tables-and-indexes"></a><span data-ttu-id="7ef11-162">Percentuale di memoria disponibile per indici e tabelle ottimizzate per la memoria</span><span class="sxs-lookup"><span data-stu-id="7ef11-162">Percent of memory available for memory-optimized tables and indexes</span></span>  
 <span data-ttu-id="7ef11-163">Se si esegue il mapping di un database con tabella ottimizzata per la memoria e un carico di lavoro di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allo stesso pool di risorse, tramite Resource Governor viene impostata una soglia interna per l'utilizzo di [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] in modo tale che gli utenti del pool non abbiano conflitti per l'utilizzo del pool.</span><span class="sxs-lookup"><span data-stu-id="7ef11-163">If you map a database with memory-optimized tables and a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] workload to the same resource pool, the Resource Governor sets an internal threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use so that the users of the pool do not have conflicts over pool usage.</span></span> <span data-ttu-id="7ef11-164">In generale, la soglia per l'utilizzo di [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] è di circa l'80% del pool.</span><span class="sxs-lookup"><span data-stu-id="7ef11-164">Generally speaking, the threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use is about 80% of the pool.</span></span> <span data-ttu-id="7ef11-165">Nella tabella seguente vengono illustrate le soglie effettive per varie dimensioni di memoria.</span><span class="sxs-lookup"><span data-stu-id="7ef11-165">The following table shows actual thresholds for various memory sizes.</span></span>  
  
 <span data-ttu-id="7ef11-166">Quando si crea un pool di risorse dedicato per il database [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] , è necessario stimare la quantità di memoria fisica necessaria per le tabelle in memoria dopo aver tenuto conto delle versioni di riga e della crescita dei dati.</span><span class="sxs-lookup"><span data-stu-id="7ef11-166">When you create a dedicated resource pool for the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database, you need to estimate how much physical memory you need for the in-memory tables after accounting for row versions and data growth.</span></span> <span data-ttu-id="7ef11-167">Dopo avere stimato la memoria necessaria, è possibile creare un pool di risorse con una percentuale della memoria di destinazione di commit per l'istanza di SQL come indicato nella colonna 'committed_target_kb' nella DMV `sys.dm_os_sys_info` (vedere [sys.dm_os_sys_information](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="7ef11-167">Once estimate the memory needed, you create a resource pool with a percent of the commit target memory for SQL Instance as reflected by column 'committed_target_kb' in the DMV `sys.dm_os_sys_info` (see [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span></span> <span data-ttu-id="7ef11-168">Ad esempio, è possibile creare un pool di risorse P1 con il 40% della memoria totale disponibile per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="7ef11-168">For example, you can create a resource pool P1 with 40% of the total memory available to the instance.</span></span> <span data-ttu-id="7ef11-169">Da questo 40%, il motore di [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] ottiene una percentuale inferiore per archiviare i dati di [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7ef11-169">Out of this 40%, the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine gets a smaller percent to store [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] data.</span></span>  <span data-ttu-id="7ef11-170">Ciò garantisce che [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] non utilizzi tutta la memoria del pool.</span><span class="sxs-lookup"><span data-stu-id="7ef11-170">This is done to make sure [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] does not consume all the memory from this pool.</span></span>  <span data-ttu-id="7ef11-171">Il valore della percentuale inferiore dipende dalla memoria riservata alla destinazione.</span><span class="sxs-lookup"><span data-stu-id="7ef11-171">This value of the smaller percent depends upon the Target committed Memory.</span></span> <span data-ttu-id="7ef11-172">Nella tabella seguente viene descritta la memoria disponibile per il database [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] in un pool di risorse (denominato o predefinito) prima che venga generato un errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="7ef11-172">The following table describes memory available to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database in a resource pool (named or default) before an OOM error is raised.</span></span>  
  
|<span data-ttu-id="7ef11-173">Memoria riservata di destinazione</span><span class="sxs-lookup"><span data-stu-id="7ef11-173">Target Committed Memory</span></span>|<span data-ttu-id="7ef11-174">Percentuale disponibile per le tabelle in memoria</span><span class="sxs-lookup"><span data-stu-id="7ef11-174">Percent available for in-memory tables</span></span>|  
|-----------------------------|---------------------------------------------|  
|<span data-ttu-id="7ef11-175"><= 8 GB</span><span class="sxs-lookup"><span data-stu-id="7ef11-175"><= 8 GB</span></span>|<span data-ttu-id="7ef11-176">70%</span><span class="sxs-lookup"><span data-stu-id="7ef11-176">70%</span></span>|  
|<span data-ttu-id="7ef11-177"><= 16 GB</span><span class="sxs-lookup"><span data-stu-id="7ef11-177"><= 16 GB</span></span>|<span data-ttu-id="7ef11-178">75%</span><span class="sxs-lookup"><span data-stu-id="7ef11-178">75%</span></span>|  
|<span data-ttu-id="7ef11-179"><= 32 GB</span><span class="sxs-lookup"><span data-stu-id="7ef11-179"><= 32 GB</span></span>|<span data-ttu-id="7ef11-180">80%</span><span class="sxs-lookup"><span data-stu-id="7ef11-180">80%</span></span>|  
|<span data-ttu-id="7ef11-181">\<= 96 GB</span><span class="sxs-lookup"><span data-stu-id="7ef11-181">\<= 96 GB</span></span>|<span data-ttu-id="7ef11-182">85%</span><span class="sxs-lookup"><span data-stu-id="7ef11-182">85%</span></span>|  
|<span data-ttu-id="7ef11-183">> 96 GB</span><span class="sxs-lookup"><span data-stu-id="7ef11-183">>96 GB</span></span>|<span data-ttu-id="7ef11-184">90%</span><span class="sxs-lookup"><span data-stu-id="7ef11-184">90%</span></span>|  
  
 <span data-ttu-id="7ef11-185">Ad esempio, se la 'memoria riservata alla destinazione' è di 100 GB e si stima che gli indici e le tabelle ottimizzate per la memoria richiedano 60 GB di memoria, è possibile creare un pool di risorse con MAX_MEMORY_PERCENT = 67 (60 GB necessari/0,90 = 66,667 GB - arrotondamento per eccesso a 67 GB; 67 GB/100 GB installato = 67%) per garantire i 60 GB di memoria necessari agli oggetti di [!INCLUDE[hek_2](../../../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ef11-185">For example, if your 'target committed memory' is 100 GB, and you estimate your memory-optimized tables and indexes need 60GBof memory, then you can create a resource pool with MAX_MEMORY_PERCENT = 67 (60GB needed / 0.90 = 66.667GB - round up to 67GB; 67GB / 100GB installed = 67%) to ensure that your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] objects have the 60GB they need.</span></span>  
  
 <span data-ttu-id="7ef11-186">Dopo l'associazione di un database a un pool di risorse denominato, usare la query seguente per visualizzare le allocazioni di memoria tra pool di risorse diversi.</span><span class="sxs-lookup"><span data-stu-id="7ef11-186">Once a database has been bound to a named resource pool, use the following query to see memory allocations across different resource pools.</span></span>  
  
```sql  
SELECT pool_id  
     , Name  
     , min_memory_percent  
     , max_memory_percent  
     , max_memory_kb/1024 AS max_memory_mb  
     , used_memory_kb/1024 AS used_memory_mb   
     , target_memory_kb/1024 AS target_memory_mb  
   FROM sys.dm_resource_governor_resource_pools  
```  
  
 <span data-ttu-id="7ef11-187">In questo esempio campione viene illustrato che la memoria usata dagli oggetti ottimizzati per la memoria è 1356 MB nel pool di risorse, PoolIMOLTP, con un limite superiore di 2307 MB.</span><span class="sxs-lookup"><span data-stu-id="7ef11-187">This sample output shows that the memory taken by memory-optimized objects is 1356 MB in resource pool, PoolIMOLTP, with an upper bound of 2307 MB.</span></span> <span data-ttu-id="7ef11-188">Il limite superiore controlla la memoria totale che può essere usata dagli oggetti ottimizzati per la memoria di utente e sistema dei quali è stato eseguito il mapping a questo pool.</span><span class="sxs-lookup"><span data-stu-id="7ef11-188">This upper bound controls the total memory that can be taken by user and system memory-optimized objects mapped to this pool.</span></span>  
  
 <span data-ttu-id="7ef11-189">**Esempio di output** </span><span class="sxs-lookup"><span data-stu-id="7ef11-189">**Sample Output** </span></span>  
<span data-ttu-id="7ef11-190">Questo output è tratto dal database e dalle tabelle create in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7ef11-190">This output is from the database and tables we created above.</span></span>  
  
```  
pool_id     Name        min_memory_percent max_memory_percent max_memory_mb used_memory_mb target_memory_mb  
----------- ----------- ------------------ ------------------ ------------- -------------- ----------------   
1           internal    0                  100                3845          125            3845  
2           default     0                  100                3845          32             3845  
259         PoolIMOLTP 0                  100                3845          1356           2307  
```  
  
 <span data-ttu-id="7ef11-191">Per altre informazioni, vedere [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7ef11-191">For more information see [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span></span>  
  
 <span data-ttu-id="7ef11-192">Se il database non viene associato a un pool di risorse denominato, viene associato al pool predefinito ('default').</span><span class="sxs-lookup"><span data-stu-id="7ef11-192">If you do not bind your database to a named resource pool, it is bound to the 'default' pool.</span></span> <span data-ttu-id="7ef11-193">Poiché il pool di risorse predefinito è usato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la maggior parte delle altre allocazioni, non sarà possibile monitorare in modo accurato la memoria usata dalle tabelle ottimizzate per la memoria tramite la DMV sys.dm_resource_governor_resource_pools per il database di interesse.</span><span class="sxs-lookup"><span data-stu-id="7ef11-193">Since default resource pool is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for most other allocations, you will not be able to monitor memory consumed by memory-optimized tables using the DMV sys.dm_resource_governor_resource_pools accurately for the database of interest.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef11-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ef11-194">See Also</span></span>  
 <span data-ttu-id="7ef11-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ef11-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="7ef11-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7ef11-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="7ef11-197">[Resource Governor](../resource-governor/resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="7ef11-197">[Resource Governor](../resource-governor/resource-governor.md) </span></span>  
 <span data-ttu-id="7ef11-198">[Pool di risorse di Resource Governor](../resource-governor/resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7ef11-198">[Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="7ef11-199">[Creare un pool di risorse](../resource-governor/create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="7ef11-199">[Create a Resource Pool](../resource-governor/create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="7ef11-200">[Modificare le impostazioni del pool di risorse](../resource-governor/change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7ef11-200">[Change Resource Pool Settings](../resource-governor/change-resource-pool-settings.md) </span></span>  
 [<span data-ttu-id="7ef11-201">Eliminare un pool di risorse</span><span class="sxs-lookup"><span data-stu-id="7ef11-201">Delete a Resource Pool</span></span>](../resource-governor/delete-a-resource-pool.md)  
  
  