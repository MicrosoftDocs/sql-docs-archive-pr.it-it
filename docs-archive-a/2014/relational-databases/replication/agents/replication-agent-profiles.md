---
title: Profili degli agenti di replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Distribution Agent, profiles
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- Merge Agent, profiles
- agents [SQL Server replication], profiles
- Queue Reader Agent, profiles
- profiles [SQL Server], replication agents
- Snapshot Agent, profiles
- Log Reader Agent, profiles
ms.assetid: 0e980725-e42f-4283-94cb-d8a6dba5df62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 985d6788d1a8df3ca0c6bfaa463299295ef66102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626662"
---
# <a name="replication-agent-profiles"></a>Profili degli agenti di replica
  Durante la configurazione della replica viene installato nel server di distribuzione un set di profili agenti. Un profilo agente contiene un set di parametri utilizzati a ogni esecuzione dell'agente. Durante il processo di avvio ogni agente esegue l'accesso al server di distribuzione ed esegue una query dei parametri nel proprio profilo. Nelle sottoscrizioni di tipo merge che utilizzano la sincronizzazione tramite il Web, i profili vengono scaricati e archiviati nel Sottoscrittore. Se il profilo viene modificato, il profilo nel Sottoscrittore viene aggiornato alla successiva esecuzione dell'agente di merge. Per ulteriori informazioni sulla sincronizzazione Web, vedere [Web Synchronization for Merge Replication](../web-synchronization-for-merge-replication.md).  
  
 Per ogni agente viene fornito un profilo predefinito, mentre per l'agente di lettura log, l'agente di distribuzione e l'agente di merge vengono creati profili predefiniti aggiuntivi. Oltre a questi profili, è possibile creare profili specifici in base alle esigenze dell'applicazione. Un profilo agente consente di modificare rapidamente i parametri chiave per tutti gli agenti associati. Se, ad esempio, sono disponibili 20 agenti snapshot ed è necessario modificare il valore di timeout delle query (il parametro **-QueryTimeout** ), è possibile aggiornare il profilo utilizzato dagli agenti snapshot. Tutti gli agenti di quel tipo utilizzeranno automaticamente il nuovo valore alla successiva esecuzione.  
  
 È inoltre possibile configurare profili diversi per istanze diverse di un agente. Ad esempio, un agente di merge che si connette al server di pubblicazione o al server di distribuzione tramite una connessione remota può utilizzare un set di parametri adeguato a un collegamento più lento, scegliendo il profilo **collegamento lento** .  
  
> [!NOTE]  
>  Se si specifica un valore per un parametro dell'agente nella riga di comando, tale valore ha la precedenza sul valore impostato per lo stesso parametro nel profilo dell'agente.  
  
 **Per utilizzare e modificare i profili degli agenti**  
  
-   [Usare i profili agenti di replica](replication-agent-profiles.md)  
  
## <a name="snapshot-agent-profiles"></a>Profili degli agenti snapshot  
 Nella tabella seguente vengono illustrati i parametri definiti nel profilo predefinito per l'agente snapshot. Per ulteriori informazioni su questi parametri, vedere [Replication Snapshot Agent](replication-snapshot-agent.md).  
  
||default|  
|-|-------------|  
|**-BcpBatchSize**|100000|  
|**-HistoryVerboseLevel**|2|  
|**-LoginTimeout**|15|  
|**-QueryTimeout**|1800|  
  
## <a name="log-reader-agent-profiles"></a>Profili dell'agente di lettura log  
 Nella tabella seguente vengono illustrati i parametri definiti nei profili per l'agente di lettura log. Ogni colonna della tabella rappresenta un profilo denominato. Per ulteriori informazioni su questi parametri, vedere [Replication Log Reader Agent](replication-log-reader-agent.md).  
  
||default|cronologia dettagliata|  
|-|-------------|---------------------|  
|**-HistoryVerboseLevel**|1|2|  
|**-LoginTimeout**|15|15|  
|**-LogScanThreshold**|500000|500000|  
|**-PollingInterval**|5|5|  
|**-QueryTimeout**|1800|1800|  
|**-ReadBatchSize**|500|500|  
  
## <a name="distribution-agent-profiles"></a>Profili dell'agente di distribuzione  
 Nella tabella seguente vengono illustrati i parametri definiti nei profili per l'agente di distribuzione. Ogni colonna della tabella rappresenta un profilo denominato. Per ulteriori informazioni su questi parametri, vedere [Replication Distribution Agent](replication-distribution-agent.md).  
  
||default|cronologia dettagliata|Gestione sincronizzazione Microsoft Windows|Continua in caso di errori di consistenza dei dati|Profilo di distribuzione per flussi OLEDB|  
|-|-------------|---------------------|-------------------------------------|-----------------------------------------|----------------------------------------------|  
|**-BcpBatchSize**|100000|100000|1000|100000|2147473647|  
|**-CommitBatchSize**|100|100|100|100|100|  
|**-CommitBatchThreshold**|1000|1000|1000|1000|1000|  
|**-HistoryVerboseLevel**|1|2|1|1|1|  
|**-KeepAliveMessageInterval**|300|300|300|300|300|  
|**-LoginTimeout**|15|15|15|15|15|  
|**-MaxBcpThreads**|1|1|1|1|1|  
|**-MaxDeliveredTransactions**|0|0|0|0|0|  
|**-OledbStreamThreshold**|NULL|NULL|NULL|NULL|32768|  
|**-PacketSize**|NULL|NULL|NULL|NULL|32768|  
|**-PollingInterval**|5|5|5|5|5|  
|**-QueryTimeout**|1800|1800|1800|1800|1800|  
|**-SkipErrors**|NULL|NULL|NULL|**-SkipErrors** 2601:2627:20598|NULL|  
|**-TransactionsPerHistory**|100|100|100|100|100|  
|**-UseOledbStreaming**|NULL|NULL|NULL|NULL|**-UseOledbStreaming**|  
  
## <a name="merge-agent-profiles"></a>Profili dell'agente di merge  
 Nella tabella seguente vengono illustrati i parametri definiti nei profili per l'agente di merge. Ogni colonna della tabella rappresenta un profilo denominato. Per ulteriori informazioni su questi parametri, vedere [Replication Merge Agent](replication-merge-agent.md).  
  
||default|cronologia dettagliata|Gestione sincronizzazione Microsoft Windows|convalida mediante conteggio delle righe|convalida eseguita mediante conteggio delle righe e checksum|collegamento lento|server-server per volumi elevati|  
|-|-------------|---------------------|-------------------------------------|-------------------------|--------------------------------------|---------------|------------------------------------|  
|**-BcpBatchSize**|100000|100000|1000|100000|100000|100000|100000|  
|**-ChangesPerHistory**|100|50|50|100|100|100|1000|  
|**-DestThreads**|2|1|1|1|1|1|4|  
|**-DownloadGenerationsPerBatch**|50|50|50|50|50|1|500|  
|**-DownloadReadChangesPerBatch**|100|100|100|100|100|100|100|  
|**-DownloadWriteChangesPerBatch**|100|100|100|100|100|100|100|  
|**-FastRowCount**|1|1|1|1|1|1|1|  
|**-HistoryVerboseLevel**|2|3|1|1|2|1|2|  
|**-KeepAliveMessageInterval**|300|300|300|300|300|300|300|  
|**-LoginTimeout**|15|15|15|15|15|15|15|  
|**-MaxDownloadChanges**|0|0|0|0|0|0|0|  
|**-MaxUploadChanges**|0|0|0|0|0|0|0|  
|**-MetadataRetentionCleanup**|1|1|1|1|1|1|1|  
|**-NumDeadlockRetries**|5|5|5|5|5|5|5|  
|**-ParallelUploadDownload**|NULL|NULL|NULL|NULL|NULL|NULL|1|  
|**-PollingInterval**|60|60|60|60|60|60|60|  
|**-QueryTimeout**|300|300|300|300|300|300|600|  
|**-QueueSizeMultiplier**|NULL|NULL|NULL|NULL|NULL|NULL|5|  
|**-SrcThreads**|2|2|2|2|2|1|3|  
|**-StartQueueTimeout**|0|0|0|0|0|0|0|  
|**-UploadGenerationsPerBatch**|50|50|50|50|50|1|500|  
|**-UploadReadChangesPerBatch**|100|100|100|100|100|100|100|  
|**-UploadWriteChangesPerBatch**|100|100|100|100|100|100|100|  
|**-Validate**|0|0|0|1|3|0|0|  
|**-ValidateInterval**|60|60|60|60|60|60|60|  
  
## <a name="queue-reader-agent-profiles"></a>Profili dell'agente di lettura coda  
 Nella tabella seguente vengono illustrati i parametri definiti nel profilo predefinito per l'agente di lettura coda. Per ulteriori informazioni su questi parametri, vedere [Replication Queue Reader Agent](replication-queue-reader-agent.md).  
  
||default|  
|-|-------------|  
|**-HistoryVerboseLevel**|1|  
|**-LoginTimeout**|15|  
|**-PollingInterval**|5|  
|**-QueryTimeout**|1800|  
  
## <a name="see-also"></a>Vedere anche  
 [Amministrazione dell'agente di replica](replication-agent-administration.md)   
 [Visualizzare e modificare i parametri del prompt dei comandi dell'agente di replica &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md)   
 [Replication Agent Executables Concepts](../concepts/replication-agent-executables-concepts.md)  
  
  
