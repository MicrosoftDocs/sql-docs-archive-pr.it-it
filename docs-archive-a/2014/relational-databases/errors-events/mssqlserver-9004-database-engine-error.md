---
title: MSSQLSERVER_9004 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627748"
---
# <a name="mssqlserver_9004"></a>MSSQLSERVER_9004
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|9004|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|LOG_CORRUPT|  
|Testo del messaggio|Si è verificato un errore durante l'elaborazione del log del database '%.*ls'.  Se possibile, ripristinarlo da un backup. Se non è disponibile un backup, potrebbe essere necessario ricompilare il log.|  
  
## <a name="explanation"></a>Spiegazione  
 Si è verificato un errore nell'elaborazione del log durante un'operazione di rollback, recupero o replica. Potrebbe trattarsi di un errore rilevato dal sistema operativo o di un errore di consistenza interno rilevato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="user-action"></a>Azione dell'utente  
 Per correggere l'errore, eseguire una delle operazioni seguenti:  
  
-   Eseguire il ripristino da un backup.  
  
-   Ricompilare il log.  
  
 Esaminare inoltre il registro eventi e il log degli errori di sistema per individuare le cause all'interno del sistema che possono aver generato il problema.  
  
  
