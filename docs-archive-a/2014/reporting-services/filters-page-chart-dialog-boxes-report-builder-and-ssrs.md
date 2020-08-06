---
title: Pagina filtri, finestre di dialogo dei grafici (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.categorygroupproperties.filters.f1
- "10409"
- sql12.rtp.rptdesigner.seriesgroupproperties.filters.f1
- "10401"
- sql12.rtp.rptdesigner.chartproperties.filters.f1
- "10165"
ms.assetid: fab97b2f-d53f-42f2-900c-c159653d89ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01d5054ce7d0c3e02d960885f149bd0ef209dc34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716124"
---
# <a name="filters-page-chart-dialog-boxes-report-builder-and-ssrs"></a>Pagina Filtri, finestre di dialogo relative ai grafici (Generatore report e SSRS)
  Fare clic su **filtri** nella:  
  
-   Finestra di dialogo**Proprietà gruppo categorie** per filtrare i punti dati in una serie raggruppata per categoria.  
  
-   Finestra di dialogo**Proprietà grafico** per definire le opzioni di filtro per il grafico.  
  
-   Finestra di dialogo**Proprietà gruppo serie** per limitare il numero di serie nel gruppo selezionato.  
  
## <a name="options"></a>Opzioni  
 **Aggiungere**  
 Consente di aggiungere all'elenco una nuova clausola di filtro.  
  
 **Elimina**  
 Consente di eliminare la clausola di filtro selezionata dall'elenco.  
  
 **Freccia in su**  
 Consente di spostare il filtro selezionato di una posizione verso l'alto nell'elenco.  
  
 **Freccia GIÙ**  
 Consente di spostare il filtro selezionato di una posizione verso il basso nell'elenco.  
  
 **Espressione**  
 Digitare o scegliere l'espressione alla quale si desidera applicare un filtro. Fare clic sul pulsante espressione (**FX**) per modificare l'espressione.  
  
 **Tipo di dati**  
 Scegliere il tipo di dati per **Valore**. Se possibile, scegliere un tipo di dati che corrisponda al tipo di dati per **Espressione**.  
  
 I valori specificati in **Espressione** e **Valore** devono restituire lo stesso tipo di dati. Ad esempio, se **Espressione** è impostato su un campo a cui è associato il tipo di dati System.Int32 e **Valore** è impostato su 7, nell'elenco a discesa selezionare **Integer**.  
  
 Se l'opzione relativa al tipo di dati necessario non è presente nell'elenco a discesa, scrivere un'espressione per convertire il valore nel tipo di dati corretto. Per altre informazioni, vedere [Esempi di equazioni di filtro &#40;Generatore report e SSRS&#41;](report-design/filter-equation-examples-report-builder-and-ssrs.md).  
  
 **Operatore**  
 Scegliere l'operatore da utilizzare per confrontare l'espressione e il valore.  
  
 **Valore**  
 Digitare l'espressione o il valore in base a cui valutare l'espressione nella colonna **Espressione**.  
  
## <a name="see-also"></a>Vedere anche  
 [Aggiungere filtri del set di dati, aree dati e gruppi &#40;Generatore report e SSRS&#41;](report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Esempi di espressioni &#40;Generatore report e SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md)   
 [Espressioni &#40;Generatore report e SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md)   
 [Filtro, raggruppamento e ordinamento di dati &#40;Generatore report e SSRS&#41;](report-design/filter-group-and-sort-data-report-builder-and-ssrs.md)  
  
  
