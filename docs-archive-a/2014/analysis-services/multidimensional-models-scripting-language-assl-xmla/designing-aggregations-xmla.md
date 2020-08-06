---
title: Progettazione di aggregazioni (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- statistical information [XML for Analysis]
- batches [XML for Analysis]
- aggregations [Analysis Services], XML for Analysis
- XMLA, aggregations
- queries [XMLA]
- XML for Analysis, aggregations
- iterative aggregation process [XMLA]
ms.assetid: 4dd27afa-10c7-408d-bc24-ca74217ddbcb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 632cc071605cff6e42adec4acd32c9bd9949fc77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636443"
---
# <a name="designing-aggregations-xmla"></a><span data-ttu-id="8a293-102">Progettazione di aggregazioni (XMLA)</span><span class="sxs-lookup"><span data-stu-id="8a293-102">Designing Aggregations (XMLA)</span></span>
  <span data-ttu-id="8a293-103">Le progettazioni delle aggregazioni sono associate alle partizioni di un gruppo di misure specifico per garantire che utilizzino la stessa struttura nell'archiviazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="8a293-103">Aggregation designs are associated with the partitions of a particular measure group to make sure that the partitions use the same structure when storing aggregations.</span></span> <span data-ttu-id="8a293-104">L'uso della stessa struttura di archiviazione per le partizioni consente di definire facilmente partizioni che possono essere unite in un secondo momento tramite il comando [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="8a293-104">Using the same storage structure for partitions lets you to easily define partitions that can be later merged using the [MergePartitions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/mergepartitions-element-xmla) command.</span></span> <span data-ttu-id="8a293-105">Per ulteriori informazioni sulle progettazioni delle aggregazioni, vedere [aggregazioni e progettazioni delle aggregazioni](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md).</span><span class="sxs-lookup"><span data-stu-id="8a293-105">For more information about aggregation designs, see [Aggregations and Aggregation Designs](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md).</span></span>  
  
 <span data-ttu-id="8a293-106">Per definire le aggregazioni per una progettazione delle aggregazioni, è possibile utilizzare il comando [DesignAggregations](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/designaggregations-element-xmla) in XML for Analysis (XMLA).</span><span class="sxs-lookup"><span data-stu-id="8a293-106">To define aggregations for an aggregation design, you can use the [DesignAggregations](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/designaggregations-element-xmla) command in XML for Analysis (XMLA).</span></span> <span data-ttu-id="8a293-107">Al comando `DesignAggregations` sono associate proprietà che identificano quale progettazione delle aggregazioni utilizzare come riferimento e il modo in cui controllare il processo di progettazione in base a tale riferimento.</span><span class="sxs-lookup"><span data-stu-id="8a293-107">The `DesignAggregations` command has properties that identify which aggregation design to use as a reference and how to control the design process based upon that reference.</span></span> <span data-ttu-id="8a293-108">L'utilizzo del comando `DesignAggregations` e delle proprietà relative consente di progettare le aggregazioni in modo iterativo oppure in batch e di visualizzare successivamente le statistiche relative alla progettazione risultanti per valutare il processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-108">Using the `DesignAggregations` command and its properties, you can design aggregations iteratively or in batch, and then view the resulting design statistics to evaluate the design process.</span></span>  
  
## <a name="specifying-an-aggregation-design"></a><span data-ttu-id="8a293-109">Specifica di una progettazione delle aggregazioni</span><span class="sxs-lookup"><span data-stu-id="8a293-109">Specifying an Aggregation Design</span></span>  
 <span data-ttu-id="8a293-110">La proprietà [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `DesignAggregations` comando deve contenere un riferimento a un oggetto di una progettazione delle aggregazioni esistente.</span><span class="sxs-lookup"><span data-stu-id="8a293-110">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `DesignAggregations` command must contain an object reference to an existing aggregation design.</span></span> <span data-ttu-id="8a293-111">Il riferimento all'oggetto contiene un identificatore di database, un identificatore di cubo, un identificatore del gruppo di misure e un identificatore della progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="8a293-111">The object reference contains a database identifier, cube identifier, measure group identifier, and aggregation design identifier.</span></span> <span data-ttu-id="8a293-112">Se la progettazione delle aggregazioni non esiste, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="8a293-112">If the aggregation design does not already exist, an error occurs.</span></span>  
  
## <a name="controlling-the-design-process"></a><span data-ttu-id="8a293-113">Controllo del processo di progettazione</span><span class="sxs-lookup"><span data-stu-id="8a293-113">Controlling the Design Process</span></span>  
 <span data-ttu-id="8a293-114">Per controllare l'algoritmo utilizzato per definire le aggregazioni per la relativa progettazione, è possibile utilizzare le proprietà del comando `DesignAggregations` seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a293-114">You can use the following properties of the `DesignAggregations` command to control the algorithm used to define aggregations for the aggregation design:</span></span>  
  
-   <span data-ttu-id="8a293-115">La proprietà [Steps](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/steps-element-xmla) determina il numero di iterazioni che il `DesignAggregations` comando deve eseguire prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-115">The [Steps](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/steps-element-xmla) property determines how many iterations the `DesignAggregations` command should take before it returns control to the client application.</span></span>  
  
-   <span data-ttu-id="8a293-116">La proprietà [Time](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/time-element-xmla) determina il numero di millisecondi che il `DesignAggregations` comando deve eseguire prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-116">The [Time](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/time-element-xmla) property determines how many milliseconds the `DesignAggregations` command should take before it returns control to the client application.</span></span>  
  
-   <span data-ttu-id="8a293-117">La proprietà di [ottimizzazione](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/optimization-element-xmla) determina la percentuale stimata di miglioramento delle prestazioni `DesignAggregations` che il comando deve tentare di ottenere.</span><span class="sxs-lookup"><span data-stu-id="8a293-117">The [Optimization](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/optimization-element-xmla) property determines the estimated percentage of performance improvement the `DesignAggregations` command should try to achieve.</span></span> <span data-ttu-id="8a293-118">Se si progettano le aggregazioni in modo iterativo, è necessario inviare questa proprietà solo al primo comando.</span><span class="sxs-lookup"><span data-stu-id="8a293-118">If you are iteratively designing aggregations, you only have to send this property on the first command.</span></span>  
  
-   <span data-ttu-id="8a293-119">La proprietà [storage](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/storage-element-xmla) determina la quantità stimata di spazio di archiviazione su disco, in byte, usata dal `DesignAggregations` comando.</span><span class="sxs-lookup"><span data-stu-id="8a293-119">The [Storage](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/storage-element-xmla) property determines the estimated amount of disk storage, in bytes, used by the `DesignAggregations` command.</span></span> <span data-ttu-id="8a293-120">Se si progettano le aggregazioni in modo iterativo, è necessario inviare questa proprietà solo al primo comando.</span><span class="sxs-lookup"><span data-stu-id="8a293-120">If you are iteratively designing aggregations, you only have to send this property on the first command.</span></span>  
  
-   <span data-ttu-id="8a293-121">La proprietà [materializza](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/materialize-element-xmla) determina se il `DesignAggregations` comando deve creare le aggregazioni definite durante il processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-121">The [Materialize](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/materialize-element-xmla) property determines whether the `DesignAggregations` command should create the aggregations defined during the design process.</span></span> <span data-ttu-id="8a293-122">Se si progettano le aggregazioni in modo iterativo, questa proprietà deve essere impostata su false fino a quando non è possibile salvare le aggregazioni progettate.</span><span class="sxs-lookup"><span data-stu-id="8a293-122">If you are iteratively designing aggregations, this property should be set to false until you are ready to save the designed aggregations.</span></span> <span data-ttu-id="8a293-123">Quando la proprietà viene impostata su true, il processo di progettazione corrente termina e le aggregazioni definite vengono aggiunte alla progettazione delle aggregazioni specificata.</span><span class="sxs-lookup"><span data-stu-id="8a293-123">When set to true, the current design process ends and the defined aggregations are added to the specified aggregation design.</span></span>  
  
## <a name="specifying-queries"></a><span data-ttu-id="8a293-124">Specifica di query</span><span class="sxs-lookup"><span data-stu-id="8a293-124">Specifying Queries</span></span>  
 <span data-ttu-id="8a293-125">Il comando DesignAggregations supporta il comando di ottimizzazione basata sull'utilizzo includendo uno o più `Query` elementi nella proprietà [query](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/queries-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="8a293-125">The DesignAggregations command supports usage-based optimization command by including one or more `Query` elements in the [Queries](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/queries-element-xmla) property.</span></span> <span data-ttu-id="8a293-126">La `Queries` proprietà può contenere uno o più elementi [query](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/query-element-xmla) .</span><span class="sxs-lookup"><span data-stu-id="8a293-126">The `Queries` property can contain one or more [Query](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/query-element-xmla) elements.</span></span> <span data-ttu-id="8a293-127">Se la proprietà `Queries` non contiene alcun elemento `Query`, la progettazione delle aggregazioni specificata nell'elemento `Object` utilizza una struttura predefinita che contiene un set generale di aggregazioni</span><span class="sxs-lookup"><span data-stu-id="8a293-127">If the `Queries` property does not contain any `Query` elements, the aggregation design specified in the `Object` element uses a default structure that contains a general set of aggregations.</span></span> <span data-ttu-id="8a293-128">appositamente progettato per soddisfare i criteri specificati nelle proprietà `Optimization` e `Storage` del comando `DesignAggregations`.</span><span class="sxs-lookup"><span data-stu-id="8a293-128">This general set of aggregations is designed to meet the criteria specified in the `Optimization` and `Storage` properties of the `DesignAggregations` command.</span></span>  
  
 <span data-ttu-id="8a293-129">Ogni elemento `Query` rappresenta una query di tipo goal utilizzata dal processo di progettazione per definire le aggregazioni destinate alle query utilizzate più di frequente.</span><span class="sxs-lookup"><span data-stu-id="8a293-129">Each `Query` element represents a goal query that the design process uses to define aggregations that target the most frequently used queries.</span></span> <span data-ttu-id="8a293-130">È possibile specificare query di tipo goal personalizzate oppure utilizzare le informazioni archiviate da un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nel log di query per recuperare informazioni sulle query utilizzate più di frequente.</span><span class="sxs-lookup"><span data-stu-id="8a293-130">You can either specify your own goal queries, or you can use the information stored by an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in the query log to retrieve information about the most frequently used queries.</span></span> <span data-ttu-id="8a293-131">Il log di query viene utilizzato dall'Ottimizzazione guidata basata sulle statistiche di utilizzo per recuperare query di tipo goal in base all'ora, all'utilizzo oppure all'utente specificato quando viene inviato un comando `DesignAggregations`.</span><span class="sxs-lookup"><span data-stu-id="8a293-131">The Usage-Based Optimization Wizard uses the query log to retrieve goal queries based on time, usage, or a specified user when it sends a `DesignAggregations` command.</span></span> <span data-ttu-id="8a293-132">Per ulteriori informazioni, vedere [Guida sensibile al contesto della procedura guidata ottimizzazione basata sull'utilizzo](../usage-based-optimization-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="8a293-132">For more information, see [Usage-Based Optimization Wizard F1 Help](../usage-based-optimization-wizard-f1-help.md).</span></span>  
  
 <span data-ttu-id="8a293-133">Se si stanno progettando aggregazioni in modo iterativo, è necessario passare le query di tipo goal solo al primo comando `DesignAggregations`, in quanto l'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] archivia queste query e le utilizza durante i comandi `DesignAggregations` successivi.</span><span class="sxs-lookup"><span data-stu-id="8a293-133">If you are iteratively designing aggregations, you only have to pass goal queries in the first `DesignAggregations` command because the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance stores these goal queries and uses these queries during subsequent `DesignAggregations` commands.</span></span> <span data-ttu-id="8a293-134">Dopo avere passato query di tipo goal al primo comando `DesignAggregations` di un processo iterativo, qualsiasi comando `DesignAggregations` successivo che contiene query di tipo goal nella proprietà `Queries` genera un errore.</span><span class="sxs-lookup"><span data-stu-id="8a293-134">After you pass goal queries in the first `DesignAggregations` command of an iterative process, any subsequent `DesignAggregations` command that contains goal queries in the `Queries` property generates an error.</span></span>  
  
 <span data-ttu-id="8a293-135">L'elemento `Query` contiene un valore delimitato da virgole in cui sono presenti gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a293-135">The `Query` element contains a comma-delimited value that contains the following arguments:</span></span>  
  
 <span data-ttu-id="8a293-136">*Frequency*,*Dataset*[,*Dataset*...]</span><span class="sxs-lookup"><span data-stu-id="8a293-136">*Frequency*,*Dataset*[,*Dataset*...]</span></span>  
  
 <span data-ttu-id="8a293-137">*Frequenza*</span><span class="sxs-lookup"><span data-stu-id="8a293-137">*Frequency*</span></span>  
 <span data-ttu-id="8a293-138">Fattore di ponderazione corrispondente al numero di volte che la query è stata eseguita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8a293-138">A weighting factor that corresponds to the number of times that the query has previously been executed.</span></span> <span data-ttu-id="8a293-139">Se l' `Query` elemento rappresenta una nuova query, il valore *Frequency* rappresenta il fattore di ponderazione utilizzato dal processo di progettazione per valutare la query.</span><span class="sxs-lookup"><span data-stu-id="8a293-139">If the `Query` element represents a new query, the *Frequency* value represents the weighting factor used by the design process to evaluate the query.</span></span> <span data-ttu-id="8a293-140">Con l'aumentare del valore della frequenza, aumenta il peso associato alla query durante il processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-140">As the frequency value becomes larger, the weight that is put on the query during the design process increases.</span></span>  
  
 <span data-ttu-id="8a293-141">*Set di dati*</span><span class="sxs-lookup"><span data-stu-id="8a293-141">*Dataset*</span></span>  
 <span data-ttu-id="8a293-142">Stringa numerica che specifica gli attributi di una dimensione da includere nella query.</span><span class="sxs-lookup"><span data-stu-id="8a293-142">A numeric string that specifies which attributes from a dimension are to be included in the query.</span></span> <span data-ttu-id="8a293-143">Questa stringa deve avere un numero di caratteri uguale al numero di attributi della dimensione.</span><span class="sxs-lookup"><span data-stu-id="8a293-143">This string must have the same number of characters as the number of attributes in the dimension.</span></span> <span data-ttu-id="8a293-144">Il valore zero (0) indica che l'attributo nella posizione ordinale specificata non è incluso nella query per la dimensione specificata, mentre il valore uno (1) indica che l'attributo nella posizione ordinale specificata è incluso nella query per la dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="8a293-144">Zero (0) indicates that the attribute in the specified ordinal position is not included in the query for the specified dimension, while one (1) indicates that the attribute in the specified ordinal position is included in the query for the specified dimension.</span></span>  
  
 <span data-ttu-id="8a293-145">La stringa "011" fa riferimento ad esempio a una query relativa a una dimensione con tre attributi, di cui il secondo e il terzo sono inclusi nella query.</span><span class="sxs-lookup"><span data-stu-id="8a293-145">For example, the string "011" would refer to a query involving a dimension with three attributes, from which the second and third attributes are included in the query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a293-146">Alcuni attributi non vengono considerati nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="8a293-146">Some attributes are excluded from consideration in the dataset.</span></span> <span data-ttu-id="8a293-147">Per ulteriori informazioni sugli attributi esclusi, vedere [elemento Query &#40;&#41;XMLA ](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/query-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="8a293-147">For more information about excluded attributes, see [Query Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/query-element-xmla).</span></span>  
  
 <span data-ttu-id="8a293-148">Ogni dimensione del gruppo di misure che contiene la progettazione delle aggregazioni è rappresentata da un valore del *set di dati* nell' `Query` elemento.</span><span class="sxs-lookup"><span data-stu-id="8a293-148">Each dimension in the measure group that contains the aggregation design is represented by a *Dataset* value in the `Query` element.</span></span> <span data-ttu-id="8a293-149">L'ordine dei valori *Dataset* deve corrispondere all'ordine delle dimensioni incluse nel gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="8a293-149">The order of *Dataset* values must match the order of dimensions included in the measure group.</span></span>  
  
## <a name="designing-aggregations-using-iterative-or-batch-processes"></a><span data-ttu-id="8a293-150">Progettazione di aggregazioni tramite processi iterativi o elaborazioni batch</span><span class="sxs-lookup"><span data-stu-id="8a293-150">Designing Aggregations Using Iterative or Batch Processes</span></span>  
 <span data-ttu-id="8a293-151">È possibile utilizzare il comando `DesignAggregations` come parte di un processo iterativo o di un'elaborazione batch, in base all'interattività richiesta dal processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-151">You can use the `DesignAggregations` command as part of an iterative process or a batch process, depending on the interactivity required by the design process.</span></span>  
  
### <a name="designing-aggregations-using-an-iterative-process"></a><span data-ttu-id="8a293-152">Progettazione di aggregazioni tramite un processo iterativo</span><span class="sxs-lookup"><span data-stu-id="8a293-152">Designing Aggregations Using an Iterative Process</span></span>  
 <span data-ttu-id="8a293-153">Per progettare le aggregazioni in modo iterativo, inviare più comandi `DesignAggregations` per fornire un controllo accurato sul processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-153">To iteratively design aggregations, you send multiple `DesignAggregations` commands to provide fine control over the design process.</span></span> <span data-ttu-id="8a293-154">Questo approccio viene utilizzato anche dalla Progettazione guidata aggregazioni per ottenere lo stesso scopo.</span><span class="sxs-lookup"><span data-stu-id="8a293-154">The Aggregation Design Wizard uses this same approach to provide fine control over the design process.</span></span> <span data-ttu-id="8a293-155">Per ulteriori informazioni, vedere [Guida sensibile al contesto della progettazione guidata aggregazioni](../aggregation-design-wizard-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="8a293-155">For more information, see [Aggregation Design Wizard F1 Help](../aggregation-design-wizard-f1-help.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a293-156">Per progettare in modo iterativo le aggregazioni, è necessaria una sessione esplicita.</span><span class="sxs-lookup"><span data-stu-id="8a293-156">An explicit session is required to iteratively design aggregations.</span></span> <span data-ttu-id="8a293-157">Per ulteriori informazioni sulle sessioni esplicite, vedere [gestione delle connessioni e delle sessioni &#40;&#41;XMLA ](managing-connections-and-sessions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="8a293-157">For more information about explicit sessions, see [Managing Connections and Sessions &#40;XMLA&#41;](managing-connections-and-sessions-xmla.md).</span></span>  
  
 <span data-ttu-id="8a293-158">Per avviare il processo iterativo, inviare innanzitutto un comando `DesignAggregations` che contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a293-158">To start the iterative process, you first send a `DesignAggregations` command that contains the following information:</span></span>  
  
-   <span data-ttu-id="8a293-159">Valori delle proprietà `Storage` e `Optimization` in base ai quali viene impostato l'intero processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-159">The `Storage` and `Optimization` property values on which the whole design process is targeted.</span></span>  
  
-   <span data-ttu-id="8a293-160">Valori delle proprietà `Steps` e `Time` in base ai quali viene limitato il primo passaggio del processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-160">The `Steps` and `Time` property values on which the first step of the design process is limited.</span></span>  
  
-   <span data-ttu-id="8a293-161">Proprietà `Queries` che contiene le query di tipo goal in base alle quali viene impostato l'intero processo di progettazione, qualora si desideri l'ottimizzazione basata sulle statistiche di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="8a293-161">If you want usage-based optimization, the `Queries` property that contains the goal queries on which the whole design process is targeted.</span></span>  
  
-   <span data-ttu-id="8a293-162">Proprietà `Materialize` impostata su false.</span><span class="sxs-lookup"><span data-stu-id="8a293-162">The `Materialize` property set to false.</span></span> <span data-ttu-id="8a293-163">L'impostazione di questa proprietà su false indica che durante il processo di progettazione le aggregazioni definite non vengono salvate nella progettazione delle aggregazioni quando il comando è completato.</span><span class="sxs-lookup"><span data-stu-id="8a293-163">Setting this property to false indicates that the design process does not save the defined aggregations to the aggregation design when the command is completed.</span></span>  
  
 <span data-ttu-id="8a293-164">Quando termina, il primo comando `DesignAggregations` restituisce un set di righe che contiene le statistiche relative alla progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-164">When the first `DesignAggregations` command finishes, the command returns a rowset that contains design statistics.</span></span> <span data-ttu-id="8a293-165">È possibile valutare tali statistiche per determinare se il processo di progettazione deve continuare o se è completato.</span><span class="sxs-lookup"><span data-stu-id="8a293-165">You can evaluate these design statistics to determine whether the design process should continue or whether the design process is finished.</span></span> <span data-ttu-id="8a293-166">Se il processo deve continuare, inviare un altro comando `DesignAggregations` che contiene i valori `Steps` e `Time` con i quali viene limitato questo passaggio del processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-166">If the process should continue, you then send another `DesignAggregations` command that contains the `Steps` and `Time` values with which this step of the design process is limited.</span></span> <span data-ttu-id="8a293-167">È possibile valutare le statistiche risultanti e successivamente determinare se il processo di progettazione deve continuare.</span><span class="sxs-lookup"><span data-stu-id="8a293-167">You evaluate the resulting statistics and then determine whether the design process should continue.</span></span> <span data-ttu-id="8a293-168">Questo processo iterativo costituito dall'invio di comandi `DesignAggregations` e dalla valutazione dei risultati continua fino a quando non si raggiungono gli obiettivi e non si ottiene un set appropriato di aggregazioni definite.</span><span class="sxs-lookup"><span data-stu-id="8a293-168">This iterative process of sending `DesignAggregations` commands and evaluating the results continues until you reach your goals and have a appropriate set of aggregations defined.</span></span>  
  
 <span data-ttu-id="8a293-169">Dopo avere ottenuto il set di aggregazioni desiderato, inviare un comando `DesignAggregations` finale.</span><span class="sxs-lookup"><span data-stu-id="8a293-169">After you have reached the set of aggregations that you want, you send one final `DesignAggregations` command.</span></span> <span data-ttu-id="8a293-170">Le proprietà `DesignAggregations` e `Steps` di tale comando `Materialize` finale devono essere impostate su 1 e su true rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="8a293-170">This final `DesignAggregations` command should have its `Steps` property set to 1 and its `Materialize` property set to true.</span></span> <span data-ttu-id="8a293-171">Utilizzando queste impostazioni il comando `DesignAggregations` finale completa il processo di progettazione e salva l'aggregazione definita nella progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="8a293-171">By using these settings, this final `DesignAggregations` command completes the design process and saves the defined aggregation to the aggregation design.</span></span>  
  
### <a name="designing-aggregations-using-a-batch-process"></a><span data-ttu-id="8a293-172">Progettazione di aggregazioni tramite un'elaborazione batch</span><span class="sxs-lookup"><span data-stu-id="8a293-172">Designing Aggregations Using a Batch Process</span></span>  
 <span data-ttu-id="8a293-173">È inoltre possibile progettare le aggregazioni in un'elaborazione batch inviando un unico comando `DesignAggregations` che contiene i valori delle proprietà `Steps`, `Time`, `Storage` e `Optimization` in base ai quali viene impostato e limitato l'intero processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-173">You can also design aggregations in a batch process by sending a single `DesignAggregations` command that contains the `Steps`, `Time`, `Storage`, and `Optimization` property values on which the whole design process is targeted and limited.</span></span> <span data-ttu-id="8a293-174">Qualora si desideri l'ottimizzazione basata sulle statistiche di utilizzo, nella proprietà `Queries` devono essere incluse anche le query di tipo goal in base alle quali viene impostato il processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-174">If you want usage-based optimization, the goal queries on which the design process is targeted should also be included in the `Queries` property.</span></span> <span data-ttu-id="8a293-175">È inoltre necessario verificare che la proprietà `Materialize` sia impostata su true, in modo che durante il processo di progettazione le aggregazioni definite vengano salvate nella progettazione delle aggregazioni quando il comando termina.</span><span class="sxs-lookup"><span data-stu-id="8a293-175">Also make sure that the `Materialize` property is set to true, so that the design process saves the defined aggregations to the aggregation design when the command finishes.</span></span>  
  
 <span data-ttu-id="8a293-176">È possibile progettare aggregazioni tramite un'elaborazione batch in una sessione implicita oppure in una esplicita.</span><span class="sxs-lookup"><span data-stu-id="8a293-176">You can design aggregations using a batch process in either an implicit or explicit session.</span></span> <span data-ttu-id="8a293-177">Per ulteriori informazioni sulle sessioni implicite ed esplicite, vedere [gestione delle connessioni e delle sessioni &#40;&#41;XMLA ](managing-connections-and-sessions-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="8a293-177">For more information about implicit and explicit sessions, see [Managing Connections and Sessions &#40;XMLA&#41;](managing-connections-and-sessions-xmla.md).</span></span>  
  
## <a name="returning-design-statistics"></a><span data-ttu-id="8a293-178">Restituzione di statistiche relative alla progettazione</span><span class="sxs-lookup"><span data-stu-id="8a293-178">Returning Design Statistics</span></span>  
 <span data-ttu-id="8a293-179">Quando il comando `DesignAggregations` restituisce il controllo all'applicazione client, viene restituito anche un set di righe contenente un'unica riga che rappresenta le statistiche relative alla progettazione per il comando.</span><span class="sxs-lookup"><span data-stu-id="8a293-179">When the `DesignAggregations` command returns control to the client application, the command returns a rowset that contains a single row representing the design statistics for the command.</span></span> <span data-ttu-id="8a293-180">Nel set di righe sono contenute le colonne elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8a293-180">The rowset contains the columns listed in the following table.</span></span>  
  
|<span data-ttu-id="8a293-181">Colonna</span><span class="sxs-lookup"><span data-stu-id="8a293-181">Column</span></span>|<span data-ttu-id="8a293-182">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="8a293-182">Data type</span></span>|<span data-ttu-id="8a293-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a293-183">Description</span></span>|  
|------------|---------------|-----------------|  
|<span data-ttu-id="8a293-184">Passaggi</span><span class="sxs-lookup"><span data-stu-id="8a293-184">Steps</span></span>|<span data-ttu-id="8a293-185">Integer</span><span class="sxs-lookup"><span data-stu-id="8a293-185">Integer</span></span>|<span data-ttu-id="8a293-186">Numero di passaggi eseguiti dal comando prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-186">The number of steps taken by the command before returning control to the client application.</span></span>|  
|<span data-ttu-id="8a293-187">Tempo</span><span class="sxs-lookup"><span data-stu-id="8a293-187">Time</span></span>|<span data-ttu-id="8a293-188">Long integer</span><span class="sxs-lookup"><span data-stu-id="8a293-188">Long integer</span></span>|<span data-ttu-id="8a293-189">Numero di millisecondi necessari al comando prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-189">The number of milliseconds taken by the command before returning control to the client application.</span></span>|  
|<span data-ttu-id="8a293-190">Ottimizzazione</span><span class="sxs-lookup"><span data-stu-id="8a293-190">Optimization</span></span>|<span data-ttu-id="8a293-191">Double</span><span class="sxs-lookup"><span data-stu-id="8a293-191">Double</span></span>|<span data-ttu-id="8a293-192">Percentuale stimata di miglioramento delle prestazioni ottenuta dal comando prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-192">The estimated percentage of performance improvement achieved by the command before returning control to the client application.</span></span>|  
|<span data-ttu-id="8a293-193">Archiviazione</span><span class="sxs-lookup"><span data-stu-id="8a293-193">Storage</span></span>|<span data-ttu-id="8a293-194">Long integer</span><span class="sxs-lookup"><span data-stu-id="8a293-194">Long integer</span></span>|<span data-ttu-id="8a293-195">Numero stimato di byte necessari al comando prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-195">The estimated number of bytes taken by the command before returning control to the client application.</span></span>|  
|<span data-ttu-id="8a293-196">Aggregazioni</span><span class="sxs-lookup"><span data-stu-id="8a293-196">Aggregations</span></span>|<span data-ttu-id="8a293-197">Long integer</span><span class="sxs-lookup"><span data-stu-id="8a293-197">Long integer</span></span>|<span data-ttu-id="8a293-198">Numero di aggregazioni definite dal comando prima di restituire il controllo all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8a293-198">The number of aggregations defined by the command before returning control to the client application.</span></span>|  
|<span data-ttu-id="8a293-199">LastStep</span><span class="sxs-lookup"><span data-stu-id="8a293-199">LastStep</span></span>|<span data-ttu-id="8a293-200">Boolean</span><span class="sxs-lookup"><span data-stu-id="8a293-200">Boolean</span></span>|<span data-ttu-id="8a293-201">Indica se i dati nel set di righe rappresentano l'ultimo passaggio del processo di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8a293-201">Indicates whether the data in the rowset represents the last step in the design process.</span></span> <span data-ttu-id="8a293-202">Se la proprietà `Materialize` del comando è impostata su true, il valore di questa colonna viene impostato su true.</span><span class="sxs-lookup"><span data-stu-id="8a293-202">If the `Materialize` property of the command was set to true,  the value of this column is set to true.</span></span>|  
  
 <span data-ttu-id="8a293-203">È possibile utilizzare le statistiche relative alla progettazione contenute nel set di righe restituito dopo ogni comando `DesignAggregations` sia nella progettazione di tipo iterativo che in quella di tipo batch.</span><span class="sxs-lookup"><span data-stu-id="8a293-203">You can use the design statistics that are contained in the rowset returned after each `DesignAggregations` command in both iterative and batch design.</span></span> <span data-ttu-id="8a293-204">Nella progettazione di tipo iterativo è possibile utilizzare le statistiche relative alla progettazione per determinare e visualizzare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="8a293-204">In iterative design, you can use the design statistics to determine and display progress.</span></span> <span data-ttu-id="8a293-205">Quando si progettano le aggregazioni in batch, è possibile utilizzare le statistiche relative alla progettazione per determinare il numero di aggregazioni create dal comando.</span><span class="sxs-lookup"><span data-stu-id="8a293-205">When you are designing aggregations in batch, you can use the design statistics to determine the number of aggregations created by the command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a293-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a293-206">See Also</span></span>  
 [<span data-ttu-id="8a293-207">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="8a293-207">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  