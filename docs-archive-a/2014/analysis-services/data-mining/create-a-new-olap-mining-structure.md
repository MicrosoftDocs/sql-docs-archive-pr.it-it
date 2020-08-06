---
title: Creazione di una nuova struttura di data mining OLAP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], OLAP
- mining structures [Analysis Services], creating
- OLAP [Analysis Services], mining models
ms.assetid: 368f4273-a016-4748-bcb6-505a3e745af3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2851fe6180254b129471c442297c419fd594e123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711147"
---
# <a name="create-a-new-olap-mining-structure"></a><span data-ttu-id="78cea-102">Creare una nuova struttura di data mining OLAP</span><span class="sxs-lookup"><span data-stu-id="78cea-102">Create a New OLAP Mining Structure</span></span>
  <span data-ttu-id="78cea-103">È possibile utilizzare la creazione guidata modello di data mining in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per creare una struttura di data mining che utilizza i dati di un modello multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="78cea-103">You can use the Data Mining Wizard in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create a mining structure that uses data from a multidimensional model.</span></span> <span data-ttu-id="78cea-104">I modelli di data mining basati su cubi OLAP possono utilizzare la colonna e i valori di tabelle dei fatti, dimensioni e gruppi di misure come attributi per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-104">Mining models that are based on OLAP cubes can use the column and values in fact tables, dimensions, and measure groups as attributes for analysis.</span></span>  
  
### <a name="to-create-a-new-olap-mining-structure"></a><span data-ttu-id="78cea-105">Per creare una nuova struttura di data mining OLAP</span><span class="sxs-lookup"><span data-stu-id="78cea-105">To create a new OLAP mining structure</span></span>  
  
1.  <span data-ttu-id="78cea-106">In Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla cartella **Strutture di data mining** in un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , quindi scegliere **Nuova struttura di data mining** per aprire la Creazione guidata modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-106">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure** to open the Data Mining Wizard.</span></span>  
  
2.  <span data-ttu-id="78cea-107">Nella pagina iniziale **Creazione guidata modello di data mining** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="78cea-108">Nella pagina **Selezione metodo di definizione** selezionare **Da cubo esistente**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-108">On the **Select the Definition Method** page, select **From existing cube**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="78cea-109">Se si riceve il messaggio di errore Impossibile recuperare un elenco degli algoritmi di data mining supportati, aprire la finestra di dialogo **Proprietà progetto** e verificare di avere specificato il nome di un'istanza di Analysis Services che supporta i modelli multidimensionali.</span><span class="sxs-lookup"><span data-stu-id="78cea-109">If you get an error with the message, Unable to retrieve a list of supported data mining algorithms, open the **Project Properties** dialog box and verify that you have specified the name of an Analysis Services instance that supports multidimensional models.</span></span> <span data-ttu-id="78cea-110">Non è possibile creare modelli di data mining in un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che supporta la modellazione tabulare.</span><span class="sxs-lookup"><span data-stu-id="78cea-110">You cannot create mining models on an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that supports tabular modeling.</span></span>  
  
4.  <span data-ttu-id="78cea-111">Nella pagina **Crea la struttura di data mining** scegliere se creare solo una struttura di data mining o una struttura di data mining e un modello di data mining correlato.</span><span class="sxs-lookup"><span data-stu-id="78cea-111">On the **Create the Data Mining Structure** page, decide whether you will create a mining structure only, or a mining structure plus one related mining model.</span></span> <span data-ttu-id="78cea-112">È in genere più facile creare contemporaneamente un modello di data mining in modo da ricevere le richieste di includere le colonne necessarie.</span><span class="sxs-lookup"><span data-stu-id="78cea-112">Generally it is easier to create a mining model at the same time, so that you can be prompted to include necessary columns.</span></span>  
  
     <span data-ttu-id="78cea-113">Se si crea un modello di data mining, selezionare l'algoritmo di data mining da usare, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-113">If you will create a mining model, select the data mining algorithm that you want to use, and then click **Next**.</span></span> <span data-ttu-id="78cea-114">Per altre informazioni su come scegliere un algoritmo, vedere [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="78cea-114">For more information about how to choose an algorithm, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="78cea-115">Nella pagina **Selezione dimensione cubo di origine** , in **Selezionare una dimensione del cubo di origine**, trovare la dimensione che contiene la maggior parte dei dati del case.</span><span class="sxs-lookup"><span data-stu-id="78cea-115">On the **Select the Source Cube Dimension** page, under **Select a Source Cube Dimension**, locate the dimension that contains the majority of your case data.</span></span>  
  
     <span data-ttu-id="78cea-116">Se ad esempio si tenta di identificare i raggruppamenti del cliente, è possibile scegliere la dimensione Customer, se si tenta di analizzare gli acquisti nelle transazioni, è possibile scegliere la dimensione Dettagli ordine vendita Internet.</span><span class="sxs-lookup"><span data-stu-id="78cea-116">For example, if you are trying to identify customer groupings, you might choose the Customer dimension; if you are trying to analyze purchases across transactions, you might choose the Internet Sales Order Details dimension.</span></span> <span data-ttu-id="78cea-117">Non si è limitati all'utilizzo dei soli dati di questa dimensione, tuttavia dovrebbe contenere attributi importanti per l'utilizzo nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-117">You are not restricted to using only the data in this dimension, but it should contain important attributes to use in analysis.</span></span>  
  
     <span data-ttu-id="78cea-118">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="78cea-119">Nella pagina **Selezione chiave del case** , in **Attributi**, selezionare l'attributo che costituirà la chiave della struttura di data mining, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-119">On the **Select the Case Key** page, under **Attributes**, select the attribute that will be the key of the mining structure, and then click **Next**.</span></span>  
  
     <span data-ttu-id="78cea-120">In genere, l'attributo utilizzato come chiave per la struttura di data mining è anche una chiave per la dimensione e risulterà pre-selezionata.</span><span class="sxs-lookup"><span data-stu-id="78cea-120">Typically the attribute that you use as key for the mining structure is also a key for the dimension and will be pre-selected.</span></span>  
  
7.  <span data-ttu-id="78cea-121">Nella pagina **Selezione colonne livello case** , in **Attributi e misure correlati**, selezionare gli attributi e le misure che contengono i valori da aggiungere alla struttura di data mining come dati del case.</span><span class="sxs-lookup"><span data-stu-id="78cea-121">On the **Select Case Level Columns** page, under **Related Attributes and Measures**, select the attributes and measures that contain values you want to add to the mining structure as case data.</span></span> <span data-ttu-id="78cea-122">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-122">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="78cea-123">Nella pagina **Impostazione utilizzo colonne modello di data mining** , in **Struttura modello di data mining**, impostare la colonna stimabile, quindi scegliere le colonne da usare come input.</span><span class="sxs-lookup"><span data-stu-id="78cea-123">On the **Specify Mining Model Column Usage** page, under **Mining model structure**, first set the predictable column, and then choose columns to use as inputs.</span></span>  
  
    -   <span data-ttu-id="78cea-124">Selezionare la casella di controllo nella colonna più a sinistra per includere i dati nella struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-124">Select the checkbox in the leftmost column to include the data in the mining structure.</span></span> <span data-ttu-id="78cea-125">È possibile includere le colonne nella struttura che verranno utilizzate come riferimento, ma non per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-125">You can include columns in the structure that you will use for reference, but not use them for analysis.</span></span>  
  
    -   <span data-ttu-id="78cea-126">Selezionare la casella di controllo nella colonna **Input** per usare l'attributo come variabile nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-126">Select the checkbox in the **Input** column to use the attribute as a variable in analysis.</span></span>  
  
    -   <span data-ttu-id="78cea-127">Selezionare la casella di controllo nella colonna **Stima** solo per gli attributi stimabili.</span><span class="sxs-lookup"><span data-stu-id="78cea-127">Select the checkbox in the **Predict** column only for predictable attributes.</span></span>  
  
     <span data-ttu-id="78cea-128">Si noti che colonne definite come chiavi non possono essere utilizzate per l'input o la stima.</span><span class="sxs-lookup"><span data-stu-id="78cea-128">Note that columns you have designated as keys cannot be used for input or prediction.</span></span>  
  
     <span data-ttu-id="78cea-129">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-129">Click **Next**.</span></span>  
  
9. <span data-ttu-id="78cea-130">Nella pagina **Impostazione utilizzo colonne modello di data mining** è anche possibile aggiungere e rimuovere le tabelle annidate dalla struttura di data mining, usando **Aggiungi tabelle annidate** e **Tabelle annidate**.</span><span class="sxs-lookup"><span data-stu-id="78cea-130">On the **Specify Mining Model Column Usage** page, you can also add and remove nested tables to the mining structure, using **Add Nested Tables** and **Nested Tables**.</span></span>  
  
     <span data-ttu-id="78cea-131">In un modello di data mining OLAP, una tabella nidificata è un altro set di dati all'interno del cubo che presenta una relazione uno-a-molti con la dimensione che rappresenta gli attributi del case.</span><span class="sxs-lookup"><span data-stu-id="78cea-131">In an OLAP mining model, a nested table is another set of data within the cube that has a one-to-many relationship with the dimension that represents the case attributes.</span></span> <span data-ttu-id="78cea-132">Di conseguenza, quando viene visualizzata la finestra di dialogo, i gruppi di misure già correlati alla dimensione selezionata come tabella del case vengono preselezionati.</span><span class="sxs-lookup"><span data-stu-id="78cea-132">Therefore, when the dialog box opens, it pre-selects measure groups that are already related to the dimension you selected as the case table.</span></span> <span data-ttu-id="78cea-133">A questo punto, si dovrebbe scegliere una dimensione diversa che contenga informazioni aggiuntive utili per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-133">At this point, you would choose a different dimension that contains additional information useful for analysis.</span></span>  
  
     <span data-ttu-id="78cea-134">Ad esempio, se si analizzano i clienti, si dovrebbe usare la dimensione [Customer] come tabella del case.</span><span class="sxs-lookup"><span data-stu-id="78cea-134">For example, if you are analyzing customers, you would use the [Customer] dimension as the case table.</span></span> <span data-ttu-id="78cea-135">Per la tabella annidata, è possibile aggiungere il motivo indicato dai clienti al momento di un acquisto, incluso nella dimensione [Sales Reason].</span><span class="sxs-lookup"><span data-stu-id="78cea-135">For the nested table, you might add the reason customers cited when making a purchase, which is included in the [Sales Reason] dimension.</span></span>  
  
     <span data-ttu-id="78cea-136">Se si aggiungono dati nidificati, è necessario specificare due colonne aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="78cea-136">If you add nested data, you must specify two additional columns:</span></span>  
  
    -   <span data-ttu-id="78cea-137">Chiave della tabella annidata: deve essere preselezionata nella pagina **Selezione chiave tabella annidata**.</span><span class="sxs-lookup"><span data-stu-id="78cea-137">The key of the nested table: This should be pre-selected on the page, **Select Nested Table Key**.</span></span>  
  
    -   <span data-ttu-id="78cea-138">Attributi o attributi da usare per l'analisi: nella pagina **Selezione colonne tabella annidata**è contenuto un elenco delle misure e degli attributi nella selezione della tabella annidata.</span><span class="sxs-lookup"><span data-stu-id="78cea-138">The attributes or attributes to use for analysis: The page, **Select Nested Table Columns**, provides a list of measures and attributes in the nested table selection.</span></span>  
  
        -   <span data-ttu-id="78cea-139">Per ogni attributo incluso nel modello, selezionare la casella nella colonna sinistra.</span><span class="sxs-lookup"><span data-stu-id="78cea-139">For each attribute that you include in the model, check the box in the left column.</span></span>  
  
        -   <span data-ttu-id="78cea-140">Se si desidera usare l'attributo solo per l'analisi, selezionare **Input**.</span><span class="sxs-lookup"><span data-stu-id="78cea-140">If you want to use the attribute for analysis only, check **Input**.</span></span>  
  
        -   <span data-ttu-id="78cea-141">Se si desidera includere la colonna come uno degli attributi stimabili per il modello, selezionare **Stima**.</span><span class="sxs-lookup"><span data-stu-id="78cea-141">If you want to include the column as one of the predictable attributes for the model, select **Predict**.</span></span>  
  
        -   <span data-ttu-id="78cea-142">Qualsiasi elemento incluso nella struttura, ma non specificato come un input o attributo stimabile viene aggiunto alla struttura con il flag `Ignore`. Ciò significa che i dati vengono elaborati quando si compila il modello, ma non vengono utilizzati nell'analisi e sono disponibili solo per il drill-through.</span><span class="sxs-lookup"><span data-stu-id="78cea-142">Any item that you include in the structure but do not specify as an input or predictable attribute is added to the structure with the flag `Ignore`; this means that the data is processed when you build the model but is not used in analysis, and is available only for drillthrough.</span></span> <span data-ttu-id="78cea-143">Questa operazione può essere utile se si desidera includere dettagli come i nomi dei clienti, ma non si desidera utilizzarli nell'analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-143">This can be handy if you want to include details such as customer names but don't want to use them in analysis.</span></span>  
  
     <span data-ttu-id="78cea-144">Fare clic su **Fine** per chiudere la parte della procedura guidata correlata alle tabelle annidate.</span><span class="sxs-lookup"><span data-stu-id="78cea-144">Click **Finish** to close the part of the wizard that works with nested tables.</span></span> <span data-ttu-id="78cea-145">È possibile ripetere il processo per aggiungere più colonne nidificate.</span><span class="sxs-lookup"><span data-stu-id="78cea-145">You can repeat the process to add multiple nested columns.</span></span>  
  
10. <span data-ttu-id="78cea-146">Nella pagina **Impostazione tipo di contenuto e dati delle colonne** , in **Struttura modello di data mining**, impostare il tipo di contenuto e il tipo di dati per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="78cea-146">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, set the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78cea-147">I modelli di data mining OLAP non supportano l'uso della caratteristica **Rileva** per rilevare automaticamente se una colonna contiene dati continui o discreti.</span><span class="sxs-lookup"><span data-stu-id="78cea-147">OLAP mining models do not support using the **Detect** feature to automatically detect whether a column contains continuous or discrete data.</span></span>  
  
     <span data-ttu-id="78cea-148">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-148">Click **Next**.</span></span>  
  
11. <span data-ttu-id="78cea-149">Nella pagina **Sezionamento cubo di origine** è possibile filtrare i dati usati per creare la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-149">On the **Slice Source Cube** page, you can filter the data that is used to create the mining structure.</span></span>  
  
     <span data-ttu-id="78cea-150">Sezionando il cubo si limitano i dati utilizzati per la compilazione del modello.</span><span class="sxs-lookup"><span data-stu-id="78cea-150">Slicing the cube lets you restrict the data that is used to build the model.</span></span> <span data-ttu-id="78cea-151">È ad esempio possibile compilare modelli separati per ogni area sezionando in base alla gerarchia Geography e</span><span class="sxs-lookup"><span data-stu-id="78cea-151">For example, you could build separate models for each region by slicing on the Geography hierarchy and</span></span>  
  
    -   <span data-ttu-id="78cea-152">**Dimensione**: scegliere una dimensione correlata dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="78cea-152">**Dimension**: Choose a related dimension from the dropdown list.</span></span>  
  
    -   <span data-ttu-id="78cea-153">**Gerarchia**: selezionare il livello della gerarchia di dimensione al quale si desidera applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="78cea-153">**Hierarchy**:  Select the level of the dimension hierarchy at which you want to apply the filter.</span></span> <span data-ttu-id="78cea-154">Ad esempio, se si seziona in base alla dimensione [Geography], è necessario scegliere un livello di gerarchia come [Region Country Name].</span><span class="sxs-lookup"><span data-stu-id="78cea-154">For example, if you are slicing by the [Geography] dimension, you would choose a hierarchy level such as [Region Country Name] .</span></span>  
  
    -   <span data-ttu-id="78cea-155">**Operatore**: scegliere un operatore dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="78cea-155">**Operator**: Choose an operator from the list.</span></span>  
  
    -   <span data-ttu-id="78cea-156">**Espressione filtro**: digitare un valore o un'espressione da usare come condizione di filtro oppure usare l'elenco a discesa per selezionare un valore dall'elenco dei membri al livello specificato della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="78cea-156">**Filter Expression**: Type a value or expression to serve as the filter condition, or use the dropdown list to select a value from the list of members at the specified level of the hierarchy.</span></span>  
  
         <span data-ttu-id="78cea-157">Se, ad esempio, si è selezionato [Geography] come dimensione e [Region Country Name] come livello della gerarchia, l'elenco a discesa contiene tutti i paesi o le aree geografiche validi che è possibile utilizzare come condizione di filtro.</span><span class="sxs-lookup"><span data-stu-id="78cea-157">For example, if you selected [Geography] as the dimension and [Region Country Name] as the hierarchy level, the dropdown list contains all the valid countries/regions that you can use as a filter condition.</span></span> <span data-ttu-id="78cea-158">È possibile effettuare più selezioni.</span><span class="sxs-lookup"><span data-stu-id="78cea-158">You can make multiple selections.</span></span> <span data-ttu-id="78cea-159">Di conseguenza, i dati nella struttura di data mining saranno limitati ai dati del cubo da queste aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="78cea-159">As a result, the data in the mining structure will be limited to cube data from these geographical areas.</span></span>  
  
    -   <span data-ttu-id="78cea-160">**Parametri**: ignorare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="78cea-160">**Parameters**: Ignore this check box.</span></span> <span data-ttu-id="78cea-161">Questa finestra di dialogo supporta più scenari di applicazione filtri del cubo e questa opzione non è attinente alla compilazione di una struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-161">This dialog box supports multiple cube filtering scenarios and this option is not relevant to building a mining structure.</span></span>  
  
     <span data-ttu-id="78cea-162">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-162">Click **Next**.</span></span>  
  
12. <span data-ttu-id="78cea-163">Nella pagina **Divisione dei dati in set di training e in set di testing** specificare la percentuale di dati della struttura di data mining da riservare al test oppure specificare il numero massimo di test case.</span><span class="sxs-lookup"><span data-stu-id="78cea-163">On the **Split data into training and testing sets** page, specify a percentage of the mining structure data to reserve for testing, or specify the maximum number of test cases.</span></span> <span data-ttu-id="78cea-164">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="78cea-164">Click **Next**.</span></span>  
  
     <span data-ttu-id="78cea-165">Se si specificano entrambi valori, i limiti vengono combinati per utilizzare quello più basso.</span><span class="sxs-lookup"><span data-stu-id="78cea-165">If you specify both values, the limits are combined to use whichever is lowest.</span></span>  
  
13. <span data-ttu-id="78cea-166">Nella pagina **Completamento procedura guidata** specificare un nome per la nuova struttura di data mining OLAP e per il modello di data mining iniziale.</span><span class="sxs-lookup"><span data-stu-id="78cea-166">On the **Completing the Wizard** page, provide a name for the new OLAP mining structure and the initial mining model.</span></span>  
  
14. <span data-ttu-id="78cea-167">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="78cea-167">Click **Finish**.</span></span>  
  
15. <span data-ttu-id="78cea-168">Nella pagina **Completamento procedura guidata** è anche disponibile l'opzione per creare una dimensione del modello di data mining e/o un cubo usando la dimensione del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-168">On the **Completing the Wizard** page, you also have the option to create a mining model dimension and/or a cube using the mining model dimension.</span></span> <span data-ttu-id="78cea-169">Queste opzioni sono supportate solo per i modelli compilati utilizzando gli algoritmi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78cea-169">These options are supported only for models built using the following algorithms:</span></span>  
  
    -   <span data-ttu-id="78cea-170">Algoritmo Microsoft Clustering</span><span class="sxs-lookup"><span data-stu-id="78cea-170">Microsoft Clustering algorithm</span></span>  
  
    -   <span data-ttu-id="78cea-171">Algoritmo Microsoft Decision Trees</span><span class="sxs-lookup"><span data-stu-id="78cea-171">Microsoft Decision Trees algorithm</span></span>  
  
    -   <span data-ttu-id="78cea-172">Algoritmo Microsoft Association Rules</span><span class="sxs-lookup"><span data-stu-id="78cea-172">Microsoft Association Rules algorithm</span></span>  
  
     <span data-ttu-id="78cea-173">**Crea dimensione del modello di data mining**: selezionare questa casella di controllo e specificare un tipo per la dimensione del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-173">**Create mining model dimension**: Select this check box and provide a type name for the mining model dimension.</span></span> <span data-ttu-id="78cea-174">Quando si utilizza questa opzione, viene creata una nuova dimensione all'interno del cubo originale utilizzato per compilare la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="78cea-174">When you use this option, a new dimension is created within the original cube that was used to build the mining structure.</span></span> <span data-ttu-id="78cea-175">È possibile utilizzare questa dimensione per eseguire il drill-down ed effettuare ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="78cea-175">You can use this dimension to drill down and conduct further analysis.</span></span> <span data-ttu-id="78cea-176">Poiché si trova all'interno del cubo, viene automaticamente eseguito il mapping della dimensione alla dimensione dei dati del case.</span><span class="sxs-lookup"><span data-stu-id="78cea-176">Because the dimension is located within the cube, the dimension is automatically mapped to the case data dimension.</span></span>  
  
     <span data-ttu-id="78cea-177">**Crea il cubo utilizzando la dimensione del modello di data mining**: selezionare questa casella di controllo e specificare un nome per il nuovo cubo.</span><span class="sxs-lookup"><span data-stu-id="78cea-177">**Create cube using mining model dimension**: Select this check box, and provide a name for the new cube.</span></span> <span data-ttu-id="78cea-178">Quando si utilizza questa opzione, viene creato un nuovo cubo contenente sia le dimensioni esistenti utilizzate nella compilazione della struttura sia la nuova dimensione di data mining contenente i risultati del modello.</span><span class="sxs-lookup"><span data-stu-id="78cea-178">When you use this option, a new cube is created that contains both the existing dimensions that were used in building the structure, and the new data mining dimension that contains the results from the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78cea-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78cea-179">See Also</span></span>  
 [<span data-ttu-id="78cea-180">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="78cea-180">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  