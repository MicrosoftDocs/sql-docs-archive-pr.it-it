---
title: Elemento Create (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711339"
---
# <a name="create-element-dta"></a>Create - elemento (DTA)
  Contiene informazioni su indici, statistiche o strutture heap in una configurazione specificata dall'utente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a>Caratteristiche elemento  
  
|Caratteristica|Descrizione|  
|--------------------|-----------------|  
|**Tipo di dati e lunghezza**|No.|  
|**Valore predefinito**|No.|  
|**Occorrenza**|Obbligatorio una sola volta per ogni struttura di progettazione fisica, quali indici, statistiche o strutture heap.|  
  
## <a name="element-relationships"></a>Relazioni elemento  
  
|Relazione|Elementi|  
|------------------|--------------|  
|**Elemento padre**|[Elemento Recommendation &#40;DTA&#41;](recommendation-element-dta.md)|  
|**Elementi figlio**|[Elemento Index &#40;DTA&#41;](index-element-dta.md)<br /><br /> `Statistics`Elemento (vedere [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) per informazioni)<br /><br /> `Heap`Elemento (vedere [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) per informazioni)|  
  
## <a name="remarks"></a>Osservazioni  
 Questo elemento appartiene al nome **CreateTypecomplexType** nell'XML Schema dell'Ottimizzazione guidata motore di database. Viene utilizzato per creare indici, statistiche e strutture heap per una configurazione specificata dall'utente. Questo elemento `Create` non deve essere confuso con altri tipi che è possibile utilizzare per creare viste (`CreateViewType`) o per il partizionamento (`CreatePType`). Per informazioni su questi altri tipi di elemento, fare riferimento alla [Ottimizzazione guidata motore di database XML Schema](https://schemas.microsoft.com/sqlserver/) `Create` .  
  
## <a name="example"></a>Esempio  
 Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
