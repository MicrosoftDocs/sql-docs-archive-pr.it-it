---
title: Sottoscrizione, Cronologia server di pubblicazione - database di distribuzione (sottoscrizione transazionale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.pubtodist.tran.f1
ms.assetid: d5a4c697-1342-49fd-8b7b-b059af32556a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3806c59e545e325fa7e60f2cd92a4b990b0505cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726884"
---
# <a name="subscription-publisher-to-distributor-history-transactional-subscription"></a>Sottoscrizione, Cronologia server di pubblicazione - server di distribuzione (sottoscrizione transazionale)
  Nella scheda **Cronologia server di pubblicazione - server di distribuzione** vengono visualizzate informazioni dettagliate sull'agente di lettura log, quali lo stato, la cronologia, i messaggi informativi ed eventuali messaggi di errore.  
  
## <a name="options"></a>Opzioni  
 Scegliere le sessioni dell'agente di lettura log da visualizzare dal menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con etichetta **Sessioni dell'agente di lettura log**. Nella griglia con etichetta **Azioni nella sessione selezionata**verranno visualizzate informazioni dettagliate sulla sessione selezionata. Se la sessione selezionata è terminata con un errore, verrà inoltre visualizzata l'area di testo con etichetta **Messaggio o dettagli errore della sessione selezionata** .  
  
 **Visualizzazione**  
 Selezionare le sessioni dell'agente di lettura log da visualizzare. L'agente di lettura log in genere viene eseguito in modo continuo, pertanto potrebbe essere disponibile una sola sessione da visualizzare.  
  
 **Status**  
 Stato dell'agente di lettura log. Nell'elenco seguente vengono indicati i valori di stato possibili:  
  
-   Errore  
  
-   Completi  
  
-   Nuovo tentativo in corso  
  
-   In esecuzione  
  
 **Ora di inizio**  
 Ora di inizio della sessione.  
  
 **Ora di fine**  
 Ora di fine della sessione. Se l'agente non è arrestato, questo campo è vuoto.  
  
 **Duration**  
 Periodo di tempo durante il quale l'agente di lettura log è stato eseguito in questa sessione. Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale della sessione se la sessione dell'agente è terminata.  
  
 **Messaggio di errore**  
 Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di lettura log. Se una sessione non è terminata con un errore, questo campo è vuoto.  
  
 **Messaggio azione**  
 Tutti i messaggi informativi e i messaggi di errore registrati dall'agente di lettura log durante la sessione selezionata.  
  
 **Ora azione**  
 Ora di esecuzione dell'azione descritta nella colonna **Messaggio azione** .  
  
 **Messaggio o dettagli errore della sessione selezionata**  
 Area visualizzata solo se per la sessione selezionata è visualizzato il valore **Errore** nella colonna **Stato** . In questa area di testo vengono visualizzate informazioni dettagliate sull'errore e viene indicato il comando di cui è stata tentata l'esecuzione quando si è verificato l'errore. Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.  
  
## <a name="see-also"></a>Vedere anche  
 [Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md)   
 [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md)   
 [Monitoraggio della replica](monitoring-replication.md)   
 [Panoramica degli agenti di replica](agents/replication-agents-overview.md)  
  
  
