---
title: Configurare una distribuzione con scalabilità orizzontale di un server di report in modalità nativa (SSRS Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], deployments
- deploying [Reporting Services], scale-out deployment model
- scale-out deployments [Reporting Services]
ms.assetid: b30d0308-4d9b-4f85-9f83-dece4dcb2775
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6855769d36632ce60b7cf299291d58d5f136d120
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635959"
---
# <a name="configure-a-native-mode-report-server-scale-out-deployment-ssrs-configuration-manager"></a><span data-ttu-id="d0164-102">Configurare una distribuzione con scalabilità orizzontale di un server di report in modalità nativa (Gestione configurazione SSRS)</span><span class="sxs-lookup"><span data-stu-id="d0164-102">Configure a Native Mode Report Server Scale-Out Deployment (SSRS Configuration Manager)</span></span>

  <span data-ttu-id="d0164-103">Reporting Services in modalità nativa supporta un modello di distribuzione con scalabilità orizzontale che consente di eseguire più istanze del server di report che condividono un singolo database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-103">Reporting Services native mode supports a scale-out deployment model that allows you to run multiple report server instances that share a single report server database.</span></span> <span data-ttu-id="d0164-104">Le distribuzioni con scalabilità orizzontale vengono utilizzate per aumentare la scalabilità di server di report in modo che siano in grado di gestire più utenti simultanei e carichi di esecuzione di report maggiori.</span><span class="sxs-lookup"><span data-stu-id="d0164-104">Scale-out deployments are used to increase scalability of report servers to handle more concurrent users and larger report execution loads.</span></span> <span data-ttu-id="d0164-105">Distribuzioni di questo tipo possono essere utilizzate inoltre per dedicare server specifici all'elaborazione di report interattivi o pianificati</span><span class="sxs-lookup"><span data-stu-id="d0164-105">It can also be used to dedicate specific servers to process interactive or scheduled reports</span></span>

 <span data-ttu-id="d0164-106">I server di report in modalità SharePoint utilizzano l'infrastruttura di prodotti SharePoint per la scalabilità orizzontale. La scalabilità orizzontale della modalità SharePoint viene eseguita aggiungendo più server di report in modalità SharePoint alla farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d0164-106">SharePoint mode report servers utilize the SharePoint products infrastructure for scale-out. SharePoint mode scale-out is performed by adding more SharePoint mode report servers to the SharePoint farm.</span></span> <span data-ttu-id="d0164-107">Per informazioni sulla scalabilità orizzontale in modalità SharePoint, vedere [Aggiungere un ulteriore server di report a una farm &#40;con scalabilità orizzontale SSRS&#41;](../../reporting-services/install-windows/add-an-additional-report-server-to-a-farm-ssrs-scale-out.md).</span><span class="sxs-lookup"><span data-stu-id="d0164-107">For information on scale-out in SharePoint mode, see [Add an Additional Report Server to a Farm &#40;SSRS Scale-out&#41;](../../reporting-services/install-windows/add-an-additional-report-server-to-a-farm-ssrs-scale-out.md).</span></span>

 <span data-ttu-id="d0164-108">**Le distribuzioni con scalabilità orizzontale sono costitute dagli elementi seguenti:**</span><span class="sxs-lookup"><span data-stu-id="d0164-108">**Scale-out deployments consist of:**</span></span>

-   <span data-ttu-id="d0164-109">Due o più istanze del server di report che condividono un unico database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-109">Two or more report server instances sharing a single report server database.</span></span>

-   <span data-ttu-id="d0164-110">Facoltativamente, un cluster con bilanciamento del carico di rete per distribuire il carico utente interattivo tra le istanze del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-110">Optionally, a network load-balanced (NLB) cluster to spread interactive user load across the report server instances.</span></span>

 <span data-ttu-id="d0164-111">Quando si distribuisce Reporting Services in un cluster con bilanciamento del carico di rete, è necessario verificare che il nome del server virtuale di bilanciamento del carico venga utilizzato nella configurazione dell'URL del server di report e che i server siano configurati per condividere lo stesso stato di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0164-111">When deploying Reporting Services on an NLB cluster, you need to ensure the NLB virtual server name is used in the configuration of report server URLs and that servers are configured to share the same view state.</span></span>

 <span data-ttu-id="d0164-112">Sebbene Reporting Services non partecipi ai cluster di Microsoft Cluster Services,</span><span class="sxs-lookup"><span data-stu-id="d0164-112">Reporting Services does not participate in Microsoft Cluster Services clusters.</span></span> <span data-ttu-id="d0164-113">è tuttavia possibile creare il database del server di report in un'istanza del Motore di database che appartiene a un cluster di failover.</span><span class="sxs-lookup"><span data-stu-id="d0164-113">However, you can create the report server database on a Database Engine instance that is part of a failover cluster.</span></span>

 <span data-ttu-id="d0164-114">**Per pianificare, installare e configurare una distribuzione con scalabilità orizzontale, effettuare le operazioni seguenti:**</span><span class="sxs-lookup"><span data-stu-id="d0164-114">**To plan, install, and configure a scale-out deployment, follow these steps:**</span></span>

-   <span data-ttu-id="d0164-115">Per istruzioni su come installare le istanze del server di report, vedere [installare SQL Server 2014 dall'installazione guidata &#40;&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) di installazione nella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] documentazione online.</span><span class="sxs-lookup"><span data-stu-id="d0164-115">Review [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for instructions on how to install report server instances.</span></span>

-   <span data-ttu-id="d0164-116">Se si intende ospitare la distribuzione con scalabilità orizzontale in un cluster con bilanciamento del carico di rete, è necessario configurare tale cluster prima di configurare la distribuzione con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d0164-116">If you are planning to host the scale-out deployment on a network load balanced (NLB) cluster, you should configure the NLB cluster before you configure the scale-out deployment.</span></span> <span data-ttu-id="d0164-117">Per altre informazioni, vedere [Configurare un server di report in un cluster per il bilanciamento del carico di rete](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).</span><span class="sxs-lookup"><span data-stu-id="d0164-117">For more information, see [Configure a Report Server on a Network Load Balancing Cluster](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).</span></span>

-   <span data-ttu-id="d0164-118">Per le linee guida su come condividere un database del server di report e aggiungere server di report a una distribuzione con scalabilità orizzontale, rivedere le procedure in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d0164-118">Review the procedures in this topic for instructions on how to share a report server database and join report servers to a scale-out.</span></span>

     <span data-ttu-id="d0164-119">Nelle procedure viene illustrato come configurare una distribuzione con scalabilità orizzontale di un server di report con due nodi.</span><span class="sxs-lookup"><span data-stu-id="d0164-119">The procedures explain how to configure a two-node report server scale-out deployment.</span></span> <span data-ttu-id="d0164-120">Ripetere i passaggi descritti in questo argomento per aggiungere altri nodi del server di report alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d0164-120">Repeat the steps described in this topic to add additional report server nodes to the deployment.</span></span>

    -   <span data-ttu-id="d0164-121">Utilizzare il programma di installazione per installare ogni istanza del server di report che verrà unita alla distribuzione con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d0164-121">Use Setup to install each report server instance that will be joined to the scale-out deployment.</span></span>

         <span data-ttu-id="d0164-122">Per evitare errori di compatibilità a livello di database al momento della connessione delle istanze del server al database condiviso, verificare che tutte le istanze abbiano la stessa versione.</span><span class="sxs-lookup"><span data-stu-id="d0164-122">To avoid database compatibility errors when connecting the server instances to the shared database, be sure that all instances are the same version.</span></span> <span data-ttu-id="d0164-123">Se, ad esempio, il database del server di report viene creato utilizzando un'istanza del server di report [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , anche tutte le altre istanze presenti nella stessa distribuzione dovranno essere istanze di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0164-123">For example, if you create the report server database using a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] report server instance, all other instances in the same deployment must also be [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>

    -   <span data-ttu-id="d0164-124">Utilizzare Gestione configurazione di Reporting Services per connettere ogni server di report al database condiviso.</span><span class="sxs-lookup"><span data-stu-id="d0164-124">Use the Reporting Services Configuration manager to connect each report server to the shared database.</span></span> <span data-ttu-id="d0164-125">È possibile connettersi e configurare un solo server di report alla volta.</span><span class="sxs-lookup"><span data-stu-id="d0164-125">You can only connect to and configure one report server at a time.</span></span>

    -   <span data-ttu-id="d0164-126">Utilizzare lo strumento di configurazione di Reporting Services per completare la distribuzione con scalabilità orizzontale unendo le nuove istanze del server di report alla prima istanza del server report già connessa al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-126">Use the Reporting Services Configuration tool to complete the scale-out by joining new report server instances to the first report server instance already connected to the report server database.</span></span>

### <a name="to-install-a-sql-server-instance-to-host-the-report-server-databases"></a><span data-ttu-id="d0164-127">Per installare un'istanza di SQL Server per ospitare i database del server di report</span><span class="sxs-lookup"><span data-stu-id="d0164-127">To install a SQL Server instance to host the report server databases</span></span>

1.  <span data-ttu-id="d0164-128">Installare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un computer che ospiterà i database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-128">Install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance on a computer that will host the report server databases.</span></span> <span data-ttu-id="d0164-129">Installare almeno il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0164-129">At a minimum, install [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>

2.  <span data-ttu-id="d0164-130">Se necessario, abilitare il server di report per le connessioni remote.</span><span class="sxs-lookup"><span data-stu-id="d0164-130">If necessary, enable the report server for remote connections.</span></span> <span data-ttu-id="d0164-131">In alcune versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] le connessioni TCP/IP e Named Pipes remote non sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d0164-131">Some versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do not enable remote TCP/IP and Named Pipes connections by default.</span></span> <span data-ttu-id="d0164-132">Per verificare se le connessioni remote sono consentite, utilizzare Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e visualizzare le impostazioni di configurazione di rete dell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d0164-132">To confirm whether remote connections are allowed, use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and view the network configuration settings of the target instance.</span></span> <span data-ttu-id="d0164-133">Se l'istanza remota è anche un'istanza denominata, verificare che il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser sia abilitato e in esecuzione nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d0164-133">If the remote instance is also a named instance, verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is enabled and running on the target server.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d0164-134">Browser fornisce il numero di porta usato per la connessione all'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="d0164-134">Browser provides the port number that is used to connect to the named instance.</span></span>

### <a name="to-install-the-first-report-server-instance"></a><span data-ttu-id="d0164-135">Per installare la prima istanza del server di report</span><span class="sxs-lookup"><span data-stu-id="d0164-135">To install the first report server instance</span></span>

1.  <span data-ttu-id="d0164-136">Installare la prima istanza del server di report che fa parte della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d0164-136">Install the first report server instance that is part of the deployment.</span></span> <span data-ttu-id="d0164-137">Quando si installa [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], scegliere l'opzione **Installa senza configurare il server** nella pagina Opzioni di installazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-137">When you install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], choose the **Install but do not configure server** option on the Report Server Installation Options page.</span></span>

2.  <span data-ttu-id="d0164-138">Avviare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0164-138">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>

3.  <span data-ttu-id="d0164-139">Configurare l'URL del servizio Web ReportServer, l'URL di Gestione report e il database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-139">Configure the Report Server Web service URL, Report Manager URL, and the report server database.</span></span> <span data-ttu-id="d0164-140">Per altre informazioni, vedere [Configurare un server di report &#40;modalità nativa di Reporting Services&#41;](../report-server/configure-a-report-server-reporting-services-native-mode.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0164-140">For more information, see [Configure a Report Server &#40;Reporting Services Native Mode&#41;](../report-server/configure-a-report-server-reporting-services-native-mode.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>

4.  <span data-ttu-id="d0164-141">Verificare che il server di report sia operativo.</span><span class="sxs-lookup"><span data-stu-id="d0164-141">Verify that the report server is operational.</span></span> <span data-ttu-id="d0164-142">Per altre informazioni, vedere [Verificare un'installazione di Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md) nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0164-142">For more information, see [Verify a Reporting Services Installation](../../reporting-services/install-windows/verify-a-reporting-services-installation.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>

### <a name="to-install-and-configure-the-second-report-server-instance"></a><span data-ttu-id="d0164-143">Per installare e configurare la seconda istanza del server di report</span><span class="sxs-lookup"><span data-stu-id="d0164-143">To install and configure the second report server instance</span></span>

1.  <span data-ttu-id="d0164-144">Eseguire il programma di installazione per installare una seconda istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in un computer diverso o come istanza denominata nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="d0164-144">Run Setup to install a second instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] on a different computer or as a named instance on the same computer.</span></span> <span data-ttu-id="d0164-145">Quando si installa Reporting Services, scegliere l'opzione **Installa senza configurare il server** nella pagina Opzioni di installazione del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-145">When you install Reporting Services, choose the **Install but do not configure server** option on the Report Server Installation Options page.</span></span>

2.  <span data-ttu-id="d0164-146">Avviare lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e connettersi alla nuova istanza installata.</span><span class="sxs-lookup"><span data-stu-id="d0164-146">Start the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the new instance you just installed.</span></span>

3.  <span data-ttu-id="d0164-147">Connettere il server di report allo stesso database utilizzato per la prima istanza del server di report:</span><span class="sxs-lookup"><span data-stu-id="d0164-147">Connect the report server to the same database you used for the first report server instance:</span></span>

    1.  <span data-ttu-id="d0164-148">Fare clic su **database** per aprire la pagina database.</span><span class="sxs-lookup"><span data-stu-id="d0164-148">Click **Database** to open the Database page.</span></span>

    2.  <span data-ttu-id="d0164-149">Fare clic su **Cambia database**.</span><span class="sxs-lookup"><span data-stu-id="d0164-149">Click **Change Database**.</span></span>

    3.  <span data-ttu-id="d0164-150">Fare clic su **Scegli un database del server di report esistente**.</span><span class="sxs-lookup"><span data-stu-id="d0164-150">Click **Choose an existing report server database**.</span></span>

    4.  <span data-ttu-id="d0164-151">Digitare il nome del server dell'istanza del Motore di database di SQL Server che ospita il database del server di report che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="d0164-151">Type the server name of the SQL Server Database Engine instance that hosts the report server database you want to use.</span></span> <span data-ttu-id="d0164-152">Il server deve essere lo stesso a cui ci si è connessi durante i passaggi del set di istruzioni precedente.</span><span class="sxs-lookup"><span data-stu-id="d0164-152">This must be the same server that you connected to in the previous set of the instructions.</span></span>

    5.  <span data-ttu-id="d0164-153">Fare clic su **Test connessione**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0164-153">Click **Test Connection**, and then click **Next**.</span></span>

    6.  <span data-ttu-id="d0164-154">Nel **database del server di report**selezionare il database creato per il primo server di report, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0164-154">In **Report Server Database**, select the database you created for the first report server, and then click **Next**.</span></span> <span data-ttu-id="d0164-155">Il nome predefinito è ReportServer.</span><span class="sxs-lookup"><span data-stu-id="d0164-155">The default name is ReportServer.</span></span> <span data-ttu-id="d0164-156">Non selezionare ReportServerTempDB. Questo database viene utilizzato solo per l'archiviazione temporanea dei dati durante l'elaborazione dei report.</span><span class="sxs-lookup"><span data-stu-id="d0164-156">Do not select ReportServerTempDB; it is used only for storing temporary data when processing reports.</span></span> <span data-ttu-id="d0164-157">Se l'elenco dei database è vuoto, ripetere i quattro passaggi precedenti per stabilire una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="d0164-157">If the database list is empty, repeat the previous four steps to establish a connection to the server.</span></span>

    7.  <span data-ttu-id="d0164-158">Nella pagina Credenziali selezionare il tipo di account e il tipo di credenziali utilizzati dal server di report per la connessione al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-158">In the Credentials page, select the type of account and credentials that the report server will use to connect to the report server database.</span></span> <span data-ttu-id="d0164-159">È possibile utilizzare le stesse credenziali della prima istanza del server di report oppure altre credenziali.</span><span class="sxs-lookup"><span data-stu-id="d0164-159">You can use the same credentials as the first report server instance or different credentials.</span></span> <span data-ttu-id="d0164-160">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0164-160">Click **Next**.</span></span>

    8.  <span data-ttu-id="d0164-161">Fare clic su **Riepilogo** , quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="d0164-161">Click **Summary** and then click **Finish**.</span></span>

4.  <span data-ttu-id="d0164-162">Configurare l'URL del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="d0164-162">Configure the Report Server Web service URL.</span></span> <span data-ttu-id="d0164-163">Non eseguire ancora il test dell'URL.</span><span class="sxs-lookup"><span data-stu-id="d0164-163">Do not test the URL yet.</span></span> <span data-ttu-id="d0164-164">L'URL non verrà risolto se prima il server di report non viene unito alla distribuzione con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d0164-164">It will not resolve until the report server is joined to the scale-out deployment.</span></span>

5.  <span data-ttu-id="d0164-165">Configurare l'URL di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="d0164-165">Configure the Report Manager URL.</span></span> <span data-ttu-id="d0164-166">Non eseguire ancora il test dell'URL e non tentare di verificare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d0164-166">Do not test the URL yet or try to verify the deployment.</span></span> <span data-ttu-id="d0164-167">Il server di report non sarà disponibile fino a quando non viene unito alla distribuzione con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d0164-167">The report server will be unavailable until the report server is joined to the scale-out deployment.</span></span>

### <a name="to-join-the-second-report-server-instance-to-the-scale-out-deployment"></a><span data-ttu-id="d0164-168">Per unire la seconda istanza del server di report alla distribuzione con scalabilità orizzontale</span><span class="sxs-lookup"><span data-stu-id="d0164-168">To join the second report server instance to the scale-out deployment</span></span>

1.  <span data-ttu-id="d0164-169">Aprire lo strumento di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e riconnettersi alla prima istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-169">Open the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, and reconnect to the first report server instance.</span></span> <span data-ttu-id="d0164-170">Poiché il primo server di report è già inizializzato per operazioni di crittografia reversibile, potrà essere utilizzato per unire altre istanze del server di report alla distribuzione con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d0164-170">The first report server is already initialized for reversible encryption operations, so it can be used to join additional report server instances to the scale-out deployment.</span></span>

2.  <span data-ttu-id="d0164-171">Fare clic su **Distribuzione con scalabilità orizzontale** per aprire la pagina Distribuzione con scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d0164-171">Click **Scale-out Deployment** to open the Scale-out Deployment page.</span></span> <span data-ttu-id="d0164-172">Verranno visualizzate due voci, una per ciascuna istanza del server di report connessa al database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-172">You should see two entries, one for each report server instance that is connected to the report server database.</span></span> <span data-ttu-id="d0164-173">La prima istanza del server di report risulterà già unita.</span><span class="sxs-lookup"><span data-stu-id="d0164-173">The first report server instance should be joined.</span></span> <span data-ttu-id="d0164-174">Il secondo server di report sarà identificato come "In attesa dell'unione".</span><span class="sxs-lookup"><span data-stu-id="d0164-174">The second report server should be "Waiting to join".</span></span> <span data-ttu-id="d0164-175">Se non viene visualizzata alcuna voce simile per la distribuzione, verificare di essere connessi al primo server di report già configurato e inizializzato per l'utilizzo del database del server di report.</span><span class="sxs-lookup"><span data-stu-id="d0164-175">If you do not see similar entries for your deployment, verify you are connected to the first report server that is already configured and initialized to use the report server database.</span></span>

     <span data-ttu-id="d0164-176">![Screenshot parziale della pagina Distribuzione con scalabilità orizzontale](../../../2014/sql-server/install/media/scaloutscreen.gif "Screenshot parziale della pagina Distribuzione con scalabilità orizzontale")</span><span class="sxs-lookup"><span data-stu-id="d0164-176">![Partial screenshot of Scale-out Deployment page](../../../2014/sql-server/install/media/scaloutscreen.gif "Partial screenshot of Scale-out Deployment page")</span></span>

3.  <span data-ttu-id="d0164-177">Nella pagina distribuzione con scalabilità orizzontale selezionare l'istanza del server di report in attesa di partecipare alla distribuzione e fare clic su **Aggiungi server**.</span><span class="sxs-lookup"><span data-stu-id="d0164-177">On the Scale-out Deployment page, select the report server instance that is waiting to join the deployment, and click **Add Server**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d0164-178">**Problema:** Quando si tenta di unire un'istanza del server di report Reporting Services alla distribuzione con scalabilità orizzontale, è possibile che si verifichino messaggi di errore simili a "accesso negato".</span><span class="sxs-lookup"><span data-stu-id="d0164-178">**Issue:** When you attempt to join a Reporting Services report server instance to the scale-out deployment, you may experience error messages similar to 'Access Denied'.</span></span>
    > 
    >  <span data-ttu-id="d0164-179">**Soluzione alternativa:** eseguire il backup della chiave di crittografia di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dalla prima istanza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e ripristinare la chiave nel secondo server di report di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0164-179">**Workaround:** Back up the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] encryption key from the first [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and restore the key to the second [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report server.</span></span> <span data-ttu-id="d0164-180">Successivamente, tentare di aggiungere il secondo server alla distribuzione con scalabilità orizzontale di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0164-180">Then try to join the second server to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] scale-out deployment.</span></span>

4.  <span data-ttu-id="d0164-181">A questo punto dovrebbe essere possibile verificare che entrambe le istanze del server di report siano operative.</span><span class="sxs-lookup"><span data-stu-id="d0164-181">You should now be able to verify that both report server instances are operational.</span></span> <span data-ttu-id="d0164-182">Per verificare la seconda istanza, è possibile utilizzare lo strumento di configurazione di Reporting Services per connettersi al server di report e fare clic su URL servizio Web o URL Gestione report.</span><span class="sxs-lookup"><span data-stu-id="d0164-182">To verify the second instance, you can use the Reporting Services Configuration tool to connect to the report server and click the Web Service URL or the Report Manager URL.</span></span>

 <span data-ttu-id="d0164-183">Se si prevede di eseguire i server di report in un cluster di report con carico bilanciato, sono necessarie ulteriori operazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d0164-183">If you plan to run the report servers in a load-balanced server cluster, additional configuration is required.</span></span> <span data-ttu-id="d0164-184">Per altre informazioni, vedere [Configurare un server di report in un cluster per il bilanciamento del carico di rete](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).</span><span class="sxs-lookup"><span data-stu-id="d0164-184">For more information, see [Configure a Report Server on a Network Load Balancing Cluster](../report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0164-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0164-185">See Also</span></span>
 <span data-ttu-id="d0164-186">[Configurare un account del servizio &#40;Configuration Manager ssrs&#41;](../../../2014/sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) [configurare un URL &#40;SSRS](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) Configuration Manager&#41;[creare un database del server di report in modalità nativa &#40;SSRS Configuration Manager](../../reporting-services/install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)&#41;configurare gli URL del server di report &#40;SSRS Configuration Manager [&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md) [configurare una connessione del database del server di report &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) [aggiungere e rimuovere le chiavi di crittografia per una distribuzione con scalabilità orizzontale &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/add-and-remove-encryption-keys-for-scale-out-deployment.md) [gestire un server di report in modalità nativa](../report-server/manage-a-reporting-services-native-mode-report-server.md)</span><span class="sxs-lookup"><span data-stu-id="d0164-186">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md) [Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;](../../../2014/sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md) [Add and Remove Encryption Keys for Scale-Out Deployment &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/add-and-remove-encryption-keys-for-scale-out-deployment.md) [Manage a Reporting Services Native Mode Report Server](../report-server/manage-a-reporting-services-native-mode-report-server.md)</span></span>

