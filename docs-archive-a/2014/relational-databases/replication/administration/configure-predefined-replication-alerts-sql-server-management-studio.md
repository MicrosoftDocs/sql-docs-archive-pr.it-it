---
title: Configurare gli avvisi di replica predefiniti (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- predefined replication alerts [SQL Server replication]
ms.assetid: c0414147-7ffe-4f9a-908c-71c1b5201584
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aa78a08757cc7bbe809c5e3a1808c9632b76763a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725576"
---
# <a name="configure-predefined-replication-alerts-sql-server-management-studio"></a>Configurazione degli avvisi di replica predefiniti (SQL Server Management Studio)
  La replica offre gli avvisi predefiniti seguenti, configurabili in risposta a eventi di replica:  
  
-   **Replica: operazione dell'agente riuscita**    
-   **Replica: errore dell'agente**    
-   **Replica: nuovo tentativo dell'agente**    
-   **Replica: eliminata sottoscrizione scaduta**    
-   **Replica: la sottoscrizione è stata reinizializzata dopo l'errore di convalida**    
-   **Replica: la convalida dei dati nel Sottoscrittore non è riuscita**    
-   **Replica: la convalida dei dati nel Sottoscrittore è riuscita**    
-   **Replica: arresto dell'agente personalizzato**  
  
 Configurare questi avvisi nella cartella **Avvisi** in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o nella scheda **Avvisi** in Monitoraggio replica. Per ulteriori informazioni sull'accesso a questa scheda, vedere [visualizzare le informazioni ed eseguire attività tramite Monitoraggio replica](../monitor/view-information-and-perform-tasks-replication-monitor.md).  
  
 In aggiunta a questi avvisi, in Monitoraggio replica è disponibile un set di avvisi relativi allo stato e alle prestazioni. Per ulteriori informazioni, vedere [impostare soglie e avvisi nell'infrastruttura di avvisi di monitoraggio replica](../monitor/set-thresholds-and-warnings-in-replication-monitor.md) . Per altre informazioni, vedere [Creare un evento definito dall'utente](../../../ssms/agent/create-a-user-defined-event.md).  
  
### <a name="to-configure-a-predefined-replication-alert-in-management-studio"></a>Per configurare un avviso di replica predefinito in Management Studio  
  
1.  Connettersi al database di distribuzione in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], quindi espandere il nodo del server.    
2.  Espandere la cartella **SQL Server Agent** e quindi la cartella **Avvisi** .    
3.  Fare clic con il pulsante destro del mouse su un avviso di replica e quindi scegliere **Proprietà**.    
4.  Impostare le opzioni nella finestra di dialogo **Proprietà dell'avviso \<AlertName>** :    
    -   Nella pagina **Generale** fare clic su **Abilita**e specificare il database a cui si desidera applicare l'avviso.    
    -   Nella pagina **Risposta** specificare se si desidera inviare un messaggio di posta elettronica e/o eseguire un processo.  
  
         Se l'avviso è **Replica: la convalida dei dati nel Sottoscrittore non è riuscita**, è possibile specificare il processo di risposta della replica per questo avviso: Selezionare **Esegui processo** e quindi fare clic sul pulsante Sfoglia ( **...** ). Nella finestra di dialogo **Individua processo** fare clic su **Sfoglia**. Nella finestra di dialogo **Cerca oggetti** selezionare **Reinizializzazione delle sottoscrizioni con errori di convalida dei dati**. Fare clic su **OK** in entrambe le finestre di dialogo aperte. Durante l'esecuzione il processo utilizza una chiamata di procedura remota (RPC) a una stored procedure che reinizializza la sottoscrizione. Se il server di pubblicazione utilizza un server di distribuzione remoto, è necessario definire un account di accesso al server remoto sul server di pubblicazione in modo che sia possibile eseguire la chiamata di procedura remota (RPC) dal server di distribuzione al server di pubblicazione.   
    -   Nella pagina **Opzioni** personalizzare il testo della risposta.    
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-configure-an-alert-for-a-threshold-in-replication-monitor"></a>Per configurare un avviso per una soglia in Monitoraggio replica  
  
1.  Nella scheda **Avvisi** fare clic su **Configura avvisi**.    
2.  Nella finestra di dialogo **Configura avvisi di replica** selezionare un avviso e quindi fare clic su **Configura**.    
3.  Impostare le opzioni nella finestra di dialogo **Proprietà dell'avviso \<AlertName>** :    
    -   Nella pagina **Generale** fare clic su **Abilita**e specificare il database a cui si desidera applicare l'avviso.    
    -   Nella pagina **Risposta** specificare se si desidera inviare un messaggio di posta elettronica e/o eseguire un processo.    
         Se l'avviso è **Replica: la convalida dei dati nel Sottoscrittore non è riuscita**, è possibile specificare il processo di risposta della replica per questo avviso: Selezionare **Esegui processo** e quindi fare clic sul pulsante Sfoglia ( **...** ). Nella finestra di dialogo **Individua processo** fare clic su **Sfoglia**. Nella finestra di dialogo **Cerca oggetti** selezionare **Reinizializzazione delle sottoscrizioni con errori di convalida dei dati**. Fare clic su **OK** in entrambe le finestre di dialogo aperte. Durante l'esecuzione il processo utilizza una chiamata di procedura remota (RPC) a una stored procedure che reinizializza la sottoscrizione. Se il server di pubblicazione utilizza un server di distribuzione remoto, è necessario definire un account di accesso al server remoto sul server di pubblicazione in modo che sia possibile eseguire la chiamata di procedura remota (RPC) dal server di distribuzione al server di pubblicazione.   
    -   Nella pagina **Opzioni** personalizzare il testo della risposta.    
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]    
5.  Fare clic su **Close**.  
  
## <a name="see-also"></a>Vedere anche  
 [Usare gli avvisi per gli eventi degli agenti di replica](../agents/use-alerts-for-replication-agent-events.md)  
  
  
