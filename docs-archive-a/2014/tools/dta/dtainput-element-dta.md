---
title: Elemento DTAInput (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712676"
---
# <a name="dtainput-element-dta"></a>Elemento DTAInput (DTA)
  Contiene la definizione dell'input XML per Ottimizzazione guidata motore di database.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a>Caratteristiche elemento  
  
|Caratteristiche|Descrizione|  
|---------------------|-----------------|  
|**Tipo di dati e lunghezza**|No.|  
|**Valore predefinito**|No.|  
|**Occorrenza**|Facoltativo una volta per ogni elemento **DTAXML** .|  
  
## <a name="element-relationships"></a>Relazioni elemento  
  
|Relazione|Elementi|  
|------------------|--------------|  
|**Elemento padre**|[Elemento DTAXML &#40;DTA&#41;](dtaxml-element-dta.md)|  
|**Elementi figlio**|[Elemento Server &#40;DTA&#41;](server-element-dta.md)<br /><br /> [Elemento Workload &#40;DTA&#41;](workload-element-dta.md)<br /><br /> [Elemento TuningOptions &#40;DTA&#41;](tuningoptions-element-dta.md)<br /><br /> [Elemento Configuration &#40;DTA&#41;](configuration-element-dta.md)|  
  
## <a name="remarks"></a>Osservazioni  
 Questo è l'elemento radice della gerarchia dello schema di input di Ottimizzazione guidata motore di database. L'input in Ottimizzazione guidata motore di database può essere costituito da argomenti che specificano i server di cui si desidera ottimizzare i database, i carichi di lavoro, le opzioni di ottimizzazione o una configurazione specificata dall'utente.  
  
## <a name="example"></a>Esempio  
 Per un esempio d'uso dell'elemento **DTAInput**, vedere [Esempio di file di input XML semplice &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
