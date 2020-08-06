---
title: Creare il catalogo SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6ed56d36-18d9-40c2-b51f-f2a4c71d1e73
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2572cc131f34a21171054a159e3b7968c453a780
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625489"
---
# <a name="create-the-ssis-catalog"></a><span data-ttu-id="69545-102">Creare il catalogo SSIS</span><span class="sxs-lookup"><span data-stu-id="69545-102">Create the SSIS Catalog</span></span>
  <span data-ttu-id="69545-103">Dopo avere progettato e testato i pacchetti in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], è possibile distribuire i progetti che contengono i pacchetti in un server di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69545-103">After you design and test packages in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], you can deploy the projects that contain the packages to an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="69545-104">Prima di poter distribuire i progetti nel server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], in quest'ultimo deve essere incluso il catalogo `SSISDB`.</span><span class="sxs-lookup"><span data-stu-id="69545-104">Before you can deploy the projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the server must contain the `SSISDB` catalog.</span></span> <span data-ttu-id="69545-105">Tramite il programma di installazione per [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] non viene creato automaticamente il catalogo. Sarà necessario crearlo manualmente usando le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="69545-105">The installation program for [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] does not automatically create the catalog; you need to manually create the catalog by using the following instructions.</span></span>  
  
 <span data-ttu-id="69545-106">Il catalogo SSISDB può essere creato in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69545-106">You can create the SSISDB catalog in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="69545-107">Il catalogo può essere creato anche a livello di programmazione utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69545-107">You also create the catalog programmatically by using Windows PowerShell.</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-in-sql-server-management-studio"></a><span data-ttu-id="69545-108">Per creare il catalogo SSISDB in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69545-108">To create the SSISDB catalog in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="69545-109">Aprire [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69545-109">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="69545-110">Connettersi al motore di database di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69545-110">Connect to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Database Engine.</span></span>  
  
3.  <span data-ttu-id="69545-111">In Esplora oggetti espandere il nodo del server, fare clic con il pulsante destro del mouse sul nodo **Cataloghi di Integration Services** e quindi fare clic su **Creazione catalogo**.</span><span class="sxs-lookup"><span data-stu-id="69545-111">In Object Explorer, expand the server node, right-click the **Integration Services Catalogs** node, and then click **Create Catalog**.</span></span>  
  
4.  <span data-ttu-id="69545-112">Fare clic su **Abilitazione integrazione con CLR**.</span><span class="sxs-lookup"><span data-stu-id="69545-112">Click **Enable CLR Integration**.</span></span>  
  
     <span data-ttu-id="69545-113">Nel catalogo vengono utilizzate stored procedure CLR.</span><span class="sxs-lookup"><span data-stu-id="69545-113">The catalog uses CLR stored procedures.</span></span>  
  
5.  <span data-ttu-id="69545-114">Fare clic su **Abilita l'esecuzione automatica della stored procedure di Integration Services all'avvio di SQL Server** per abilitare l'esecuzione della stored procedure [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) a ogni riavvio dell’istanza del server [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69545-114">Click **Enable automatic execution of Integration Services stored procedure at SQL Server startup** to enable the [catalog.startup](/sql/integration-services/system-stored-procedures/catalog-startup) stored procedure to run each time the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance is restarted.</span></span>  
  
     <span data-ttu-id="69545-115">La stored procedure esegue la manutenzione dello stato delle operazioni per il catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="69545-115">The stored procedure performs maintenance of the state of operations for the SSISDB catalog.</span></span> <span data-ttu-id="69545-116">Corregge lo stato di eventuali pacchetti in esecuzione in caso di arresto dell'istanza del server [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="69545-116">It fixes the status of any packages there were running if and when the [!INCLUDE[ssIS](../includes/ssis-md.md)] server instance goes down.</span></span>  
  
6.  <span data-ttu-id="69545-117">Immettere una password quindi fare clic su **Ok**.</span><span class="sxs-lookup"><span data-stu-id="69545-117">Enter a password, and then click **Ok**.</span></span>  
  
     <span data-ttu-id="69545-118">La password consente di proteggere la chiave del database master utilizzata per crittografare i dati del catalogo.</span><span class="sxs-lookup"><span data-stu-id="69545-118">The password protects the database master key that is used for encrypting the catalog data.</span></span> <span data-ttu-id="69545-119">Salvare la password in un percorso sicuro.</span><span class="sxs-lookup"><span data-stu-id="69545-119">Save the password in a secure location.</span></span> <span data-ttu-id="69545-120">È consigliabile eseguire inoltre il backup della chiave master del database.</span><span class="sxs-lookup"><span data-stu-id="69545-120">It is recommended that you also back up the database master key.</span></span> <span data-ttu-id="69545-121">Per altre informazioni, vedere [Backup della chiave master di un database](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="69545-121">For more information, see [Back Up a Database Master Key](../relational-databases/security/encryption/back-up-a-database-master-key.md).</span></span>  
  
### <a name="to-create-the-ssisdb-catalog-programmatically"></a><span data-ttu-id="69545-122">Per creare il catalogo SSISDB a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="69545-122">To create the SSISDB catalog programmatically</span></span>  
  
1.  <span data-ttu-id="69545-123">Eseguire lo script di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="69545-123">Execute the following PowerShell script:</span></span>  
  
    ```powershell
    # Load the IntegrationServices Assembly  
    [Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.Management.IntegrationServices")  
  
    # Store the IntegrationServices Assembly namespace to avoid typing it every time  
    $ISNamespace = "Microsoft.SqlServer.Management.IntegrationServices"  
  
    Write-Host "Connecting to server ..."  
  
    # Create a connection to the server  
    $sqlConnectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=SSPI;"  
    $sqlConnection = New-Object System.Data.SqlClient.SqlConnection $sqlConnectionString  
  
    # Create the Integration Services object  
    $integrationServices = New-Object $ISNamespace".IntegrationServices" $sqlConnection  
  
    # Provision a new SSIS Catalog  
    $catalog = New-Object $ISNamespace".Catalog" ($integrationServices, "SSISDB", "P@assword1")  
    $catalog.Create()
    ```  
  
     <span data-ttu-id="69545-124">Per altri esempi di come usare Windows PowerShell e lo spazio dei nomi <xref:Microsoft.SqlServer.Management.IntegrationServices>, vedere l'intervento sul blog relativo a [SSIS e PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539) nel sito blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="69545-124">For more examples of how to use Windows PowerShell and the <xref:Microsoft.SqlServer.Management.IntegrationServices> namespace, see the blog entry, [SSIS and PowerShell in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=242539), on blogs.msdn.com.</span></span> <span data-ttu-id="69545-125">Per una panoramica dello spazio dei nomi e degli esempi di codice, vedere l'intervento sul blog relativo a [uno sguardo rapido del modello a oggetti gestito del catalogo SSIS](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892)sul sito blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="69545-125">For an overview of the namespace and code examples, see the blog entry, [A Glimpse of the SSIS Catalog Managed Object Model](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69545-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69545-126">See Also</span></span>  
 <span data-ttu-id="69545-127">[Catalogo SSIS](catalog/ssis-catalog.md) </span><span class="sxs-lookup"><span data-stu-id="69545-127">[SSIS Catalog](catalog/ssis-catalog.md) </span></span>  
 [<span data-ttu-id="69545-128">Backup, ripristino e spostamento del catalogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="69545-128">Backup, Restore, and Move the SSIS Catalog</span></span>](../../2014/integration-services/backup-restore-and-move-the-ssis-catalog.md)  
