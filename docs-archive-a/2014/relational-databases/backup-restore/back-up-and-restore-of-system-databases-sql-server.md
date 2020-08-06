---
title: Backup e ripristino di database di sistema (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server], backing up and restoring
- restoring system databases [SQL Server]
- backing up [SQL Server], system databases
- database backups [SQL Server], system databases
- servers [SQL Server], backup
ms.assetid: aef0c4fa-ba67-413d-9359-1a67682fdaab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51ccf1aeadcf4ab9a662cdd629a812d3ee4b82aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637945"
---
# <a name="back-up-and-restore-of-system-databases-sql-server"></a><span data-ttu-id="58245-102">Backup e ripristino di Database di sistema (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="58245-102">Back Up and Restore of System Databases (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="58245-103">gestisce un set di database a livello di sistema, denominati*database di sistema*, fondamentali per un corretto funzionamento di un'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="58245-103">maintains a set of system-level databases, s*ystem databases*, which are essential for the operation of a server instance.</span></span> <span data-ttu-id="58245-104">Dopo ogni aggiornamento importante, è necessario eseguire il backup di numerosi database di sistema.</span><span class="sxs-lookup"><span data-stu-id="58245-104">Several of the system databases must be backed up after every significant update.</span></span> <span data-ttu-id="58245-105">Alcuni database di sistema di cui è necessario eseguire sempre il backup sono **msdb**, **master**e **model**.</span><span class="sxs-lookup"><span data-stu-id="58245-105">The system databases that you must always back up include **msdb**, **master**, and **model**.</span></span> <span data-ttu-id="58245-106">Se un database usa la replica nell'istanza del server, è necessario eseguire il backup anche di un database di sistema **distribution** .</span><span class="sxs-lookup"><span data-stu-id="58245-106">If any database uses replication on the server instance, there is a **distribution** system database that you must also back up.</span></span> <span data-ttu-id="58245-107">I backup di questi database di sistema consentono di ripristinare e recuperare il sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qualora si verifichi un errore a livello di sistema, ad esempio un problema che impedisce di utilizzare un disco rigido.</span><span class="sxs-lookup"><span data-stu-id="58245-107">Backups of these system databases let you restore and recover the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system in the event of system failure, such as the loss of a hard disk.</span></span>  
  
 <span data-ttu-id="58245-108">Nella tabella seguente è presentato un riepilogo di tutti i database di sistema.</span><span class="sxs-lookup"><span data-stu-id="58245-108">The following table summarizes all of the system databases.</span></span>  
  
|<span data-ttu-id="58245-109">Database di sistema</span><span class="sxs-lookup"><span data-stu-id="58245-109">System database</span></span>|<span data-ttu-id="58245-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="58245-110">Description</span></span>|<span data-ttu-id="58245-111">Necessità di backup</span><span class="sxs-lookup"><span data-stu-id="58245-111">Are backups required?</span></span>|<span data-ttu-id="58245-112">modello di recupero</span><span class="sxs-lookup"><span data-stu-id="58245-112">Recovery model</span></span>|<span data-ttu-id="58245-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="58245-113">Comments</span></span>|  
|---------------------|-----------------|---------------------------|--------------------|--------------|  
|[<span data-ttu-id="58245-114">master</span><span class="sxs-lookup"><span data-stu-id="58245-114">master</span></span>](../databases/master-database.md)|<span data-ttu-id="58245-115">Nel database vengono registrate tutte le informazioni a livello di sistema relative a un sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58245-115">The database that records all of the system level information for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system.</span></span>|<span data-ttu-id="58245-116">Sì</span><span class="sxs-lookup"><span data-stu-id="58245-116">Yes</span></span>|<span data-ttu-id="58245-117">Semplice</span><span class="sxs-lookup"><span data-stu-id="58245-117">Simple</span></span>|<span data-ttu-id="58245-118">Eseguire il backup di **master** con la frequenza necessaria a garantire una sufficiente protezione dei dati in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="58245-118">Back up **master** as often as necessary to protect the data sufficiently for your business needs.</span></span> <span data-ttu-id="58245-119">È consigliabile pianificare i backup con regolarità, pianificazione che è possibile integrare con backup aggiuntivi dopo un aggiornamento importante.</span><span class="sxs-lookup"><span data-stu-id="58245-119">We recommend a regular backup schedule, which you can supplement with an additional backup after a substantial update.</span></span>|  
|[<span data-ttu-id="58245-120">model</span><span class="sxs-lookup"><span data-stu-id="58245-120">model</span></span>](../databases/model-database.md)|<span data-ttu-id="58245-121">Modello per tutti i database creati nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58245-121">The template for all databases that are created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|<span data-ttu-id="58245-122">Sì</span><span class="sxs-lookup"><span data-stu-id="58245-122">Yes</span></span>|<span data-ttu-id="58245-123">Configurabile dall'utente<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="58245-123">User configurable<sup>1</sup></span></span>|<span data-ttu-id="58245-124">Eseguire il backup di **model** solo se necessario in base alle esigenze aziendali, ad esempio immediatamente dopo la personalizzazione delle opzioni del database.</span><span class="sxs-lookup"><span data-stu-id="58245-124">Back up **model** only when necessary for your business needs; for example, immediately after customizing its database options.</span></span><br /><br /> <span data-ttu-id="58245-125">**Procedura consigliata:** creare solo backup completi del database **model** in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="58245-125">**Best practice:** We recommend that you create only full database backups of **model**, as required.</span></span> <span data-ttu-id="58245-126">Poiché nel database **model** vengono apportate solo di rado lievi modifiche, il backup del log non è necessario.</span><span class="sxs-lookup"><span data-stu-id="58245-126">Because **model** is small and rarely changes, backing up the log is unnecessary.</span></span>|  
|[<span data-ttu-id="58245-127">msdb</span><span class="sxs-lookup"><span data-stu-id="58245-127">msdb</span></span>](../databases/msdb-database.md)|<span data-ttu-id="58245-128">Il database utilizzato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per la pianificazione di avvisi e processi e per la registrazione di operatori.</span><span class="sxs-lookup"><span data-stu-id="58245-128">The database used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent for scheduling alerts and jobs, and for recording operators.</span></span> <span data-ttu-id="58245-129">**msdb** contiene anche tabelle di cronologia, ad esempio tabelle di cronologia di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="58245-129">**msdb** also contains history tables such as the backup and restore history tables.</span></span>|<span data-ttu-id="58245-130">Sì</span><span class="sxs-lookup"><span data-stu-id="58245-130">Yes</span></span>|<span data-ttu-id="58245-131">Con registrazione minima (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="58245-131">Simple (default)</span></span>|<span data-ttu-id="58245-132">Eseguire il backup di **msdb** a ogni aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="58245-132">Back up **msdb** whenever it is updated.</span></span>|  
|<span data-ttu-id="58245-133">[Resource](../databases/resource-database.md) (RDB)</span><span class="sxs-lookup"><span data-stu-id="58245-133">[Resource](../databases/resource-database.md) (RDB)</span></span>|<span data-ttu-id="58245-134">Database di sola lettura che include copie di tutti gli oggetti di sistema forniti con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58245-134">A read-only database that contains copies of all system objects that ship with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>|<span data-ttu-id="58245-135">No</span><span class="sxs-lookup"><span data-stu-id="58245-135">No</span></span>|-|<span data-ttu-id="58245-136">Il database **Resource** risiede nel file mssqlsystemresource.mdf, che contiene solo codice.</span><span class="sxs-lookup"><span data-stu-id="58245-136">The **Resource** database resides in the mssqlsystemresource.mdf file, which contains only code.</span></span> <span data-ttu-id="58245-137">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non può quindi eseguire il backup del database **Resource** .</span><span class="sxs-lookup"><span data-stu-id="58245-137">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot back up the **Resource** database.</span></span><br /><br /> <span data-ttu-id="58245-138">Nota: è possibile eseguire un backup basato su file o su disco sul file mssqlsystemresource.mdf, considerando il file come un file binario con estensione exe anziché come un file di database.</span><span class="sxs-lookup"><span data-stu-id="58245-138">Note: You can perform a file-based or a disk-based backup on the mssqlsystemresource.mdf file by treating the file as if it were a binary (.exe) file, instead of a database file.</span></span> <span data-ttu-id="58245-139">Non è tuttavia possibile utilizzare la funzionalità di ripristino di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su questi backup.</span><span class="sxs-lookup"><span data-stu-id="58245-139">But you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] restore on the backups.</span></span> <span data-ttu-id="58245-140">Il ripristino di una copia di backup di mssqlsystemresource.mdf può essere eseguito solo manualmente, prestando attenzione a non sovrascrivere il database **Resource** corrente con una versione non aggiornata e potenzialmente non sicura.</span><span class="sxs-lookup"><span data-stu-id="58245-140">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current **Resource** database with an out-of-date or potentially insecure version.</span></span>|  
|[<span data-ttu-id="58245-141">tempdb</span><span class="sxs-lookup"><span data-stu-id="58245-141">tempdb</span></span>](../databases/tempdb-database.md)|<span data-ttu-id="58245-142">Area di lavoro per il mantenimento dei set di risultati temporanei o intermedi.</span><span class="sxs-lookup"><span data-stu-id="58245-142">A workspace for holding temporary or intermediate result sets.</span></span> <span data-ttu-id="58245-143">Questo database viene ricreato ogni volta che viene avviata un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58245-143">This database is re-created every time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> <span data-ttu-id="58245-144">Quando l'istanza del server viene chiusa, i dati inclusi in **tempdb** vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="58245-144">When the server instance is shut down, any data in **tempdb** is deleted permanently.</span></span>|<span data-ttu-id="58245-145">No</span><span class="sxs-lookup"><span data-stu-id="58245-145">No</span></span>|<span data-ttu-id="58245-146">Semplice</span><span class="sxs-lookup"><span data-stu-id="58245-146">Simple</span></span>|<span data-ttu-id="58245-147">Non è possibile eseguire il backup del database di sistema **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="58245-147">You cannot back up the **tempdb** system database.</span></span>|  
|[<span data-ttu-id="58245-148">Configurare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="58245-148">Configure Distribution</span></span>](../replication/configure-distribution.md)|<span data-ttu-id="58245-149">Database esistente solo se il server è configurato come server di distribuzione repliche.</span><span class="sxs-lookup"><span data-stu-id="58245-149">A database that exists only if the server is configured as a replication Distributor.</span></span> <span data-ttu-id="58245-150">In questo database sono memorizzati metadati e dati della cronologia per tutti i tipi di replica, nonché transazioni per la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="58245-150">This database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>|<span data-ttu-id="58245-151">Sì</span><span class="sxs-lookup"><span data-stu-id="58245-151">Yes</span></span>|<span data-ttu-id="58245-152">Semplice</span><span class="sxs-lookup"><span data-stu-id="58245-152">Simple</span></span>|<span data-ttu-id="58245-153">Per informazioni su quando eseguire il backup del database **distribution** , vedere [Eseguire il backup e ripristino di database replicati](../replication/administration/back-up-and-restore-replicated-databases.md).</span><span class="sxs-lookup"><span data-stu-id="58245-153">For information about when to back up the **distribution** database, see [Back Up and Restore Replicated Databases](../replication/administration/back-up-and-restore-replicated-databases.md).</span></span>|  
  
 <span data-ttu-id="58245-154"><sup>1</sup> per informazioni sul modello di recupero corrente del modello, vedere [visualizzare o modificare il modello di recupero di un database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md) o [sys. databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="58245-154"><sup>1</sup> To learn the current recovery model of the model, see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](view-or-change-the-recovery-model-of-a-database-sql-server.md) or [sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql).</span></span>  
  
## <a name="limitations-on-restoring-system-databases"></a><span data-ttu-id="58245-155">Limitazioni sul ripristino di database di sistema</span><span class="sxs-lookup"><span data-stu-id="58245-155">Limitations on Restoring System Databases</span></span>  
  
-   <span data-ttu-id="58245-156">I database di sistema possono essere ripristinati solo da backup creati nella versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguita nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="58245-156">System databases can be restored only from backups that are created on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the server instance is currently running.</span></span> <span data-ttu-id="58245-157">Ad esempio, per ripristinare un database di sistema in un'istanza del server in esecuzione in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="58245-157">For example, to restore a system database on a server instance that is running on [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] SP1.</span></span>  
  
-   <span data-ttu-id="58245-158">Per ripristinare un database, è necessario che l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="58245-158">To restore any database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be running.</span></span> <span data-ttu-id="58245-159">Per l'avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è necessario che il database **master** sia accessibile e utilizzabile almeno in parte.</span><span class="sxs-lookup"><span data-stu-id="58245-159">Startup of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires that the **master** database is accessible and at least partly usable.</span></span> <span data-ttu-id="58245-160">Se il database **master** diventa inutilizzabile, è possibile ripristinare uno stato utilizzabile del database in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="58245-160">If **master** becomes unusable, you can return the database to a usable state in either of the following ways:</span></span>  
  
    -   <span data-ttu-id="58245-161">Ripristinare il database **master** da un backup del database corrente.</span><span class="sxs-lookup"><span data-stu-id="58245-161">Restore **master** from a current database backup.</span></span>  
  
         <span data-ttu-id="58245-162">Se è possibile avviare l'istanza del server, dovrebbe essere possibile anche ripristinare il database **master** da un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="58245-162">If you can start the server instance, you should be able to restore **master** from a full database backup.</span></span>  
  
    -   <span data-ttu-id="58245-163">Ricompilare il database **master** da zero.</span><span class="sxs-lookup"><span data-stu-id="58245-163">Rebuild **master** completely.</span></span>  
  
         <span data-ttu-id="58245-164">Se non è possibile avviare **in seguito a gravi danni al database** master [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è necessario ricompilare il database **master**.</span><span class="sxs-lookup"><span data-stu-id="58245-164">If severe damage to **master** prevents you from starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must rebuild **master**.</span></span> <span data-ttu-id="58245-165">Per altre informazioni, vedere [Ricompilare database di sistema](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="58245-165">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="58245-166">La ricompilazione del database **master** comporta la ricompilazione di tutti i database di sistema.</span><span class="sxs-lookup"><span data-stu-id="58245-166">Rebuilding **master** rebuilds all of the system databases.</span></span>  
  
-   <span data-ttu-id="58245-167">In alcune circostanze, per i problemi relativi al recupero del database modello può essere necessario ricompilare i database di sistema o sostituire i file mdf e ldf del database modello.</span><span class="sxs-lookup"><span data-stu-id="58245-167">Under some circumstances, problems recovering the model database may require rebuilding the system databases or replacing the mdf and ldf files for the model database.</span></span> <span data-ttu-id="58245-168">Per altre informazioni, vedere [Ricompilare database di sistema](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="58245-168">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="58245-169">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="58245-169">Related Tasks</span></span>  
  
-   [<span data-ttu-id="58245-170">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58245-170">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="58245-171">Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;</span><span class="sxs-lookup"><span data-stu-id="58245-171">Complete Database Restores &#40;Simple Recovery Model&#41;</span></span>](complete-database-restores-simple-recovery-model.md)  
  
-   [<span data-ttu-id="58245-172">Ripristinare il database master &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="58245-172">Restore the master Database &#40;Transact-SQL&#41;</span></span>](restore-the-master-database-transact-sql.md)  
  
-   [<span data-ttu-id="58245-173">Visualizzazione o modifica del modello di recupero di un database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="58245-173">View or Change the Recovery Model of a Database &#40;SQL Server&#41;</span></span>](view-or-change-the-recovery-model-of-a-database-sql-server.md)  
  
-   [<span data-ttu-id="58245-174">Spostare i database di sistema</span><span class="sxs-lookup"><span data-stu-id="58245-174">Move System Databases</span></span>](../databases/move-system-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="58245-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58245-175">See Also</span></span>  
 <span data-ttu-id="58245-176">[Database di distribuzione](../../relational-databases/replication/distribution-database.md) </span><span class="sxs-lookup"><span data-stu-id="58245-176">[Distribution Database](../../relational-databases/replication/distribution-database.md) </span></span>  
 <span data-ttu-id="58245-177">[Database master](../databases/master-database.md) </span><span class="sxs-lookup"><span data-stu-id="58245-177">[master Database](../databases/master-database.md) </span></span>  
 <span data-ttu-id="58245-178">[Database msdb](../databases/msdb-database.md) </span><span class="sxs-lookup"><span data-stu-id="58245-178">[msdb Database](../databases/msdb-database.md) </span></span>  
 <span data-ttu-id="58245-179">[Database model](../databases/model-database.md) </span><span class="sxs-lookup"><span data-stu-id="58245-179">[model Database](../databases/model-database.md) </span></span>  
 <span data-ttu-id="58245-180">[Database Resource](../databases/resource-database.md) </span><span class="sxs-lookup"><span data-stu-id="58245-180">[Resource Database](../databases/resource-database.md) </span></span>  
 [<span data-ttu-id="58245-181">Database tempdb</span><span class="sxs-lookup"><span data-stu-id="58245-181">tempdb Database</span></span>](../databases/tempdb-database.md)  
  
  