---
title: Selezionare righe non corrispondenti a un valore (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- search conditions [SQL Server], rows not matching value
- row not matching value [SQL Server]
- NOT operator [Visual Database Tools]
- search criteria [SQL Server], rows not matching value
ms.assetid: 19898578-7b2f-401c-bb8f-9f2a017efdf7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 412ec93cbfedc87e92da9e86c7e4c7455919722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719319"
---
# <a name="select-rows-that-do-not-match-a-value-visual-database-tools"></a>Selezione di righe non corrispondenti a un valore (Visual Database Tools)
  Per individuare le righe che non corrispondono a un valore, utilizzare l'operatore NOT.  
  
### <a name="to-find-rows-that-do-not-match-a-value"></a>Per individuare le righe che non corrispondono a un valore  
  
1.  Se non è ancora stato fatto, aggiungere nel [riquadro Criteri](visual-database-tools.md)le colonne o le espressioni da usare nella condizione di ricerca.  
  
2.  Individuare la riga contenente la colonna di dati o l'espressione da includere nella ricerca, quindi immettere l'operatore NOT seguito da un valore di ricerca nella colonna **Filtro** della griglia.  
  
 Per trovare, ad esempio, tutte le righe in una tabella `products` in cui i valori nella colonna del codice del prodotto iniziano con un carattere diverso da "A", immettere una condizione di ricerca analoga alla seguente:  
  
```  
NOT LIKE 'A%'  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Regole per l'immissione di valori di ricerca &#40;Visual Database Tools&#41;](rules-for-entering-search-values-visual-database-tools.md)   
 [Specifica dei criteri di ricerca &#40;Visual Database Tools&#41;](specify-search-criteria-visual-database-tools.md)  
  
  
