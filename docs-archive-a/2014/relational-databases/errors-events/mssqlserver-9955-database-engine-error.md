---
title: MSSQLSERVER_9955 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627729"
---
# <a name="mssqlserver_9955"></a>MSSQLSERVER_9955
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|9955|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|FTXT2_MSSEARCHACCESSDENY|  
|Testo del messaggio|Impossibile creare la named pipe '%ls' per comunicare con il daemon di filtri full-text (errore di Windows: %d). Una named pipe esiste già per il processo host del daemon di filtri, il sistema non dispone di risorse sufficienti oppure la ricerca del numero di identificazione di sicurezza (SID) per il gruppo account del daemon di filtri non è riuscita. Per risolvere il problema, interrompere eventuali processi del daemon di filtri full-text in esecuzione e, se necessario, riconfigurare l'account di servizio dell'utilità di avvio del daemon full-text.|  
  
## <a name="explanation"></a>Spiegazione  
 Questo messaggio viene visualizzato quando in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è possibile creare una named pipe per comunicare con il daemon di filtri full-text. Una named pipe esiste già per il processo host del daemon di filtri, il sistema non dispone di risorse sufficienti oppure la ricerca del numero di identificazione di sicurezza (SID) per il gruppo account del daemon di filtri non è riuscita.  
  
## <a name="user-action"></a>Azione dell'utente  
 Per risolvere il problema, interrompere eventuali processi del daemon di filtri full-text in esecuzione e, se necessario, riconfigurare l'account host del daemon full-text utilizzando Gestione configurazione SQL Server.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestione configurazione SQL Server](../sql-server-configuration-manager.md)   
 [Impostare l'account del servizio per l'utilità di avvio del daemon filtri full-text](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md)   
 [Ricerca full-text](../search/full-text-search.md)  
  
  
