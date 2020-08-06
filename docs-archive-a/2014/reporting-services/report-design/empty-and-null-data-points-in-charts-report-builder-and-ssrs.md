---
title: Punti dati vuoti e Null nei grafici (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: faddd29d-4cc1-4c2c-8e29-d3d9918fe22a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f0826a202969b432e53b3c57ddfe80680ba99e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711719"
---
# <a name="empty-and-null-data-points-in-charts-report-builder-and-ssrs"></a><span data-ttu-id="a25a0-102">Punti dati vuoti e Null nei grafici (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a25a0-102">Empty and Null Data Points in Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a25a0-103">Quando si visualizzano campi con valori vuoti o Null nel grafico, è possibile che il grafico non presenti l'aspetto previsto.</span><span class="sxs-lookup"><span data-stu-id="a25a0-103">If you are displaying fields with empty or null values in your chart, the chart may not look as you expect.</span></span> <span data-ttu-id="a25a0-104">I valori vuoti vengono elaborati in modo diverso a seconda del tipo di grafico specificato:</span><span class="sxs-lookup"><span data-stu-id="a25a0-104">Charts process empty values differently depending on the specified chart type:</span></span>  
  
-   <span data-ttu-id="a25a0-105">Se il grafico è di tipo lineare (grafico a barre, a dispersione, a linee, ad area, con intervalli o istogramma) i valori vuoti vengono visualizzati come spazi vuoti o "gap".</span><span class="sxs-lookup"><span data-stu-id="a25a0-105">If the chart type is a linear chart type (bar, column, scatter, line, area, range), empty values are displayed as empty spaces or "gaps" in the chart.</span></span> <span data-ttu-id="a25a0-106">Se si desidera identificare i punti vuoti, è necessario aggiungere segnaposti di punti vuoti.</span><span class="sxs-lookup"><span data-stu-id="a25a0-106">If you want to indicate empty points, you must add empty point placeholders.</span></span> <span data-ttu-id="a25a0-107">Per ulteriori informazioni, vedere [aggiungere punti vuoti al grafico &#40;Generatore report e SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a25a0-107">For more information, see [Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   <span data-ttu-id="a25a0-108">Se il grafico è di tipo lineare contiguo (ad area, a barre, a linee, a dispersione o istogramma), vengono aggiunti punti dati vuoti per mantenere la continuità nella serie.</span><span class="sxs-lookup"><span data-stu-id="a25a0-108">If the chart type is a contiguous, linear chart type (area, bar, column, line, scatter), empty data points are added to the chart to maintain continuity in the series.</span></span>  
  
-   <span data-ttu-id="a25a0-109">Se il grafico è di tipo non lineare (polare, a torta, ad anello, a imbuto o a piramide), i valori vuoti non vengono visualizzati.</span><span class="sxs-lookup"><span data-stu-id="a25a0-109">If the chart type is a nonlinear chart type (polar, pie, doughnut, funnel or pyramid), empty values are omitted from display on the chart.</span></span>  
  
-   <span data-ttu-id="a25a0-110">Nei tipi di grafico con forme i valori Null vengono omessi.</span><span class="sxs-lookup"><span data-stu-id="a25a0-110">In shape chart types, null values are omitted.</span></span>  
  
 <span data-ttu-id="a25a0-111">Un esempio di grafico con punti dati vuoti è disponibile come report di esempio.</span><span class="sxs-lookup"><span data-stu-id="a25a0-111">An example of a chart with empty data points is available as a sample report.</span></span> <span data-ttu-id="a25a0-112">Per altre informazioni sul download di questo e di altri report di esempio, vedere la pagina relativa ai [report di esempio per Generatore report e Progettazione report](https://go.microsoft.com/fwlink/?LinkId=198283) di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a25a0-112">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="removing-empty-or-null-values"></a><span data-ttu-id="a25a0-113">Rimozione di valori vuoti o Null</span><span class="sxs-lookup"><span data-stu-id="a25a0-113">Removing Empty or Null Values</span></span>  
 <span data-ttu-id="a25a0-114">Per evitare che dati importanti risultino nascosti, rimuovere i valori vuoti dal set di dati.</span><span class="sxs-lookup"><span data-stu-id="a25a0-114">To avoid obscuring important data, consider removing empty values from your dataset.</span></span> <span data-ttu-id="a25a0-115">Per filtrare i valori Null, è possibile usare la clausola NOT IS NULL nella query.</span><span class="sxs-lookup"><span data-stu-id="a25a0-115">To filter nulls, you can use the NOT IS NULL clause in your query.</span></span> <span data-ttu-id="a25a0-116">In alternativa, è possibile aggiungere un'espressione di filtro per specificare che si desidera visualizzare solo i valori diversi da zero.</span><span class="sxs-lookup"><span data-stu-id="a25a0-116">Alternatively, you can add a filtering expression that specifies that you only want to display values not equal to zero.</span></span> <span data-ttu-id="a25a0-117">Per altre informazioni, vedere [Aggiungere filtri per set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="a25a0-117">For more information, see [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
## <a name="fields-with-no-values-in-a-chart"></a><span data-ttu-id="a25a0-118">Campi senza valori in un grafico</span><span class="sxs-lookup"><span data-stu-id="a25a0-118">Fields with No Values in a Chart</span></span>  
 <span data-ttu-id="a25a0-119">Se un campo non contiene valori nel set di dati restituito, verrà visualizzato un grafico vuoto senza punti dati, ma con l'aggiunta del nome della serie (solitamente il nome del campo) come elemento della legenda.</span><span class="sxs-lookup"><span data-stu-id="a25a0-119">If a field does not contain any values in the returned dataset, the chart displays an empty chart with no data points, but the series name (typically the field name) is added as a legend item.</span></span>  
  
 <span data-ttu-id="a25a0-120">Questo comportamento è diverso dal caso in cui il set di dati restituito non contiene alcuna riga di dati, che può verificarsi quando il report include parametri e il valore selezionato restituisce un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="a25a0-120">This behavior differs from the case where there are zero rows of data in the returned dataset, which can occur when the report is parameterized and the selected value returns an empty result set.</span></span> <span data-ttu-id="a25a0-121">Se la query del set di dati non restituisce alcuna riga di dati, in fase di esecuzione verrà visualizzato un messaggio indicante che non è possibile visualizzare dati.</span><span class="sxs-lookup"><span data-stu-id="a25a0-121">If your dataset query returns zero rows of data, a message is displayed at run time to indicate that no data can be shown.</span></span> <span data-ttu-id="a25a0-122">È possibile personalizzare questo messaggio modificando la didascalia NoDataMessage per il report nel riquadro **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="a25a0-122">You can customize this message by modifying the NoDataMessage caption for the report in the **Properties** pane.</span></span> <span data-ttu-id="a25a0-123">Per altre informazioni, vedere [Set di dati condivisi e incorporati del report &#40;Generatore report e SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a25a0-123">For more information, see [Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](../report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25a0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a25a0-124">See Also</span></span>  
 <span data-ttu-id="a25a0-125">[Grafici &#40;Generatore report e SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a25a0-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a25a0-126">[Formattazione di un grafico &#40;Generatore report e SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a25a0-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="a25a0-127">[Aggiungere un grafico a un report &#40;Generatore report e SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a25a0-127">[Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="a25a0-128">Risoluzione dei problemi relativi ai grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a25a0-128">Troubleshoot Charts &#40;Report Builder and SSRS&#41;</span></span>](troubleshoot-charts-report-builder-and-ssrs.md)  
  
  