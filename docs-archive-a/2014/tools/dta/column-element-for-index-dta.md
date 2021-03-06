---
title: Elemento Column per index (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Column element
ms.assetid: ba9fac20-26bd-4333-940e-842c15241b46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67853dc7d1193d3a0f80e56023846bc55a20bdaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711363"
---
# <a name="column-element-for-index-dta"></a>Elemento Column per Index (DTA)
  Specifica le colonne sulle quali viene creato l'indice per una configurazione specificata dall'utente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
<Create>  
  <Index>  
    <Name>...</Name>  
    <Column [Type | SortOrder]>  
     ...code removed here...  
     </Column>  
```  
  
## <a name="element-attributes"></a>Attributi elemento  
  
|Attributo della colonna|Descrizione|  
|----------------------|-----------------|  
|`Type`|Facoltativa. Specifica il tipo di colonna dell'indice. Usare un tipo di dati **string** per specificare questo attributo con uno dei valori consentiti seguenti:<br /><br /> `KeyColumn`:<br />                  Specifica che alla colonna viene fatto riferimento mediante una chiave di indice. Per impostare questo attributo, utilizzare la sintassi seguente:<br />`<Column Type="KeyColumn">`<br />Per altre informazioni sulle colonne chiave, vedere [Descrizione di indici cluster e non cluster](../../relational-databases/indexes/clustered-and-nonclustered-indexes-described.md).<br /><br /> `IncludedColumn`: Specifica che la colonna è una colonna inclusa, anziché una colonna chiave. Per impostare questo attributo, utilizzare la sintassi seguente:<br />`<Column Type="IncludedColumn">`<br />Per altre informazioni sulle colonne incluse, vedere [Creare indici con colonne incluse](../../relational-databases/indexes/create-indexes-with-included-columns.md).|  
|`SortOrder`|facoltativo. Specifica l'ordinamento della colonna. Usare un tipo di dati **string** per specificare un ordinamento **"Ascending"** o **"Descending"** come segue:<br /><br /> `<Column SortOrder="Ascending">`|  
  
## <a name="element-characteristics"></a>Caratteristiche elemento  
  
|Caratteristica|Descrizione|  
|--------------------|-----------------|  
|**Tipo di dati e lunghezza**|No.|  
|**Valore predefinito**|No.|  
|**Occorrenza**|È possibile specificare un massimo di 1024 colonne per l'elemento `Index`.|  
  
## <a name="element-relationships"></a>Relazioni elemento  
  
|Relazione|Elementi|  
|------------------|--------------|  
|**Elemento padre**|[Elemento Index &#40;DTA&#41;](index-element-dta.md)|  
|**Elementi figlio**|[Elemento Name per Column &#40;DTA&#41;](name-element-for-column-dta.md)|  
  
## <a name="example"></a>Esempio  
 Per un esempio di utilizzo di questo elemento, vedere [Esempio di file di input XML con configurazione specificata dall'utente &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
