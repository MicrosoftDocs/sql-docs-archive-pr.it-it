---
title: Aggiungere SQL Server nodo del cluster di failover | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e5035122-784f-40ee-8188-7f485a9ae3e8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a4cad03db71b6736b7c590aabc7682eda04ec9a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628247"
---
# <a name="add-sql-server-failover-cluster-node"></a>Aggiunta di un nodo del cluster di failover di SQL Server
  Prima che l'operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] venga completata, viene convalidata la configurazione del computer. Durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguita l'analisi del computer in cui verrà installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite Controllo configurazione sistema. Questo strumento consente di verificare le condizioni che impediscono la corretta operazione di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Prima dell'avvio dell'installazione guidata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , lo strumento recupera le informazioni sullo stato di ciascun elemento. Il risultato viene confrontato con i requisiti, quindi vengono fornite indicazioni per la rimozione di eventuali problemi che impediscono di proseguire.  
  
 Con il controllo della configurazione di sistema viene generato un report con una breve descrizione di ogni regola eseguita, nonché lo stato dell'esecuzione. Il report di controllo della configurazione di sistema si trova nel percorso%Programmi%\Microsoft SQL Server\120\Setup Bootstrap\Log \\<YYYYMMDD_HHMM>\\ .  
  
 Prima di eseguire l'operazione di installazione, esaminare i seguenti argomenti:  
  
1.  [Requisiti hardware e software per l'installazione di SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [Funzionalità supportate dalle edizioni di SQL Server 2014](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [Considerazioni sulla sicurezza per un'installazione di SQL Server](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [Versioni in lingua locale di SQL Server](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 Altri riferimenti:  
  
1.  [Aggiornamenti di versione ed edizione supportati](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [Operazioni preliminari all'installazione del clustering di failover](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Regole di installazione](../../../2014/sql-server/install/install-rules.md)  
  
  
