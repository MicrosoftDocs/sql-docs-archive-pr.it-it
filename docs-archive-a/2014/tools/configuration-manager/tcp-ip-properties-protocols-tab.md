---
title: Proprietà TCP-IP (scheda protocolli) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624500"
---
# <a name="tcp---ip-properties-protocols-tab"></a>Proprietà TCP-IP (scheda protocolli)
  La finestra di dialogo **Proprietà - TCP/IP** consente di configurare le opzioni relative al protocollo TCP/IP. Fare clic su **TCP/IP** nel riquadro sinistro per visualizzare le configurazioni dei singoli indirizzi IP nel riquadro dei dettagli.  
  
 Per rendere effettive le modifiche, è necessario riavviare Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="options"></a>Opzioni  
 **Enabled**  
 I valori possibili sono **Sì** e **No**.  
  
 **Keep-alive**  
 Specificare l'intervallo, in millisecondi, in cui i pacchetti keep-alive vengono trasmessi per verificare che il computer remoto sia ancora disponibile.  
  
 **Attesa su tutti**  
 Specificare se SQL Server resterà in attesa su tutti gli indirizzi IP associati alle schede di rete del computer. Se è impostato su **No**, configurare separatamente ogni indirizzo IP usando la finestra di dialogo delle proprietà dei singoli indirizzi. Se è impostato su **Sì**, le impostazioni della casella delle proprietà relative a **IPAll** verranno applicate a tutti gli indirizzi IP. Il valore predefinito è **Sì**.  
  
 **Nessun ritardo**  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non implementa modifiche a questa proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Scelta di un protocollo di rete](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)   
 [Creazione di una stringa di connessione valida con TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
