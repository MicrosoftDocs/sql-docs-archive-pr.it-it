---
title: Gestione connessione MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636348"
---
# <a name="msmq-connection-manager"></a>gestione connessione MSMQ
  Una gestione connessione MSMQ consente la connessione di un pacchetto a una coda di messaggi che utilizza MSMQ (Message Queuing, Accodamento messaggi). La gestione connessione MSMQ viene usata dall'attività Message Queue inclusa in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 Quando si aggiunge una gestione connessione MSMQ a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione MSMQ, imposta le proprietà di tale gestione connessione, quindi la aggiunge alla raccolta `Connections` del pacchetto. La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `MSMQ`.  
  
 Per configurare la gestione connessione MSMQ, procedere nel modo seguente:  
  
-   Specificare una stringa di connessione.  
  
-   Specificare il percorso della coda di messaggi a cui connettersi.  
  
 Il formato del percorso dipende dal tipo di coda, come illustrato nella tabella seguente.  
  
|Tipo di coda|Percorso di esempio|  
|----------------|-----------------|  
|Pubblico|\<computer name>\\<nome della coda\>|  
|Privato|\<computer name>\Private$\\<nome della coda\>|  
  
 Per rappresentare il computer locale è possibile utilizzare un punto (.).  
  
## <a name="configuration-of-the-msmq-connection-manager"></a>Configurazione della gestione connessione MSMQ  
 È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.  
  
 Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione MSMQ](../msmq-connection-manager-editor.md).  
  
 Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Attività Message Queue](../control-flow/message-queue-task.md)   
 [Connessioni in Integration Services &#40;SSIS&#41;](integration-services-ssis-connections.md)  
  
  
