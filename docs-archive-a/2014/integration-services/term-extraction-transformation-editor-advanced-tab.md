---
title: Editor trasformazione Estrazione termini (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.advanced.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 87118281-6e3c-499e-bac4-fa4c24bb12c6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4be56f8ac2deeab49e43071a07894a466019287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718468"
---
# <a name="term-extraction-transformation-editor-advanced-tab"></a>Editor trasformazione Estrazione termini (Scheda Avanzate)
  Usare la scheda **Avanzate** della finestra di dialogo **Editor trasformazione Estrazione termini** per specificare le proprietà per l'estrazione, ad esempio la frequenza, la lunghezza e le eventuali parole o frasi da estrarre.  
  
 Per ulteriori informazioni sulla trasformazione Estrazione termini, vedere [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).  
  
## <a name="options"></a>Opzioni  
 **Sostantivo**  
 Consente di specificare che la trasformazione estrarrà solo singoli sostantivi.  
  
 **Sintagma nominale**  
 Consente di specificare che la trasformazione estrarrà solo sintagmi nominali.  
  
 **Sostantivo e sintagma nominale**  
 Consente di specificare che la trasformazione estrarrà sia sostantivi che sintagmi nominali.  
  
 **Frequenza**  
 Consente di specificare che il punteggio è rappresentato dalla frequenza del termine.  
  
 **TFIDF**  
 Consente di specificare che il punteggio è rappresentato dal valore TFIDF del termine. Il punteggio TFIDF è il prodotto della frequenza dei termini e della frequenza inversa dei documenti, definito come: TFIDF di un termine T = (frequenza di T) * log( (numero di righe nell'input) / (numero di righe contenenti T) )  
  
 **Soglia di frequenza**  
 Consente di specificare il numero di volte in cui una parola o una frase deve ricorrere prima che venga estratta. Il valore predefinito è 2.  
  
 **Lunghezza massima termine**  
 Consente di specificare la lunghezza massima in parole di una frase. Questa opzione ha effetto soltanto sui sintagmi nominali. Il valore predefinito è 12.  
  
 **Estrazione con distinzione maiuscole/minuscole**  
 Consente di specificare se eseguire l'estrazione rilevando la distinzione tra maiuscole e minuscole. Il valore predefinito è `False`.  
  
 **Configura output errori**  
 Usare la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) per specificare la gestione degli errori per le righe che causano errori.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor trasformazione Estrazione termini &#40;scheda Estrazione termini&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md)   
 [Editor trasformazione Estrazione termini &#40;scheda esclusione&#41;](../../2014/integration-services/term-extraction-transformation-editor-exclusion-tab.md)   
 [Trasformazione Ricerca termini](data-flow/transformations/lookup-transformation.md)  
  
  
