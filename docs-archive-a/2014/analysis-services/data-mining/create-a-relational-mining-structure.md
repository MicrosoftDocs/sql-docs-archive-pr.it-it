---
title: Creare una struttura di data mining relazionale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], data mining
- data mining [Analysis Services], structure
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
- OLAP mining models [Analysis Services]
ms.assetid: 5547d639-377d-4ca7-88fc-ce1f9e2babc5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 34316c0e462a922abf5c5ab069e5150e61db232d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625041"
---
# <a name="create-a-relational-mining-structure"></a><span data-ttu-id="9db6c-102">Creare una struttura di data mining relazionale</span><span class="sxs-lookup"><span data-stu-id="9db6c-102">Create a Relational Mining Structure</span></span>
  <span data-ttu-id="9db6c-103">La maggior parte dei modelli di data mining sono basati su origini dati relazionali.</span><span class="sxs-lookup"><span data-stu-id="9db6c-103">Most data mining models are based on relational data sources.</span></span> <span data-ttu-id="9db6c-104">La creazione di un modello di data mining relazionale offre il vantaggio di poter assemblare dati ad hoc e aggiornare ed eseguire il training di un modello evitando la complessità di dover creare un cubo.</span><span class="sxs-lookup"><span data-stu-id="9db6c-104">The advantages of creating a relational data mining model are that you can assemble ad hoc data and train and update a model without the complexity of creating a cube.</span></span>  
  
 <span data-ttu-id="9db6c-105">Una struttura di data mining relazionale può ottenere dati da origini disparate.</span><span class="sxs-lookup"><span data-stu-id="9db6c-105">A relational mining structure can draw data from disparate sources.</span></span> <span data-ttu-id="9db6c-106">È possibile archiviare i dati non elaborati in sistemi di tabelle, file o database relazionali, purché i dati possano essere definiti come parte di una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-106">The raw data can be stored in tables, files, or relational database systems, so long as the data can be defined as part of data source view.</span></span> <span data-ttu-id="9db6c-107">Ad esempio, è necessario utilizzare una struttura di data mining relazionale se i dati sono in Excel, in un data warehouse di SQL Server o in un database di report di SQL Server oppure in origini esterne cui si accede tramite provider OLE DB o ODBC.</span><span class="sxs-lookup"><span data-stu-id="9db6c-107">For example, you should use a relational mining structure if your data is in Excel, a SQL Server data warehouse or SQL Server reporting database, or in external sources that are accessed via the OLE DB or ODBC providers.</span></span>  
  
 <span data-ttu-id="9db6c-108">In questo argomento vengono forniti cenni preliminari sull'utilizzo di Creazione guidata modello di data mining per creare una struttura di data mining relazionale.</span><span class="sxs-lookup"><span data-stu-id="9db6c-108">This topic provides an overview of how to use the Data Mining Wizard to create a relational mining structure.</span></span>  
  
 [<span data-ttu-id="9db6c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9db6c-109">Requirements</span></span>](#BKMK_Relational_Structure)  
  
 [<span data-ttu-id="9db6c-110">Processo di creazione di una struttura di data mining relazionale</span><span class="sxs-lookup"><span data-stu-id="9db6c-110">Process for Creating a Relational Mining Structure</span></span>](#BKMK_Relational_Structure)  
  
 [<span data-ttu-id="9db6c-111">Come scegliere le origini dati</span><span class="sxs-lookup"><span data-stu-id="9db6c-111">How to Choose Data Sources</span></span>](#BKMK_ChooseRelData)  
  
 [<span data-ttu-id="9db6c-112">Come specificare il tipo di contenuto e di dati</span><span class="sxs-lookup"><span data-stu-id="9db6c-112">How to Specify Content Type and Data Type</span></span>](#bkmk_ContentDataType)  
  
 [<span data-ttu-id="9db6c-113">Come creare un set di dati di controllo e perché</span><span class="sxs-lookup"><span data-stu-id="9db6c-113">Why and How to Create a Holdout Data Set</span></span>](#bkmk_Holdout)  
  
 [<span data-ttu-id="9db6c-114">Come abilitare il drill-through e perché</span><span class="sxs-lookup"><span data-stu-id="9db6c-114">Why and How to Enable Drillthrough</span></span>](#BKMK_DrillThru)  
  
## <a name="requirements"></a><span data-ttu-id="9db6c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9db6c-115">Requirements</span></span>  
 <span data-ttu-id="9db6c-116">Innanzitutto, è necessario disporre di un'origine dati esistente.</span><span class="sxs-lookup"><span data-stu-id="9db6c-116">First, you must have an existing data source.</span></span> <span data-ttu-id="9db6c-117">È possibile utilizzare Progettazione origine dati per impostare un'origine dati, se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="9db6c-117">You can use the Data Source designer to set up a data source, if one does not already exist.</span></span> <span data-ttu-id="9db6c-118">Per altre informazioni, vedere [Creare un'origine dati &#40;SSAS multidimensionale&#41;](../multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-118">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](../multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="9db6c-119">Successivamente, utilizzare la Creazione guidata vista origine dati per assemblare i dati richiesti in una sola vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-119">Next, use the Data Source View Wizard to assemble required data into a single data source view.</span></span> <span data-ttu-id="9db6c-120">Per altre informazioni sulla modalità di selezione, trasformazione, filtro o gestione dei dati con le viste origine dati, vedere [Viste origine dati in modelli multidimensionali](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-120">For more information about how you can select, transform, filter, or manage data with data source views, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
##  <a name="overview-of-process"></a><a name="BKMK_Relational_Structure"></a><span data-ttu-id="9db6c-121">Panoramica del processo</span><span class="sxs-lookup"><span data-stu-id="9db6c-121">Overview of Process</span></span>  
 <span data-ttu-id="9db6c-122">Avviare la Creazione guidata modello di data mining facendo clic con il pulsante destro del mouse sul nodo **Strutture di data mining** in Esplora soluzioni e scegliendo **Aggiungi nuova struttura di data mining**.</span><span class="sxs-lookup"><span data-stu-id="9db6c-122">Start the Data Mining Wizard, by right-clicking the **Mining Structures** node in Solution Explorer, and selecting **Add New Mining Structure**.</span></span> <span data-ttu-id="9db6c-123">La procedura guidata consente di eseguire in modo semplificato i passaggi indicati di seguito per la creazione della struttura di un nuovo modello di data mining relazionale:</span><span class="sxs-lookup"><span data-stu-id="9db6c-123">The wizard guides you through the following steps to create the structure for a new relational mining model:</span></span>  
  
1.  <span data-ttu-id="9db6c-124">**Selezione metodo di definizione**: consente di selezionare un tipo di origine dati e scegliere **Da database relazionale o data warehouse**.</span><span class="sxs-lookup"><span data-stu-id="9db6c-124">**Select the Definition Method**: Here you select a data source type, and choose **From relational database or data warehouse**.</span></span>  
  
2.  <span data-ttu-id="9db6c-125">**Crea la struttura di data mining**: consente di determinare se verrà compilata solo una struttura o una struttura con un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="9db6c-125">**Create the Data Mining Structure**: Determine whether you will build just a structure, or a structure with a mining model.</span></span>  
  
     <span data-ttu-id="9db6c-126">Scegliere inoltre un algoritmo appropriato per il modello iniziale.</span><span class="sxs-lookup"><span data-stu-id="9db6c-126">You also choose an appropriate algorithm for your initial model.</span></span> <span data-ttu-id="9db6c-127">Per indicazioni sugli algoritmi ottimali per attività specifiche, vedere [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-127">For guidance on which algorithm is best for certain tasks, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
3.  <span data-ttu-id="9db6c-128">**Selezione vista origine dati**: scegliere una vista origine dati da usare per il training del modello.</span><span class="sxs-lookup"><span data-stu-id="9db6c-128">**Select Data Source View**: Choose a data sources view to use in training your model.</span></span> <span data-ttu-id="9db6c-129">La vista origine dati può inoltre contenere dati utilizzati per il test o dati non correlati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-129">The data source view can also contain data used for testing, or unrelated data.</span></span> <span data-ttu-id="9db6c-130">Scegliere quali dati verranno effettivamente utilizzati nella struttura e nel modello.</span><span class="sxs-lookup"><span data-stu-id="9db6c-130">You get to pick and choose which data is actually used in the structure and in the model.</span></span> <span data-ttu-id="9db6c-131">È inoltre possibile applicare filtri ai dati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9db6c-131">You can also apply filters to the data later on.</span></span>  
  
4.  <span data-ttu-id="9db6c-132">**Impostazione tipi di tabelle**: selezionare la tabella che contiene i case usati per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9db6c-132">**Specify Table Types**: Select the table that contains the cases used for analysis.</span></span> <span data-ttu-id="9db6c-133">Per alcuni set di dati, in particolare quelli utilizzati per la compilazione di modelli di analisi di mercato su acquisti, può essere necessario includere anche una tabella correlata, da utilizzare come tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9db6c-133">For some data sets, especially ones used for building market basket models, you might also include a related table, to use as a nested table.</span></span>  
  
     <span data-ttu-id="9db6c-134">Per ogni tabella, è necessario specificare la chiave, per consentire all'algoritmo di identificare un record univoco e i record correlati, se è stata aggiunta una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9db6c-134">For each table, you must specify the key, so that the algorithm knows how to identify a unique record, and related records if you have added a nested table.</span></span>  
  
     <span data-ttu-id="9db6c-135">Per altre informazioni, vedere [Mining Structure Columns](mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-135">For more information, see [Mining Structure Columns](mining-structure-columns.md).</span></span>  
  
5.  <span data-ttu-id="9db6c-136">**Impostazione dati di training**: in questa pagina, si sceglie la *tabella del case*, ovvero la tabella che contiene i dati più importanti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9db6c-136">**Specify the Training Data**: On this page, you choose as the *case table*, which is the table that contains the most important data for analysis.</span></span>  
  
     <span data-ttu-id="9db6c-137">Per alcuni set di dati, in particolare quelli utilizzati per la compilazione di modelli di analisi di mercato su acquisti, può essere necessario includere anche una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="9db6c-137">For some data sets, especially ones used for building market basket models, you might also include a related table.</span></span> <span data-ttu-id="9db6c-138">I valori in tale tabella nidificata verranno gestiti come più valori tutti correlati a una sola riga (o case) nella tabella principale.</span><span class="sxs-lookup"><span data-stu-id="9db6c-138">The values in that nested table will be handled as multiple values that are all related to a single row (or case) in the main table.</span></span>  
  
6.  <span data-ttu-id="9db6c-139">**Impostazione tipo di contenuto e dati delle colonne**: per ogni colonna usata nella struttura è necessario scegliere sia un *tipo di dati* che un *tipo di contenuto*.</span><span class="sxs-lookup"><span data-stu-id="9db6c-139">**Specify Columns Content and Data Types**: For each column that you use in the structure, you must choose both a *data type* and a *content type*.</span></span>  
  
     <span data-ttu-id="9db6c-140">Tramite la procedura guidata vengono rilevati automaticamente i tipi di dati possibili, ma non è necessario utilizzare il tipo di dati consigliato dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="9db6c-140">The wizard will automatically detect possible data types, but you don't need to use the data type recommended by the wizard.</span></span> <span data-ttu-id="9db6c-141">Ad esempio, anche se i dati contengono numeri, potrebbero essere rappresentativi di dati di categoria.</span><span class="sxs-lookup"><span data-stu-id="9db6c-141">For example, even if your data contains numbers, they might be representative of categorical data.</span></span> <span data-ttu-id="9db6c-142">Alle colonne specificate come chiavi viene assegnato automaticamente il tipo di dati corretto per tale tipo di modello particolare.</span><span class="sxs-lookup"><span data-stu-id="9db6c-142">Columns that you specify as keys are automatically assigned the correct data type for that particular model type.</span></span> <span data-ttu-id="9db6c-143">Per altre informazioni, vedere [Colonne del modello di data mining](mining-model-columns.md) e [Tipi di dati &#40;data mining&#41;](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-143">For more information, see [Mining Model Columns](mining-model-columns.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
     <span data-ttu-id="9db6c-144">Il *tipo di contenuto* scelto per ogni colonna utilizzata nel modello indica all'algoritmo in che modo devono essere elaborati i dati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-144">The *content type* that you choose for each column that you use in the model tells the algorithm how the data should be processed.</span></span>  
  
     <span data-ttu-id="9db6c-145">Ad esempio, è possibile decidere di discretizzare i numeri, anziché utilizzare valori continui.</span><span class="sxs-lookup"><span data-stu-id="9db6c-145">For example, you might decide to discretize numbers, rather than use continuous values.</span></span> <span data-ttu-id="9db6c-146">È inoltre possibile utilizzare l'algoritmo per rilevare automaticamente il tipo di contenuto migliore per la colonna.</span><span class="sxs-lookup"><span data-stu-id="9db6c-146">You can also ask the algorithm to automatically detect the best content type for the column.</span></span> <span data-ttu-id="9db6c-147">Per altre informazioni, vedere [Tipi di contenuto &#40;Data mining&#41;](content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-147">For more information, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="9db6c-148">**Crea set di testing**: in questa pagina è possibile definire nella procedura guidata la quantità di dati da mettere da parte durante il test del modello.</span><span class="sxs-lookup"><span data-stu-id="9db6c-148">**Create Testing Set**: On this page, you can tell the wizard how much data should be set aside for use in testing the model.</span></span> <span data-ttu-id="9db6c-149">Se i dati supporteranno più modelli, è consigliabile creare un set di dati di controllo, in modo da poter eseguire il test di tutti i modelli sugli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-149">If your data will support multiple models, it is a good idea to create a holdout data set, so that all models can be tested on the same data.</span></span>  
  
     <span data-ttu-id="9db6c-150">Per altre informazioni, vedere [Test e convalida &#40;Data mining&#41;](testing-and-validation-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-150">For more information, see [Testing and Validation &#40;Data Mining&#41;](testing-and-validation-data-mining.md).</span></span>  
  
8.  <span data-ttu-id="9db6c-151">**Completamento procedura guidata**: in questa pagina si assegna un nome alla nuova struttura di data mining e al modello di data mining associato, quindi si salvano struttura e modello.</span><span class="sxs-lookup"><span data-stu-id="9db6c-151">**Completing the Wizard**: On this page, you give a name to the new mining structure and the associated mining model, and save the structure and model.</span></span>  
  
     <span data-ttu-id="9db6c-152">È inoltre possibile impostare alcune opzioni importanti, a seconda del tipo di modello.</span><span class="sxs-lookup"><span data-stu-id="9db6c-152">You also can set some important options, depending on the model type.</span></span> <span data-ttu-id="9db6c-153">Ad esempio, è possibile abilitare il drill-through sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="9db6c-153">For example, you can enable drillthrough on the structure.</span></span>  
  
     <span data-ttu-id="9db6c-154">In questa fase la struttura di data mining e il modello sono esclusivamente metadati; sarà necessario elaborarli entrambi per ottenere risultati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-154">At this point the mining structure and its model are just metadata; you will need to process them both to get results.</span></span>  
  
##  <a name="how-to-choose-relational-data"></a><a name="BKMK_ChooseRelData"></a><span data-ttu-id="9db6c-155">Come scegliere dati relazionali</span><span class="sxs-lookup"><span data-stu-id="9db6c-155">How to Choose Relational Data</span></span>  
 <span data-ttu-id="9db6c-156">Le strutture di data mining relazionali possono essere basate sui dati disponibili tramite un'origine dei dati OLE DB.</span><span class="sxs-lookup"><span data-stu-id="9db6c-156">Relational mining structures can be based on any data that is available through an OLE DB data source.</span></span> <span data-ttu-id="9db6c-157">Se i dati di origine sono contenuti all'interno di più tabelle, si utilizza una vista origine dati per assemblare le tabelle e le colonne necessarie in una sola posizione.</span><span class="sxs-lookup"><span data-stu-id="9db6c-157">If the source data is contained within multiple tables, you use a data source view to assemble the tables and columns that you need in one place.</span></span>  
  
 <span data-ttu-id="9db6c-158">Se le tabelle includono relazioni uno-a-molti, ad esempio se si dispone di più record di acquisto per ogni cliente che si desidera analizzare, è possibile aggiungere entrambe le tabelle e quindi utilizzare una tabella come tabella del case, collegando i dati sul lato molti della relazione come tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="9db6c-158">If the tables include any one-to-many relationships-for example, you have multiple purchase records for each customer that you want to analyze-you can add both tables, and then use one table as the case table, linking data on the many side of the relationship as a nested table.</span></span>  
  
 <span data-ttu-id="9db6c-159">I dati di una struttura di data mining derivano dal contenuto all'interno della vista origine dati esistente.</span><span class="sxs-lookup"><span data-stu-id="9db6c-159">The data in a mining structure is derived from whatever is in the existing data source view.</span></span> <span data-ttu-id="9db6c-160">È possibile modificare dati secondo le esigenze all'interno della vista origine dati, aggiungendo relazioni o colonne derivate che potrebbero non essere presenti nei dati relazionali sottostanti.</span><span class="sxs-lookup"><span data-stu-id="9db6c-160">You can modify data as you need within the data source view, adding relationships or derived columns that might not be present in the underlying relational data.</span></span> <span data-ttu-id="9db6c-161">È inoltre possibile creare calcoli o aggregazioni denominati all'interno della vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-161">You can also create named calculations or aggregations within the data source view.</span></span> <span data-ttu-id="9db6c-162">Queste funzionalità sono molto utili se non è possibile controllare la disposizione dei dati nell'origine dati o se si desidera sperimentare diverse aggregazioni di dati per i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="9db6c-162">These features are very handy if you do not have control over the arrangement of data in the data source, or if you want to experiment with different aggregations of data for your data mining models.</span></span>  
  
 <span data-ttu-id="9db6c-163">Non è necessario utilizzare tutti i dati disponibili; è possibile scegliere quali colonne includere nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="9db6c-163">You do not have to use all the data that is available; you can pick and choose which columns to include in the mining structure.</span></span> <span data-ttu-id="9db6c-164">Tutti i modelli basati su tale struttura possono quindi utilizzare tali colonne o è possibile contrassegnare determinate colonne come `Ignore` per un particolare modello.</span><span class="sxs-lookup"><span data-stu-id="9db6c-164">All models that are based on that structure then can use those columns, or you can flag certain columns as `Ignore` for a particular model.</span></span> <span data-ttu-id="9db6c-165">È inoltre possibile consentire agli utenti di un modello di data mining di eseguire il drill-down a partire dai risultati del modello per visualizzare colonne della struttura di data mining aggiuntive non incluse nel modello di data mining stesso.</span><span class="sxs-lookup"><span data-stu-id="9db6c-165">You can enable users of a data mining model to drill down from the results of the mining model to see additional mining structure columns that were not included in the mining model itself.</span></span>  
  
##  <a name="how-to-specify-content-type-and-data-type"></a><a name="bkmk_ContentDataType"></a><span data-ttu-id="9db6c-166">Come specificare il tipo di contenuto e il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="9db6c-166">How to Specify Content Type and Data Type</span></span>  
 <span data-ttu-id="9db6c-167">Il tipo di dati è molto simile ai tipi di dati specificati in SQL Server o nelle interfacce di altre applicazioni: date e ore, numeri di dimensioni diverse, valori booleani, testo e altri dati discreti.</span><span class="sxs-lookup"><span data-stu-id="9db6c-167">The data type is pretty much the same as the data types you specify in SQL Server or other application interfaces: dates and times, numbers of different sizes, Boolean values, text and other discrete data.</span></span>  
  
 <span data-ttu-id="9db6c-168">Tuttavia, i tipi di contenuto sono importanti per il data mining e influiscono sul risultato dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="9db6c-168">However, content types are important for data mining and affect the outcome of analysis.</span></span> <span data-ttu-id="9db6c-169">Il tipo di contenuto indica all'algoritmo come procedere con i dati: i numeri devono essere considerati su scala continua o suddivisi in contenitori?</span><span class="sxs-lookup"><span data-stu-id="9db6c-169">The content type tells the algorithm what it should do with the data: should numbers be treated on a continuous scale, or binned?</span></span> <span data-ttu-id="9db6c-170">Quanti valori potenziali sono presenti?</span><span class="sxs-lookup"><span data-stu-id="9db6c-170">How many potential values are there?</span></span> <span data-ttu-id="9db6c-171">Ogni valore è distinto?</span><span class="sxs-lookup"><span data-stu-id="9db6c-171">Is each value distinct?</span></span> <span data-ttu-id="9db6c-172">Se il valore è una chiave, qual è il tipo di chiave che indica un valore di data/ora, una sequenza o un altro tipo di chiave?</span><span class="sxs-lookup"><span data-stu-id="9db6c-172">If the value is a key, what kind of key is it - does it indicate a date/time value, a sequence, or some other kind of key?</span></span>  
  
 <span data-ttu-id="9db6c-173">Si noti che la scelta del tipo di dati può limitare la scelta dei tipi di contenuto.</span><span class="sxs-lookup"><span data-stu-id="9db6c-173">Note that the choice of data type can limit your choice of content types.</span></span> <span data-ttu-id="9db6c-174">Ad esempio, non è possibile discretizzare valori non numerici.</span><span class="sxs-lookup"><span data-stu-id="9db6c-174">For example, you cannot discretize values that are not numeric.</span></span> <span data-ttu-id="9db6c-175">Se il tipo di contenuto desiderato non è visibile, fare clic su **Indietro** per tornare alla pagina del tipo di dati e provarne uno diverso.</span><span class="sxs-lookup"><span data-stu-id="9db6c-175">If you cannot see the content type that you want, you can click **Back** to return to the data type page and try a different data type.</span></span>  
  
 <span data-ttu-id="9db6c-176">Non è importante preoccuparsi di evitare di ottenere il tipo di contenuto errato.</span><span class="sxs-lookup"><span data-stu-id="9db6c-176">You need not worry too much about getting the content type wrong.</span></span> <span data-ttu-id="9db6c-177">È molto facile creare un nuovo modello e modificare il tipo di contenuto all'interno del modello, purché il nuovo tipo di contenuto sia supportato dal tipo di dati impostato nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="9db6c-177">It is very easy to create a new model and change the content type within the model, as long as the new content type is supported by the data type set in the mining structure.</span></span> <span data-ttu-id="9db6c-178">È inoltre molto comune creare più modelli con tipi di contenuto diversi, come esperimento o per soddisfare i requisiti di un algoritmo diverso.</span><span class="sxs-lookup"><span data-stu-id="9db6c-178">It is also very common to create multiple models using different content types, either as an experiment, or to meet the requirements of a different algorithm.</span></span>  
  
 <span data-ttu-id="9db6c-179">Ad esempio, se i dati contengono una colonna del reddito, è possibile creare due modelli diversi quando si utilizza l'algoritmo Microsoft Decision Trees e configurare la colonna alternativamente come numeri continui o intervalli discreti.</span><span class="sxs-lookup"><span data-stu-id="9db6c-179">For example, if your data contains an income column, you could create two different models when using the Microsoft Decision Trees algorithm, and configure the column alternately as either continuous numbers or discrete ranges.</span></span> <span data-ttu-id="9db6c-180">Tuttavia, se è stato aggiunto un modello utilizzando l'algoritmo Microsoft Naive Bayes, sarebbe necessario impostare la colonna solo sui valori discretizzati, perché tale algoritmo non supporta i numeri continui.</span><span class="sxs-lookup"><span data-stu-id="9db6c-180">However, if you added a model using the Microsoft Naïve Bayes algorithm, you would be forced to change the column to discretized values only, because that algorithm does not support continuous numbers.</span></span>  
  
##  <a name="why-and-how-to-split-data-into-training-and-testing-sets"></a><a name="bkmk_Holdout"></a><span data-ttu-id="9db6c-181">Perché e come suddividere i dati in set di training e di testing</span><span class="sxs-lookup"><span data-stu-id="9db6c-181">Why and How to Split Data into Training and Testing Sets</span></span>  
 <span data-ttu-id="9db6c-182">Verso la fine della procedura guidata è necessario decidere se partizionare i dati in set di training e di testing.</span><span class="sxs-lookup"><span data-stu-id="9db6c-182">Near the end of the wizard, you must decide whether to partition your data into training and testing sets.</span></span> <span data-ttu-id="9db6c-183">La possibilità di fornire una parte dei dati campionati in modo casuale per eseguire il testing è molto utile e consente di garantire che un set coerente di dati di test sia disponibile per essere utilizzato con tutti i modelli di data mining associati alla nuova struttura.</span><span class="sxs-lookup"><span data-stu-id="9db6c-183">The ability to provision a randomly sampled portion of the data for testing is very convenient, as it ensures that a consistent set of test data is available for use with all mining models associated with the new mining structure.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9db6c-184">Si noti che questa opzione non è disponibile per tutti i tipi di modelli.</span><span class="sxs-lookup"><span data-stu-id="9db6c-184">Note that this option is not available for all model types.</span></span> <span data-ttu-id="9db6c-185">Se, ad esempio, si crea un modello di previsione, non sarà possibile utilizzare i dati di attesa perché l'algoritmo Time Series richiede che non siano presenti gap nei dati.</span><span class="sxs-lookup"><span data-stu-id="9db6c-185">For example, if you create a forecasting model, you won't be able to use holdout, because the time series algorithm requires that there be no gaps in data.</span></span> <span data-ttu-id="9db6c-186">Per un elenco dei tipi di modelli che supportano i set di dati di controllo, vedere [Set di dati di training e di testing](training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-186">For a list of the model types that support holdout data sets, see [Training and Testing Data Sets](training-and-testing-data-sets.md).</span></span>  
  
 <span data-ttu-id="9db6c-187">Per creare questo set di dati di controllo, specificare la percentuale dei dati che si desidera utilizzare per il test.</span><span class="sxs-lookup"><span data-stu-id="9db6c-187">To create this holdout data set, you specify the percentage of the data you want to use for testing.</span></span> <span data-ttu-id="9db6c-188">Tutti i dati rimanenti saranno utilizzati per il training.</span><span class="sxs-lookup"><span data-stu-id="9db6c-188">All remaining data will be used for training.</span></span> <span data-ttu-id="9db6c-189">Facoltativamente, è possibile impostare un numero massimo di case da utilizzare per i test o impostare un valore di inizializzazione da utilizzare per avviare il processo di selezione casuale.</span><span class="sxs-lookup"><span data-stu-id="9db6c-189">Optionally, you can set a maximum number of cases to use for testing, or set a seed value to use in starting the random selection process.</span></span>  
  
 <span data-ttu-id="9db6c-190">La definizione del set di test di dati di controllo viene archiviata con la struttura di data mining, in modo che tutte le volte in cui si crea un nuovo modello basato sulla struttura, il set di dati di testing sarà disponibile per valutarne l'accuratezza.</span><span class="sxs-lookup"><span data-stu-id="9db6c-190">The definition of the holdout test set is stored with the mining structure, so that whenever you create a new model based on the structure, the testing data set will be available for assessing the accuracy of the model.</span></span> <span data-ttu-id="9db6c-191">Se si elimina la cache della struttura di data mining, verranno anche eliminate le informazioni sui case utilizzati per il training e su quelli utilizzati per i test.</span><span class="sxs-lookup"><span data-stu-id="9db6c-191">If you delete the cache of the mining structure, the information about which cases were used for training and which were used for testing will be deleted as well.</span></span>  
  
##  <a name="why-and-how-to-enable-drillthrough"></a><a name="BKMK_DrillThru"></a><span data-ttu-id="9db6c-192">Perché e come abilitare il drill-through</span><span class="sxs-lookup"><span data-stu-id="9db6c-192">Why and How to Enable Drillthrough</span></span>  
 <span data-ttu-id="9db6c-193">Nella parte conclusiva della procedura guidata, è possibile scegliere di abilitare il *drill-through*.</span><span class="sxs-lookup"><span data-stu-id="9db6c-193">Almost at the very end of the wizard, you have the option to enable *drillthrough*.</span></span> <span data-ttu-id="9db6c-194">È facile perdere questa opzione, ma è importante.</span><span class="sxs-lookup"><span data-stu-id="9db6c-194">It is easy to miss this option, but it's an important one.</span></span> <span data-ttu-id="9db6c-195">Il drill-through consente di visualizzare i dati di origine nella struttura di data mining eseguendo una query sul modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="9db6c-195">Drillthrough lets you view source data in the mining structure by querying the mining model.</span></span>  
  
 <span data-ttu-id="9db6c-196">Perché è utile?</span><span class="sxs-lookup"><span data-stu-id="9db6c-196">Why is this useful?</span></span> <span data-ttu-id="9db6c-197">Si supponga di visualizzare i risultati di un modello di clustering e di voler vedere i clienti inseriti in un cluster specifico.</span><span class="sxs-lookup"><span data-stu-id="9db6c-197">Suppose you are viewing the results of a clustering model, and want to see the customers who were put into a specific cluster.</span></span> <span data-ttu-id="9db6c-198">Tramite il drill-through, è possibile visualizzare dettagli quali le informazioni di contatto.</span><span class="sxs-lookup"><span data-stu-id="9db6c-198">By using drillthrough, you can view details such as contact information.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9db6c-199">Per utilizzare il drill-through è necessario abilitarlo durante la creazione della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="9db6c-199">To use drillthrough, you must enable it when you create the mining structure.</span></span> <span data-ttu-id="9db6c-200">È possibile abilitare il drill-through sui modelli in un secondo momento, impostando una proprietà sul modello, ma per le strutture di data mining questa opzione deve essere impostata all'inizio.</span><span class="sxs-lookup"><span data-stu-id="9db6c-200">You can enable drillthrough on models later, by setting a property on the model, but mining structures require that this option be set at the beginning.</span></span> <span data-ttu-id="9db6c-201">Per altre informazioni, vedere [Query drill-through &#40;Data mining&#41;](drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="9db6c-201">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](drillthrough-queries-data-mining.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db6c-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9db6c-202">See Also</span></span>  
 <span data-ttu-id="9db6c-203">[Progettazione modelli di data mining](data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9db6c-203">[Data Mining Designer](data-mining-designer.md) </span></span>  
 <span data-ttu-id="9db6c-204">[Creazione guidata modello di data mining &#40;Analysis Services-&#41;di data mining](data-mining-wizard-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="9db6c-204">[Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="9db6c-205">[Proprietà modello di data mining](mining-model-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9db6c-205">[Mining Model Properties](mining-model-properties.md) </span></span>  
 <span data-ttu-id="9db6c-206">[Proprietà per le colonne della struttura e della struttura di data mining](properties-for-mining-structure-and-structure-columns.md) </span><span class="sxs-lookup"><span data-stu-id="9db6c-206">[Properties for Mining Structure and Structure Columns](properties-for-mining-structure-and-structure-columns.md) </span></span>  
 [<span data-ttu-id="9db6c-207">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="9db6c-207">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  