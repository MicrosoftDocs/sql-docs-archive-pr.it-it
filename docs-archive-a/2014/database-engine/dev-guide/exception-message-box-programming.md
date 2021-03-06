---
title: Programmazione della finestra di messaggio eccezione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- ExceptionMessageBox class, about ExceptionMessageBox class
- exception message box [SQL Server], about exception message box
- exception message box [SQL Server]
- interfaces [SQL Server]
- exceptions [SQL Server]
- messages [SQL Server], exception message box
ms.assetid: 0b1ba514-6959-4e69-bfd2-3cf3c1ac4b9c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2425169f838199ce24b4331dd57c74b480adf62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726216"
---
# <a name="exception-message-box-programming"></a>Programmazione della finestra di messaggio eccezione
  La finestra di messaggio eccezione è un'interfaccia a livello di codice installata con e utilizzata dai [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componenti grafici di. La finestra di messaggio eccezione è un assembly gestito supportato che è possibile utilizzare nelle applicazioni per fornire un controllo significativamente maggiore sulla messaggistica e per offrire agli utenti la possibilità di salvare il contenuto dei messaggi di errore per riferimento futuro, nonché per ottenere informazioni sui messaggi. Poiché la finestra di messaggio eccezione viene installata in tutte le edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ad eccezione di [!INCLUDE[ssEW](../../includes/ssew-md.md)] , è possibile utilizzarla senza alcuna configurazione aggiuntiva in qualsiasi computer in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono stati installati i componenti client.  
  
 La classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> dello spazio dei nomi di <xref:Microsoft.SqlServer.MessageBox> presenta, tra le altre, tutte le funzionalità della classe <xref:System.Windows.Forms.MessageBox>. Ideale per qualsiasi attività per la quale potrebbe essere utilizzata la classe <xref:System.Windows.Forms.MessageBox>, la classe <xref:Microsoft.SqlServer.MessageBox.ExceptionMessageBox> è stata progettata per gestire in modo elegante le eccezioni del codice gestito. La finestra di messaggio eccezione consente di eseguire le operazioni seguenti:  
  
-   Fornire testo per pulsanti personalizzato per un numero massimo di cinque pulsanti. Le dimensioni dei pulsanti e della finestra di dialogo vengono modificate automaticamente per adeguarsi alla lunghezza del testo.  
  
-   Consentire agli utenti di copiare facilmente il testo e il titolo del messaggio, il testo del pulsante e gli eventuali collegamenti alla Guida negli Appunti o di inviare queste informazioni in un messaggio di posta elettronica.  
  
-   Visualizza tutti gli errori e le eccezioni sottostanti in un albero delle relazioni gerarchiche quando gli utenti fanno clic su **informazioni aggiuntive**.  
  
-   Consentire agli utenti di decidere se visualizzare nuovamente il messaggio quando si verifica la stessa eccezione.  
  
-   Accedere a un sistema di Guida online tramite un collegamento alla Guida associato all'eccezione.  
  
 Per ulteriori informazioni, vedere la [finestra di messaggio eccezione programma](../../../2014/database-engine/dev-guide/program-exception-message-box.md).  
  
  
