---
title: Colonne calcolate (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e1011278-556d-4984-b01d-a37f8a33b304
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5d77b36ee3327d1b9e0d31ac97e5dbe135093a63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711032"
---
# <a name="calculated-columns-ssas-tabular"></a><span data-ttu-id="686b3-102">Colonne calcolate (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="686b3-102">Calculated Columns (SSAS Tabular)</span></span>
  <span data-ttu-id="686b3-103">Nei modelli tabulari, le colonne calcolate consentono all'utente di aggiungere nuovi dati al modello.</span><span class="sxs-lookup"><span data-stu-id="686b3-103">Calculated columns, in tabular models, allow you to add new data to your model.</span></span> <span data-ttu-id="686b3-104">Anziché incollare o importare i valori nella colonna, viene creata una formula DAX che definisce i valori a livello di riga della colonna.</span><span class="sxs-lookup"><span data-stu-id="686b3-104">Instead of pasting or importing values into the column, you create a DAX formula that defines the column's row level values.</span></span> <span data-ttu-id="686b3-105">La colonna calcolata può quindi essere utilizzata in un report, in una tabella pivot o in un grafico pivot come qualsiasi altra colonna.</span><span class="sxs-lookup"><span data-stu-id="686b3-105">The calculated column can then be used in a report, PivotTable, or PivotChart as would any other column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="686b3-106">Le colonne calcolate non sono supportate per i modelli tabulari in modalità DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="686b3-106">Calculated columns are not supported for tabular models in DirectQuery mode.</span></span> <span data-ttu-id="686b3-107">Per altre informazioni, vedere [Modalità DirectQuery &#40;SSAS tabulare&#41;](directquery-mode-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="686b3-107">For more information, see [DirectQuery Mode &#40;SSAS Tabular&#41;](directquery-mode-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="686b3-108">Sezioni dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="686b3-108">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="686b3-109">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="686b3-109">Benefits</span></span>](#bkmk_understanding)  
  
-   [<span data-ttu-id="686b3-110">Denominazione di una colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="686b3-110">Naming a Calculated Column</span></span>](#bkmk_naming)  
  
-   [<span data-ttu-id="686b3-111">Prestazioni delle colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="686b3-111">Performance of Calculated Columns</span></span>](#bkmk_perf)  
  
-   [<span data-ttu-id="686b3-112">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="686b3-112">Related Tasks</span></span>](#bkmk_rel_tasks)  
  
##  <a name="benefits"></a><a name="bkmk_understanding"></a> <span data-ttu-id="686b3-113">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="686b3-113">Benefits</span></span>  
 <span data-ttu-id="686b3-114">Le formule nelle colonne calcolate sono molto simili a quelle in Excel.</span><span class="sxs-lookup"><span data-stu-id="686b3-114">Formulas in calculated columns are much like formulas in Excel.</span></span> <span data-ttu-id="686b3-115">A differenza di Excel tuttavia, non è possibile creare formule diverse per le diverse righe di una tabella, infatti la formula DAX viene applicata automaticamente a tutta la colonna.</span><span class="sxs-lookup"><span data-stu-id="686b3-115">Unlike Excel, however, you cannot create different formulas for different rows in a table; instead, the DAX formula is automatically applied to the entire column.</span></span>  
  
 <span data-ttu-id="686b3-116">Se in una colonna è contenuta una formula, il valore viene calcolato per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="686b3-116">When a column contains a formula, the value is computed for each row.</span></span> <span data-ttu-id="686b3-117">I risultati vengono calcolati per la colonna quando si immette una formula valida.</span><span class="sxs-lookup"><span data-stu-id="686b3-117">The results are calculated for the column when you enter a valid formula.</span></span> <span data-ttu-id="686b3-118">I valori della colonna vengono quindi ricalcolati se necessario, ad esempio quando vengono aggiornati i dati sottostanti.</span><span class="sxs-lookup"><span data-stu-id="686b3-118">Column values are then recalculated as necessary, such as when the underlying data is refreshed.</span></span>  
  
 <span data-ttu-id="686b3-119">È possibile creare colonne calcolate basate su misure e su altre colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="686b3-119">You can create calculated columns that are based on measures and other calculated columns.</span></span> <span data-ttu-id="686b3-120">È ad esempio possibile creare una colonna calcolata per estrarre un numero da una stringa di testo, quindi utilizzare tale numero in un'altra colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="686b3-120">For example, you might create one calculated column to extract a number from a string of text, and then use that number in another calculated column.</span></span>  
  
 <span data-ttu-id="686b3-121">Una colonna calcolata è basata sui dati già presenti in una tabella esistente o creati tramite una formula DAX.</span><span class="sxs-lookup"><span data-stu-id="686b3-121">A calculated column is based on data that you already have in an existing table, or created by using a DAX formula.</span></span> <span data-ttu-id="686b3-122">Ad esempio, è possibile scegliere di concatenare valori, di effettuare un'aggiunta, di estrarre sottostringhe o di confrontare i valori in altri campi.</span><span class="sxs-lookup"><span data-stu-id="686b3-122">For example, you might choose to concatenate values, perform addition, extract substrings, or compare the values in other fields.</span></span> <span data-ttu-id="686b3-123">Per aggiungere una colonna calcolata, è necessario disporre già di almeno una tabella nel modello.</span><span class="sxs-lookup"><span data-stu-id="686b3-123">To add a calculated column, you must have at least one table in your model.</span></span>  
  
 <span data-ttu-id="686b3-124">In questo esempio viene dimostrata una semplice formula in una colonna calcolata:</span><span class="sxs-lookup"><span data-stu-id="686b3-124">This example demonstrates a simple formula in a calculated column:</span></span>  
  
```  
=EOMONTH([StartDate],0])  
  
```  
  
 <span data-ttu-id="686b3-125">Questa formula consente di estrarre il mese dalla colonna StartDate.</span><span class="sxs-lookup"><span data-stu-id="686b3-125">This formula extracts the month from the StartDate column.</span></span> <span data-ttu-id="686b3-126">Successivamente viene calcolato il valore di fine mese per ogni riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="686b3-126">It then calculates the end of the month value for each row in the table.</span></span> <span data-ttu-id="686b3-127">Il secondo parametro consente di specificare il numero di mesi precedenti o successivi al mese indicato in StartDate; in questo caso, 0 indica che si tratta dello stesso mese.</span><span class="sxs-lookup"><span data-stu-id="686b3-127">The second parameter specifies the number of months before or after the month in StartDate; in this case, 0 means the same month.</span></span> <span data-ttu-id="686b3-128">Ad esempio, se il valore nella colonna StartDate è 01/06/2001, il valore nella colonna calcolata sarà 30/06/2001.</span><span class="sxs-lookup"><span data-stu-id="686b3-128">For example, if the value in the StartDate column is 6/1/2001, the value in the calculated column will be 6/30/2001.</span></span>  
  
##  <a name="naming-a-calculated-column"></a><a name="bkmk_naming"></a><span data-ttu-id="686b3-129">Denominazione di una colonna calcolata</span><span class="sxs-lookup"><span data-stu-id="686b3-129">Naming a Calculated Column</span></span>  
 <span data-ttu-id="686b3-130">Per impostazione predefinita, le nuove colonne calcolate vengono aggiunte a destra delle altre colonne in una tabella e alla colonna viene assegnato automaticamente il nome predefinito **CalculatedColumn1**, **CalculatedColumn2**e così via.</span><span class="sxs-lookup"><span data-stu-id="686b3-130">By default, new calculated columns are added to the right of other columns in a table, and the column is automatically assigned the default name of **CalculatedColumn1**, **CalculatedColumn2**, and so forth.</span></span> <span data-ttu-id="686b3-131">Per creare una nuova colonna tra due esistenti è anche possibile fare clic con il pulsante destro del mouse su una colonna e, successivamente, selezionare Inserisci colonna.</span><span class="sxs-lookup"><span data-stu-id="686b3-131">You can also right click a column, and then click Insert Column to create a new column between two existing columns.</span></span> <span data-ttu-id="686b3-132">Le colonne possono essere ridisposte all'interno della stessa tabella facendo clic su di esse e trascinandole, nonché rinominate dopo la relativa creazione; tuttavia, è consigliabile tenere presente le seguenti restrizioni relative alla modifica delle colonne calcolate:</span><span class="sxs-lookup"><span data-stu-id="686b3-132">You can rearrange columns within the same table by clicking and dragging, and you can rename columns after they are created; however, you should be aware of the following restrictions on changes to calculated columns:</span></span>  
  
-   <span data-ttu-id="686b3-133">Ogni nome di colonna deve essere univoco all'interno di una tabella.</span><span class="sxs-lookup"><span data-stu-id="686b3-133">Each column name must be unique within a table.</span></span>  
  
-   <span data-ttu-id="686b3-134">Evitare nomi che sono già stati utilizzati per le misure all'interno dello stesso modello.</span><span class="sxs-lookup"><span data-stu-id="686b3-134">Avoid names that have already been used for measures within the same model.</span></span> <span data-ttu-id="686b3-135">Anche se una misura e una colonna calcolata possono avere lo stesso nome, se i nomi non sono univoci si possono facilmente verificare errori di calcolo.</span><span class="sxs-lookup"><span data-stu-id="686b3-135">Although it is possible for a measure and a calculated column to have the same name, if names are not unique you can get calculation errors.</span></span> <span data-ttu-id="686b3-136">Per evitare di richiamare casualmente una misura, quando si fa riferimento a una colonna è meglio utilizzare sempre un riferimento alla colonna completo.</span><span class="sxs-lookup"><span data-stu-id="686b3-136">To avoid accidentally invoking a measure, when referring to a column always use a fully qualified column reference.</span></span>  
  
-   <span data-ttu-id="686b3-137">Quando si rinomina una colonna calcolata, è necessario aggiornare tutte le formule basate sulla colonna manualmente.</span><span class="sxs-lookup"><span data-stu-id="686b3-137">When you rename a calculated column, any formulas that rely on the column must be updated manually.</span></span> <span data-ttu-id="686b3-138">A meno che non si tratti di una modalità di aggiornamento manuale, l'aggiornamento dei risultati delle formule viene eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="686b3-138">Unless you are in manual update mode, updating the results of formulas takes place automatically.</span></span> <span data-ttu-id="686b3-139">Tuttavia, questa operazione potrebbe richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="686b3-139">However, this operation might take some time.</span></span>  
  
-   <span data-ttu-id="686b3-140">Vi sono determinati caratteri che non possono essere utilizzati all'interno dei nomi di colonne.</span><span class="sxs-lookup"><span data-stu-id="686b3-140">There are some characters that cannot be used within the names of columns.</span></span> <span data-ttu-id="686b3-141">Per altre informazioni, vedere "Requisiti per la denominazione" in [Specifica della sintassi DAX per PowerPivot](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="686b3-141">For more information, see "Naming Requirements" in [DAX Syntax Specification for PowerPivot](/dax/dax-syntax-reference).</span></span>  
  
##  <a name="performance-of-calculated-columns"></a><a name="bkmk_perf"></a><span data-ttu-id="686b3-142">Prestazioni delle colonne calcolate</span><span class="sxs-lookup"><span data-stu-id="686b3-142">Performance of Calculated Columns</span></span>  
 <span data-ttu-id="686b3-143">La formula per una colonna calcolata può richiedere un maggior numero di risorse rispetto alla formula utilizzata per una misura,</span><span class="sxs-lookup"><span data-stu-id="686b3-143">The formula for a calculated column can be more resource-intensive than the formula used for a measure.</span></span> <span data-ttu-id="686b3-144">poiché, ad esempio, il risultato di una colonna calcolata viene calcolato sempre per ogni riga di una tabella, mentre una misura viene calcolata solo per le celle definite dal filtro utilizzato in un report, in una tabella pivot o in un grafico pivot.</span><span class="sxs-lookup"><span data-stu-id="686b3-144">One reason is that the result for a calculated column is always calculated for each row in a table, whereas a measure is only calculated for the cells defined by the filter used in a report, PivotTable, or PivotChart.</span></span> <span data-ttu-id="686b3-145">In una tabella con un milione di righe, ad esempio, sarà sempre presente una colonna calcolata con un milione di risultati con conseguente effetto sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="686b3-145">For example, a table with a million rows will always have a calculated column with a million results, and a corresponding effect on performance.</span></span> <span data-ttu-id="686b3-146">Una tabella pivot, invece, consente in genere di filtrare i dati applicando le intestazioni di riga e colonna. Una misura viene pertanto calcolata solo per il subset di dati presente in ogni cella della tabella pivot.</span><span class="sxs-lookup"><span data-stu-id="686b3-146">However, a PivotTable generally filters data by applying row and column headings; therefore, a measure is calculated only for the subset of data in each cell of the PivotTable.</span></span>  
  
 <span data-ttu-id="686b3-147">Una formula dipende dagli oggetti a cui fa riferimento, quali altre colonne o espressioni che valutano i valori.</span><span class="sxs-lookup"><span data-stu-id="686b3-147">A formula has dependencies on the objects that are referenced in the formula, such as other columns or expressions that evaluate values.</span></span> <span data-ttu-id="686b3-148">Ad esempio, una colonna calcolata basata su un'altra colonna o un calcolo che contiene un'espressione con un riferimento a una colonna non può pertanto essere valutato fino a quando non viene valutata l'altra colonna.</span><span class="sxs-lookup"><span data-stu-id="686b3-148">For example, a calculated column that is based on another column, or a calculation that contains an expression with a column reference, cannot be evaluated until the other column is evaluated.</span></span> <span data-ttu-id="686b3-149">Per impostazione predefinita, l'aggiornamento automatico è abilitato nelle cartelle di lavoro; pertanto, tutte queste dipendenze possono influire sulle prestazioni mentre le formule e i valori vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="686b3-149">By default, automatic refresh is enabled in workbooks; therefore, all such dependencies can affect performance while values are updated and formulas refreshed.</span></span>  
  
 <span data-ttu-id="686b3-150">Per evitare problemi di prestazioni quando si creano colonne calcolate, seguire queste linee guida:</span><span class="sxs-lookup"><span data-stu-id="686b3-150">To avoid performance issues when you create calculated columns, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="686b3-151">Anziché creare una sola formula contenente più dipendenze complesse, creare le formule in passaggi, salvando i risultati nelle colonne in modo che sia possibile convalidarli e valutare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="686b3-151">Rather than create a single formula that contains many complex dependencies, create the formulas in steps, with results saved to columns, so that you can validate the results and assess performance.</span></span>  
  
-   <span data-ttu-id="686b3-152">La modifica dei dati comporta spesso il ricalcolo delle colonne calcolate.</span><span class="sxs-lookup"><span data-stu-id="686b3-152">Modification of data will often require that calculated columns be recalculated.</span></span> <span data-ttu-id="686b3-153">È possibile impedire questo comportamento impostando la modalità di ricalcolo manuale. Tuttavia, se i valori nella colonna calcolata non sono corretti, la colonna verrà disattivata fino a quando non si aggiornano e si ricalcolano i dati.</span><span class="sxs-lookup"><span data-stu-id="686b3-153">You can prevent this by setting the recalculation mode to manual; however, if any values in the calculated column are incorrect the column will be grayed out until you refresh and recalculate the data.</span></span>  
  
-   <span data-ttu-id="686b3-154">Se si modificano o si eliminano relazioni tra tabelle, le formule per le quali vengono utilizzate le colonne di tali tabelle non saranno più valide.</span><span class="sxs-lookup"><span data-stu-id="686b3-154">If you change or delete relationships between tables, formulas that use columns in those tables will become invalid.</span></span>  
  
-   <span data-ttu-id="686b3-155">Se si crea una formula contenente una dipendenza circolare o autoreferenziale, si verificherà un errore.</span><span class="sxs-lookup"><span data-stu-id="686b3-155">If you create a formula that contains a circular or self-referencing dependency, an error will occur.</span></span>  
  
##  <a name="related-tasks"></a><a name="bkmk_rel_tasks"></a> <span data-ttu-id="686b3-156">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="686b3-156">Related Tasks</span></span>  
  
|<span data-ttu-id="686b3-157">Argomento</span><span class="sxs-lookup"><span data-stu-id="686b3-157">Topic</span></span>|<span data-ttu-id="686b3-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="686b3-158">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="686b3-159">Creare una colonna calcolata &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="686b3-159">Create a Calculated Column &#40;SSAS Tabular&#41;</span></span>](ssas-calculated-columns-create-a-calculated-column.md)|<span data-ttu-id="686b3-160">Nelle attività di questo argomento viene descritto come aggiungere una nuova colonna calcolata a una tabella.</span><span class="sxs-lookup"><span data-stu-id="686b3-160">Tasks in this topic describe how to add a new calculated column to a table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="686b3-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="686b3-161">See Also</span></span>  
 <span data-ttu-id="686b3-162">[Tabelle e colonne &#40;SSAS tabulare&#41;](tables-and-columns-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="686b3-162">[Tables and Columns &#40;SSAS Tabular&#41;](tables-and-columns-ssas-tabular.md) </span></span>  
 <span data-ttu-id="686b3-163">[Misure &#40;SSAS tabulare&#41;](measures-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="686b3-163">[Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="686b3-164">Calcoli &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="686b3-164">Calculations &#40;SSAS Tabular&#41;</span></span>](calculations-ssas-tabular.md)  
  
  