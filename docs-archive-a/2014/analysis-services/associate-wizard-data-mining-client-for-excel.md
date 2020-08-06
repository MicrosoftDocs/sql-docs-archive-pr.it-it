---
title: Procedura guidata associazione (client di data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- nested tables, in association models
- association [data mining]
ms.assetid: 4db6462f-93c7-443f-8ff7-39474dc7029e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 73ce4bbedb710de1ded149a12f6f9b83f0b92a11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625883"
---
# <a name="associate-wizard-data-mining-client-for-excel"></a><span data-ttu-id="39516-102">Procedura guidata Associazione (client di data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="39516-102">Associate Wizard (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="39516-103">![Procedura guidata Associazione sulla barra multifunzione Data mining](media/dmc-associate.gif "Procedura guidata Associazione sulla barra multifunzione Data mining")</span><span class="sxs-lookup"><span data-stu-id="39516-103">![Associate wizard in Data Mining ribbon](media/dmc-associate.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="39516-104">La procedura guidata Associazione consente di creare un modello di data mining utilizzando l'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules.</span><span class="sxs-lookup"><span data-stu-id="39516-104">The Associate wizard helps you create a data mining model using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm.</span></span> <span data-ttu-id="39516-105">Questi modelli di data mining sono particolarmente utili per la creazione di *sistemi di raccomandazione*.</span><span class="sxs-lookup"><span data-stu-id="39516-105">Such mining models are particularly useful for creating *recommendation systems*.</span></span>  
  
 <span data-ttu-id="39516-106">L'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules esegue l'analisi di un set di dati costituito da transazioni o eventi e trova le combinazioni che sono di frequente abbinate.</span><span class="sxs-lookup"><span data-stu-id="39516-106">How it works is that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm scans a dataset comprised of transactions or events, and finds the combinations that frequently appear together.</span></span> <span data-ttu-id="39516-107">Potrebbero esistere molte migliaia di combinazioni, ma l'algoritmo può essere personalizzato per trovarne di più o di meno e conservare solo le combinazioni più probabili.</span><span class="sxs-lookup"><span data-stu-id="39516-107">There can be many thousand combinations, but the algorithm can be customized to find more or fewer, and to retain only the most probable combinations.</span></span>  
  
 <span data-ttu-id="39516-108">È possibile applicare l'analisi di associazione a molti problemi.</span><span class="sxs-lookup"><span data-stu-id="39516-108">You can apply association analysis to many problems.</span></span> <span data-ttu-id="39516-109">L'applicazione più comune di questo metodo è Market basket analysis, che trova singoli prodotti acquistati spesso insieme.</span><span class="sxs-lookup"><span data-stu-id="39516-109">The most popular application of this method is market basket analysis, which finds individual products that are often purchased together.</span></span> <span data-ttu-id="39516-110">È quindi possibile utilizzare tali informazioni per consigliare prodotti ai clienti in base agli elementi che hanno già acquistato.</span><span class="sxs-lookup"><span data-stu-id="39516-110">You can then use that information to recommend products to customers based on items they have already bought.</span></span>  
  
## <a name="using-the-associate-wizard"></a><span data-ttu-id="39516-111">Utilizzo della procedura guidata Associazione</span><span class="sxs-lookup"><span data-stu-id="39516-111">Using the Associate Wizard</span></span>  
  
1.  <span data-ttu-id="39516-112">Sulla barra multifunzione **data mining** fare clic su **associa**.</span><span class="sxs-lookup"><span data-stu-id="39516-112">In the **Data Mining** ribbon, click **Associate**.</span></span>  
  
2.  <span data-ttu-id="39516-113">Nella pagina **selezione dati di origine** scegliere una tabella o un intervallo di dati di Excel e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="39516-113">On the **Select Source Data** page, choose an Excel table or data range, and click **Next**.</span></span>  
  
     <span data-ttu-id="39516-114">La cartella di lavoro dei dati di esempio contiene un esempio, nella scheda Associazione, di come i dati delle transazioni vengono in genere disposti se, ad esempio, sono presenti più prodotti in ogni transazione o più record di acquisto per ogni cliente che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="39516-114">The sample data workbook contains an example, in the Associate tab, of how transaction data is typically arranged if, for example, you have multiple products in each transaction or multiple purchasing records per customer that you want to analyze.</span></span>  
  
     <span data-ttu-id="39516-115">Se si desidera utilizzare dati esterni per compilare un modello di associazione utilizzando la procedura guidata associazione, è prima necessario aggiungere i dati a Excel e rendere *Flat* i dati.</span><span class="sxs-lookup"><span data-stu-id="39516-115">If you want to use external data to build an association model using the Associate wizard, you must add the data to Excel first, and *flatten* the data.</span></span> <span data-ttu-id="39516-116">Per ulteriori informazioni sulla preparazione dei dati per la modellazione dell'associazione, vedere [tabelle nidificate &#40;Analysis Services-Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), in documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="39516-116">For more information about preparing data for association modeling, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md), in SQL Server Books Online.</span></span>  
  
3.  <span data-ttu-id="39516-117">Nella pagina **associazione** scegliere la colonna che identifica la transazione.</span><span class="sxs-lookup"><span data-stu-id="39516-117">On the **Association** page, choose the column that identifies the transaction.</span></span>  
  
     <span data-ttu-id="39516-118">Per i modelli Market Basket, questo identificatore rappresenta l'unità che si desidera modellare.</span><span class="sxs-lookup"><span data-stu-id="39516-118">For market basket models, this identifier represents the unit you want to model.</span></span> <span data-ttu-id="39516-119">Si desidera analizzare gli elementi che singoli clienti hanno acquistato nel corso del tempo o si desidera analizzare molte transazioni che interessano più clienti?</span><span class="sxs-lookup"><span data-stu-id="39516-119">Do you want to analyze items that individual customers have purchased over time, or do you want to analyze many transactions involving multiple customers?</span></span> <span data-ttu-id="39516-120">Nel primo caso, scegliere l'ID cliente; nel secondo caso, scegliere l'ordine di acquisto o un altro ID transazione</span><span class="sxs-lookup"><span data-stu-id="39516-120">In the first case, you would choose the customer ID; in the latter you would choose the purchase order or other transaction ID.</span></span>  
  
4.  <span data-ttu-id="39516-121">Per **elemento**selezionare la colonna che contiene gli elementi tra cui è necessario trovare le associazioni.</span><span class="sxs-lookup"><span data-stu-id="39516-121">For **Item**, select the column that contains the things among which you need to find associations.</span></span>  
  
     <span data-ttu-id="39516-122">Ad esempio, in un modello Market Basket, scegliere un campo dei prodotti per analizzare i prodotti acquistati spesso insieme.</span><span class="sxs-lookup"><span data-stu-id="39516-122">For example, in a market basket model, you would choose a products field, to analyze which products are often purchased together.</span></span> <span data-ttu-id="39516-123">Se è presente un numero di singoli prodotti troppo elevato per garantire un'efficiente correlazione, è possibile scegliere un campo relativo a una categoria o sottocategoria di prodotto.</span><span class="sxs-lookup"><span data-stu-id="39516-123">If there are too many individual products to correlate them effectively, you might choose a product category or subcategory field.</span></span>  
  
5.  <span data-ttu-id="39516-124">Nelle **soglie**è possibile impostare valori che controllano o influiscono sull'output del modello:</span><span class="sxs-lookup"><span data-stu-id="39516-124">In **Thresholds**, you can set values that control or affect the output of the model:</span></span>  
  
    -   <span data-ttu-id="39516-125">**Supporto minimo.**</span><span class="sxs-lookup"><span data-stu-id="39516-125">**Minimum support.**</span></span> <span data-ttu-id="39516-126">Specifica il numero di volte che un gruppo di elementi deve essere presente per essere considerato importante.</span><span class="sxs-lookup"><span data-stu-id="39516-126">Specifies how many times a group of items must appear to be considered important.</span></span> <span data-ttu-id="39516-127">Verranno ignorate dall'algoritmo tutte le eventuali combinazioni di elementi che non soddisfano questo criterio.</span><span class="sxs-lookup"><span data-stu-id="39516-127">The algorithm will ignore any item combinations that do not meet this criterion.</span></span> <span data-ttu-id="39516-128">Ad esempio, potrebbe essere necessario visualizzare solo i set di elementi in cui gli elementi risultavano abbinati almeno 10 volte complessivamente.</span><span class="sxs-lookup"><span data-stu-id="39516-128">For example, you might want to see only itemsets where the items appeared together at least 10 times overall.</span></span>  
  
    -   <span data-ttu-id="39516-129">**Probabilità della regola minima**.</span><span class="sxs-lookup"><span data-stu-id="39516-129">**Minimum rule probability**.</span></span> <span data-ttu-id="39516-130">Specifica il valore di probabilità minima richiesto per il salvataggio di una regola.</span><span class="sxs-lookup"><span data-stu-id="39516-130">Specifies the minimum probability value required for a rule to be saved.</span></span> <span data-ttu-id="39516-131">L'intero set di dati viene analizzato per trovare tutte le combinazioni e quindi viene calcolata la probabilità.</span><span class="sxs-lookup"><span data-stu-id="39516-131">The entire data set is analyzed to find all combinations, and then probability is calculated.</span></span> <span data-ttu-id="39516-132">Se si imposta un valore di soglia basso, la procedura guidata potrebbe associare elementi con correlazioni deboli.</span><span class="sxs-lookup"><span data-stu-id="39516-132">If the threshold is low, the wizard may associate items that are only loosely correlated.</span></span> <span data-ttu-id="39516-133">Se il valore di soglia è troppo alto, invece, alcune associazioni potrebbero essere omesse a causa di dati di supporto insufficienti.</span><span class="sxs-lookup"><span data-stu-id="39516-133">If the threshold is too high, some associations may be omitted because they do not have enough supporting data.</span></span>  
  
     <span data-ttu-id="39516-134">In generale, la modifica di questi valori ha gli effetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="39516-134">In general, changing these values has the following effects:</span></span>  
  
    -   <span data-ttu-id="39516-135">Diminuendo il valore di supporto, aumenta il numero di combinazioni individuate.</span><span class="sxs-lookup"><span data-stu-id="39516-135">As you lower the value for support, you increase the number of combinations that are found.</span></span>  
  
    -   <span data-ttu-id="39516-136">Diminuendo il supporto massimo, vengono esclusi tramite filtro gli elementi con una frequenza di occorrenza elevata e pertanto poco significativi.</span><span class="sxs-lookup"><span data-stu-id="39516-136">As you decrease the maximum support, you filter out items that occur so often that they have little meaning.</span></span>  
  
    -   <span data-ttu-id="39516-137">Diminuendo la probabilità di una regola, si riducono i requisiti che una combinazione deve soddisfare per essere considerata importante nel contesto del set di dati complessivo.</span><span class="sxs-lookup"><span data-stu-id="39516-137">As you lower the probability of a rule, you lower the requirements that a combination must meet to be considered important in the context of the total data set.</span></span>  
  
     <span data-ttu-id="39516-138">**Suggerimento:** È consigliabile creare più modelli di data mining utilizzando combinazioni diverse di supporto e probabilità.</span><span class="sxs-lookup"><span data-stu-id="39516-138">**Tip:** It is a good idea to create multiple mining models using different combinations of support and probability.</span></span> <span data-ttu-id="39516-139">Per tenere traccia delle impostazioni utilizzate per ogni modello, è possibile utilizzare la procedura guidata **modello di documento** , disponibile nel client di data mining per Excel, e utilizzare l'opzione report **dettagliato** .</span><span class="sxs-lookup"><span data-stu-id="39516-139">To track which settings you used for each model, you can use the **Document Model** wizard, available in the Data Mining Client for Excel, and use the **Detailed** report option.</span></span> <span data-ttu-id="39516-140">Per ulteriori informazioni, vedere la documentazione relativa ai [modelli di data mining &#40;componenti aggiuntivi Data mining per Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="39516-140">For more information, see [Documenting Mining Models &#40;Data Mining Add-ins for Excel&#41;](documenting-mining-models-data-mining-add-ins-for-excel.md).</span></span>  
  
6.  <span data-ttu-id="39516-141">Facoltativamente, fare clic su **parametri** per modificare i parametri dell'algoritmo e personalizzare il comportamento del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="39516-141">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="39516-142">La finestra di dialogo Parametri algoritmo include tutti i parametri impostati nella procedura guidata, nonché alcuni utilizzati meno di frequente, ad esempio MAXIMUM_SUPPORT.</span><span class="sxs-lookup"><span data-stu-id="39516-142">The Algorithm Parameters dialog box includes all of the parameters you set in the wizard, plus a few that are less commonly used, such as MAXIMUM_SUPPORT.</span></span> <span data-ttu-id="39516-143">Per informazioni sull'utilizzo di questi parametri, vedere [riferimento tecnico per l'algoritmo Microsoft Association](data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="39516-143">For information about how to use these parameters, see [Microsoft Association Algorithm Technical Reference](data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
7.  <span data-ttu-id="39516-144">Nella pagina **fine** Digitare un nome univoco per il set di dati e il modello.</span><span class="sxs-lookup"><span data-stu-id="39516-144">On the **Finish** page, type a unique name for the data set and the model.</span></span>  
  
8.  <span data-ttu-id="39516-145">In **Opzioni**è possibile definire il modo in cui si desidera utilizzare il modello dopo che è stato completato:</span><span class="sxs-lookup"><span data-stu-id="39516-145">In **Options**, you define how you want to work with the model after it is completed:</span></span>  
  
    -   <span data-ttu-id="39516-146">**Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="39516-146">**Browse**.</span></span>  <span data-ttu-id="39516-147">Quando il modello è pronto, tramite la procedura guidata viene aperta una finestra nella quale vengono visualizzati le regole, i set di elementi e un grafico della rete di dipendenze che illustra le associazioni.</span><span class="sxs-lookup"><span data-stu-id="39516-147">When the model is ready, the wizard opens a window that displays the rules, the itemsets, and a dependency network graph that depicts associations.</span></span>  
  
         <span data-ttu-id="39516-148">Per ulteriori informazioni su come interpretare i dati nel Visualizzatore modello di associazione, vedere [esplorazione di un modello Association Rules](browsing-an-association-rules-model.md).</span><span class="sxs-lookup"><span data-stu-id="39516-148">For more information about how to interpret the data in the association model viewer, see [Browsing an Association Rules Model](browsing-an-association-rules-model.md).</span></span>  
  
    -   <span data-ttu-id="39516-149">**Abilitare il drill-through**.</span><span class="sxs-lookup"><span data-stu-id="39516-149">**Enable drillthrough**.</span></span> <span data-ttu-id="39516-150">Selezionare questa opzione per accedere ai dati sottostanti, tramite il modello.</span><span class="sxs-lookup"><span data-stu-id="39516-150">Select this option to gain access to the underlying data, via the model.</span></span>  
  
         <span data-ttu-id="39516-151">Il drill-through è utile, ad esempio, se si desidera fare clic su un set di elementi specifico e visualizzare i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="39516-151">Drillthrough is useful, for example, if you want to click on a particular itemset and see the source data.</span></span>  
  
    -   <span data-ttu-id="39516-152">**Usa modello temporaneo**.</span><span class="sxs-lookup"><span data-stu-id="39516-152">**Use temporary model**.</span></span> <span data-ttu-id="39516-153">Selezionare questa opzione se non si desidera che il modello venga salvato nel server.</span><span class="sxs-lookup"><span data-stu-id="39516-153">Select this option if you don't want the model saved on the server.</span></span> <span data-ttu-id="39516-154">I modelli temporanei vengono eliminati quando si chiude Excel.</span><span class="sxs-lookup"><span data-stu-id="39516-154">Temporary models are deleted when you close Excel.</span></span>  
  
9. <span data-ttu-id="39516-155">Tramite la procedura guidata vengono analizzate tutte le possibili combinazioni e viene creato un report contenente i set di elementi e le regole.</span><span class="sxs-lookup"><span data-stu-id="39516-155">The wizard analyzes all possible combinations and creates a report that contains the itemsets and rules.</span></span>  
  
## <a name="more-about-association-models"></a><span data-ttu-id="39516-156">Ulteriori informazioni sui modelli di associazione</span><span class="sxs-lookup"><span data-stu-id="39516-156">More About Association Models</span></span>  
 <span data-ttu-id="39516-157">L'algoritmo [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules esamina il set di dati di training per individuare gli elementi che compaiono insieme in una transazione.</span><span class="sxs-lookup"><span data-stu-id="39516-157">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Association Rules algorithm examines the training data to find items that appear together in a transaction.</span></span> <span data-ttu-id="39516-158">Ogni gruppo di elementi costituisce un *set di elementi*.</span><span class="sxs-lookup"><span data-stu-id="39516-158">Each group of items constitutes an *itemset*.</span></span> <span data-ttu-id="39516-159">Tramite l'algoritmo viene quindi contato quante volte è presente ogni set di elementi e viene calcolata l'importanza relativa di ogni set di elementi in tutte le transazioni.</span><span class="sxs-lookup"><span data-stu-id="39516-159">The algorithm then counts the number of times each itemset appears and calculates the relative importance of each itemset across all transactions.</span></span>  
  
 <span data-ttu-id="39516-160">L'algoritmo utilizza queste informazioni sui set di elementi per generare regole che possono essere utilizzate per stimare associazioni o generare indicazioni.</span><span class="sxs-lookup"><span data-stu-id="39516-160">The algorithm uses this information about itemsets to generate rules that can be used to predict associations or make recommendations.</span></span> <span data-ttu-id="39516-161">Una regola potrebbe ad esempio indicare che se l'utente ha acquistato un libro di Autore 1 e un libro di Autore 2, è probabile che acquisti anche un libro di Autore 3.</span><span class="sxs-lookup"><span data-stu-id="39516-161">For example, a rule could be "if the user purchased a book by Author 1 and a book by Author 2, then it is likely that the user will also purchase a book by Author 3".</span></span> <span data-ttu-id="39516-162">A ogni indicazione viene assegnata una probabilità basata sul livello di attendibilità delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="39516-162">Each recommendation is assigned a probability, based on the strength of the associations.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="39516-163">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39516-163">Requirements</span></span>  
 <span data-ttu-id="39516-164">Per utilizzare la procedura guidata Associazione, è necessario disporre di una connessione a un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39516-164">To use the Associate wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="39516-165">I dati di origine devono essere organizzati come una tabella di transazioni</span><span class="sxs-lookup"><span data-stu-id="39516-165">Your source data must be organized as a transaction table.</span></span> <span data-ttu-id="39516-166">e includere una colonna che contiene l'identificatore della transazione.</span><span class="sxs-lookup"><span data-stu-id="39516-166">The source data must contain one column that contains the transaction identifier.</span></span> <span data-ttu-id="39516-167">Tale colonna consente di identificare ogni gruppo di elementi.</span><span class="sxs-lookup"><span data-stu-id="39516-167">This column identifies each group of items.</span></span> <span data-ttu-id="39516-168">La colonna delle transazioni deve essere collegata con una relazione uno-a-molti a una seconda colonna contenente l'ID degli elementi, nella quale vengono archiviati i nomi o i numeri di ID dei singoli elementi nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="39516-168">That transaction column must be in a one-to-many relationship with a second column, the item ID, which stores names or ID numbers for the individual items in the group.</span></span>  
  
 <span data-ttu-id="39516-169">Per chiarire questi concetti può essere utile ricorrere all'esempio di un carrello acquisti.</span><span class="sxs-lookup"><span data-stu-id="39516-169">Conceptually, this might be easiest to understand by recalling the shopping cart example.</span></span> <span data-ttu-id="39516-170">Se si assegna un ID al carrello acquisti, l'ID del carrello acquisti funge da identificatore della transazione.</span><span class="sxs-lookup"><span data-stu-id="39516-170">If the shopping cart is assigned an ID, the shopping cart ID serves as the identifier for the transaction.</span></span> <span data-ttu-id="39516-171">Ogni elemento nel carrello acquisti, ad esempio un libro o un DVD, è un membro della transazione.</span><span class="sxs-lookup"><span data-stu-id="39516-171">Each item in the shopping cart, such as potatoes or milk, is a member of that transaction.</span></span> <span data-ttu-id="39516-172">L'algoritmo di associazione consente di esaminare gli elementi in più transazioni, ad esempio per individuare il numero di occorrenze degli elementi libro e DVD all'interno di una singola transazione.</span><span class="sxs-lookup"><span data-stu-id="39516-172">The Associate algorithm can track items across transactions: for example, to determine how many times potatoes and milk appear within any single transaction.</span></span>  
  
 <span data-ttu-id="39516-173">I dati di origine devono essere ordinati in base alla colonna di identificazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="39516-173">Your source data must be sorted by the transaction identifier column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39516-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39516-174">See Also</span></span>  
 <span data-ttu-id="39516-175">[Creazione di un modello di data mining](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="39516-175">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="39516-176">[Esplorazione di un modello Association Rules](browsing-an-association-rules-model.md) </span><span class="sxs-lookup"><span data-stu-id="39516-176">[Browsing an Association Rules Model](browsing-an-association-rules-model.md) </span></span>  
 <span data-ttu-id="39516-177">[Shopping Basket Analysis &#40;Table AnalysisTools per Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="39516-177">[Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;](shopping-basket-analysis-table-analysistools-for-excel.md) </span></span>  
 [<span data-ttu-id="39516-178">Diagramma della rete di dipendenze procedura dettagliata &#40;componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="39516-178">Dependency Network Diagram Walkthrough &#40;Data Mining Add-ins&#41;</span></span>](dependency-network-diagram-walkthrough-data-mining-add-ins.md)  
  
  