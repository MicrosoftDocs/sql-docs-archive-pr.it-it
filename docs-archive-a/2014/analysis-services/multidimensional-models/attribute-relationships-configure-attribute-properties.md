---
title: Configurare le proprietà della relazione tra attributi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- flexible relationships (Analysis Services)
- attributes [Analysis Services], relationships
- relationships [Analysis Services], attributes
- properties [Analysis Services], attribute relationships
- rigid relationships (Analysis Services)
ms.assetid: fce511af-66d7-42fc-bb3a-6c516f16b10e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 241fa2af16377fd2cacf657ec6f99c5ca4bd0c53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624418"
---
# <a name="configure-attribute-relationship-properties"></a>Configurare le proprietà della relazione tra attributi
  Nella tabella seguente vengono elencate e descritte le proprietà di una relazione tra attributi.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|Attributo|Nome dell'attributo.|  
|Cardinalità|Indica la cardinalità della relazione. Il valore è Many per una relazione molti-a-uno e One per una relazione uno-a-uno. Il valore predefinito è Many. In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] la proprietà Cardinality non ha alcun effetto. il suo utilizzo è riservato per un'implementazione futura.|  
|Nome|Nome descrittivo dell'attributo.|  
|RelationshipType|Indica se le relazioni tra membri cambiano nel tempo. Il valore di questa proprietà è Rigid se le relazioni tra membri non cambiano nel tempo o Flexible in caso contrario. Il valore predefinito è Flexible. Se si definisce una relazione flessibile, le aggregazioni verranno eliminate e ricalcolate come parte di un aggiornamento incrementale. Non verranno invece eliminate se vengono aggiunti solo nuovi membri. Se viene definita una relazione rigida, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] consente di mantenere le aggregazioni quando la dimensione viene aggiornata in modo incrementale. Se una relazione definita rigida viene modificata, in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] verrà generato un errore durante l'aggiornamento incrementale. L'impostazione corretta delle relazioni e delle rispettive proprietà determina un miglioramento delle prestazioni durante l'esecuzione di query e i processi di elaborazione.|  
|Visible|Determina la visibilità della relazione tra attributi. Il valore è True o False. Il valore predefinito è true.|  
  
  
