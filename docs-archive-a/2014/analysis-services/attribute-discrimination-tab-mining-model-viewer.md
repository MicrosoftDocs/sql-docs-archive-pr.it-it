---
title: Scheda Analisi discriminante attributi (Visualizzatore modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.naivebayse.discrimination.f1
ms.assetid: 68323f23-121e-44fc-be85-6f9915d6d3c7
author: minewiskan
ms.author: owend
ms.openlocfilehash: a8b0d4bc99b1c8f1c5de0269312f02eeb09df022
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625877"
---
# <a name="attribute-discrimination-tab-mining-model-viewer"></a>Scheda Analisi discriminante attributi (Visualizzatore modello di data mining)
  Usare la scheda **Analisi discriminante attributi** per confrontare gli stati degli attributi di input e visualizzare la relativa correlazione con l'attributo risultante. I valori degli attributi che presentano le maggiori differenze tra i due stati di attributo stimabile selezionati vengono elencati per primi.  
  
 **Per altre informazioni:** [Algoritmo Microsoft Naive Bayes](data-mining/microsoft-naive-bayes-algorithm.md)e [Visualizzare un modello utilizzando il Visualizzatore Microsoft Naive Bayes](data-mining/browse-a-model-using-the-microsoft-naive-bayes-viewer.md)  
  
## <a name="options"></a>Opzioni  
 **Aggiorna contenuto visualizzatore**  
 Consente di ricaricare il modello di data mining nel visualizzatore.  
  
 **Modello di data mining**  
 Consente di scegliere un modello di data mining tra quelli presenti nella struttura di data mining corrente. Il modello di data mining viene aperto automaticamente nel visualizzatore personalizzato corretto.  
  
 **Visualizzatore**  
 Consente di scegliere un visualizzatore da utilizzare per l'esplorazione del modello di data mining selezionato. Per ogni modello è possibile scegliere il Visualizzatore personalizzato o [!INCLUDE[msCoName](../includes/msconame-md.md)] Mining Content Viewer. Se disponibili, è anche possibile utilizzare i visualizzatori plug-in.  
  
 **Attributo**  
 Consente di scegliere un attributo stimabile.  
  
 **Valore 1**  
 Consente di scegliere uno stato dell'attributo stimabile da confrontare con lo stato contenuto in **Valore 2**.  
  
 **Valore 2**  
 Consente di scegliere uno stato dell'attributo stimabile da confrontare con lo stato contenuto in **Valore 1**. È anche possibile selezionare **tutti gli altri Stati** per confrontare il valore in **valore 1** con il relativo complemento, ovvero tutti gli altri valori eccetto valore 1.  
  
 **Punteggi discriminanti per \<Value 1> e\<Value 2>**  
 Nel grafico sono contenute le colonne seguenti in cui viene descritta la modalità di correlazione tra l'attributo di destinazione e gli stati specifici dell'attributo di input.  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|**Attributes (Attributi)**|Un attributo di input nel modello di data mining.|  
|**Valori**|Uno stato dell'attributo contenuto nell'elenco **Attributi**.|  
|**Predilige\<Value 1>**|La barra indica se l'attributo corrente e il valore prediligono il risultato di destinazione selezionato in **Valore 1**.|  
|**Predilige\<Value 2>**|La barra indica se l'attributo corrente e il valore prediligono il risultato di destinazione selezionato in **Valore 2**.|  
  
## <a name="see-also"></a>Vedere anche  
 [Algoritmi di data mining &#40;Analysis Services-&#41;di data mining](data-mining/data-mining-algorithms-analysis-services-data-mining.md)   
 [Visualizzatori modello di data mining &#40;Progettazione modelli di data mining&#41;](mining-model-viewers-data-mining-model-designer.md)   
 [Visualizzatori modello di data mining](data-mining/data-mining-model-viewers.md)  
  
  
