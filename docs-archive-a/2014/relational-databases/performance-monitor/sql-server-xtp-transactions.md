---
title: Transazioni XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 443d67e4-1c7f-41d7-b18d-2d657f58c22a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 75fa8bc9a673d9e0e018b8578a35af2e46b5044c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714243"
---
# <a name="xtp-transactions"></a>XTP Transactions
  L'oggetto prestazione XTP Transactions contiene contatori correlati alle transazioni del motore XTP in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 In questa tabella vengono descritti i contatori delle **transazioni di XTP** .  
  
|Contatore|Descrizione|  
|-------------|-----------------|  
|**Interruzioni a catena/sec**|Numero medio di transazioni di cui è stato eseguito il rollback a causa di un rollback di dipendenza di commit, al secondo.|  
|**Dipendenze di commit acquisite/sec**|Numero medio delle dipendenze di commit acquisite dalle transazioni, al secondo.|  
|**Transazioni di sola lettura preparate/sec**|Numero di transazioni di sola lettura che sono state preparate per l'elaborazione del commit, al secondo.|  
|**Aggiornamenti del punto di salvataggio/sec**|Numero medio di volte in cui un punto di salvataggio "è stato aggiornato", al secondo. L'aggiornamento di un punto di salvataggio avviene quando un punto di salvataggio esistente viene reimpostato sul punto corrente della durata della transazione.|  
|**Rollback del punto di salvataggio/sec**|Numero medio di volte che è stato eseguito il rollback di una transazione a un punto di salvataggio, al secondo.|  
|**Punti di salvataggio creati/sec**|Numero medio di punti di salvataggio creati, al secondo.|  
|**Errori di convalida delle transazioni/sec**|Numero medio di transazioni per cui l'elaborazione di convalida ha avito esito negativo, al secondo.|  
|**Transazioni interrotte dall'utente/sec**|Numero medio di transazioni che sono state interrotte dall'utente, al secondo.|  
|**Transazioni interrotte/sec**|Numero medio di transazioni che sono state interrotte (sia dall'utente che dal sistema), al secondo.|  
|**Transazioni create/sec**|Numero medio di transazioni create nel sistema, al secondo.<br /><br /> Le transazioni XTP sono calcolate in modo diverso rispetto alle transazioni basate su disco (come indicato in Database:Transazioni/sec). Ad esempio, Transazioni create/sec conteggia le transazioni di sola lettura, a differenza di Database:Transazioni/sec.|  
  
## <a name="see-also"></a>Vedere anche  
 [XTP &#40;i contatori delle prestazioni di OLTP in memoria&#41;](../../integration-services/performance/performance-counters.md)  
  
  
