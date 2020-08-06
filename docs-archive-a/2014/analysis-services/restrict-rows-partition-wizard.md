---
title: Limitazione righe (creazione guidata partizione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.typefilterexpression.f1
ms.assetid: eec8da8f-eab4-4ac4-a81d-995c814f88ca
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b0acc9ab24cfe92877d9abcd86353c85b4f8905
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625646"
---
# <a name="restrict-rows-partition-wizard"></a>Limitazione righe (Creazione guidata partizione)
  La pagina **Limitazione righe** consente di limitare le righe che verranno recuperate dalla tabella specificata e quindi aggregate e incluse nella partizione.  
  
> [!NOTE]  
>   Questa pagina viene visualizzata solo se è stata selezionata un'unica tabella nella pagina **Impostazione informazioni origine** .  
  
> [!CAUTION]  
>   Se in **Tabelle disponibili** nella pagina **Impostazione informazioni origine** è stata specificata una tabella utilizzata da un'altra partizione, sarà necessario inserire una query nella pagina **Limitazione righe** o si rischia la duplicazione dei dati nel cubo.  
  
## <a name="options"></a>Opzioni  
 **Specificare una query per limitare le righe**  
 Selezionare questa opzione per immettere nella casella **Query** una query che limiti le righe.  
  
 Se la casella **Query** è vuota quando viene selezionata l'opzione, tale opzione verrà popolata con un'istruzione SQL che recupera tutte le colonne e le righe dalla tabella precedentemente selezionata.  
  
 **Query**  
 Consente di digitare o modificare l'istruzione SQL utilizzata quando vengono recuperate le righe dalla tabella durante l'elaborazione della partizione.  
  
> [!IMPORTANT]  
>  è possibile specificare una clausola WHERE per utilizzare un subset di record per questa partizione. Quando più partizioni si basano su un'unica tabella dei fatti è essenziale evitare la duplicazione di dati.  
  
 **Controllo**  
 Verifica che l'istruzione presente in **Query** sia un'istruzione SQL valida.  
  
## <a name="see-also"></a>Vedere anche  
 [Partizioni &#40;Analysis Services - Dati multidimensionali&#41;](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
