---
title: Impostazione della proprietà Slice della partizione (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 08/05/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- partitions [Analysis Services], data slices
- data slices [Analysis Services]
ms.assetid: 507b91e5-7f85-4c22-be97-4d7a676e6667
author: minewiskan
ms.author: owend
ms.openlocfilehash: f42c4536b99ba3fecf9b947942b881a3be72784f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635227"
---
# <a name="set-the-partition-slice-property-analysis-services"></a><span data-ttu-id="9a20d-102">Impostare la proprietà Slice delle partizioni (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="9a20d-102">Set the Partition Slice Property (Analysis Services)</span></span>
  <span data-ttu-id="9a20d-103">Una sezione di dati è una funzionalità di ottimizzazione importante che semplifica l'indirizzamento delle query sui dati delle partizioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="9a20d-103">A data slice is an important optimization feature that helps direct queries to the data of the appropriate partitions.</span></span> <span data-ttu-id="9a20d-104">Impostare in modo esplicito la proprietà Slice può migliorare le prestazioni delle query tramite l'override delle sezioni predefinite generate per le partizioni MOLAP e HOLAP.</span><span class="sxs-lookup"><span data-stu-id="9a20d-104">Explicitly setting the Slice property can improve query performance by overriding default slices generated for MOLAP and HOLAP partitions.</span></span> <span data-ttu-id="9a20d-105">Inoltre, la proprietà Slice offre un ulteriore controllo di convalida durante l'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="9a20d-105">Additionally, the Slice property provides an extra validation check when processing the partition.</span></span>  
  
 <span data-ttu-id="9a20d-106">È possibile specificare una sezione di dati dopo avere creato una partizione, ma prima di elaborarla, utilizzando la proprietà Slice.</span><span class="sxs-lookup"><span data-stu-id="9a20d-106">You can specify a data slice after you create a partition, but before processing it, using the Slice property.</span></span> <span data-ttu-id="9a20d-107">Nella scheda Partizioni espandere un gruppo di misure, fare clic con il pulsante destro del mouse su una partizione e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9a20d-107">On the Partitions tab, expand a measure group, right-click a partition, and select **Properties**.</span></span>  
  
## <a name="defining-a-slice"></a><span data-ttu-id="9a20d-108">Definizione di una proprietà Slice</span><span class="sxs-lookup"><span data-stu-id="9a20d-108">Defining a Slice</span></span>  
 <span data-ttu-id="9a20d-109">I valori validi per una proprietà Slice sono un membro, un set o una tupla MDX.</span><span class="sxs-lookup"><span data-stu-id="9a20d-109">Valid values for a slice property are an MDX member, set, or tuple.</span></span> <span data-ttu-id="9a20d-110">Negli esempi seguenti viene illustrata la sintassi valida per la proprietà Slice:</span><span class="sxs-lookup"><span data-stu-id="9a20d-110">The following examples illustrate valid slice syntax:</span></span>  
  
|<span data-ttu-id="9a20d-111">Sezione</span><span class="sxs-lookup"><span data-stu-id="9a20d-111">Slice</span></span>|<span data-ttu-id="9a20d-112">Membro, set o tupla</span><span class="sxs-lookup"><span data-stu-id="9a20d-112">Member, set or tuple</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="9a20d-113">[Date].[Calendar].[Calendar Year].&[2010]</span><span class="sxs-lookup"><span data-stu-id="9a20d-113">[Date].[Calendar].[Calendar Year].&[2010]</span></span>|<span data-ttu-id="9a20d-114">Specificare questa sezione in una partizione contenente i fatti dall'anno 2010 (supponendo che il modello includa una dimensione Date con la gerarchia Calendar Year, dove 2010 è un membro).</span><span class="sxs-lookup"><span data-stu-id="9a20d-114">Specify this slice on a partition containing facts from year 2010 (assuming the model includes a Date dimension with Calendar Year hierarchy, where 2010 is a member).</span></span> <span data-ttu-id="9a20d-115">Sebbene la clausola WHERE o la tabella di origine della partizione possa già prevedere il filtraggio in base all'anno 2010, la specificazione della proprietà Slice fornisce un ulteriore controllo durante l'elaborazione, nonché analisi maggiormente mirate durante l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="9a20d-115">Although the partition source WHERE clause or table might already filter by 2010, specifying the Slice provides an additional check during processing, as well as more targeted scans during query execution.</span></span>|  
|<span data-ttu-id="9a20d-116">{ [Sales Territory].[Sales Territory Country].&[Australia], [Sales Territory].[Sales Territory Country].&[Canada] }</span><span class="sxs-lookup"><span data-stu-id="9a20d-116">{ [Sales Territory].[Sales Territory Country].&[Australia], [Sales Territory].[Sales Territory Country].&[Canada] }</span></span>|<span data-ttu-id="9a20d-117">Specificare questa sezione in una partizione contenente i fatti che includono informazioni sui territori di vendita.</span><span class="sxs-lookup"><span data-stu-id="9a20d-117">Specify this slice on a partition containing facts that include sales territory information.</span></span> <span data-ttu-id="9a20d-118">Una sezione può essere un set MDX costituito da due o più membri.</span><span class="sxs-lookup"><span data-stu-id="9a20d-118">A slice can be an MDX set consisting of two or more members.</span></span>|  
|<span data-ttu-id="9a20d-119">[Measures].[Sales Amount Quota] > '5000'</span><span class="sxs-lookup"><span data-stu-id="9a20d-119">[Measures].[Sales Amount Quota] > '5000'</span></span>|<span data-ttu-id="9a20d-120">Per questa sezione viene utilizzata un'espressione MDX.</span><span class="sxs-lookup"><span data-stu-id="9a20d-120">This slice shows an MDX expression.</span></span>|  
  
 <span data-ttu-id="9a20d-121">Una sezione di dati di una partizione deve riflettere quanto più accuratamente possibile i dati della partizione.</span><span class="sxs-lookup"><span data-stu-id="9a20d-121">A data slice of a partition should reflect, as closely as possible, the data in the partition.</span></span> <span data-ttu-id="9a20d-122">Se ad esempio una partizione contiene solo i dati relativi al 2012, la sezione di dati corrispondente deve specificare il membro 2012 della dimensione temporale.</span><span class="sxs-lookup"><span data-stu-id="9a20d-122">For example, if a partition is limited to 2012 data, the partition's data slice should specify the 2012 member of the Time dimension.</span></span> <span data-ttu-id="9a20d-123">Non è tuttavia possibile specificare sempre una sezione di dati che rifletta il contenuto esatto di una partizione.</span><span class="sxs-lookup"><span data-stu-id="9a20d-123">It is not always possible to specify a data slice that reflects the exact contents of a partition.</span></span> <span data-ttu-id="9a20d-124">Se ad esempio una partizione contiene solo i dati relativi ai mesi di gennaio e febbraio ma i livelli della dimensione temporale sono Anno, Trimestre e Mese, nella Creazione guidata partizione non è possibile selezionare entrambi i membri Gennaio e Febbraio.</span><span class="sxs-lookup"><span data-stu-id="9a20d-124">For example, if a partition contains data for only January and February, but the levels of the Time dimension are Year, Quarter, and Month, the Partition Wizard cannot select both the January and February members.</span></span> <span data-ttu-id="9a20d-125">In tali casi, selezionare il padre dei membri che riflettono il contenuto della partizione,</span><span class="sxs-lookup"><span data-stu-id="9a20d-125">In such cases, select the parent of the members that reflect the partition's contents.</span></span> <span data-ttu-id="9a20d-126">che in questo esempio è Trimestre 1.</span><span class="sxs-lookup"><span data-stu-id="9a20d-126">In this example, select Quarter 1.</span></span>  
  
 <span data-ttu-id="9a20d-127">Per una illustrazione dei vantaggi delle sezioni di dati, vedere l'articolo relativo all' [impostazione di una sezione nella partizione del cubo SSAS](https://go.microsoft.com/fwlink/?LinkId=317783).</span><span class="sxs-lookup"><span data-stu-id="9a20d-127">For an explanation of data slice benefits, see [Set the Slice on your SSAS Cube Partition](https://go.microsoft.com/fwlink/?LinkId=317783).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9a20d-128">Si noti che le funzioni MDX dinamiche, ad esempio [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) o [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function) non sono supportate nella proprietà Slice per le partizioni.</span><span class="sxs-lookup"><span data-stu-id="9a20d-128">Note that dynamic MDX functions (such as [Generate &#40;MDX&#41;](/sql/mdx/generate-mdx) or [Except &#40;MDX&#41;](/sql/mdx/except-mdx-function)) are not supported in the Slice property for partitions.</span></span> <span data-ttu-id="9a20d-129">È necessario definire la sezione usando tuple esplicite o riferimenti ai membri.</span><span class="sxs-lookup"><span data-stu-id="9a20d-129">You must define the slice by using explicit tuples or member references.</span></span>  
>   
>  <span data-ttu-id="9a20d-130">Ad esempio, anziché utilizzare l' [intervallo &#40;&#41; &#40;funzione MDX&#41;](/sql/mdx/range-mdx) per definire un intervallo, è necessario enumerare ogni membro in base agli anni specifici.</span><span class="sxs-lookup"><span data-stu-id="9a20d-130">For example, rather than using the [: &#40;Range&#41; &#40;MDX&#41;](/sql/mdx/range-mdx) function to define a range, you would need to enumerate each member by the specific years.</span></span>  
>   
>  <span data-ttu-id="9a20d-131">Se occorre definire una sezione complessa, è consigliabile definire le tuple nella sezione mediante uno script XMLA Alter.</span><span class="sxs-lookup"><span data-stu-id="9a20d-131">If you need to define a complex slice, we recommend that you define the tuples in the slice by using an XMLA Alter script.</span></span> <span data-ttu-id="9a20d-132">È quindi possibile usare lo strumento da riga di comando ascmd o l'attività [Analysis Services Execute DDL Task](../../integration-services/control-flow/analysis-services-execute-ddl-task.md) di SSIS per eseguire lo script e creare il set di membri specificato immediatamente prima dell'elaborazione della partizione.</span><span class="sxs-lookup"><span data-stu-id="9a20d-132">Then, you can use either the ascmd command-line tool or the SSIS [Analysis Services Execute DDL Task](../../integration-services/control-flow/analysis-services-execute-ddl-task.md) task to run the script and create the specified set of members immediately before you process the partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a20d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a20d-133">See Also</span></span>  
 [<span data-ttu-id="9a20d-134">Creare e gestire una partizione locale &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9a20d-134">Create and Manage a Local Partition &#40;Analysis Services&#41;</span></span>](create-and-manage-a-local-partition-analysis-services.md)  
  
  