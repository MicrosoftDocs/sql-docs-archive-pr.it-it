---
title: Creare query UNION (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3c10f39c3e44844c4ec8a6a2328c41ea2de350d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629696"
---
# <a name="create-union-queries-visual-database-tools"></a>Creare query UNION (Visual Database Tools)
  La parola chiave UNION consente di includere i risultati di due istruzioni SELECT in una tabella risultante. Tutte le righe restituite dalle due istruzioni SELECT vengono combinate nel risultato dell'espressione UNION. Per esempi, vedere gli [esempi di selezione &#40;&#41;Transact-SQL ](/sql/t-sql/queries/select-examples-transact-sql).  
  
> [!NOTE]  
>  Poiché nel riquadro Diagramma è possibile visualizzare solo una clausola SELECT, quando si lavora a una query di unione (query UNION), il Riquadro operazioni tabella verrà nascosto in Progettazione query.  
  
### <a name="to-create-a-merged-select-query"></a>Per creare una query SELECT unita  
  
1.  Aprire una query esistente o crearne una nuova.  
  
2.  Nel riquadro SQL digitare un'espressione UNION valida.  
  
     Nell'esempio seguente viene illustrata un'espressione UNION valida.  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  Per eseguire la query, scegliere **Esegui SQL** dal menu **Progettazione query** .  
  
     La query di unione verrà così formattata da Progettazione query.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di query supportati &#40;Visual Database Tools&#41;](visual-database-tools.md)   
 [Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md)   
 [Esecuzione di operazioni di base con le query &#40;Visual Database Tools&#41;](perform-basic-operations-with-queries-visual-database-tools.md)   
 [UNION &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/set-operators-union-transact-sql)  
  
  
