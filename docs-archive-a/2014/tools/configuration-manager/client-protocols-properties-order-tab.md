---
title: Proprietà-protocolli client (scheda ordine) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713648"
---
# <a name="client-protocols-properties-order-tab"></a>Proprietà - Protocolli client (scheda Ordine)
  Usare la pagina **Ordine**della finestra di dialogo **Proprietà protocolli client** per visualizzare e abilitare i protocolli client.  
  
 Fare clic su un protocollo e quindi su **Abilita** o **Disabilita** per spostare il protocollo selezionato nell'elenco **Protocolli disabilitati** o **Protocolli abilitati** .  
  
 I protocolli vengono utilizzati nell'ordine dell'elenco, ovvero viene effettuato un tentativo di connessione con il primo protocollo, quindi con il secondo e così via. Per spostare un protocollo verso l'alto o verso il basso nell'elenco **Protocolli abilitati** , fare clic sui pulsanti freccia. Se ci si connette a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client installato nello stesso computer, verrà sempre eseguito un primo tentativo di connessione con il protocollo **Shared Memory**, se abilitato.  
  
> [!NOTE]  
>  Queste impostazioni non vengono usate da [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient. L'ordine dei protocolli per .NET SqlClient è TCP, quindi named pipe e non può essere modificato.  
  
## <a name="options"></a>Opzioni  
 **Protocolli disabilitati**  
 Include un elenco dei protocolli installati ma non in uso.  
  
 **Protocolli abilitati**  
 Elenca i protocolli disponibili per [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i client di questo computer.  
  
 **>**  
 Abilita il protocollo selezionato nella casella **Protocolli disabilitati** , spostandolo nella casella **Protocolli abilitati** .  
  
 **\<**  
 Disabilita il protocollo selezionato nella casella **Protocolli abilitati** , spostandolo nella casella **Protocolli disabilitati** .  
  
 Freccia in su  
 Sposta il protocollo selezionato verso l'alto nell'elenco. In tal modo, è possibile aumentare le priorità in base alla quale la libreria di rete tenterà di utilizzare il protocollo selezionato per le connessioni.  
  
 Freccia GIÙ  
 Sposta il protocollo selezionato verso il basso nell'elenco. In tal modo, è possibile diminuire il grado di priorità in base alla quale la libreria di rete tenterà di utilizzare il protocollo selezionato per le connessioni.  
  
 **Abilita protocollo di memoria condivisa**  
 Abilita il protocollo di memoria condivisa, che, se abilitato, viene sempre usato per primo per tentare una connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da un client installato nello stesso computer.  
  
> [!NOTE]  
>  Se il protocollo viene specificato tramite un prefisso o come parte della stringa di connessione, viene eseguito un tentativo solo con il protocollo specificato.  
  
## <a name="see-also"></a>Vedere anche  
 [Scelta di un protocollo di rete](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
