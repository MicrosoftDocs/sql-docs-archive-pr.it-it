---
title: Attività Esegui processo di SQL Server Agent (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.executejob.f1
helpviewer_keywords:
- Execute SQL Server Agent Job Task dialog box
ms.assetid: 4ed75956-ebb8-4d8c-9c16-fc0eb00bd3a0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b997d5144b113102ba0ed2d9d1df59b6707acbee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635565"
---
# <a name="execute-sql-server-agent-job-task-maintenance-plan"></a>Attività Esegui processo di SQL Server Agent (Piano di manutenzione)
  Utilizzare la finestra di dialogo **Attività Esegui processo di SQL Server Agent** per eseguire i processi di Microsoft SQL Server Agent nell'ambito di un piano di manutenzione. Questa opzione non sarà disponibile se la connessione selezionata non contiene alcun processo di SQL Server Agent.  
  
 Questa attività usa l'istruzione **.sp_start_job** .  
  
## <a name="ui-element-list"></a>Elenco di elementi dell'interfaccia utente  
 **Connection**  
 Consente di selezionare la connessione server da utilizzare per l'esecuzione dell'attività.  
  
 **Nuovo**  
 Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività. La finestra di dialogo **Nuova connessione** è descritta di seguito.  
  
 **Processi di SQL Server Agent disponibili**  
 Consente di selezionare il processo da eseguire. Nella griglia vengono visualizzati il **Nome processo** e la **Descrizione** per identificare i processi.  
  
 **Visualizza codice T-SQL**  
 Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.  
  
> [!NOTE]  
>  Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.  
  
## <a name="new-connection-dialog-box"></a>Finestra di dialogo Nuova connessione  
 **Nome connessione**  
 Consente di immettere un nome per la nuova connessione.  
  
 **Selezionare o immettere il nome di un server**  
 Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.  
  
 **Aggiorna**  
 Consente di aggiornare l'elenco dei server disponibili.  
  
 **Immettere le informazioni per l'accesso al server**  
 Consente di specificare le opzioni di autenticazione per l'accesso al server.  
  
 **Usa la sicurezza integrata di Windows NT**  
 Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di Microsoft Windows.  
  
 **Usa nome utente e password specifici**  
 Consente di connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Questa opzione non è disponibile.  
  
 **Nome utente**  
 Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione. Questa opzione non è disponibile.  
  
 **Password**  
 Consente di specificare una password da utilizzare per l'autenticazione. Questa opzione non è disponibile.  
  
## <a name="see-also"></a>Vedere anche  
 [sp_add_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-job-transact-sql)   
 [Creazione di un processo](../../ssms/agent/create-a-job.md)   
 [sp_start_job &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-start-job-transact-sql)  
  
  
