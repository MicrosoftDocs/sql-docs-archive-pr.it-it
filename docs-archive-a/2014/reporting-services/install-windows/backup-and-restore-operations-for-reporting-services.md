---
title: Operazioni di backup e ripristino per Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- databases [Reporting Services], backing up
- databases [Reporting Services], restoring
- databases [Reporting Services], moving
- backing up databases [Reporting Services]
- moving databases
- restoring databases [Reporting Services]
- files [Reporting Services], restoring
- files [Reporting Services], backing up
ms.assetid: 157bc376-ab72-4c99-8bde-7b12db70843a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e895733457fe0c8892294540bbe8345cb121f2a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635960"
---
# <a name="backup-and-restore-operations-for-reporting-services"></a><span data-ttu-id="71b0c-102">Operazioni di backup e ripristino per Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71b0c-102">Backup and Restore Operations for Reporting Services</span></span>
  <span data-ttu-id="71b0c-103">In questo argomento viene fornita una panoramica di tutti i file di dati utilizzato in un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e viene descritto quando e come è necessario eseguire il backup dei file.</span><span class="sxs-lookup"><span data-stu-id="71b0c-103">This topic provides an overview of all data files used in a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation and describes when and how you should back up the files.</span></span> <span data-ttu-id="71b0c-104">Lo sviluppo di un piano di backup e ripristino per i file dei database del server di report rappresenta la parte più importante di una strategia di recupero.</span><span class="sxs-lookup"><span data-stu-id="71b0c-104">Developing a backup and restore plan for the report server database files is the most important part of a recovery strategy.</span></span> <span data-ttu-id="71b0c-105">Una strategia di recupero più completa include tuttavia i backup delle chiavi di crittografia, di estensioni o assembly personalizzati, dei file di configurazione e dei file di origine di report e modelli.</span><span class="sxs-lookup"><span data-stu-id="71b0c-105">However, a more comprehensive recovery strategy would include backups of the encryption keys, custom assemblies or extensions, configuration files, and source files for reports and models.</span></span>  
  
 <span data-ttu-id="71b0c-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  Modalità nativa di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] | Modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b0c-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native Mode | [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint Mode</span></span>  
  
 <span data-ttu-id="71b0c-107">Le operazioni di backup e ripristino vengono spesso utilizzate per spostare un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] o parte di essa:</span><span class="sxs-lookup"><span data-stu-id="71b0c-107">Backup and restore operations are often used to move all or part of a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation:</span></span>  
  
-   <span data-ttu-id="71b0c-108">Se si stanno spostando solo i database del server di report, è possibile utilizzare il backup e il ripristino oppure eseguire il collegamento e lo scollegamento per spostare i database in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] diversa.</span><span class="sxs-lookup"><span data-stu-id="71b0c-108">If you are moving just the report server databases, you can use backup and restore or attach and detach to relocate the databases on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="71b0c-109">Per altre informazioni, vedere [Spostamento di database del server di report in un altro computer &#40;modalità nativa SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="71b0c-109">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>  
  
-   <span data-ttu-id="71b0c-110">Lo spostamento di un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un nuovo computer viene definito migrazione.</span><span class="sxs-lookup"><span data-stu-id="71b0c-110">Moving a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation to a new computer is called a migration.</span></span> <span data-ttu-id="71b0c-111">In caso di migrazione di un'installazione, eseguire il programma di installazione per installare una nuova istanza del server di report e quindi copiare i dati dell'istanza in un nuovo computer.</span><span class="sxs-lookup"><span data-stu-id="71b0c-111">When you migrate an installation, you run Setup to install a new report server instance and then copy instance data to the new computer.</span></span> <span data-ttu-id="71b0c-112">Per ulteriori informazioni sulla migrazione di un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="71b0c-112">For more information about migrating a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="71b0c-113">Eseguire l'aggiornamento e la migrazione di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="71b0c-113">Upgrade and Migrate Reporting Services</span></span>](upgrade-and-migrate-reporting-services.md)  
  
    -   [<span data-ttu-id="71b0c-114">Eseguire la migrazione di un'installazione di Reporting Services &#40;modalità SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="71b0c-114">Migrate a Reporting Services Installation &#40;SharePoint Mode&#41;</span></span>](migrate-a-reporting-services-installation-sharepoint-mode.md)  
  
    -   [<span data-ttu-id="71b0c-115">Eseguire la migrazione di un'installazione di Reporting Services &#40;modalità nativa&#41;</span><span class="sxs-lookup"><span data-stu-id="71b0c-115">Migrate a Reporting Services Installation &#40;Native Mode&#41;</span></span>](migrate-a-reporting-services-installation-native-mode.md)  
  
## <a name="backing-up-the-report-server-databases"></a><span data-ttu-id="71b0c-116">Backup dei database del server di report</span><span class="sxs-lookup"><span data-stu-id="71b0c-116">Backing Up the Report Server Databases</span></span>  
 <span data-ttu-id="71b0c-117">Poiché un server di report è un server senza stato, tutti i dati delle applicazioni vengono archiviati nei database **reportserver** e **reportservertempdb** in esecuzione su un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71b0c-117">Because a report server is a stateless server, all application data is stored in the **reportserver** and **reportservertempdb** databases that run on a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance.</span></span> <span data-ttu-id="71b0c-118">È possibile eseguire il backup dei database **reportserver** e **reportservertempdb** usando uno dei metodi supportati per il backup dei database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71b0c-118">You can backup the **reportserver** and **reportservertempdb** databases using one of the supported methods for backing up [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="71b0c-119">Per i database del server di report, tenere presenti le seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="71b0c-119">Recommendations that are specific to the report server databases include the following:</span></span>  
  
-   <span data-ttu-id="71b0c-120">Per il backup del database **reportserver** , usare il modello di recupero con registrazione completa.</span><span class="sxs-lookup"><span data-stu-id="71b0c-120">Use the full recovery model to backup the **reportserver** database.</span></span>  
  
-   <span data-ttu-id="71b0c-121">Per il backup del database **reportservertempdb** , usare il modello di recupero con registrazione minima.</span><span class="sxs-lookup"><span data-stu-id="71b0c-121">Use the simple recovery model to backup the **reportservertempdb** database.</span></span>  
  
-   <span data-ttu-id="71b0c-122">Per ogni database, è possibile utilizzare diverse pianificazioni di backup.</span><span class="sxs-lookup"><span data-stu-id="71b0c-122">You can use different backup schedules for each database.</span></span> <span data-ttu-id="71b0c-123">È consigliabile eseguire il backup del database **reportservertempdb** solo per non doverlo ricreare nel caso in cui si verifichi un errore hardware.</span><span class="sxs-lookup"><span data-stu-id="71b0c-123">The only reason to backup the **reportservertempdb** is to avoid having to recreate it if there is a hardware failure.</span></span> <span data-ttu-id="71b0c-124">Nel caso di un errore hardware, non è necessario recuperare i dati di **reportservertempdb**, ma è necessaria la struttura della tabella.</span><span class="sxs-lookup"><span data-stu-id="71b0c-124">In the event of hardware failure, it is not necessary to recover the data in **reportservertempdb**, but you do need the table structure.</span></span> <span data-ttu-id="71b0c-125">Se il database **reportservertempdb**viene perso, l'unico modo per recuperarlo consiste nel ricreare il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="71b0c-125">If you lose **reportservertempdb**, the only way to get it back is to recreate the report server database.</span></span> <span data-ttu-id="71b0c-126">Se si ricrea il database **reportservertempdb**, è importante assegnare lo stesso nome del database del server di report principale.</span><span class="sxs-lookup"><span data-stu-id="71b0c-126">If you recreate the **reportservertempdb**, it is important that it have the same name as the primary report server database.</span></span>  
  
 <span data-ttu-id="71b0c-127">Per altre informazioni sul backup e il ripristino dei database relazionali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [Backup e ripristino di database SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span><span class="sxs-lookup"><span data-stu-id="71b0c-127">For more information about backup and recovery of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] relational databases, see [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="71b0c-128">Se il server di report [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] è in modalità SharePoint, è necessario occuparsi di altri database, tra cui i database di configurazione di SharePoint e il database di avvisi di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71b0c-128">If your [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] report server is in SharePoint mode, there are additional databases to be concerned with, including SharePoint configuration databases and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] alerting database.</span></span> <span data-ttu-id="71b0c-129">In modalità SharePoint vengono creati tre database per ciascuna applicazione di servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="71b0c-129">In SharePoint mode, three databases are created for each [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="71b0c-130">**reportserver**, **reportservertempdb**e **dataalerting** .</span><span class="sxs-lookup"><span data-stu-id="71b0c-130">The **reportserver**, **reportservertempdb**, and **dataalerting** databases.</span></span> <span data-ttu-id="71b0c-131">Per altre informazioni, vedere [Eseguire il backup e il ripristino di applicazioni di servizio SharePoint di Reporting Services](../backup-and-restore-reporting-services-sharepoint-service-applications.md)</span><span class="sxs-lookup"><span data-stu-id="71b0c-131">For more information see [Backup and Restore Reporting Services SharePoint Service Applications](../backup-and-restore-reporting-services-sharepoint-service-applications.md)</span></span>  
  
## <a name="backing-up-the-encryption-keys"></a><span data-ttu-id="71b0c-132">Backup delle chiavi di crittografia</span><span class="sxs-lookup"><span data-stu-id="71b0c-132">Backing Up the Encryption Keys</span></span>  
 <span data-ttu-id="71b0c-133">Quando si configura un'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per la prima volta, è consigliabile eseguire il backup delle chiavi di crittografia.</span><span class="sxs-lookup"><span data-stu-id="71b0c-133">You should backup the encryption keys when you configure a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation for the first time.</span></span> <span data-ttu-id="71b0c-134">È inoltre consigliabile eseguire il backup delle chiavi ogni volta che si modifica l'identità degli account di servizio o si rinomina il computer.</span><span class="sxs-lookup"><span data-stu-id="71b0c-134">You should also backup the keys any time you change the identity of the service accounts or rename the computer.</span></span> <span data-ttu-id="71b0c-135">Per altre informazioni, vedere [Eseguire il backup e il ripristino delle chiavi di crittografia di Reporting Services](ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="71b0c-135">For more information, see [Back Up and Restore Reporting Services Encryption Keys](ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span> <span data-ttu-id="71b0c-136">Per i server di report in modalità SharePoint, vedere la sezione "gestione chiavi" di [gestire un'applicazione di servizio sharepoint Reporting Services](../manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="71b0c-136">For SharePoint mode report servers, see the "Key Management" section of [Manage a Reporting Services SharePoint Service Application](../manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
## <a name="backing-up-the-configuration-files"></a><span data-ttu-id="71b0c-137">Backup dei file di configurazione</span><span class="sxs-lookup"><span data-stu-id="71b0c-137">Backing Up the Configuration Files</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="71b0c-138">usa i file di configurazione per archiviare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="71b0c-138">uses configuration files to store application settings.</span></span> <span data-ttu-id="71b0c-139">È consigliabile eseguire il backup dei file quando si configura il server per la prima volta e dopo avere distribuito eventuali estensioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="71b0c-139">You should backup the files when you first configure the server and after you deploy any custom extensions.</span></span> <span data-ttu-id="71b0c-140">I file di cui eseguire il backup includono:</span><span class="sxs-lookup"><span data-stu-id="71b0c-140">Files to back up include:</span></span>  
  
-   <span data-ttu-id="71b0c-141">RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="71b0c-141">Rsreportserver.config</span></span>  
  
-   <span data-ttu-id="71b0c-142">Rssvrpolicy.config</span><span class="sxs-lookup"><span data-stu-id="71b0c-142">Rssvrpolicy.config</span></span>  
  
-   <span data-ttu-id="71b0c-143">Rsmgrpolicy.config</span><span class="sxs-lookup"><span data-stu-id="71b0c-143">Rsmgrpolicy.config</span></span>  
  
-   <span data-ttu-id="71b0c-144">Reportingservicesservice.exe.config</span><span class="sxs-lookup"><span data-stu-id="71b0c-144">Reportingservicesservice.exe.config</span></span>  
  
-   <span data-ttu-id="71b0c-145">Web.config per entrambe le applicazioni [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] del server di report e Gestione report.</span><span class="sxs-lookup"><span data-stu-id="71b0c-145">Web.config for both the Report Server and Report Manager [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications</span></span>  
  
-   <span data-ttu-id="71b0c-146">Machine.config per [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71b0c-146">Machine.config for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]</span></span>  
  
## <a name="backing-up-data-files"></a><span data-ttu-id="71b0c-147">Backup dei file di dati</span><span class="sxs-lookup"><span data-stu-id="71b0c-147">Backing Up Data Files</span></span>  
 <span data-ttu-id="71b0c-148">Eseguire il backup dei file creati e gestiti in Progettazione report e in Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="71b0c-148">Backup the files that you create and maintain in Report Designer and Model Designer.</span></span> <span data-ttu-id="71b0c-149">Tra questi sono inclusi i file di definizione del report (con estensione rdl), i file modello di report (con estensione smdl), i file delle origini dei dati condivise (con estensione rds), i file di visualizzazione dei dati (con estensione dv), i file dell'origine dati (con estensione ds), i file di progetto del server di report (con estensione rptproj) e i file di soluzione di report (con estensione sln).</span><span class="sxs-lookup"><span data-stu-id="71b0c-149">These include report definition (.rdl) files, report model (.smdl) files, shared data source (.rds) files, data view (.dv) files, data source (.ds) files, report server project (.rptproj) files, and report solution (.sln) files.</span></span>  
  
 <span data-ttu-id="71b0c-150">Ricordarsi di eseguire il backup di eventuali file script, con estensione rss, creati per attività di amministrazione o di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="71b0c-150">Remember to backup any script files (.rss) that you created for administration or deployment tasks.</span></span>  
  
 <span data-ttu-id="71b0c-151">Verificare di avere una copia di backup per tutte le estensioni e gli assembly personalizzati utilizzati.</span><span class="sxs-lookup"><span data-stu-id="71b0c-151">Verify that you have a backup copy of any custom extensions and custom assemblies you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71b0c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71b0c-152">See Also</span></span>  
 <span data-ttu-id="71b0c-153">[Database del server di report &#40;modalità nativa SSRS&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="71b0c-153">[Report Server Database &#40;SSRS Native Mode&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="71b0c-154">[File di configurazione di Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="71b0c-154">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="71b0c-155">[Utilità rskeymgmt &#40;SSRS&#41;](../tools/rskeymgmt-utility-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="71b0c-155">[rskeymgmt Utility &#40;SSRS&#41;](../tools/rskeymgmt-utility-ssrs.md) </span></span>  
 <span data-ttu-id="71b0c-156">[Copiare database tramite backup e ripristino](../../relational-databases/databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="71b0c-156">[Copy Databases with Backup and Restore](../../relational-databases/databases/copy-databases-with-backup-and-restore.md) </span></span>  
 <span data-ttu-id="71b0c-157">[Amministrare un database del server di report &#40;modalità nativa SSRS&#41;](../report-server/administer-a-report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="71b0c-157">[Administer a Report Server Database &#40;SSRS Native Mode&#41;](../report-server/administer-a-report-server-database-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="71b0c-158">Configurare e gestire chiavi di crittografia &#40;Gestione configurazione SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="71b0c-158">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](ssrs-encryption-keys-manage-encryption-keys.md)  
  
  