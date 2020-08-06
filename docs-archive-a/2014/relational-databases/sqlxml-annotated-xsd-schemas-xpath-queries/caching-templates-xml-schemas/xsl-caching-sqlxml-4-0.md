---
title: Caching XSL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- registry keys [SQLXML]
- cache [SQLXML]
- XSL caching [SQLXML]
ms.assetid: 91994142-32f0-4d8d-a8cf-eb0d8b1f1999
author: rothja
ms.author: jroth
ms.openlocfilehash: e41f247c34c1b40bedfdf6924a45afe5f63735b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716164"
---
# <a name="xsl-caching-sqlxml-40"></a><span data-ttu-id="57ae8-102">Memorizzazione nella cache file XSL (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="57ae8-102">XSL Caching (SQLXML 4.0)</span></span>
  <span data-ttu-id="57ae8-103">La memorizzazione nella cache di fogli di stile XSL migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="57ae8-103">Caching XSL style sheets improves performance.</span></span> <span data-ttu-id="57ae8-104">Fino alla prima esecuzione, il foglio di stile XSL resta in memoria se la memorizzazione nella cache XSL è impostata su ON. Questa impostazione offre prestazioni migliori per l'elaborazione successiva.</span><span class="sxs-lookup"><span data-stu-id="57ae8-104">Upon its first execution, an XSL style sheet remains in memory if XSL caching is set to ON; this improves performance for subsequent processing.</span></span> <span data-ttu-id="57ae8-105">L'impostazione predefinita è ON.</span><span class="sxs-lookup"><span data-stu-id="57ae8-105">The default setting is ON.</span></span>  
  
 <span data-ttu-id="57ae8-106">È possibile impostare le dimensioni della cache per i file XSL aggiungendo la chiave seguente nel Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="57ae8-106">You can set the XSL cache size by adding the following key in the registry:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSSQLServer\Client\SQLXML4\XSLCacheSize  
```  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="57ae8-107">La cache dei file XSL deve essere impostata in base alla memoria disponibile e al numero di fogli di stile XSL utilizzati.</span><span class="sxs-lookup"><span data-stu-id="57ae8-107">The XSL cache size should be set on the basis of the available memory and the number of XSL style sheets you are using.</span></span> <span data-ttu-id="57ae8-108">Il valore predefinito di **XSLCacheSize** è 31.</span><span class="sxs-lookup"><span data-stu-id="57ae8-108">The default of **XSLCacheSize** size is 31.</span></span> <span data-ttu-id="57ae8-109">È possibile aumentare le dimensioni della cache se l'accesso a XSL appare rallentato oppure diminuire le dimensioni della cache se la memoria risulta insufficiente.</span><span class="sxs-lookup"><span data-stu-id="57ae8-109">You can increase the cache size if XSL access seems slow, or decrease the cache size if memory is low.</span></span>  
  
 <span data-ttu-id="57ae8-110">Per ottenere prestazioni ottimali, è consigliabile impostare **XSLCacheSize** su un valore superiore al numero di fogli di stile XSL usati in genere.</span><span class="sxs-lookup"><span data-stu-id="57ae8-110">For better performance, it is recommended that you set **XSLCacheSize** higher than the number of XSL style sheets you usually use.</span></span> <span data-ttu-id="57ae8-111">Se **XSLCacheSize** è inferiore al numero di fogli di stile XSL disponibili, le prestazioni diminuiscono man mano che aumenta il numero di fogli di stile XSL.</span><span class="sxs-lookup"><span data-stu-id="57ae8-111">If **XSLCacheSize** is less than the number of XSL style sheets you have, the performance degrades as the number of XSL style sheets increases.</span></span> <span data-ttu-id="57ae8-112">**XSLCacheSize** può essere impostato su un massimo di 128.</span><span class="sxs-lookup"><span data-stu-id="57ae8-112">The **XSLCacheSize** can be set to a maximum of 128.</span></span>  
  
 <span data-ttu-id="57ae8-113">Ogni volta che si utilizza il foglio di stile XSL memorizzato nella cache, viene verificata la durata delle modifiche del file XSL per determinare se deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="57ae8-113">Every time the cached XSL style sheet is used, the modification time of the XSL file is checked to determine whether it needs to be refreshed.</span></span> <span data-ttu-id="57ae8-114">Ciò accade in quanto la copia su disco è più recente della copia della cache.</span><span class="sxs-lookup"><span data-stu-id="57ae8-114">This is because the disk copy is newer than the cache copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57ae8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57ae8-115">See Also</span></span>  
 <span data-ttu-id="57ae8-116">[Caching del modello &#40;SQLXML 4,0&#41;](template-caching-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="57ae8-116">[Template Caching &#40;SQLXML 4.0&#41;](template-caching-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="57ae8-117">Caching dello schema &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="57ae8-117">Schema Caching &#40;SQLXML 4.0&#41;</span></span>](schema-caching-sqlxml-4-0.md)  
  
  
