---
title: Aggiunta di modelli di data mining a una struttura (Analysis Services-Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], creating
- mining models [Analysis Services], creating
- mining models [Analysis Services], modifying
ms.assetid: a175daa5-58ea-474c-a82f-9648c5155dc8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2cc504016ac378a66795e7522365bd570cfca84d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625046"
---
# <a name="add-mining-models-to-a-structure-analysis-services---data-mining"></a><span data-ttu-id="55178-102">Aggiungere modelli di data mining a una struttura (Analysis Services - Data mining)</span><span class="sxs-lookup"><span data-stu-id="55178-102">Add Mining Models to a Structure (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="55178-103">Una struttura di data mining può supportare più modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-103">A mining structure is intended to support multiple mining models.</span></span> <span data-ttu-id="55178-104">Pertanto dopo avere completato la procedura guidata è possibile aprire la struttura e aggiungere nuovi modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-104">Therefore, after you finish the wizard, you can open the structure and add new mining models.</span></span> <span data-ttu-id="55178-105">Ogni volta che si crea un modello, è possibile utilizzare un algoritmo diverso, modificare i parametri o applicare filtri per utilizzare un subset di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="55178-105">Each time that you create a model, you can use a different algorithm, change the parameters, or apply filters to use a different subset of the data.</span></span>  
  
## <a name="adding-new-mining-models"></a><span data-ttu-id="55178-106">Aggiunta di nuovi modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="55178-106">Adding New Mining Models</span></span>  
 <span data-ttu-id="55178-107">Quando si utilizza Creazione guidata modello di data mining per creare un nuovo modello di data mining, per impostazione predefinita è sempre necessario creare prima una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-107">When you use the Data Mining Wizard to create a new mining model, by default you must always create a mining structure first.</span></span> <span data-ttu-id="55178-108">Tramite la procedura guidata è quindi possibile aggiungere un modello di data mining iniziale alla struttura.</span><span class="sxs-lookup"><span data-stu-id="55178-108">The wizard then gives you the option to add an initial mining model to the structure.</span></span> <span data-ttu-id="55178-109">Tuttavia, non è necessario creare immediatamente un modello.</span><span class="sxs-lookup"><span data-stu-id="55178-109">However, you don't need to create a model right away.</span></span> <span data-ttu-id="55178-110">Se si crea solo la struttura, non è necessario prendere una decisione in merito alla colonna da utilizzare come attributo stimabile o su come utilizzare i dati in un determinato modello.</span><span class="sxs-lookup"><span data-stu-id="55178-110">If you create the structure only, you do not need to make a decision about which column to use as the predictable attribute, or how to use the data in a particular model.</span></span> <span data-ttu-id="55178-111">Al contrario, è sufficiente impostare la struttura dei dati generale da utilizzare in futuro e in seguito utilizzare [Data Mining Designer](data-mining-designer.md) per aggiungere nuovi modelli di data mining basati su tale struttura.</span><span class="sxs-lookup"><span data-stu-id="55178-111">Instead, you just set up the general data structure that you want to use in future, and later you can use [Data Mining Designer](data-mining-designer.md) to add new mining models that are based on the structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55178-112">In DMX l'istruzione CREATE MINING MODEL inizia con il modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-112">In DMX, the CREATE MINING MODEL statement  begins with the mining model.</span></span> <span data-ttu-id="55178-113">Ovvero, si definisce il modello di data mining prescelto e la struttura sottostante viene automaticamente generata in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55178-113">That is, you define your choice of mining model, and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically generates the underlying structure.</span></span> <span data-ttu-id="55178-114">In un secondo momento è possibile continuare ad aggiungere nuovi modelli di data mining alla struttura usando l'istruzione ALTER STRUCTURE... Aggiungi istruzione del modello.</span><span class="sxs-lookup"><span data-stu-id="55178-114">Later you can continue to add new mining models to that structure, by using the ALTER STRUCTURE... ADD MODEL statement.</span></span>  
  
## <a name="choosing-an-algorithm"></a><span data-ttu-id="55178-115">Scelta di un algoritmo</span><span class="sxs-lookup"><span data-stu-id="55178-115">Choosing an Algorithm</span></span>  
 <span data-ttu-id="55178-116">Quando si aggiunge un nuovo modello a una struttura esistente, la prima operazione da eseguire è la selezione di un algoritmo di data mining da utilizzare in tale modello.</span><span class="sxs-lookup"><span data-stu-id="55178-116">When you add a new model to an existing structure, the first thing you should do is select a data mining algorithm to use in that model.</span></span> <span data-ttu-id="55178-117">La scelta dell'algoritmo è importante perché ogni algoritmo esegue un tipo diverso di analisi e presenta requisiti diversi.</span><span class="sxs-lookup"><span data-stu-id="55178-117">Choosing the algorithm is important because each algorithm performs a different type of analysis and has different requirements.</span></span>  
  
 <span data-ttu-id="55178-118">Quando si seleziona un algoritmo incompatibile con i dati, viene visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="55178-118">When you select an algorithm that is incompatible with your data, you will get a warning.</span></span> <span data-ttu-id="55178-119">In alcuni casi, potrebbe essere necessario ignorare le colonne che non è possibile elaborare tramite l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="55178-119">In some cases, you might need to ignore columns that cannot be processed by the algorithm.</span></span> <span data-ttu-id="55178-120">In altri casi le modifiche verranno effettuate automaticamente dall'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="55178-120">In other cases, the algorithm will automatically make the adjustments for you.</span></span> <span data-ttu-id="55178-121">Ad esempio, se la struttura contiene dati numerici e l'algoritmo può funzionare solo con valori discreti, i valori numerici verranno automaticamente raggruppati in intervalli discreti.</span><span class="sxs-lookup"><span data-stu-id="55178-121">For example, if your structure contains numeric data, and the algorithm can only work with discrete values, it will group the numeric values into discrete ranges for you.</span></span> <span data-ttu-id="55178-122">In alcuni casi, potrebbe essere necessario correggere prima i dati manualmente, scegliendo una chiave o un attributo stimabile.</span><span class="sxs-lookup"><span data-stu-id="55178-122">In some cases, you might need to manually fix the data first, by choosing a key or choosing a predictable attribute.</span></span>  
  
 <span data-ttu-id="55178-123">Non è necessario modificare l'algoritmo quando si crea un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="55178-123">You do not need to change the algorithm when you create a new model.</span></span> <span data-ttu-id="55178-124">Spesso con lo stesso algoritmo si possono ottenere risultati molto diversi, ma occorre applicare un filtro ai dati o modificare un parametro come il metodo di clustering o le dimensioni minime del set di elementi.</span><span class="sxs-lookup"><span data-stu-id="55178-124">Often you can get very different results by using the same algorithm, but filtering the data, or changing a parameter such as the clustering method or the minimum itemset size.</span></span> <span data-ttu-id="55178-125">È consigliabile provare a utilizzare più modelli per individuare i parametri che consentono di ottenere risultati migliori.</span><span class="sxs-lookup"><span data-stu-id="55178-125">We recommend that you experiment with multiple models to see which parameters produce the best results.</span></span>  
  
 <span data-ttu-id="55178-126">Si noti che tutti i nuovi modelli devono essere elaborati prima di poterli utilizzare.</span><span class="sxs-lookup"><span data-stu-id="55178-126">Note that all new models need to be processed before you can use them.</span></span>  
  
## <a name="specifying-the-usage-of-columns-in-a-new-mining-model"></a><span data-ttu-id="55178-127">Specifica dell'utilizzo di colonne in un nuovo modello di data mining</span><span class="sxs-lookup"><span data-stu-id="55178-127">Specifying the Usage of Columns in a New Mining Model</span></span>  
 <span data-ttu-id="55178-128">Quando si aggiungono nuovi modelli di data mining a una struttura di data mining esistente, è necessario specificare come ciascuna colonna di dati dovrà essere utilizzata dal modello.</span><span class="sxs-lookup"><span data-stu-id="55178-128">When you add new mining models to an existing mining structure, you must specify how each column of data should be used by the model.</span></span> <span data-ttu-id="55178-129">A seconda del tipo di algoritmo scelto per il modello, è possibile che alcune scelte siano effettuate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="55178-129">Depending on the type of algorithm you choose for the model, some of these choices may be made by default.</span></span> <span data-ttu-id="55178-130">Le colonne di cui non si specifica la modalità di utilizzo non vengono incluse nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-130">If you do not specify a usage type for a column, the column will not be included in the mining structure.</span></span> <span data-ttu-id="55178-131">Tuttavia, i dati nella colonna possono essere ancora disponibili per il drill-through, se è supportato dal modello.</span><span class="sxs-lookup"><span data-stu-id="55178-131">However, the data in the column can still be available for drillthrough, if the model supports it.</span></span>  
  
 <span data-ttu-id="55178-132">Le colonne della struttura di data mining utilizzate dal modello (se non impostate su Ignora) devono essere una chiave, una colonna di input, una colonna stimabile o una colonna stimabile i cui valori vengono anche utilizzati come input nel modello.</span><span class="sxs-lookup"><span data-stu-id="55178-132">Columns from the mining structure that are used by the model (if not set to Ignore) must be a key, an input column, a predictable column, or a predictable column the values of which are also used as inputs to the model.</span></span>  
  
-   <span data-ttu-id="55178-133">Le colonne chiave contengono l'identificatore univoco di ogni riga di una tabella.</span><span class="sxs-lookup"><span data-stu-id="55178-133">Key columns contain a unique identifier for each row in a table.</span></span> <span data-ttu-id="55178-134">Alcuni modelli di data mining, ad esempio quelli basati sul clustering delle sequenze o gli algoritmi Time Series, possono includere più colonne chiave.</span><span class="sxs-lookup"><span data-stu-id="55178-134">Some mining models, such as those based on the sequence clustering or time series algorithms, can contain multiple key columns.</span></span> <span data-ttu-id="55178-135">Queste chiavi tuttavia non sono chiavi composte nel senso relazionale, ma devono essere selezionate per supportare l'analisi delle serie temporali e del clustering delle sequenze.</span><span class="sxs-lookup"><span data-stu-id="55178-135">However, these multiple keys are not compound keys in the relational sense, but instead must be selected so as to provide support for time series and sequence clustering analysis.</span></span>  
  
-   <span data-ttu-id="55178-136">Le colonne di input contengono informazioni per l'esecuzione di stime.</span><span class="sxs-lookup"><span data-stu-id="55178-136">Input columns provide the information from which predictions are made.</span></span> <span data-ttu-id="55178-137">Nella Creazione guidata modello di data mining è disponibile la funzionalità **Suggerisci** , che risulta abilitata quando si seleziona una colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="55178-137">The Data Mining Wizard provides the **Suggest** feature, which is enabled when you select a predictable column.</span></span> <span data-ttu-id="55178-138">Se si fa clic su questo pulsante, nella procedura guidata verranno campionati i valori stimabili e verrà determinato quali altre colonne della struttura possono fungere da variabili.</span><span class="sxs-lookup"><span data-stu-id="55178-138">If you click this button, the wizard will sample the predictable values and determine which of the other columns in the structure make good variables.</span></span> <span data-ttu-id="55178-139">Verranno rifiutate le colonne chiave o altre colonne con molti valori univoci e verranno suggerite le colonne che risultano essere correlate con il risultato.</span><span class="sxs-lookup"><span data-stu-id="55178-139">It will reject key columns or other columns with many unique values, and suggest columns that appear to be correlated with the outcome.</span></span>  
  
     <span data-ttu-id="55178-140">Questa funzionalità è particolarmente utile quando i set di dati contengono un numero di colonne più elevato di quanto sia necessario per compilare un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-140">This feature is particularly handy when datasets contain more columns than you really need to build a mining model.</span></span> <span data-ttu-id="55178-141">La funzionalità **Suggerisci** calcola un valore numerico compreso tra 0 e 1 che descrive la relazione tra ogni colonna del set di dati e la colonna stimabile.</span><span class="sxs-lookup"><span data-stu-id="55178-141">The **Suggest** feature calculates a numeric score, from 0 to 1, that describes the relationship between each column in the dataset and the predictable column.</span></span> <span data-ttu-id="55178-142">In base a questo valore vengono indicate le colonne da utilizzare come input per il modello.</span><span class="sxs-lookup"><span data-stu-id="55178-142">Based on this score, the feature suggests columns to use as input for the mining model.</span></span> <span data-ttu-id="55178-143">Se si utilizza la funzionalità **Suggerisci** , è possibile utilizzare la selezione di colonne indicate, modificare la selezione in base alle specifiche esigenze o ignorare la selezione di colonne suggerita.</span><span class="sxs-lookup"><span data-stu-id="55178-143">If you use the **Suggest** feature, you can use the suggested columns, modify the selections to fit your needs, or ignore the suggestions.</span></span>  
  
-   <span data-ttu-id="55178-144">Le colonne stimabili contengono le informazioni che vengono stimate nel modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="55178-144">Predictable columns contain the information that you try to predict in the mining model.</span></span> <span data-ttu-id="55178-145">È possibile selezionare più colonne come attributi stimabili.</span><span class="sxs-lookup"><span data-stu-id="55178-145">You can select multiple columns as the predictable attributes.</span></span> <span data-ttu-id="55178-146">I modelli di clustering costituiscono un'eccezione in quanto un attributo stimabile è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="55178-146">Clustering models are the exception in that a predictable attribute is optional.</span></span>  
  
     <span data-ttu-id="55178-147">A seconda del tipo di modello, può essere necessario che la colonna stimabile sia un tipo di dati specifico: ad esempio un modello di regressione lineare richiede una colonna numerica come valore stimato; l'algoritmo Naive Bayes richiede un valore discreto (anche tutti gli input devono essere discreti).</span><span class="sxs-lookup"><span data-stu-id="55178-147">Depending on the model type, the predictable column might need to be a specific data type: for example, a linear regression model requires a numeric column as the predicted value; Naïve Bayes algorithm requires a discrete value (and all the inputs must be discrete as well).</span></span>  
  
## <a name="specifying-column-content"></a><span data-ttu-id="55178-148">Specifica del contenuto delle colonne</span><span class="sxs-lookup"><span data-stu-id="55178-148">Specifying Column Content</span></span>  
 <span data-ttu-id="55178-149">In alcuni casi può anche essere necessario specificare il *contenuto della colonna*.</span><span class="sxs-lookup"><span data-stu-id="55178-149">For some columns, you might also need to specify the *column content*.</span></span> <span data-ttu-id="55178-150">Nel data mining di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la proprietà Tipo di contenuto di ogni colonna di dati indica all'algoritmo come devono essere elaborati i dati in tale colonna.</span><span class="sxs-lookup"><span data-stu-id="55178-150">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data mining, the Content Type property of each data columns tells the algorithm how it should process the data in that column.</span></span> <span data-ttu-id="55178-151">Se ad esempio i dati includono una colonna Income, è necessario specificare che la colonna contiene numeri continui impostando il tipo di contenuto su Continuous.</span><span class="sxs-lookup"><span data-stu-id="55178-151">For example, if your data has an Income column, you must specify that the column contains continuous numbers by setting the content type to Continuous.</span></span> <span data-ttu-id="55178-152">Tuttavia, è anche possibile specificare che i numeri della colonna Income devono essere raggruppati in bucket impostando il tipo di contenuto su Discretized e, se si desidera, specificando il numero esatto di bucket.</span><span class="sxs-lookup"><span data-stu-id="55178-152">However, you could also specify that the numbers in the Income column be grouped into buckets by setting the content type to Discretized and optionally specifying the exact number of buckets.</span></span> <span data-ttu-id="55178-153">È possibile creare modelli diversi che gestiscono le colonne in modo diverso. Ad esempio, è possibile provare con un modello che raggruppa i clienti in tre bucket di età e un altro che li raggruppa in 10 bucket di età.</span><span class="sxs-lookup"><span data-stu-id="55178-153">You can create different models that handle columns differently: for example, you might try one model that buckets customers into three age groups, and another model that buckets customers into 10 age groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55178-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55178-154">See Also</span></span>  
 <span data-ttu-id="55178-155">[Strutture di data mining &#40;Analysis Services-&#41;di data mining](mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="55178-155">[Mining Structures &#40;Analysis Services - Data Mining&#41;](mining-structures-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="55178-156">[Creare una struttura di data mining relazionale](create-a-relational-mining-structure.md) </span><span class="sxs-lookup"><span data-stu-id="55178-156">[Create a Relational Mining Structure](create-a-relational-mining-structure.md) </span></span>  
 <span data-ttu-id="55178-157">[Proprietà modello di data mining](mining-model-properties.md) </span><span class="sxs-lookup"><span data-stu-id="55178-157">[Mining Model Properties](mining-model-properties.md) </span></span>  
 [<span data-ttu-id="55178-158">Colonne del modello di data mining</span><span class="sxs-lookup"><span data-stu-id="55178-158">Mining Model Columns</span></span>](mining-model-columns.md)  
  
  