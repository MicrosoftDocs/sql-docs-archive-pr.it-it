---
title: Regole di confronto di motore di database server incompatibili (preparazione aggiornamento) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 80f499d6-2c90-49eb-a5b3-0bb5b7faaa3b
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: b6ce0555bdf5a878e56d87a8bd55b5ce6c4b2649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637040"
---
# <a name="incompatible-database-engine-server-collation-upgrade-advisor"></a>Regole di confronto del server del motore di database incompatibili (Upgrade Advisor)
  È stata rilevata l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utilizzo di un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurata per l'utilizzo di regole di confronto del server incompatibili.  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità SharePoint di.|  
  
## <a name="component"></a>Componente  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a>Descrizione  
 È stata rilevata l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utilizzo di un'istanza di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurata per l'utilizzo di regole di confronto del server incompatibili.  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modalità SharePoint viene utilizzata l'architettura dei servizi condivisi di SharePoint. In SharePoint non viene supportato [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] configurato per la distinzione tra maiuscole e minuscole o per regole di confronto del server o per regole di confronto del server binarie. Le regole di confronto incompatibili includono regole di confronto che per impostazione predefinita supportano la distinzione tra maiuscole e minuscole o che sono binarie e regole di confronto di base che per impostazione predefinita sono compatibili ma sono state configurate con alcune delle designazioni delle regole di confronto seguenti:  
  
-   **Binario**  
  
-   **Distinzione maiuscole/minuscole**  
  
-   **Punto di codice binario**  
  
 Poiché le regole di confronto del server [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] correnti sono incompatibili, l'aggiornamento è bloccato.  
  
## <a name="corrective-action"></a>Azione correttiva  
 La proprietà delle regole di confronto del server [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] non può essere modificata. Non sarà possibile completare un aggiornamento di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Sarà necessario eseguire la migrazione dell'installazione [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] a un nuovo server che sta utilizzando regole di confronto del server compatibili. Per altre informazioni, vedere gli argomenti seguenti:  
  
-   [Eseguire l'aggiornamento e la migrazione di Reporting Services](https://go.microsoft.com/fwlink/?LinkId=233227)  
  
-   [Selezione delle regole di confronto di SQL Server](https://go.microsoft.com/fwlink/?LinkId=233226)  
  
  
