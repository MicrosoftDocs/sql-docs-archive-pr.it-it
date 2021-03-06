---
title: Sottoscrizione, Cronologia sincronizzazione (sottoscrizione di tipo merge, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.synchhistory.f1
- sql12.rep.monitor.subscription.downlevelsynchhistory.f1
ms.assetid: 85f666f6-14ee-4f19-b385-e5cc508aabe4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 49fe19f22976116813ac2454b2d08fc1fe47d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636024"
---
# <a name="subscription-synchronization-history-merge-subscription-sql-server-2005-and-later"></a>Sottoscrizione, Cronologia sincronizzazione (Sottoscrizione di tipo merge, SQL Server 2005 e versioni successive)
  La scheda **Cronologia sincronizzazione** visualizza informazioni dettagliate sull'agente di merge, tra cui lo stato, le statistiche degli articoli, la cronologia, i messaggi informativi e gli eventuali messaggi di errore.  
  
## <a name="options"></a>Opzioni  
 Scegliere le sessioni dell'agente di merge da visualizzare dal menu **Visualizza** e quindi selezionare una sessione specifica nella griglia con l'etichetta **Sessioni dell'agente di merge**. Nella griglia con l'etichetta **Articoli elaborati nella sessione selezionata**vengono visualizzate informazioni dettagliate sulla sessione.  
  
 **Visualizza**  
 Consente di selezionare l'agente di merge da visualizzare.  
  
 **Status**  
 Stato dell'agente di merge al termine della sessione. Nell'elenco seguente vengono indicati i valori di stato possibili:  
  
-   Errore  
  
-   Completi  
  
-   Nuovo tentativo in corso  
  
-   In esecuzione  
  
 **Start Time**  
 Ora di inizio della sessione.  
  
 **Ora fine**  
 Ora di fine della sessione. Se l'agente non è arrestato, questo campo è vuoto.  
  
 **Duration**  
 Quantità di tempo di esecuzione dell'agente di merge in una sessione. Il valore di durata rappresenta il tempo trascorso se l'agente è ancora in esecuzione e la durata totale se l'agente è stato eseguito in precedenza.  
  
 **Comandi caricati**  
 Numero di righe caricate durante la sessione dell'agente di merge.  
  
 **Comandi scaricati**  
 Numero di righe scaricate durante la sessione dell'agente di merge.  
  
 **Messaggio di errore**  
 Se una sessione è terminata con un errore, in questo campo viene visualizzato l'ultimo messaggio di errore registrato dall'agente di merge. Se una sessione non è terminata con un errore, questo campo è vuoto.  
  
 **Articolo**  
 Il nome di ogni articolo della pubblicazione e le fasi di elaborazione seguenti per l'intera pubblicazione:  
  
-   **Inizializzazione**. Si riferisce all'avvio dell'agente di merge e non all'inizializzazione di una sottoscrizione, che invece implica l'applicazione di uno snapshot.  
  
-   **Modifiche dello schema e inserimenti bulk**.  
  
-   **Carica modifiche nel server di pubblicazione**.  
  
-   **Download modifiche nel Sottoscrittore**.  
  
 Le fasi sono incluse in modo che nella griglia sia possibile visualizzare la quantità di tempo e la percentuale della durata totale riferite a ogni fase della sessione selezionata.  
  
 **% del totale**  
 Percentuale del tempo di elaborazione totale riferita a ogni fase della sessione selezionata.  
  
 **Duration**  
 Quantità di tempo utilizzata per ogni fase di elaborazione. Il valore di durata rappresenta il tempo trascorso se l'agente di merge è attualmente in esecuzione per la sessione e la durata totale se l'agente di merge è stato eseguito in precedenza.  
  
 **Inserts**  
 Numero di righe inserite nella fase specifica della sessione selezionata.  
  
 **Aggiornamenti**  
 Numero di righe aggiornate nella fase specifica della sessione selezionata.  
  
 **Eliminazioni**  
 Numero di righe eliminate nella fase specifica della sessione selezionata.  
  
 **Conflitti**  
 Numero di conflitti nella sessione selezionata.  
  
 **Modifiche dello schema**  
 Numero di modifiche dello schema nella sessione selezionata. Le modifiche dello schema possono dipendere da modifiche dello schema apportate al database della pubblicazione, dall'aggiunta o eliminazione di articoli e da modifiche delle proprietà dell'articolo o della pubblicazione.  
  
 **Ultimo messaggio della sessione selezionata**  
 In quest'area di testo viene visualizzato l'ultimo messaggio della sessione selezionata. Se si è verificato un errore, vengono visualizzate informazioni dettagliate sull'errore e il comando di cui si è tentata l'esecuzione al momento dell'errore. Sono inoltre disponibili collegamenti a contenuto aggiuntivo correlato all'errore.  
  
## <a name="see-also"></a>Vedere anche  
 [Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md)   
 [Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md)   
 [Monitoraggio della replica](monitoring-replication.md)   
 [Panoramica degli agenti di replica](agents/replication-agents-overview.md)  
  
  
