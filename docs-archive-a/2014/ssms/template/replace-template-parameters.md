---
title: Sostituire i parametri del modello | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.templates.replaceparameters.f1
helpviewer_keywords:
- template parameters [Template Explorer]
- templates [Transact-SQL], replacing parameters
- Replace (Query) Template Parameters dialog box
- replacing template parameters
ms.assetid: 1234aa14-3464-4a3e-922a-5cfb8fb23627
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d87b17a110efe118f7796487448e4d3bae30375
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630221"
---
# <a name="replace-template-parameters"></a>Sostituisci parametri modello
  I modelli contengono parametri che possono essere sostituiti da valori specifici dell'implementazione ogni volta che il modello è utilizzato. Dopo avere aperto un modello in un editor di codice, è possibile sostituire i parametri con i valori attinenti all'implementazione.  
  
## <a name="before-you-begin"></a>Prima di iniziare  
 La finestra di dialogo **Imposta valori per parametri modello** è una griglia con tre colonne. Le colonne **Parametro** e **Tipo** sono di sola lettura e non possono essere modificate. Rivedere il contenuto della colonna **Valore** e modificare i valori predefiniti in base all'implementazione.  
  
 Per usare questa finestra di dialogo, è necessario che i parametri nello script siano racchiusi tra parentesi angolari (`< >`) nel formato `<`*parameter_name*`,` *data_type*`,` *default_value*`>`.  
  
## <a name="replace-template-parameters"></a>Sostituisci parametri modello  
 Dopo avere aperto il modello in una finestra dell'editor di codice:  
  
1.  Scegliere **Imposta valori per parametri modello** dal menu **Query**.  
  
2.  Nella finestra di dialogo **Imposta valori per parametri modello** la colonna **Valori** contiene un valore suggerito per ogni parametro. Accettare il valore o sostituirlo con uno nuovo.  
  
3.  Fare clic su **OK** per chiudere la finestra di dialogo **Replace Template Parameters** (Sostituisci parametri modello) e modificare lo script nell'editor di query.  
  
## <a name="see-also"></a>Vedere anche  
 [Esplora modelli](template-explorer.md)   
 [Aprire un modello](open-a-template.md)  
  
  
