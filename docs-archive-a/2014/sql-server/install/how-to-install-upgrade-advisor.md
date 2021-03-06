---
title: 'Procedura: installazione di preparazione aggiornamento | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, installing
- Upgrade Advisor [SQL Server], installing
ms.assetid: 481b0704-ce79-4543-b141-67306128aa2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3ed5b66522126bfabc94bfa8036ec6c31ac04500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637056"
---
# <a name="how-to-install-upgrade-advisor"></a>Procedura: Installazione di Preparazione aggiornamento
  Preparazione aggiornamento supporta l'analisi remota di tutti i componenti supportati, ad eccezione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Se non si prevede di analizzare le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è possibile installare Preparazione aggiornamento in qualsiasi computer in grado di connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e che soddisfi i prerequisiti di Preparazione aggiornamento. Se si prevede di analizzare le istanze di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è necessario installare Preparazione aggiornamento nel server di report.  
  
 Per ulteriori informazioni, vedere [installazione di preparazione aggiornamento](../../../2014/sql-server/install/installing-upgrade-advisor.md).  
  
### <a name="to-install-upgrade-advisor"></a>Per installare Preparazione aggiornamento  
  
1.  Avviare l'installazione utilizzando uno dei metodi seguenti:  
  
    -   Se si sta eseguendo l'installazione dal [!INCLUDE[msCoName](../../includes/msconame-md.md)] sito Web, fare clic sul collegamento **download** , quindi fare clic sul pulsante **Esegui** per avviare l'installazione.  
  
    -   Se si sta eseguendo l'installazione dal supporto del prodotto, aprire la cartella **Redist** , aprire la cartella **Preparazione aggiornamento** , quindi fare doppio clic su **SQLUA.msi**.  
  
    > [!NOTE]  
    >  Preparazione aggiornamento richiede [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework 4. Se non è installato, o se si dispone di una versione non definitiva, verrà visualizzato un messaggio di errore. Disinstallare qualsiasi versione precedente di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], quindi installare la versione più recente di .NET Framework 4.  
    >   
    >  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom è un prerequisito per l'installazione [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] di preparazione aggiornamento e non viene installato tramite l'installazione di preparazione aggiornamento. Per il programma di installazione è necessario scaricare e installare [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[tsql](../../includes/tsql-md.md)] ScriptDom dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Feature Pack.  
  
2.  Nella pagina ** [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installazione di preparazione aggiornamento** , fare clic su **Avanti**.  
  
3.  Nella pagina **contratto di licenza** leggere il contratto di licenza. Se si accettano le condizioni, selezionare Accetto **il contratto di licenza** e quindi fare clic su **Avanti**.  
  
4.  Nella pagina **informazioni di registrazione** immettere il nome e la società.  
  
5.  Nella pagina **Selezione funzionalità** esaminare il valore del **percorso di installazione** . Se necessario, utilizzare il pulsante **Sfoglia** per modificare il percorso. Fare clic su **Avanti**.  
  
6.  Nella pagina **pronto per l'installazione del programma** fare clic su **Installa** per installare Upgrade Advisor.  
  
7.  Fare clic su **Fine** per uscire dalla procedura guidata.  
  
## <a name="see-also"></a>Vedere anche  
 [Prerequisiti di Preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-prerequisites.md)  
  
  
