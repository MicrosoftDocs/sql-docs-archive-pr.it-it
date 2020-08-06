---
title: Gestione di account di accesso e processi per i database di un gruppo di disponibilità (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], failover
- failover [SQL Server], AlwaysOn Availability Groups
ms.assetid: d7da14d3-848c-44d4-8e49-d536a1158a61
author: rothja
ms.author: jroth
ms.openlocfilehash: 457f3ef946b5cfaf86a4a19774af63c5d7635882
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638035"
---
# <a name="management-of-logins-and-jobs-for-the-databases-of-an-availability-group-sql-server"></a><span data-ttu-id="ac605-102">Gestione di account di accesso e processi per i database di un gruppo di disponibilità (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ac605-102">Management of Logins and Jobs for the Databases of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="ac605-103">È necessario gestire periodicamente lo stesso set di account di accesso utente e processi [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent in ogni database primario di un gruppo di disponibilità AlwaysOn e nei database secondari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ac605-103">You should routinely maintain the same set of user logins and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs on every primary database of an AlwaysOn availability group and the corresponding secondary databases.</span></span> <span data-ttu-id="ac605-104">Gli account di accesso e i processi devono essere riprodotti in ogni istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in cui è ospitata una replica di disponibilità per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ac605-104">The logins and jobs must be reproduced on every instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that hosts an availability replica for the availability group.</span></span>  
  
-   <span data-ttu-id="ac605-105">**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]Processi di Agent**</span><span class="sxs-lookup"><span data-stu-id="ac605-105">**[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs**</span></span>  
  
     <span data-ttu-id="ac605-106">È necessario copiare manualmente i processi rilevanti dall'istanza del server in cui è ospitata la replica primaria originale alle istanze del server in cui sono ospitate le repliche secondarie originali.</span><span class="sxs-lookup"><span data-stu-id="ac605-106">You need to manually copy relevant jobs from the server instance that hosts the original primary replica to the server instances that host the original secondary replicas.</span></span> <span data-ttu-id="ac605-107">Per tutti i database è necessario aggiungere logica all'inizio di ogni processo rilevante affinché il processo venga eseguito solo nel database primario, ovvero solo se la replica locale è la replica primaria del database.</span><span class="sxs-lookup"><span data-stu-id="ac605-107">For all databases, you need to add logic at the beginning of each relevant job to make the job execute only on the primary database, that is, only when the local replica is the primary replica for the database.</span></span>  
  
     <span data-ttu-id="ac605-108">Le istanze del server che ospitano le repliche di disponibilità di un gruppo di disponibilità potrebbero essere configurate in modo diverso, con lettere di unità nastro diverse e così via.</span><span class="sxs-lookup"><span data-stu-id="ac605-108">The server instances that host the availability replicas of an availability group might be configured differently, with different tape drive letters or such.</span></span> <span data-ttu-id="ac605-109">I processi per ogni replica di disponibilità devono supportare eventuali differenze di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="ac605-109">The jobs for each availability replica must allow for any such differences.</span></span>  
  
     <span data-ttu-id="ac605-110">I processi di backup possono usare la funzione [sys.fn_hadr_is_preferred_backup_replica](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql) per identificare se la replica locale è quella preferita per i backup, in base alle preferenze di backup del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ac605-110">Notice that backup jobs can use the [sys.fn_hadr_is_preferred_backup_replica](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql) function to identify whether the local replica is the preferred one for backups, according to the availability group backup preferences.</span></span> <span data-ttu-id="ac605-111">I processi di backup creati tramite la [Creazione guidata piano di manutenzione](../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md) a livello nativo usano questa funzione.</span><span class="sxs-lookup"><span data-stu-id="ac605-111">Backup jobs created using the [Maintenance Plan Wizard](../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md) natively use this function.</span></span> <span data-ttu-id="ac605-112">Per altri processi di backup, è consigliabile utilizzare questa funzione come condizione nei processi di backup, pertanto vengono eseguiti solo nella replica preferita.</span><span class="sxs-lookup"><span data-stu-id="ac605-112">For other backup jobs, we recommend that you use this function as a condition in your backup jobs, so they execute only on the preferred replica.</span></span> <span data-ttu-id="ac605-113">Per ulteriori informazioni, vedere [repliche secondarie attive: backup in repliche secondarie (gruppi di disponibilità AlwaysOn)](availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ac605-113">For more information, see [Active Secondaries: Backup on Secondary Replicas (AlwaysOn Availability Groups)](availability-groups/windows/active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md).</span></span>  
  
-   <span data-ttu-id="ac605-114">**Account di accesso**</span><span class="sxs-lookup"><span data-stu-id="ac605-114">**Logins**</span></span>  
  
     <span data-ttu-id="ac605-115">Se si utilizzano database indipendenti, è possibile configurare utenti indipendenti nei database per i quali non è necessario creare account di accesso nelle istanze del server che ospitano una replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="ac605-115">If you are using contained databases, you can configure contained users in the databases, and for these users, you do not need to create logins on the server instances that host a secondary replica.</span></span> <span data-ttu-id="ac605-116">Per un database di disponibilità non indipendente, sarà necessario creare utenti per gli account di accesso nelle istanze del server che ospitano le repliche di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ac605-116">For a non-contained availability database, you will need to create users for the logins on the server instances that host the availability replicas.</span></span> <span data-ttu-id="ac605-117">Per altre informazioni, vedere [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ac605-117">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="ac605-118">Se una o più applicazioni usano l'autenticazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o un account Windows locale, vedere [Account di accesso di applicazioni in cui viene utilizzata l'autenticazione di SQL Server o un account di accesso di Windows locale](../../2014/database-engine/logins-and-jobs-for-availability-group-databases.md#SSauthentication), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ac605-118">If any of your applications use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication or a local Windows login, see [Logins Of Applications That Use SQL Server Authentication or a Local Windows Login](../../2014/database-engine/logins-and-jobs-for-availability-group-databases.md#SSauthentication), later in this topic.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ac605-119">Un utente del database il cui account di accesso di SQL Server non è definito o è definito in modo errato in un'istanza del server non potrà accedere a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="ac605-119">A database user for which the SQL Server login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="ac605-120">Questo utente viene definito *utente orfano* del database nell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="ac605-120">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="ac605-121">Se un utente è isolato in una determinata istanza del server, è possibile impostare account di accesso utente in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ac605-121">If a user is orphaned on a given server instance, you can set up the user logins at any time.</span></span> <span data-ttu-id="ac605-122">Per altre informazioni, vedere [Risolvere i problemi relativi agli utenti isolati &#40;SQL Server&#41;](../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac605-122">For more information, see [Troubleshoot Orphaned Users &#40;SQL Server&#41;](../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md).</span></span>  
  
-   <span data-ttu-id="ac605-123">**Metadati aggiuntivi**</span><span class="sxs-lookup"><span data-stu-id="ac605-123">**Additional metadata**</span></span>  
  
     <span data-ttu-id="ac605-124">Gli account di accesso e i processi non sono le uniche informazioni che è necessario ricreare in ogni istanza del server in cui è ospitata una replica secondaria per uno specifico gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="ac605-124">Logins and jobs are not the only information that need to be recreated on each of the server instances that hosts an secondary replica for a given availability group.</span></span> <span data-ttu-id="ac605-125">Potrebbe ad esempio essere necessario ricreare le impostazioni di configurazione del server, credenziali, dati crittografati, autorizzazioni, impostazioni di replica, applicazioni di Service Broker, trigger (a livello di server) e così via.</span><span class="sxs-lookup"><span data-stu-id="ac605-125">For example, you might need to recreate server configuration settings, credentials, encrypted data, permissions, replication settings, service broker applications, triggers (at server level), and so forth.</span></span> <span data-ttu-id="ac605-126">Per altre informazioni, vedere [Gestione dei metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;](../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="ac605-126">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
##  <a name="logins-of-applications-that-use-sql-server-authentication-or-a-local-windows-login"></a><a name="SSauthentication"></a> <span data-ttu-id="ac605-127">Account di accesso di applicazioni in cui viene utilizzata l'autenticazione di SQL Server o un account di accesso di Windows locale</span><span class="sxs-lookup"><span data-stu-id="ac605-127">Logins Of Applications That Use SQL Server Authentication or a Local Windows Login</span></span>  
 <span data-ttu-id="ac605-128">Se in un'applicazione viene utilizzata l'autenticazione di SQL Server o un account di accesso di Windows locale, i SID non corrispondenti possono impedire la risoluzione in un'istanza remota di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]da parte dell'account di accesso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac605-128">If an application uses SQL Server Authentication or a local Windows login, mismatched SIDs can prevent the application's login from resolving on a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac605-129">In caso di SID non corrispondenti, l'account di accesso diventa un utente orfano nell'istanza del server remoto.</span><span class="sxs-lookup"><span data-stu-id="ac605-129">The mismatched SIDs cause the login to become an orphaned user on the remote server instance.</span></span> <span data-ttu-id="ac605-130">Questo problema si può verificare quando tramite un'applicazione si effettua la connessione a un database di log shipping o con mirroring dopo un failover o a un database Sottoscrittore di replica inizializzato da un backup.</span><span class="sxs-lookup"><span data-stu-id="ac605-130">This issue can occur when an application connects to a mirrored or log shipping database after a failover or to a replication subscriber database that was initialized from a backup.</span></span>  
  
 <span data-ttu-id="ac605-131">Per evitare questo problema, è consigliabile intraprendere misure preventive quando si configura un'applicazione di questo tipo per utilizzare un database ospitato da un'istanza remota di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac605-131">To prevent this issue, we recommend that you take preventative measures when you set up such an application to use a database that is hosted by a remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac605-132">La prevenzione comporta il trasferimento degli account di accesso e delle password dall'istanza locale di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] all'istanza remota di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ac605-132">Prevention involves transferring the logins and the passwords from the local instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to the remote instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ac605-133">Per altre informazioni su come evitare questo problema, vedere l'articolo della Knowledge Base 918992 relativo alla [modalità di trasferimento degli account di accesso e delle password tra le istanze di SQL Server](https://support.microsoft.com/kb/918992/).</span><span class="sxs-lookup"><span data-stu-id="ac605-133">For more information about how to prevent this issue, see KB article 918992-[How to transfer the logins and the passwords between instances of SQL Server](https://support.microsoft.com/kb/918992/)).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac605-134">Questo problema influisce sugli account di Windows locali in computer diversi.</span><span class="sxs-lookup"><span data-stu-id="ac605-134">This problem affects Windows local accounts on different computers.</span></span> <span data-ttu-id="ac605-135">Tuttavia, non si verifica in caso di account di dominio, dal momento che il SID è identico in ogni computer.</span><span class="sxs-lookup"><span data-stu-id="ac605-135">However, this problem does not occur for domain accounts because the SID is the same on each of the computers.</span></span>  
  
 <span data-ttu-id="ac605-136">Per altre informazioni, vedere la pagina relativa agli [utenti orfani con log shipping e mirroring del database](https://blogs.msdn.com/b/sqlserverfaq/archive/2009/04/13/orphaned-users-with-database-mirroring-and-log-shipping.aspx) (blog del motore di database).</span><span class="sxs-lookup"><span data-stu-id="ac605-136">For more information, see [Orphaned Users with Database Mirroring and Log Shipping](https://blogs.msdn.com/b/sqlserverfaq/archive/2009/04/13/orphaned-users-with-database-mirroring-and-log-shipping.aspx) (a Database Engine blog).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="ac605-137">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="ac605-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="ac605-138">Creare un account di accesso</span><span class="sxs-lookup"><span data-stu-id="ac605-138">Create a Login</span></span>](../relational-databases/security/authentication-access/create-a-login.md)  
  
-   <span data-ttu-id="ac605-139">[Creare un utente del database](../relational-databases/security/authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="ac605-139">[Create a Database User](../relational-databases/security/authentication-access/create-a-database-user.md).</span></span>  
  
-   [<span data-ttu-id="ac605-140">Creazione di un processo</span><span class="sxs-lookup"><span data-stu-id="ac605-140">Create a Job</span></span>](../ssms/agent/create-a-job.md)  
  
-   [<span data-ttu-id="ac605-141">Gestire i metadati quando si rende disponibile un database in un'altra istanza del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ac605-141">Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;</span></span>](../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac605-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac605-142">See Also</span></span>  
 <span data-ttu-id="ac605-143">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ac605-143">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](availability-groups/windows/overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="ac605-144">[Database indipendenti](../relational-databases/databases/contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ac605-144">[Contained Databases](../relational-databases/databases/contained-databases.md) </span></span>  
 [<span data-ttu-id="ac605-145">Creazione di processi</span><span class="sxs-lookup"><span data-stu-id="ac605-145">Create Jobs</span></span>](../ssms/agent/create-jobs.md)  
  
  