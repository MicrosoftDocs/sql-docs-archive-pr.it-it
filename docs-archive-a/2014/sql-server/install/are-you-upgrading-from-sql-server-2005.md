---
title: Aggiornamento da SQL Server 2005 | Microsoft Docs
ms.custom: ''
ms.date: 12/15/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3d50a66a-1845-4116-8b3a-7b5a2eeb78e6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6d1e7ab42e2e4fc41694d34a335cea3045adcb3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628236"
---
# <a name="are-you-upgrading-from-sql-server-2005"></a><span data-ttu-id="52bb5-103">Aggiornamento da SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="52bb5-103">Are you upgrading from SQL Server 2005?</span></span>
  <span data-ttu-id="52bb5-104">La fine del supporto esteso per SQL Server 2005 è uno dei motivi per cui si consiglia di aggiornare subito il sistema a una nuova versione di SQL Server e al database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="52bb5-104">The end of extended support for SQL Server 2005 is one reason to upgrade now to a newer version of SQL Server and to Azure SQL Database.</span></span> <span data-ttu-id="52bb5-105">L'aggiornamento consente di garantire sicurezza e conformità, di raggiungere eccellenti livelli di prestazioni e di ottimizzare l'infrastruttura della piattaforma di dati.</span><span class="sxs-lookup"><span data-stu-id="52bb5-105">Upgrading enables you to maintain security and compliance, achieve breakthrough performance, and optimize your data platform infrastructure.</span></span>  
  
 <span data-ttu-id="52bb5-106">Per altre informazioni, indicazioni e strumenti per pianificare e automatizzare l'aggiornamento o la migrazione, vedere [SQL Server 2005 end of support](https://www.microsoft.com/sql-server/sql-server-2005)(Fine del supporto per SQL Server 2005).</span><span class="sxs-lookup"><span data-stu-id="52bb5-106">For more info, guidance, and tools to plan and automate your upgrade or migration, see [SQL Server 2005 end of support](https://www.microsoft.com/sql-server/sql-server-2005).</span></span>  
  
## <a name="why-upgrade"></a><span data-ttu-id="52bb5-107">Ragioni dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="52bb5-107">Why upgrade?</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52bb5-108">Il supporto esteso per SQL Server 2005 termina il 12 aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="52bb5-108">Extended support for SQL Server 2005 ends on April 12, 2016.</span></span> <span data-ttu-id="52bb5-109">Se si continua a usare SQL Server 2005 dopo il 12 aprile 2016, non si riceveranno più aggiornamenti della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="52bb5-109">If you're still running SQL Server 2005 after April 12, 2016, you'll no longer receive security updates.</span></span>  
  
 <span data-ttu-id="52bb5-110">Per ottenere il foglio dati in formato PDF sull'aggiornamento da SQL Server 2005, [fare clic qui](https://info.microsoft.com/rs/157-GQE-382/images/EN-CNTNT-Infographic-UpgradeSQL2005Datasheet.pdf) (non sull'immagine di anteprima riportata di seguito).</span><span class="sxs-lookup"><span data-stu-id="52bb5-110">To get the data sheet in PDF format about upgrading from SQL Server 2005, [click here](https://info.microsoft.com/rs/157-GQE-382/images/EN-CNTNT-Infographic-UpgradeSQL2005Datasheet.pdf) (not on the thumbnail image below).</span></span>  
  
 <span data-ttu-id="52bb5-111">![Foglio dati sull'aggiornamento da SQL Server 2005](../../../2014/sql-server/install/media/sqlserver2005eos.png "Foglio dati sull'aggiornamento da SQL Server 2005")</span><span class="sxs-lookup"><span data-stu-id="52bb5-111">![Data sheet about upgrading from SQL Server 2005](../../../2014/sql-server/install/media/sqlserver2005eos.png "Data sheet about upgrading from SQL Server 2005")</span></span>  
  
## <a name="choose-your-upgrade-option"></a><span data-ttu-id="52bb5-112">Opzioni di aggiornamento disponibili</span><span class="sxs-lookup"><span data-stu-id="52bb5-112">Choose your upgrade option</span></span>  
 <span data-ttu-id="52bb5-113">Se si stanno aggiornando database relazionali da SQL Server 2005, di seguito sono riportate le opzioni per l'archiviazione relazionale nella piattaforma Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52bb5-113">If you're upgrading relational databases from SQL Server 2005, here are your options for relational storage on the Microsoft platform.</span></span>  
  
 <span data-ttu-id="52bb5-114">Per un'analisi più completa di queste opzioni, [fare clic qui](https://sql05upgrade.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-114">To see a more comprehensive analysis of these options, [click here](https://sql05upgrade.azurewebsites.net/).</span></span>  
  
|<span data-ttu-id="52bb5-115">Opzione di archiviazione relazionale</span><span class="sxs-lookup"><span data-stu-id="52bb5-115">Relational storage option</span></span>|<span data-ttu-id="52bb5-116">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="52bb5-116">Benefits</span></span>|<span data-ttu-id="52bb5-117">Altri fattori da considerare</span><span class="sxs-lookup"><span data-stu-id="52bb5-117">Other factors to consider</span></span>|  
|-------------------------------|--------------|-------------------------------|  
|<span data-ttu-id="52bb5-118">**SQL Server locale**</span><span class="sxs-lookup"><span data-stu-id="52bb5-118">**SQL Server on premises**</span></span><br /><br /> <span data-ttu-id="52bb5-119">Prendere in considerazione questa opzione per le applicazioni di database di qualsiasi tipo, dai sistemi transazionali ai data warehouse.</span><span class="sxs-lookup"><span data-stu-id="52bb5-119">Consider this option for database applications of any kind, from transactional systems to data warehouses.</span></span><br /><br /> <span data-ttu-id="52bb5-120">Per ulteriori informazioni, vedere [SQL Server 2014](https://www.microsoft.com/EN-US/server-cloud/products/sql-server/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-120">For more info, see [SQL Server 2014](https://www.microsoft.com/EN-US/server-cloud/products/sql-server/).</span></span>|<span data-ttu-id="52bb5-121">Si ha un maggiore controllo sulle funzionalità e la scalabilità perché vengono gestiti sia l'hardware che il software.</span><span class="sxs-lookup"><span data-stu-id="52bb5-121">You have the most control over features and scalability because you manage both hardware and software.</span></span><br /><br /> <span data-ttu-id="52bb5-122">Se si sta eseguendo l'aggiornamento da SQL Server 2005, questo è l'ambiente più simile.</span><span class="sxs-lookup"><span data-stu-id="52bb5-122">If you're upgrading from SQL Server 2005, this is the most similar environment.</span></span>|<span data-ttu-id="52bb5-123">L'investimento iniziale è elevato ed è necessaria una gestione continua perché è necessario acquistare, mantenere e gestire il proprio hardware e software.</span><span class="sxs-lookup"><span data-stu-id="52bb5-123">You have to make the biggest up-front investment and provide the most ongoing management, because you have to buy, maintain, and manage your own hardware and software.</span></span>|  
|<span data-ttu-id="52bb5-124">**SQL Server ospitato in macchine virtuali di Azure**</span><span class="sxs-lookup"><span data-stu-id="52bb5-124">**SQL Server hosted on Azure virtual machines**</span></span><br /><br /> <span data-ttu-id="52bb5-125">Prendere in considerazione questa opzione se si hanno le esigenze seguenti.</span><span class="sxs-lookup"><span data-stu-id="52bb5-125">Consider this option if you want the following things.</span></span><br /><span data-ttu-id="52bb5-126">-Vantaggi della migrazione a un ambiente ospitato.</span><span class="sxs-lookup"><span data-stu-id="52bb5-126">-Benefits of migrating to a hosted environment.</span></span><br /><span data-ttu-id="52bb5-127">-Controllo sull'ambiente operativo.</span><span class="sxs-lookup"><span data-stu-id="52bb5-127">-Control over the operating environment.</span></span><br /><span data-ttu-id="52bb5-128">-Set di funzionalità familiare di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52bb5-128">-Familiar feature set of SQL Server.</span></span><br /><br /> <span data-ttu-id="52bb5-129">Per altre informazioni, vedere [SQL Server in Panoramica di macchine virtuali di Azure](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-infrastructure-services/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-129">For more info, see [SQL Server on Azure Virtual Machines overview](https://azure.microsoft.com/documentation/articles/virtual-machines-sql-server-infrastructure-services/).</span></span><br /><br /> <span data-ttu-id="52bb5-130">Per informazioni sulla migrazione, vedere [Eseguire la migrazione di un database di SQL Server a SQL Server in una macchina virtuale di Azure](https://azure.microsoft.com/documentation/articles/virtual-machines-migrate-onpremises-database/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-130">For info about migrating, see [Migrate a database to SQL Server on an Azure VM](https://azure.microsoft.com/documentation/articles/virtual-machines-migrate-onpremises-database/).</span></span>|<span data-ttu-id="52bb5-131">È possibile eseguire rapidamente la distribuzione da una libreria di immagini della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="52bb5-131">You can deploy quickly from a library of virtual machine images.</span></span><br /><br /> <span data-ttu-id="52bb5-132">Viene fornito il set di funzionalità completo di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52bb5-132">You get the full SQL Server feature set.</span></span><br /><br /> <span data-ttu-id="52bb5-133">Si risparmiano i costi per l'hardware e il software del server.</span><span class="sxs-lookup"><span data-stu-id="52bb5-133">You save the cost of hardware and of server software.</span></span> <span data-ttu-id="52bb5-134">Si paga per ora in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="52bb5-134">You pay only for hourly usage.</span></span>|<span data-ttu-id="52bb5-135">È necessario configurare e gestire sia SQL Server che il software del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="52bb5-135">You have to configure and manage both the SQL Server and the operating system software.</span></span>|  
|<span data-ttu-id="52bb5-136">**Servizio di database ospitato nel database SQL di Azure**</span><span class="sxs-lookup"><span data-stu-id="52bb5-136">**Azure SQL Database hosted database service**</span></span><br /><br /> <span data-ttu-id="52bb5-137">Prendere in considerazione questa opzione se si preferisce una soluzione a basso costo che necessita di poca manutenzione.</span><span class="sxs-lookup"><span data-stu-id="52bb5-137">Consider this option if you want a lower-cost solution with less maintenance.</span></span><br /><br /> <span data-ttu-id="52bb5-138">Questa opzione è particolarmente adatta per le app che non richiedono una capacità costante o che devono fornire un accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="52bb5-138">This option is particularly well suited for apps that don't require the same capacity at all times, or that have to provide external access.</span></span><br /><br /> <span data-ttu-id="52bb5-139">Per altre informazioni, vedere [database SQL](https://azure.microsoft.com/services/sql-database/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-139">For more info, see [SQL Database](https://azure.microsoft.com/services/sql-database/).</span></span><br /><br /> <span data-ttu-id="52bb5-140">Per informazioni sulla migrazione, vedere [migrazione di un database di SQL Server al database SQL di Azure](https://azure.microsoft.com/documentation/articles/sql-database-cloud-migrate/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-140">For info about migrating, see [Migrating a SQL Server database to Azure SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-cloud-migrate/).</span></span>|<span data-ttu-id="52bb5-141">La distribuzione è rapida e la scalabilità verticale semplice.</span><span class="sxs-lookup"><span data-stu-id="52bb5-141">You can deploy quickly and scale up easily.</span></span><br /><br /> <span data-ttu-id="52bb5-142">Si paga per ora in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="52bb5-142">You pay only for hourly usage.</span></span><br /><br /> <span data-ttu-id="52bb5-143">Il costo del servizio include anche la disponibilità elevata e i backup automatici, oltre all'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="52bb5-143">The cost of the service includes not only storage, but high availability and automated backups.</span></span>|<span data-ttu-id="52bb5-144">Il database SQL di Azure non offre alcune delle funzionalità di SQL Server non applicabili a un ambiente cloud ospitato.</span><span class="sxs-lookup"><span data-stu-id="52bb5-144">Azure SQL Database lacks some SQL Server features that are not applicable in a hosted cloud environment.</span></span> <span data-ttu-id="52bb5-145">Per altre informazioni, vedere [Differenze di Transact-SQL del database SQL di Azure](https://azure.microsoft.com/documentation/articles/sql-database-transact-sql-information/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-145">For more info, see [Azure SQL Database Transact-SQL information](https://azure.microsoft.com/documentation/articles/sql-database-transact-sql-information/).</span></span><br /><br /> <span data-ttu-id="52bb5-146">Anche le dimensioni massime del database SQL di Azure sono di 500 GB, invece dei 524 PB di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52bb5-146">Azure SQL Database also has a maximum database size of 500 GB, compared to 524 PB for SQL Server.</span></span>|  
  
 <span data-ttu-id="52bb5-147">Per alcuni dati e applicazioni si può valutare anche una soluzione non relazionale o NoSQL.</span><span class="sxs-lookup"><span data-stu-id="52bb5-147">You may also want to consider a non-relational or NoSQL solution for certain data and applications.</span></span>  
  
|<span data-ttu-id="52bb5-148">Soluzione non relazionale</span><span class="sxs-lookup"><span data-stu-id="52bb5-148">Non-relational solution</span></span>|<span data-ttu-id="52bb5-149">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="52bb5-149">Benefits</span></span>|  
|------------------------------|--------------|  
|<span data-ttu-id="52bb5-150">**Azure DocumentDB**</span><span class="sxs-lookup"><span data-stu-id="52bb5-150">**Azure DocumentDB**</span></span><br /><br /> <span data-ttu-id="52bb5-151">Prendere in considerazione questa opzione per applicazioni moderne, scalabili, mobili e Web che usano i dati JSON e richiedono una combinazione affidabile di funzionalità di query e di elaborazione dei dati transazionali.</span><span class="sxs-lookup"><span data-stu-id="52bb5-151">Consider this option for modern, scalable, mobile and web applications that use JSON data and require a combination of robust querying and transactional data processing.</span></span><br /><br /> <span data-ttu-id="52bb5-152">Per altre informazioni, vedere [DocumentDB](https://azure.microsoft.com/services/documentdb/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-152">For more info, see [DocumentDB](https://azure.microsoft.com/services/documentdb/).</span></span>|<span data-ttu-id="52bb5-153">I documenti vengono indicizzati ed è possibile eseguire query usando la sintassi SQL con cui si ha già familiarità.</span><span class="sxs-lookup"><span data-stu-id="52bb5-153">Your documents are indexed and you can use familiar SQL syntax to query them.</span></span><br /><br /> <span data-ttu-id="52bb5-154">Il database è senza schema.</span><span class="sxs-lookup"><span data-stu-id="52bb5-154">The database is schema-free.</span></span><br /><br /> <span data-ttu-id="52bb5-155">È possibile aggiungere proprietà ai documenti senza dover ricompilare gli indici.</span><span class="sxs-lookup"><span data-stu-id="52bb5-155">You can add properties to documents without having to rebuild indexes.</span></span><br /><br /> <span data-ttu-id="52bb5-156">Il supporto per JSON e JavaScript viene fornito direttamente all'interno del motore di database.</span><span class="sxs-lookup"><span data-stu-id="52bb5-156">You get JSON and JavaScript support right inside the database engine.</span></span><br /><br /> <span data-ttu-id="52bb5-157">Il supporto nativo viene fornito per i dati geospaziali e l'integrazione con altri servizi di Azure, inclusi Ricerca di Azure, HDInsight e Data Factory.</span><span class="sxs-lookup"><span data-stu-id="52bb5-157">You get native support for geospatial data and integration with other Azure Services including Azure Search, HDInsight, and Data Factory.</span></span><br /><br /> <span data-ttu-id="52bb5-158">Si ottiene un'archiviazione a bassa latenza e ad alte prestazioni con livelli di velocità effettiva riservati.</span><span class="sxs-lookup"><span data-stu-id="52bb5-158">You get low latency, high performance storage with reserved throughput levels.</span></span>|  
|<span data-ttu-id="52bb5-159">**Archiviazione tabelle di Azure**</span><span class="sxs-lookup"><span data-stu-id="52bb5-159">**Azure table storage**</span></span><br /><br /> <span data-ttu-id="52bb5-160">Prendere in considerazione questa opzione per archiviare petabyte di dati semistrutturati in una soluzione conveniente.</span><span class="sxs-lookup"><span data-stu-id="52bb5-160">Consider this option to store petabytes of semi-structured data in a cost-effective solution.</span></span><br /><br /> <span data-ttu-id="52bb5-161">Per altre informazioni, vedere [Archivio tabelle](https://azure.microsoft.com/services/storage/tables/).</span><span class="sxs-lookup"><span data-stu-id="52bb5-161">For more info, see [Table Storage](https://azure.microsoft.com/services/storage/tables/).</span></span>|<span data-ttu-id="52bb5-162">È possibile sviluppare le app e lo schema della tabella senza disconnettere i dati.</span><span class="sxs-lookup"><span data-stu-id="52bb5-162">You can evolve your apps and your table schema without taking the data offline.</span></span><br /><br /> <span data-ttu-id="52bb5-163">È possibile usare la scalabilità verticale senza partizionamento orizzontale del set di dati.</span><span class="sxs-lookup"><span data-stu-id="52bb5-163">You can scale up without sharding your dataset.</span></span><br /><br /> <span data-ttu-id="52bb5-164">Si ottiene un'archiviazione con ridondanza geografica che replica i dati in più regioni.</span><span class="sxs-lookup"><span data-stu-id="52bb5-164">You get geo-redundant storage that replicates data across multiple regions.</span></span>|  
  
 <span data-ttu-id="52bb5-165">Per scaricare il report sulla migrazione da SQL Server 2005 di Directions on Microsoft, contenente altre informazioni sulle opzioni di aggiornamento, [fare clic qui](https://info.microsoft.com/CO-SQL-CNTNT-FY16-09Sep-14-ModernizationDirOnMFST-Register.html) (non sull'immagine di anteprima riportata di seguito).</span><span class="sxs-lookup"><span data-stu-id="52bb5-165">To download the report "Migrating from SQL Server 2005" by Directions on Microsoft, which contains more details about the upgrade options, [click here](https://info.microsoft.com/CO-SQL-CNTNT-FY16-09Sep-14-ModernizationDirOnMFST-Register.html) (not on the thumbnail image below).</span></span>  
  
 <span data-ttu-id="52bb5-166">![Report sulla migrazione da SQL Server 2005](../../../2014/sql-server/install/media/sqlserver2005migratingdoc.png "Report sulla migrazione da SQL Server 2005")</span><span class="sxs-lookup"><span data-stu-id="52bb5-166">![Report about migrating from SQL Server 2005](../../../2014/sql-server/install/media/sqlserver2005migratingdoc.png "Report about migrating from SQL Server 2005")</span></span>  
  
## <a name="plan-your-upgrade"></a><span data-ttu-id="52bb5-167">Pianificare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="52bb5-167">Plan your upgrade</span></span>  
  
-   <span data-ttu-id="52bb5-168">Per informazioni su come pianificare l'aggiornamento, vedere la serie seguente di post di blog del team di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="52bb5-168">Read about how to plan your upgrade in the following series of blog posts from the SQL Server team.</span></span>  
  
    -   [<span data-ttu-id="52bb5-169">Pianificazione di un aggiornamento efficiente da SQL Server 2005: Passaggio 1 di 3</span><span class="sxs-lookup"><span data-stu-id="52bb5-169">Planning an efficient upgrade from SQL Server 2005: Step 1 of 3</span></span>](https://cloudblogs.microsoft.com/sqlserver/2015/12/10/planning-an-efficient-upgrade-from-sql-server-2005-step-1-of-3/)  
  
    -   [<span data-ttu-id="52bb5-170">Pianificazione di un aggiornamento efficiente da SQL Server 2005: Passaggio 2 di 3</span><span class="sxs-lookup"><span data-stu-id="52bb5-170">Planning an efficient upgrade from SQL Server 2005: Step 2 of 3</span></span>](https://cloudblogs.microsoft.com/sqlserver/2015/12/15/planning-an-efficient-upgrade-from-sql-server-2005-step-2-of-3/)  
  
    -   [<span data-ttu-id="52bb5-171">Pianificazione di un aggiornamento efficiente da SQL Server 2005: Passaggio 3 di 3</span><span class="sxs-lookup"><span data-stu-id="52bb5-171">Planning an efficient upgrade from SQL Server 2005: Step 3 of 3</span></span>](https://cloudblogs.microsoft.com/sqlserver/2015/12/17/planning-an-efficient-upgrade-from-sql-server-2005-step-3-of-3/)  
  
-   <span data-ttu-id="52bb5-172">Esaminare i requisiti e le considerazioni in [pianificazione di un'installazione di SQL Server](../../../2014/sql-server/install/planning-a-sql-server-installation.md), inclusi i [requisiti hardware e software per l'installazione di SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="52bb5-172">Review the requirements and considerations under [Planning a SQL Server Installation](../../../2014/sql-server/install/planning-a-sql-server-installation.md), including the [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
-   <span data-ttu-id="52bb5-173">Vedere come eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="52bb5-173">Read about how to upgrade.</span></span>  
  
    -   <span data-ttu-id="52bb5-174">Esaminare i metodi di aggiornamento disponibili e ottenere informazioni sulla pianificazione e sull'esecuzione dei test nell'argomento [Aggiornare il motore di database](../../database-engine/install-windows/upgrade-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="52bb5-174">Review the available upgrade methods and learn how to plan and test in the topic [Upgrade Database Engine](../../database-engine/install-windows/upgrade-database-engine.md).</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="52bb5-175">Non è possibile eseguire l'aggiornamento di un server SQL Server 2005 a un server SQL Server 2014 sul posto.</span><span class="sxs-lookup"><span data-stu-id="52bb5-175">You can't upgrade a SQL Server 2005 server to a SQL Server 2014 server in place.</span></span> <span data-ttu-id="52bb5-176">È necessario installare SQL Server 2014, quindi eseguire la migrazione dei database SQL Server 2005 alla nuova installazione.</span><span class="sxs-lookup"><span data-stu-id="52bb5-176">You have to install SQL Server 2014, then migrate your SQL Server 2005 databases to the new installation.</span></span>  
  
    -   <span data-ttu-id="52bb5-177">Per ottenere una guida tecnica all'aggiornamento più dettagliata in formato PDF, [fare clic qui](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="52bb5-177">To get the more detailed "Technical Upgrade Guide"  in PDF format, [click here](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf).</span></span>  
  
-   <span data-ttu-id="52bb5-178">Per altre informazioni, indicazioni e strumenti per pianificare e automatizzare l'aggiornamento o la migrazione, vedere [SQL Server 2005 end of support](https://www.microsoft.com/sql-server/sql-server-2005)(Fine del supporto per SQL Server 2005).</span><span class="sxs-lookup"><span data-stu-id="52bb5-178">For more info, guidance, and tools to plan and automate your upgrade or migration, see [SQL Server 2005 end of support](https://www.microsoft.com/sql-server/sql-server-2005).</span></span>  
  
## <a name="get-sql-server-2014"></a><span data-ttu-id="52bb5-179">Ottenere SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="52bb5-179">Get SQL Server 2014</span></span>  
 <span data-ttu-id="52bb5-180">Per scaricare una copia di valutazione di SQL Server 2014, [fare clic qui](https://www.microsoft.com/evalcenter/evaluate-sql-server-2014).</span><span class="sxs-lookup"><span data-stu-id="52bb5-180">To download an evaluation copy of SQL Server 2014, [click here](https://www.microsoft.com/evalcenter/evaluate-sql-server-2014).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bb5-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52bb5-181">See Also</span></span>  
 <span data-ttu-id="52bb5-182">[SQL Server 2014](https://docs.microsoft.com/sql/getting-started/getting-started-sql-server-2014) </span><span class="sxs-lookup"><span data-stu-id="52bb5-182">[SQL Server 2014](https://docs.microsoft.com/sql/getting-started/getting-started-sql-server-2014) </span></span>  
 <span data-ttu-id="52bb5-183">[Fine del supporto SQL Server 2005](https://www.microsoft.com/sql-server/sql-server-2005) </span><span class="sxs-lookup"><span data-stu-id="52bb5-183">[SQL Server 2005 end of support](https://www.microsoft.com/sql-server/sql-server-2005) </span></span>  
 [<span data-ttu-id="52bb5-184">Aggiornare da SQL Server 2005 a SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="52bb5-184">Upgrade from SQL Server 2005 to SQL Server 2016</span></span>](https://msdn.microsoft.com/library/mt168847.aspx)  
  
  