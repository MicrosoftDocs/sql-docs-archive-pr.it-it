---
title: Connessione BI Semantic Model (BISM) di PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 04/19/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 08828eec-4f8c-4f34-a145-e442f7b7031d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 14a30128986a5ba23cb093be771c036c94fa25ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636422"
---
# <a name="powerpivot-bi-semantic-model-connection-bism"></a><span data-ttu-id="2b987-102">Connessione BI Semantic Model (bism) di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="2b987-102">PowerPivot BI Semantic Model Connection (.bism)</span></span>
  <span data-ttu-id="2b987-103">Una connessione BI Semantic Model (BISM) è una connessione portatile che connette report di Excel o [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] a un database modello tabulare di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] o a un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in modalità multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="2b987-103">A BI semantic model connection (.bism) is a portable connection that connects Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tabular model database or an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance in multidimensional mode.</span></span> <span data-ttu-id="2b987-104">Chi ha familiarità con i file Office Data Connection (estensione odc) noterà una somiglianza con la modalità di definizione e di utilizzo di un file di connessione BISM.</span><span class="sxs-lookup"><span data-stu-id="2b987-104">If you are familiar with office data connection (.odc) files, you will notice a similarity in how a .bism connection file is defined and used.</span></span>  
  
 <span data-ttu-id="2b987-105">La creazione e l'accesso a una connessione BISM avvengono tramite SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2b987-105">A BI semantic model connection is created and accessed via SharePoint.</span></span> <span data-ttu-id="2b987-106">La creazione di connessioni BISM abilita i comandi di avvio veloce su una connessione BISM in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="2b987-106">Creating BI semantic model connections enables quick launch commands on a BI semantic model connection in a library.</span></span> <span data-ttu-id="2b987-107">I comandi di avvio veloce consentono di aprire una nuova cartella di lavoro di Excel o opzioni per la modifica del file della connessione.</span><span class="sxs-lookup"><span data-stu-id="2b987-107">Quick launch commands open a new Excel workbook or options for editing the connection file.</span></span> <span data-ttu-id="2b987-108">Se [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è installato, verrà visualizzato anche un comando per creare un report di [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b987-108">If [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is installed, you will also see a command to create a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report.</span></span>  
  
 <span data-ttu-id="2b987-109">![Schermata del comando di avvio rapido BISM](../media/ssas-bism-quicklaunch.gif "Schermata del comando di avvio rapido BISM")</span><span class="sxs-lookup"><span data-stu-id="2b987-109">![Screenshot of BISM quick launch command](../media/ssas-bism-quicklaunch.gif "Screenshot of BISM quick launch command")</span></span>  
  
##  <a name="supported-databases"></a><a name="bkmk_prereq"></a><span data-ttu-id="2b987-110">Database supportati</span><span class="sxs-lookup"><span data-stu-id="2b987-110">Supported databases</span></span>  
 <span data-ttu-id="2b987-111">Una connessione BISM punta a dati del modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2b987-111">A BI semantic model connection points to tabular model data.</span></span> <span data-ttu-id="2b987-112">Per questi dati sono disponibili tre origini:</span><span class="sxs-lookup"><span data-stu-id="2b987-112">There are three sources for this data:</span></span>  
  
-   <span data-ttu-id="2b987-113">Un database modello tabulare in esecuzione su un'istanza di Analysis Services autonoma in modalità server tabulare.</span><span class="sxs-lookup"><span data-stu-id="2b987-113">A tabular model database running on a standalone Analysis Services instance in tabular server mode.</span></span> <span data-ttu-id="2b987-114">Una distribuzione di un'istanza di Analysis Services autonoma è esterna alla farm.</span><span class="sxs-lookup"><span data-stu-id="2b987-114">A deployment of a standalone Analysis Services instance is external to the farm.</span></span> <span data-ttu-id="2b987-115">Per l'accesso a origini dati esterne alla farm sono necessarie autorizzazioni aggiuntive; informazioni in merito vengono fornite in questo argomento: [Create a BI Semantic Model Connection to a Tabular Model Database](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md).</span><span class="sxs-lookup"><span data-stu-id="2b987-115">Accessing data sources off the farm requires additional permissions, which you can read about in this topic: [Create a BI Semantic Model Connection to a Tabular Model Database](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md).</span></span>  
  
-   <span data-ttu-id="2b987-116">Cartelle di lavoro di PowerPivot salvate in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2b987-116">PowerPivot workbooks saved to SharePoint.</span></span> <span data-ttu-id="2b987-117">I database PowerPivot delle cartelle di lavoro di Excel sono considerati equivalenti ai database modello tabulare eseguiti in un server in modalità tabulare di Analysis Services autonomo.</span><span class="sxs-lookup"><span data-stu-id="2b987-117">Embedded PowerPivot databases inside Excel workbooks are equivalent to tabular model databases that run on a standalone Analysis Services tabular mode server.</span></span> <span data-ttu-id="2b987-118">Se si usano già PowerPivot per Excel e PowerPivot per SharePoint, è possibile definire una connessione BISM tramite cui si punta alle cartelle di lavoro di PowerPivot in una raccolta di SharePoint e compilare report [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] che usano i dati PowerPivot esistenti.</span><span class="sxs-lookup"><span data-stu-id="2b987-118">If you already use PowerPivot for Excel and PowerPivot for SharePoint, you can define a BI semantic model connection that points to PowerPivot workbooks in a SharePoint library and build [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports using existing PowerPivot data.</span></span>  <span data-ttu-id="2b987-119">È possibile usare cartelle di lavoro create in SQL Server 2008 R2 o in versioni di [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] di PowerPivot per Excel.</span><span class="sxs-lookup"><span data-stu-id="2b987-119">You can use workbooks created in either SQL Server 2008 R2 or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] versions of PowerPivot for Excel.</span></span>  
  
-   <span data-ttu-id="2b987-120">Un modello di dati multidimensionali in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b987-120">A multidimensional data model on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="2b987-121">Per un confronto tra le origini dati, vedere il contenuto della community che [comprende il SQL Server 2012 BI Semantic Model (BISM)](http://www.mssqltips.com/sqlservertip/2818/understanding-the-sql-server-2012-bi-semantic-model-bism/).</span><span class="sxs-lookup"><span data-stu-id="2b987-121">For a comparison of the data sources, see the community  content [Understanding the SQL Server 2012 BI Semantic Model (BISM)](http://www.mssqltips.com/sqlservertip/2818/understanding-the-sql-server-2012-bi-semantic-model-bism/).</span></span>  
  
## <a name="understanding-the-connection-sequence-for-bi-semantic-connections"></a><span data-ttu-id="2b987-122">Informazioni sulla sequenza di connessione per connessioni BISM</span><span class="sxs-lookup"><span data-stu-id="2b987-122">Understanding the Connection Sequence for BI Semantic Connections</span></span>  
 <span data-ttu-id="2b987-123">In questa sezione viene illustrato il comportamento della connessione tra le varie applicazioni client, quale l'applicazione desktop di Excel o lo strumento client di creazione report di Power View su SharePoint e un database modello tabulare all'interno o all'esterno della farm di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2b987-123">This section explains the connection behavior between various client applications, such as the Excel desktop application or the Power View reporting client on SharePoint, and a tabular model database inside or outside the SharePoint farm.</span></span>  
  
 <span data-ttu-id="2b987-124">Tutte le connessioni a un database modello tabulare vengono eseguite tramite le credenziali dell'utente che sta richiedendo i dati.</span><span class="sxs-lookup"><span data-stu-id="2b987-124">All connections to a tabular model database are made using the credentials of the user who is requesting the data.</span></span> <span data-ttu-id="2b987-125">Tuttavia, i meccanismi di connessione variano a seconda se si tratta di una connessione interna alla farm, una connessione a hop singolo o doppio e se l'autenticazione Kerberos è abilitata.</span><span class="sxs-lookup"><span data-stu-id="2b987-125">However, the mechanics of that connection will vary depending on whether the connection is an in-farm connection, a single or double-hop connection, and whether Kerberos is enabled.</span></span> <span data-ttu-id="2b987-126">Per altre informazioni sulle connessioni autenticate tra origini dati SharePoint e back-end, vedere [Autenticazione hop doppio: perché NTLM non riesce e Kerberos funziona](https://go.microsoft.com/fwlink/?LinkId=237137).</span><span class="sxs-lookup"><span data-stu-id="2b987-126">For more information about authenticated connections between SharePoint and backend data sources, see [Double-hop authentication: Why NTLM fails and Kerberos works](https://go.microsoft.com/fwlink/?LinkId=237137).</span></span>  
  
 <span data-ttu-id="2b987-127">**Connessione da Excel ai dati tabulari su una rete**</span><span class="sxs-lookup"><span data-stu-id="2b987-127">**Connecting from Excel to tabular data on a network**</span></span>  
  
 <span data-ttu-id="2b987-128">Quando un utente di Excel specifica una connessione BISM come origine dati, le informazioni di connessione nel file con estensione bism vengono scaricate nell'applicazione client che quindi pubblica la propria richiesta diretta nel database modello tabulare su Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2b987-128">When an Excel user specifies a BI semantic model connection as a data source, the connection information inside the .bism file is downloaded to the client application, which then issues its own direct request to the tabular model database on Analysis Services.</span></span> <span data-ttu-id="2b987-129">Per accedere alla connessione BISM, l'utente di Excel deve essere un utente di SharePoint con le autorizzazioni di lettura sul file di connessione con estensione bism.</span><span class="sxs-lookup"><span data-stu-id="2b987-129">To access the .bism connection, the Excel user must be a SharePoint user with read permissions on the .bism connection file.</span></span> <span data-ttu-id="2b987-130">Una volta scaricate le informazioni di connessione, tutte le connessioni successive ignorano SharePoint, passando direttamente da Excel al database modello tabulare di back-end.</span><span class="sxs-lookup"><span data-stu-id="2b987-130">Once the connection information is downloaded, all subsequent connections bypass SharePoint, flowing directly from Excel to the backend tabular model database.</span></span>  
  
 <span data-ttu-id="2b987-131">Nella figura seguente è illustrata tale sequenza di connessione.</span><span class="sxs-lookup"><span data-stu-id="2b987-131">The following illustration shows this connection sequence.</span></span> <span data-ttu-id="2b987-132">Inizia con una richiesta per la connessione con estensione bism, seguita dal download di informazioni di connessione al client e infine dalla connessione a hop singolo al database.</span><span class="sxs-lookup"><span data-stu-id="2b987-132">It starts with a request for the .bism connection, followed by the download of connection information to the client, and finally the single-hop connection to the database.</span></span> <span data-ttu-id="2b987-133">La connessione viene eseguita utilizzando le credenziali di Windows dell'utente di Excel che ha le autorizzazioni di lettura sul database di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2b987-133">The connection is made using the Windows credentials of the Excel user, who has read permissions on the Analysis Services database.</span></span> <span data-ttu-id="2b987-134">È una comunicazione a hop singolo, pertanto anche se è abilitata, l'autenticazione Kerberos non è richiesta per questo scenario.</span><span class="sxs-lookup"><span data-stu-id="2b987-134">It is a single hop, so even if Kerberos is enabled, it is not required for this scenario.</span></span>  
  
 <span data-ttu-id="2b987-135">![Connessioni da Excel a un database modello tabulare](../media/ssas-powerpivotbismconnection-1.gif "Connessioni da Excel a un database modello tabulare")</span><span class="sxs-lookup"><span data-stu-id="2b987-135">![Connections from Excel to tabular model database](../media/ssas-powerpivotbismconnection-1.gif "Connections from Excel to tabular model database")</span></span>  
  
 <span data-ttu-id="2b987-136">**Connessione da Power View ai dati tabulari su una rete**</span><span class="sxs-lookup"><span data-stu-id="2b987-136">**Connecting from Power View to tabular data on a network**</span></span>  
  
 <span data-ttu-id="2b987-137">Quando un utente di SharePoint fa clic su una connessione BISM in una raccolta documenti, Power View (se installato) immediatamente avvia e apre una connessione al database modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2b987-137">When a SharePoint user clicks on a BI semantic connection in a document library, Power View (if it is installed), starts immediately and opens a connection to the tabular model database.</span></span>  
  
 <span data-ttu-id="2b987-138">Le connessioni tra Power View e un database modello tabulare seguono una sequenza di autenticazione a hop doppio dove l'identità utente viene passata dal client a SharePoint e quindi da SharePoint a un database modello tabulare di Analysis Services di back-end in esecuzione all'esterno della farm.</span><span class="sxs-lookup"><span data-stu-id="2b987-138">Connections between Power View and a tabular model database follow a double-hop authentication sequence where the user identity is flowed from the client to SharePoint, and then from SharePoint to a back-end Analysis Services tabular model database that runs outside of the farm.</span></span> <span data-ttu-id="2b987-139">La libreria client ADOMD.NET che gestisce la richiesta di connessione prova sempre l'autenticazione Kerberos al primo tentativo.</span><span class="sxs-lookup"><span data-stu-id="2b987-139">The ADOMD.NET client library that handles the connection request always tries Kerberos on the first attempt.</span></span> <span data-ttu-id="2b987-140">Se Kerberos è configurato, l'identità utente è rappresentata sulla connessione al database modello tabulare e la connessione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="2b987-140">If Kerberos is configured, the user identity is impersonated on the connection to the tabular model database, and the connection succeeds.</span></span>  
  
 <span data-ttu-id="2b987-141">Se Kerberos non è configurato e la richiesta non riesce, Reporting Services effettua un secondo tentativo.</span><span class="sxs-lookup"><span data-stu-id="2b987-141">If Kerberos is not configured and the request fails, Reporting Services makes a second attempt.</span></span> <span data-ttu-id="2b987-142">In questo scenario, la libreria client si connette a Analysis Services usando l'identità del servizio Reporting Services e l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="2b987-142">Under this scenario, the client library connects to Analysis Services using the Reporting Services service identity and NTLM authentication.</span></span> <span data-ttu-id="2b987-143">L'identità dell'utente di Power View viene passata sulla stringa di connessione usando il parametro `effectiveusername`.</span><span class="sxs-lookup"><span data-stu-id="2b987-143">The identity of the Power View user is passed on the connection string using the `effectiveusername` parameter.</span></span>  
  
 <span data-ttu-id="2b987-144">Solo un membro del ruolo di amministratore di sistema sull'istanza di Analysis Services dispone delle autorizzazioni per effettuare una connessione utilizzando il parametro `effectiveusername` e rappresentare un altro utente sull'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="2b987-144">Only a member of the system administrator role on the Analysis Services instance has permission to make a connection using the `effectiveusername` parameter and impersonate another user on the server instance.</span></span> <span data-ttu-id="2b987-145">Per questo motivo, l'account di esecuzione del servizio condiviso Reporting Services deve disporre di diritti amministrativi sull'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="2b987-145">For this reason, the execution account of the Reporting Services shared service must have administrative rights on the Analysis Services instance.</span></span>  <span data-ttu-id="2b987-146">Per le istruzioni per concedere le autorizzazioni amministrative all'account del servizio, vedere l'argomento [Creare una connessione BISM a un database modello tabulare](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md).</span><span class="sxs-lookup"><span data-stu-id="2b987-146">Instructions for granting administrative permissions to the service account is provided in this topic, [Create a BI Semantic Model Connection to a Tabular Model Database](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md).</span></span>  
  
 <span data-ttu-id="2b987-147">Nell'illustrazione seguente viene mostrata una sequenza di connessione che utilizza la stessa identità utente di Windows per ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="2b987-147">The following illustration shows a connection sequence that uses the same Windows user identity for each connection.</span></span> <span data-ttu-id="2b987-148">Nell'ultima connessione a Analysis Services, la connessione viene eseguita dall'identità dell'applicazione del servizio Reporting Services, passando l'identità utente di Windows tramite `effectiveusername`.</span><span class="sxs-lookup"><span data-stu-id="2b987-148">On the last connection to Analysis Services, the connection is made by the Reporting Services service application identity, passing the Windows user identity using `effectiveusername`.</span></span>  
  
 <span data-ttu-id="2b987-149">![connessione rappresentata a un database tabulare](../media/ssas-powerpivotbismconnection-2.gif "connessione rappresentata a un database tabulare")</span><span class="sxs-lookup"><span data-stu-id="2b987-149">![Imersonated connection to tabular db](../media/ssas-powerpivotbismconnection-2.gif "Imersonated connection to tabular db")</span></span>  
  
 <span data-ttu-id="2b987-150">**Connessione da Power View ai dati PowerPivot in SharePoint**</span><span class="sxs-lookup"><span data-stu-id="2b987-150">**Connecting from Power View to PowerPivot data in SharePoint**</span></span>  
  
 <span data-ttu-id="2b987-151">Quando un utente di SharePoint fa clic su una connessione BISM che si risolve in una cartella di lavoro di PowerPivot della stessa farm, le connessioni si verificano all'interno del contesto dell'ambiente SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2b987-151">When a SharePoint user clicks on a BI semantic connection that resolves to a PowerPivot workbook in the same farm, the connections occur within the context of the SharePoint environment.</span></span> <span data-ttu-id="2b987-152">Un'applicazione del servizio PowerPivot gestisce la richiesta di connessione che viene inoltrata all'istanza di Analysis Services sullo stesso computer.</span><span class="sxs-lookup"><span data-stu-id="2b987-152">A PowerPivot service application handles the connection request, which it forwards to the Analysis Services instance on the same computer.</span></span> <span data-ttu-id="2b987-153">L'istanza di Analysis Services estrae i dati PowerPivot dalla cartella di lavoro e li carica.</span><span class="sxs-lookup"><span data-stu-id="2b987-153">The Analysis Services instance extracts the PowerPivot data from the workbook and loads it.</span></span> <span data-ttu-id="2b987-154">Tutte le connessioni successive sono gestite dalle applicazioni del servizio PowerPivot nella farm.</span><span class="sxs-lookup"><span data-stu-id="2b987-154">All subsequent connections are managed by PowerPivot service applications in the farm.</span></span>  
  
 <span data-ttu-id="2b987-155">In questo scenario, tutte le connessioni si verificano all'interno della stessa farm, pertanto non c'è richiesta di Kerberos o di delega vincolata.</span><span class="sxs-lookup"><span data-stu-id="2b987-155">In this scenario, all connections occur within the same farm, so there is no requirement for Kerberos or constrained delegation.</span></span>  
  
##  <a name="related-tasks"></a><a name="bkmk_rel"></a> <span data-ttu-id="2b987-156">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="2b987-156">Related Tasks</span></span>  
 [<span data-ttu-id="2b987-157">Aggiungere un tipo di contenuto connessione BI Semantic Model a una raccolta &#40;PowerPivot per SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="2b987-157">Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;</span></span>](add-bi-semantic-model-connection-content-type-to-library.md)  
  
 [<span data-ttu-id="2b987-158">Creare una connessione BISM (BI Semantic Model) a una cartella di lavoro di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="2b987-158">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="2b987-159">Creare una connessione BISM a un database modello tabulare</span><span class="sxs-lookup"><span data-stu-id="2b987-159">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
 [<span data-ttu-id="2b987-160">Utilizzare una connessione BISM (BI Semantic Model) in Excel o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2b987-160">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="2b987-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b987-161">See Also</span></span>  
 <span data-ttu-id="2b987-162">[Determinare la modalità server di un'istanza di Analysis Services](../instances/determine-the-server-mode-of-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="2b987-162">[Determine the Server Mode of an Analysis Services Instance](../instances/determine-the-server-mode-of-an-analysis-services-instance.md) </span></span>  
 [<span data-ttu-id="2b987-163">Connetti ad Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2b987-163">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
  