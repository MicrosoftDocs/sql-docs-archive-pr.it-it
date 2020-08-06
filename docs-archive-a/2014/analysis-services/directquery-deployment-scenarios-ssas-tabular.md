---
title: Scenari di distribuzione DirectQuery (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2aaf5cb8-294b-4031-94b3-fe605d7fc4c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c90d90b40686b5953e26853ed9f53dcfd157f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637495"
---
# <a name="directquery-deployment-scenarios-ssas-tabular"></a><span data-ttu-id="0fbc1-102">Scenari di distribuzione DirectQuery (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="0fbc1-102">DirectQuery Deployment Scenarios (SSAS Tabular)</span></span>
  <span data-ttu-id="0fbc1-103">In questo argomento viene fornita una procedura dettagliata del processo di progettazione e distribuzione per i modelli DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-103">This topic provides a walkthrough of the design and deployment process for DirectQuery models.</span></span> <span data-ttu-id="0fbc1-104">È possibile configurare DirectQuery per l'utilizzo dei soli dati relazionali (solo DirectQuery) oppure è possibile configurare il modello per alternare l'utilizzo dei soli dati memorizzati nella cache o dei soli dati relazionali (modalità ibrida).</span><span class="sxs-lookup"><span data-stu-id="0fbc1-104">You can configure DirectQuery to use relational data only (DirectQuery only), or you can configure the model to switch between using cached data only or relational data only (hybrid mode).</span></span> <span data-ttu-id="0fbc1-105">In questo argomento viene illustrato il processo di implementazione per entrambe le modalità e vengono descritte le possibili differenze nei risultati della query a seconda della modalità e della configurazione della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-105">This topic explains the implementation process for both modes, and describes possible differences in query results depending on the mode and the security configuration.</span></span>  
  
 [<span data-ttu-id="0fbc1-106">Passaggi di progettazione e distribuzione</span><span class="sxs-lookup"><span data-stu-id="0fbc1-106">Design and Deployment Steps</span></span>](#bkmk_DQProcedure)  
  
 [<span data-ttu-id="0fbc1-107">Confronto tra le opzioni di configurazione DirectQuery</span><span class="sxs-lookup"><span data-stu-id="0fbc1-107">Comparing DirectQuery Configurations</span></span>](#bkmk_Configurations)  
  
##  <a name="design-and-deployment-steps"></a><a name="bkmk_DQProcedure"></a><span data-ttu-id="0fbc1-108">Fasi di progettazione e distribuzione</span><span class="sxs-lookup"><span data-stu-id="0fbc1-108">Design and Deployment Steps</span></span>  
 <span data-ttu-id="0fbc1-109">**Passaggio 1. Creazione della soluzione**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-109">**Step 1. Create the solution**</span></span>  
  
 <span data-ttu-id="0fbc1-110">Indipendentemente dalla modalità che verrà utilizzata, è necessario rivedere le informazioni che descrivono le limitazioni riguardo ai dati che è possibile utilizzare nei modelli DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-110">Regardless of which mode you will use, you must review the information that describes limitations on the data that can be used in DirectQuery models.</span></span> <span data-ttu-id="0fbc1-111">Ad esempio, tutti i dati utilizzati nel modello e i report devono provenire da un solo database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-111">For example, all the data used in your model and reports must come from a single SQL Server database.</span></span> <span data-ttu-id="0fbc1-112">Per altre informazioni, vedere [Modalità DirectQuery &#40;SSAS tabulare&#41;](tabular-models/directquery-mode-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0fbc1-112">For more information, see [DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="0fbc1-113">Inoltre, consultare le limitazioni relative alle misure e alle colonne calcolate e determinare se le formule che si intende utilizzare sono compatibili con la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-113">Also, review the limitations on measures and calculated columns, and determine whether the formulas you intend to use are compatible with DirectQuery mode.</span></span> <span data-ttu-id="0fbc1-114">Potrebbe essere necessario rimuovere o modificare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fbc1-114">You might need to remove or modify the following elements:</span></span>  
  
-   <span data-ttu-id="0fbc1-115">Le colonne calcolate non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-115">Calculated columns are not supported.</span></span>  
  
-   <span data-ttu-id="0fbc1-116">Non è possibile utilizzare i dati incollati dall'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-116">Copy-pasted data cannot be used.</span></span> <span data-ttu-id="0fbc1-117">Se si importa un modello PowerPivot per avviare la soluzione, assicurarsi di eliminare le tabelle collegate prima di importare la soluzione, poiché questi dati non possono essere eliminati e causeranno il blocco della convalida di DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-117">If you import a PowerPivot model to jumpstart your solution, be sure to delete linked tables before importing the solution, as this data cannot be deleted and will block DirectQuery validation.</span></span>  
  
 <span data-ttu-id="0fbc1-118">**Passaggio 2. Abilitare la modalità DirectQuery in Progettazione modelli**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-118">**Step 2. Enable DirectQuery mode in the model designer**</span></span>  
  
 <span data-ttu-id="0fbc1-119">Per impostazione predefinita, la modalità DirectQuery è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-119">By default, DirectQuery is disabled.</span></span> <span data-ttu-id="0fbc1-120">Pertanto, è necessario configurare l'ambiente di progettazione per supportare la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-120">Therefore, you must configure the design environment to support DirectQuery mode.</span></span>  
  
 <span data-ttu-id="0fbc1-121">Fare clic con il pulsante destro del mouse sul nodo **Model. BIM** in Esplora soluzioni e impostare la proprietà **DirectQuery Mode**su `On` .</span><span class="sxs-lookup"><span data-stu-id="0fbc1-121">Right-click the **Model.bim** node in Solution Explorer and set the property, **DirectQuery Mode**, to `On`.</span></span>  
  
 <span data-ttu-id="0fbc1-122">È possibile attivare la modalità DirectQuery in qualsiasi momento. Tuttavia, per assicurarsi di non creare colonne o formule incompatibili con la modalità DirectQuery, è consigliabile abilitare da subito la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-122">You can turn on DirectQuery at any time; however, to ensure that you do not create columns or formulas that are incompatible with DirectQuery mode, we recommend that you enable DirectQuery mode right from the beginning.</span></span>  
  
 <span data-ttu-id="0fbc1-123">Inizialmente, anche i modelli DirectQuery sono sempre creati in memoria.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-123">Initially, even DirectQuery models are always created in memory.</span></span> <span data-ttu-id="0fbc1-124">La modalità di query predefinita per il database dell'area di lavoro viene inoltre impostata su **DirectQuery con In-Memory**.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-124">The default query mode for the workspace database is also set to **DirectQuery with In-Memory**.</span></span> <span data-ttu-id="0fbc1-125">Questa modalità operativa ibrida consente di utilizzare la cache dei dati importati per migliorare le prestazioni durante il processo di progettazione del modello, convalidando al contempo il modello rispetto ai requisiti di DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-125">This hybrid working mode lets you use the cache of imported data for improved performance during the model design process, while validating the model against DirectQuery requirements.</span></span>  
  
 <span data-ttu-id="0fbc1-126">**Passaggio 3. Risolvere gli errori di convalida**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-126">**Step 3. Resolve validation errors**</span></span>  
  
 <span data-ttu-id="0fbc1-127">Se si verificano errori di convalida quando si attiva DirectQuery o si aggiungono nuovi dati o nuove formule, aprire l' **Elenco errori**di Visual Studio ed effettuare le azioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-127">If you get validation errors when you turn DirectQuery on, or when you add new data or formulas, open the Visual Studio **Error List**, and then take the required actions.</span></span>  
  
-   <span data-ttu-id="0fbc1-128">Modificare le impostazioni delle proprietà necessarie per la modalità DirectQuery seguendo le indicazioni dei messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-128">Change any required property settings for DirectQuery mode, as described in the error messages.</span></span>  
  
-   <span data-ttu-id="0fbc1-129">Rimuovere le colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-129">Remove calculated columns.</span></span> <span data-ttu-id="0fbc1-130">Se è necessaria una colonna calcolata per una misura specifica, è sempre possibile creare la colonna utilizzando la [finestra Progettazione query relazionale &#40;SSAS&#41;](relational-query-designer-ssas.md) fornita nell'importazione guidata tabella.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-130">If you require a calculated column for a particular measure, you can always create the column by using the [Relational Query Designer &#40;SSAS&#41;](relational-query-designer-ssas.md) provided in the Table Import wizard.</span></span>  
  
-   <span data-ttu-id="0fbc1-131">Modificare o rimuovere le formule incompatibili con la modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-131">Modify or remove formulas that are incompatible with DirectQuery mode.</span></span> <span data-ttu-id="0fbc1-132">Se un calcolo richiede una funzione particolare, valutare il modo in cui fornire un equivalente utilizzando Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-132">If you require a particular function for a calculation, consider ways that you could provide an equivalent by using Transact-SQL.</span></span>  
  
-   <span data-ttu-id="0fbc1-133">Aggiungere i dati necessari.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-133">Add data as needed.</span></span>  <span data-ttu-id="0fbc1-134">Se nel modello sono stati utilizzati in precedenza dati da un'operazione copia-incolla o da provider diversi da SQL Server, è possibile creare nuove viste e nuove colonne derivate all'interno della connessione esistente o utilizzare query distribuite.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-134">If your model previously used copy-paste data or data from providers other than SQL Server, you can create new views and derived columns within the existing connection, or use distributed queries.</span></span>  <span data-ttu-id="0fbc1-135">Tutti i dati utilizzati in un modello DirectQuery devono essere accessibili tramite una singola origine dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-135">All data used in a DirectQuery model must be accessible via a single SQL Server data source.</span></span>  
  
 <span data-ttu-id="0fbc1-136">**Passaggio 4. Impostare il metodo preferito per rispondere alle query sul modello**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-136">**Step 4. Set the preferred method for answering queries on the model**</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fbc1-137">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-137">**DirectQuery only**</span></span>|<span data-ttu-id="0fbc1-138">Impostare la proprietà su **DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-138">Set the property to **DirectQuery**.</span></span>|  
|<span data-ttu-id="0fbc1-139">**Modalità ibrida**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-139">**Hybrid mode**</span></span>|<span data-ttu-id="0fbc1-140">Impostare la proprietà su **In-Memory con DirectQuery** o **DirectQuery con In-Memory**.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-140">Set the property to **In-Memory With DirectQuery** or **DirectQuery With In-Memory**.</span></span><br /><br /> <span data-ttu-id="0fbc1-141">È possibile modificare questo valore in un secondo momento per utilizzare una preferenza diversa.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-141">You can change this value later to use a different preference.</span></span><br /><br /> <span data-ttu-id="0fbc1-142">Si noti che i client possono eseguire l'override del metodo preferito nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-142">Note that clients can override the preferred method in the connection string.</span></span>|  
  
 <span data-ttu-id="0fbc1-143">**Passaggio 5. Specificare la partizione DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-143">**Step 5. Specify the DirectQuery partition**</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fbc1-144">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-144">**DirectQuery only**</span></span>|<span data-ttu-id="0fbc1-145">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-145">Optional.</span></span> <span data-ttu-id="0fbc1-146">Per un modello di tipo solo DirectQuery non occorre una partizione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-146">A DirectQuery only model has no need for a partition.</span></span><br /><br /> <span data-ttu-id="0fbc1-147">Tuttavia, se sono state create partizioni nel modello durante la fase di progettazione, solo una partizione può essere utilizzata come origine dati.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-147">However, if you created partitions in the model during the design phase, remember that only one partition can be used as the data source.</span></span> <span data-ttu-id="0fbc1-148">Per impostazione predefinita, la prima partizione creata verrà utilizzata come partizione DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-148">By default the first partition you created will be used as the DirectQuery partition.</span></span><br /><br /> <span data-ttu-id="0fbc1-149">Per assicurarsi che tutti i dati richiesti dal modello siano disponibili nella partizione DirectQuery, scegliere una partizione DirectQuery e modificare l'istruzione SQL per ottenere l'intero set di dati.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-149">To ensure that all the data required by the model is available from the DirectQuery partition, choose a DirectQuery partition and edit the SQL statement to get the entire data set.</span></span>|  
|<span data-ttu-id="0fbc1-150">**Modalità ibrida**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-150">**Hybrid mode**</span></span>|<span data-ttu-id="0fbc1-151">Se una tabella nel modello dispone di più partizioni, è necessario scegliere una sola partizione come *partizione DirectQuery*.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-151">If any table in your model has multiple partitions, you must choose a single partition as the *DirectQuery partition*.</span></span> <span data-ttu-id="0fbc1-152">Se non si assegna una partizione, per impostazione predefinita la prima partizione creata verrà utilizzata come partizione DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-152">If you do not assign a partition, by default, the first partition that was created will be used as the DirectQuery partition.</span></span><br /><br /> <span data-ttu-id="0fbc1-153">Impostare le opzioni di elaborazione su tutte le partizioni tranne DirectQuery</span><span class="sxs-lookup"><span data-stu-id="0fbc1-153">Set processing options on all partitions except the DirectQuery.</span></span> <span data-ttu-id="0fbc1-154">In genere, la partizione DirectQuery non viene mai elaborata perché i dati vengono passati dall'origine relazionale.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-154">Typically the DirectQuery partition is never processed, because the data is passed through from the relational source.</span></span><br /><br /> <span data-ttu-id="0fbc1-155">Per altre informazioni, vedere [partizioni e modalità DirectQuery &#40;&#41;tabulare di SSAS ](tabular-models/define-partitions-in-directquery-models-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0fbc1-155">For more information, see [Partitions and DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/define-partitions-in-directquery-models-ssas-tabular.md).</span></span>|  
  
 <span data-ttu-id="0fbc1-156">**Passaggio 6. Configurare la rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-156">**Step 6. Configure impersonation**</span></span>  
  
 <span data-ttu-id="0fbc1-157">La rappresentazione è supportata unicamente per i modelli DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-157">Impersonation is supported only for DirectQuery models.</span></span> <span data-ttu-id="0fbc1-158">L'opzione di rappresentazione, **Impostazioni di rappresentazione**, consente di definire le credenziali utilizzate per la visualizzazione dei dati dall'origine dati SQL Server specificata.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-158">The impersonation option, **Impersonation Settings**, defines the credentials that are used when viewing data from the specified SQL Server data source.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fbc1-159">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-159">**DirectQuery only**</span></span>|<span data-ttu-id="0fbc1-160">Per la proprietà  **Impostazioni di rappresentazione** , specificare l'account che verrà utilizzato per la connessione all'origine dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-160">For the  **Impersonation Settings** property, specify the account that will be used to connect to the SQL Server data source.</span></span><br /><br /> <span data-ttu-id="0fbc1-161">Se si utilizza il valore **ImpersonateCurrentUser**, l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] che ospita il modello passerà le credenziali dell'utente corrente del modello al database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-161">If you use the value, **ImpersonateCurrentUser**, the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that hosts the model will pass the credentials of the current user of the model to the SQL Server database.</span></span>|  
|<span data-ttu-id="0fbc1-162">**Modalità ibrida**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-162">**Hybrid mode**</span></span>|<span data-ttu-id="0fbc1-163">Per la proprietà **Impostazioni di rappresentazione** , specificare l'account che verrà utilizzato per accedere ai dati nell'origine dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-163">For the **Impersonation Settings** property, specify the account that will be used to access the data in the SQL Server data source.</span></span><br /><br /> <span data-ttu-id="0fbc1-164">Questa impostazione non influisce sulle credenziali utilizzate per elaborare la cache utilizzata dal modello.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-164">This setting does not affect the credentials that are used to process the cache used by the model.</span></span>|  
  
 <span data-ttu-id="0fbc1-165">**Passaggio 7. Distribuire il modello**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-165">**Step 7. Deploy the model**</span></span>  
  
 <span data-ttu-id="0fbc1-166">Quando si è pronti per distribuire il modello, aprire il menu **progetto** di Visual Studio e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-166">When you are ready to deploy the model, open the **Project** menu of Visual Studio, and select **Properties**.</span></span> <span data-ttu-id="0fbc1-167">Impostare la proprietà **QueryMode** su uno dei valori descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="0fbc1-167">Set the **QueryMode** property to one of the values described in the following table:</span></span>  
  
 <span data-ttu-id="0fbc1-168">Per ulteriori informazioni, vedere la pagina relativa alla [distribuzione da SQL Server Data Tools &#40;&#41;tabulare SSAS ](tabular-models/deploy-from-sql-server-data-tools-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="0fbc1-168">For more information, see [Deploy From SQL Server Data Tools &#40;SSAS Tabular&#41;](tabular-models/deploy-from-sql-server-data-tools-ssas-tabular.md).</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fbc1-169">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-169">**DirectQuery only**</span></span>|<span data-ttu-id="0fbc1-170">**DirectQueryOnly**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-170">**DirectQueryOnly**</span></span><br /><br /> <span data-ttu-id="0fbc1-171">Poiché è stata impostata la modalità Solo Direct Query, i metadati del modello vengono distribuiti nel server, ma il modello non viene elaborato.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-171">Because you have specified Direct Query only, the metadata of the model is deployed to the server, but the model is not processed.</span></span><br /><br /> <span data-ttu-id="0fbc1-172">Si noti che la cache utilizzata dal database dell'area di lavoro non viene eliminata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-172">Note that the cache that was used by the workspace database is not automatically deleted.</span></span> <span data-ttu-id="0fbc1-173">Per assicurarsi che gli utenti non possano visualizzare i dati memorizzati nella cache, cancellare il contenuto della cache in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-173">If you want to ensure that users are not able to see the cached data, you might wish to clear the design-time cache.</span></span> <span data-ttu-id="0fbc1-174">Per ulteriori informazioni, vedere [la pagina relativa alla cancellazione delle cache Analysis Services](instances/clear-the-analysis-services-caches.md).</span><span class="sxs-lookup"><span data-stu-id="0fbc1-174">For more information, see [Clear the Analysis Services Caches](instances/clear-the-analysis-services-caches.md).</span></span>|  
|<span data-ttu-id="0fbc1-175">**Modalità ibrida**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-175">**Hybrid mode**</span></span>|<span data-ttu-id="0fbc1-176">**DirectQuery con In-Memory**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-176">**DirectQuery with In-Memory**</span></span><br /><br /> <span data-ttu-id="0fbc1-177">**In memoria con DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-177">**In-Memory with DirectQuery**</span></span><br /><br /> <span data-ttu-id="0fbc1-178">Entrambi questi valori consentono di utilizzare la cache o l'origine dati relazionale secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-178">Both of these values allow you to use either the cache or the relational data source as necessary.</span></span> <span data-ttu-id="0fbc1-179">L'ordine determina l'origine dati che verrà utilizzata per impostazione predefinita per rispondere alle query sul modello.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-179">The order defines which data source is used by default when answering queries against the model.</span></span><br /><br /> <span data-ttu-id="0fbc1-180">In una modalità ibrida, l'elaborazione della cache deve avvenire contemporaneamente alla distribuzione dei metadati del modello nel server.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-180">In a hybrid mode, the cache must be processed at the same time that the model metadata is deployed to the server.</span></span><br /><br /> <span data-ttu-id="0fbc1-181">Dopo la distribuzione sarà possibile modificare questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-181">You can change this setting after deployment.</span></span>|  
  
 <span data-ttu-id="0fbc1-182">**Passaggio 8. Verificare il modello distribuito**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-182">**Step 8. Verify deployed model**</span></span>  
  
 <span data-ttu-id="0fbc1-183">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]aprire l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in cui è stato distribuito il modello.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-183">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], open the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] where you deployed the model.</span></span> <span data-ttu-id="0fbc1-184">Fare clic con il pulsante destro del mouse sul nome del database e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-184">Right-click the name of the database and select **Properties**.</span></span>  
  
-   <span data-ttu-id="0fbc1-185">La proprietà **DirectQueryMode**è stata impostata al momento di definire le proprietà di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-185">The property, **DirectQueryMode**, was set when you defined the deployment properties.</span></span>  
  
-   <span data-ttu-id="0fbc1-186">La proprietà **Impostazioni di rappresentazione origine dati**è stata impostata al momento di definire le opzioni di rappresentazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-186">The property, **Data Source Impersonation Info**, was set when you defined the user impersonation options.</span></span> <span data-ttu-id="0fbc1-187">Per altre informazioni, vedere [Impostare opzioni di rappresentazione &#40;SSAS - Multidimensionale&#41;](multidimensional-models/set-impersonation-options-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="0fbc1-187">For more information, see [Set Impersonation Options &#40;SSAS - Multidimensional&#41;](multidimensional-models/set-impersonation-options-ssas-multidimensional.md).</span></span>  
  
-   <span data-ttu-id="0fbc1-188">È possibile modificare queste proprietà in qualsiasi momento dopo la distribuzione del modello.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-188">You can change these properties any time after the model has been deployed.</span></span>  
  
##  <a name="comparing-directquery-options"></a><a name="bkmk_Configurations"></a><span data-ttu-id="0fbc1-189">Confronto tra le opzioni di DirectQuery</span><span class="sxs-lookup"><span data-stu-id="0fbc1-189">Comparing DirectQuery Options</span></span>  
 <span data-ttu-id="0fbc1-190">**Solo DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-190">**DirectQuery Only**</span></span>  
 <span data-ttu-id="0fbc1-191">Questa opzione è da preferire quando si desidera garantire una singola origine dati o quando la memoria non è in grado di contenere i dati a causa delle loro dimensioni troppo elevate.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-191">This option is preferred when you want to guarantee a single source of data, or when your data is too large to fit in memory.</span></span> <span data-ttu-id="0fbc1-192">Se si utilizza un'origine dati relazionale di grandi dimensioni, in fase di progettazione è possibile creare il modello utilizzando un subset dei dati.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-192">If you are working with a very large relational data source, during design time you can create the model by using some subset of the data.</span></span> <span data-ttu-id="0fbc1-193">Quando si distribuisce il modello in modalità Solo DirectQuery, è possibile modificare la definizione dell'origine dati per includere tutti i dati obbligatori.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-193">When you deploy the model in DirectQuery only mode, you can edit the data source definition to include all the required data.</span></span>  
  
 <span data-ttu-id="0fbc1-194">Preferire questa opzione anche quando si desidera utilizzare la sicurezza fornita dall'origine dati relazionale per controllare l'accesso utente ai dati.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-194">This option is also preferred if you want to use the security provided by the relational data source to control user access to data.</span></span> <span data-ttu-id="0fbc1-195">Con i modelli tabulari memorizzati nella cache, è anche possibile utilizzare i ruoli di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per controllare l'accesso ai dati, tuttavia anche i dati archiviati nella cache devono essere protetti.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-195">With cached tabular models, you can also use [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] roles to control data access, but the data stored in the cache must also be secured.</span></span> <span data-ttu-id="0fbc1-196">Utilizzare sempre questa opzione se il contesto di sicurezza richiede che i dati non vengano mai memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-196">You should always use this option if your security context requires that data should never be cached.</span></span>  
  
 <span data-ttu-id="0fbc1-197">Nella tabella seguente vengono descritti i possibili risultati della distribuzione per la modalità Solo DirectQuery:</span><span class="sxs-lookup"><span data-stu-id="0fbc1-197">The following table describes the possible deployment outcomes for DirectQuery only mode:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fbc1-198">**DirectQuery senza cache**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-198">**DirectQuery with no cache**</span></span>|<span data-ttu-id="0fbc1-199">Non sono stati caricati dati nella cache.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-199">No data is loaded into the cache.</span></span> <span data-ttu-id="0fbc1-200">Il modello non potrà mai essere elaborato.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-200">The model can never be processed.</span></span><br /><br /> <span data-ttu-id="0fbc1-201">Sarà possibile eseguire query sul modello solo utilizzando client che supportano le query DAX.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-201">The model can only be queried by using clients that support DAX queries.</span></span> <span data-ttu-id="0fbc1-202">I risultati delle query vengono sempre restituiti dall'origine dati originale.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-202">Query results are always returned from the original data source.</span></span><br /><br /> <span data-ttu-id="0fbc1-203">**DirectQueryMode** = `On`</span><span class="sxs-lookup"><span data-stu-id="0fbc1-203">**DirectQueryMode** = `On`</span></span><br /><br /> <span data-ttu-id="0fbc1-204">**QueryMode**  =  **DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-204">**QueryMode** = **DirectQuery**</span></span>|  
|<span data-ttu-id="0fbc1-205">**DirectQuery con query solo sulla cache**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-205">**DirectQuery with queries against cache only**</span></span>|<span data-ttu-id="0fbc1-206">La distribuzione non viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-206">Deployment fails.</span></span> <span data-ttu-id="0fbc1-207">Questa configurazione non è supportata.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-207">This configuration is not supported.</span></span><br /><br /> <span data-ttu-id="0fbc1-208">**DirectQueryMode** = `On`</span><span class="sxs-lookup"><span data-stu-id="0fbc1-208">**DirectQueryMode** = `On`</span></span><br /><br /> <span data-ttu-id="0fbc1-209">**QueryMode**  =  **In memoria**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-209">**QueryMode** = **In-Memory**</span></span>|  
  
 <span data-ttu-id="0fbc1-210">**Modalità ibrida**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-210">**Hybrid mode**</span></span>  
 <span data-ttu-id="0fbc1-211">La distribuzione del modello in una modalità ibrida comporta molti vantaggi: la possibilità di ottenere dati aggiornati dall'origine dati SQL Server secondo necessità, ma conservando la cache, consente di lavorare con i dati in memoria e di ottenere prestazioni più elevate durante la progettazione di report o il test del modello.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-211">Deploying your model in a hybrid mode has many advantages: you can get up-to-date data from the SQL Server data source if needed, but preserving the cache gives you the ability to work with data in memory for faster performance while designing reports or testing the model.</span></span>  
  
 <span data-ttu-id="0fbc1-212">Una modalità ibrida DirectQuery è inoltre utile se le dimensioni del modello sono grandi.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-212">A DirectQuery hybrid mode is also useful if your model is very large.</span></span> <span data-ttu-id="0fbc1-213">Per evitare che gli utenti ottengano dati non aggiornati o che il modello non sia disponibile durante l'elaborazione della cache, è possibile impostare la modalità DirectQuery durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-213">Rather than have users get stale data or have the model be unavailable while the cache is processed, you can switch the model to DirectQuery mode while processing is in progress.</span></span> <span data-ttu-id="0fbc1-214">Anche se potrebbe verificarsi un leggero calo delle prestazioni, gli utenti sarebbero comunque in grado di ottenere i dati direttamente dall'archivio relazionale, con risultati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-214">Users might experience slightly slower performance but they would be able to get data directly from the relational store, ensuring that results were up-to-date.</span></span>  
  
 <span data-ttu-id="0fbc1-215">Nella tabella seguente viene confrontato il risultato della distribuzione in ognuna delle combinazioni di opzioni DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-215">The following table compares the deployment outcome in each of the combinations of DirectQuery options.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fbc1-216">**Modalità ibrida con cache preferita**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-216">**Hybrid mode with cache preferred**</span></span>|<span data-ttu-id="0fbc1-217">Il modello può essere elaborato e i dati possono essere caricati nella cache.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-217">The model can be processed and data can be loaded into the cache.</span></span> <span data-ttu-id="0fbc1-218">Per impostazione predefinita, per le query viene utilizzata la cache.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-218">Queries use the cache by default.</span></span>  <span data-ttu-id="0fbc1-219">Se un client desidera utilizzare l'origine DirectQuery, è necessario inserire un parametro nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-219">If a client wants to use the DirectQuery source, a parameter must be inserted in the connection string.</span></span><br /><br /> <span data-ttu-id="0fbc1-220">**DirectQueryMode** = `On`</span><span class="sxs-lookup"><span data-stu-id="0fbc1-220">**DirectQueryMode** = `On`</span></span><br /><br /> <span data-ttu-id="0fbc1-221">**QueryMode**  =  **In memoria con DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-221">**QueryMode** = **In-Memory with DirectQuery**</span></span>|  
|<span data-ttu-id="0fbc1-222">**Modalità ibrida con DirectQuery preferita**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-222">**Hybrid mode with DirectQuery preferred**</span></span>|<span data-ttu-id="0fbc1-223">Il modello viene elaborato e i dati possono essere caricati nella cache.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-223">The model is processed and data can be loaded into the cache.</span></span> <span data-ttu-id="0fbc1-224">Per impostazione predefinita, le query utilizzano tuttavia DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-224">However, queries use DirectQuery by default.</span></span> <span data-ttu-id="0fbc1-225">Se un client desidera utilizzare i dati memorizzati nella cache, è necessario inserire un parametro nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-225">If a client wants to use the cached data, a parameter must be inserted in the connection string.</span></span> <span data-ttu-id="0fbc1-226">Se le tabelle del modello sono partizionate, anche la partizione principale della cache viene impostata su **In-Memory con DirectQuery**.</span><span class="sxs-lookup"><span data-stu-id="0fbc1-226">If the tables in the model are partitioned, the principal partition of the cache is also set to **In-Memory with DirectQuery**.</span></span><br /><br /> <span data-ttu-id="0fbc1-227">**DirectQueryMode** = `On`</span><span class="sxs-lookup"><span data-stu-id="0fbc1-227">**DirectQueryMode** = `On`</span></span><br /><br /> <span data-ttu-id="0fbc1-228">**QueryMode**  =  **DirectQuery con in-Memory**</span><span class="sxs-lookup"><span data-stu-id="0fbc1-228">**QueryMode** = **DirectQuery with In-Memory**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fbc1-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fbc1-229">See Also</span></span>  
 <span data-ttu-id="0fbc1-230">[Modalità DirectQuery &#40;SSAS tabulare&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="0fbc1-230">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="0fbc1-231">Accesso ai dati di modello tabulare</span><span class="sxs-lookup"><span data-stu-id="0fbc1-231">Tabular Model Data Access</span></span>](tabular-models/tabular-model-data-access.md)  
  
  