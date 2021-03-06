---
title: Utilizzo delle proprietà membro (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- DIMENSION PROPERTIES keyword
- Properties function
- member properties [MDX]
- members [MDX], properties
ms.assetid: 26b5ad08-3799-4a5e-89f3-dca25e637d45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5b7fdf989fc23ea70be7d7863f5d4c6ac0b61d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714635"
---
# <a name="using-member-properties-mdx"></a>Utilizzo delle proprietà dei membri (MDX)
  Le proprietà dei membri contengono informazioni di base su ogni membro di ogni tupla. Tali informazioni di base includono il nome del membro, il livello padre, il numero di elementi figli e così via. Le proprietà dei membri sono disponibili per tutti i membri a un livello specifico. Per quanto riguarda l'organizzazione, le proprietà dei membri vengono gestite come dati organizzati a livello di dimensione, archiviati in una singola dimensione.  
  
> [!NOTE]  
>  In [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]le proprietà dei membri sono dette relazioni tra attributi. Per altre informazioni, vedere [Relazioni tra attributi](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).  
  
 Le proprietà dei membri possono essere *intrinseche* o *personalizzate*:  
  
 Proprietà intrinseche dei membri  
 Tutti i membri supportano le proprietà intrinseche dei membri, ad esempio il valore formattato di un membro, mentre per le dimensioni e i livelli sono disponibili ulteriori proprietà intrinseche dei membri per livelli e dimensioni, quale l'ID di un membro.  
  
 Per altre informazioni, vedere [Proprietà intrinseche dei membri &#40;MDX&#41;](mdx-member-properties-intrinsic-member-properties.md).  
  
 Proprietà dei membri definite dall'utente  
 Ai membri sono spesso associate proprietà aggiuntive. Il livello Products, ad esempio, può includere le proprietà SKU, SRP, Weight e Volume per ogni prodotto. Tali proprietà non sono membri, ma includono informazioni aggiuntive sui membri del livello Products.  
  
 Per altre informazioni, vedere [Proprietà dei membri definite dall'utente &#40;MDX&#41;](mdx-member-properties-user-defined-member-properties.md).  
  
 Sia le proprietà intrinseche dei membri che quelle definite dall'utente possono essere recuperate usando la `PROPERTIES` parola chiave o la funzione [Properties](/sql/mdx/properties-mdx) .  
  
## <a name="using-the-properties-keyword"></a>Utilizzo della parola chiave PROPERTIES  
 La parola chiave `PROPERTIES` specifica le proprietà dei membri che devono essere utilizzate per una determinata dimensione dell'asse. La `PROPERTIES` parola chiave viene nascosta all'interno della `<axis specification>` clausola dell'istruzione MDX [Select](/sql/mdx/mdx-data-manipulation-select) :  
  
```  
SELECT [<axis_specification>  
       [, <axis_specification>...]]  
  FROM [<cube_specification>]  
[WHERE [<slicer_specification>]]  
```  
  
 La clausola `<axis_specification>` include la clausola facoltativa `<dim_props>` , come illustrato nella sintassi seguente:  
  
```  
<axis_specification> ::= <set> [<dim_props>] ON <axis_name>  
```  
  
> [!NOTE]  
>  Per altre informazioni sui valori di `<set>` e `<axis_name>`, vedere [Impostazione del contenuto di un asse della query &#40;MDX&#41;](mdx-query-and-slicer-axes-specify-the-contents-of-a-query-axis.md).  
  
 La clausola `<dim_props>` consente di eseguire query sulle proprietà di dimensioni, livelli e membri, tramite la parola chiave `PROPERTIES`. Il formato della clausola `<dim_props>` è illustrato nella sintassi seguente:  
  
```  
<dim_props> ::= [DIMENSION] PROPERTIES <property> [,<property>...]  
```  
  
 Il dettaglio della sintassi di `<property>` dipende dalla proprietà su cui viene eseguita la query:  
  
-   Le proprietà dei membri intrinseche e sensibili al contesto devono essere precedute dal nome della dimensione o del livello. Le proprietà dei membri intrinseche e non sensibili al contesto non possono essere invece qualificate dal nome della dimensione o del livello. Per ulteriori informazioni sull'utilizzo della `PROPERTIES` parola chiave con le proprietà intrinseche dei membri, vedere [proprietà intrinseche dei membri &#40;&#41;MDX ](mdx-member-properties-intrinsic-member-properties.md).  
  
-   Le proprietà dei membri definite dall'utente devono essere precedute dal nome del livello in cui si trovano. Per ulteriori informazioni sull'utilizzo della `PROPERTIES` parola chiave con le proprietà dei membri definite dall'utente, vedere [proprietà dei membri definite dall'utente &#40;&#41;MDX ](mdx-member-properties-user-defined-member-properties.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione e utilizzo di valori di proprietà &#40;MDX&#41;](../../creating-and-using-property-values-mdx.md)  
  
  
