---
title: Modificare la partizione DirectQuery (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9df1e66-dd23-41b4-95eb-af110d10eda4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 43d14785f72d9bfe6406e2b81d3f1b97e9b7cc2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626413"
---
# <a name="change-the-directquery-partition-ssas-tabular"></a>Modificare la partizione DirectQuery (SSAS tabulare)
  Poiché è possibile designare come partizione DirectQuery solo una partizione di una tabella, per impostazione predefinita in Analysis Services viene utilizzata la prima partizione creata nella tabella. Durante la creazione del progetto di modello, è possibile modificare la partizione DirectQuery tramite la finestra di dialogo Gestione partizioni di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]. Per i modelli distribuiti, tale partizione può essere modificata tramite [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].  
  
### <a name="change-the-directquery-partition-for-a-tabular-model-project"></a>Modificare la partizione DirectQuery per un progetto di modello tabulare  
  
1.  In Progettazione modelli di [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]fare clic sulla tabella (scheda) in cui è contenuta la tabella partizionata.  
  
2.  Fare clic sul menu **Tabella** , quindi scegliere **Partizioni**.  
  
3.  In **Gestione partizioni**nel nome della partizione attualmente designata come partizione DirectQuery è contenuto il prefisso **(DirectQuery)** .  
  
     Selezionare una partizione diversa dall'elenco **Partizioni** , quindi fare clic su **Imposta come DirectQuery**. Il pulsante **Imposta come DirectQuery** non è abilitato quando è selezionata la partizione DirectQuery corrente e non è visibile se il modello non è stato abilitato per la modalità DirectQuery.  
  
4.  Se necessario, modificare le opzioni di elaborazione, quindi fare clic su **OK**.  
  
### <a name="change-the-directquery-partition-for-a-deployed-tabular-model"></a>Modificare la partizione DirectQuery per un modello tabulare distribuito  
  
1.  In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]aprire il database modello in Esplora oggetti.  
  
2.  Espandere il nodo **Tabelle** , fare clic con il pulsante destro del mouse sulla tabella partizionata e selezionare **Partizioni**.  
  
     Nel nome della partizione designata per l'utilizzo nella modalità DirectQuery è contenuto il prefisso (DirectQuery).  
  
3.  Per cambiare la partizione, fare clic sull'icona della barra degli strumenti **DirectQuery** per aprire la finestra di dialogo **Imposta partizione DirectQuery** . L'icona della barra degli strumenti DirectQuery non è disponibile per i modelli che non sono stati abilitati per DirectQuery.  
  
4.  Scegliere una partizione diversa dall'elenco a discesa **Nome partizione** e modificare le opzioni di elaborazione sulla partizione, se necessario.  
  
## <a name="see-also"></a>Vedere anche  
 [Partizioni &#40;SSAS tabulare&#41;](tabular-models/partitions-ssas-tabular.md)  
  
  
