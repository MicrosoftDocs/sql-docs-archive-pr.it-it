---
title: 'Proprietà processo: nuovo processo (pagina notifiche) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624506"
---
# <a name="job-properties-new-job-notifications-page"></a>Proprietà processo: Nuovo processo (pagina Notifiche)
  Utilizzare questa pagina per impostare le azioni [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che Agent deve eseguire al completamento del processo.  
  
## <a name="options"></a>Opzioni  
 **Posta elettronica**  
 Selezionare questa opzione per inviare un messaggio di posta elettronica al completamento del processo. Dopo aver selezionato questa opzione, specificare l'operatore a cui inviare la notifica e la condizione che attiverà tale notifica: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.  
  
 **Page**  
 Selezionare questa opzione per inviare un messaggio di posta elettronica al cercapersone di un operatore al completamento del processo. Dopo aver selezionato questa opzione, specificare l'operatore a cui inviare la notifica e la condizione che attiverà tale notifica: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.  
  
 **NET SEND**  
 Selezionare questa opzione se al completamento del processo si desidera inviare la notifica all'operatore tramite Net Send. Dopo aver selezionato questa opzione, specificare l'operatore a cui inviare la notifica e la condizione che attiverà tale notifica: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.  
  
 **Scrivi nel registro eventi applicazioni di Windows**  
 Selezionare questa opzione per scrivere una voce nel registro degli eventi dell'applicazione al completamento del processo. Dopo aver selezionato questa opzione, specificare la condizione che causerà la scrittura della voce: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.  
  
 **Elimina il processo automaticamente**  
 Selezionare questa opzione per eliminare il processo dopo il completamento. Dopo aver selezionato questa opzione, specificare la condizione che attiverà l'eliminazione del processo: **In caso di esito positivo processo**, **In caso di esito negativo processo**o **Al termine del processo**.  
  
## <a name="see-also"></a>Vedere anche  
 [Implementazione di processi](implement-jobs.md)   
 [Configurare Posta elettronica di SQL Server Agent per l'uso di Posta elettronica database](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
