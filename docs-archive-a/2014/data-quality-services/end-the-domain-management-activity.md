---
title: Terminare l'attività di gestione del dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ab6505ad-3090-453b-bb01-58435e7fa7c0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c776674a369bfae8c7da6fa0deabfbd932029570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715724"
---
# <a name="end-the-domain-management-activity"></a>Sospensione dell'attività di gestione del dominio
  In questo argomento viene descritto come completare, chiudere o annullare l'attività di gestione del dominio in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). La gestione del dominio non viene eseguita da una procedura guidata, pertanto i controlli descritti sotto possono essere utilizzati da qualsiasi pagina dell'attività di gestione del dominio.  
  
## <a name="end-domain-management"></a>Annullare la gestione del dominio  
 **Fine**  
 Fare clic per completare l'attività di gestione del dominio. Verrà visualizzata una finestra popup con le opzioni seguenti:  
  
-   **Sì-pubblica la Knowledge base e Chiudi**: la Knowledge base verrà pubblicata per l'uso da parte dell'utente corrente o di altri utenti. La Knowledge Base non verrà bloccata, lo stato della Knowledge Base nella relativa tabella verrà impostato come vuoto e saranno disponibili entrambe le attività, Gestione dominio e Individuazione informazioni. Verrà di nuovo visualizzata la schermata Apri Knowledge Base.  
  
-   **No-Salva il lavoro sulla Knowledge base e Chiudi**: il lavoro verrà salvato, la Knowledge base rimarrà bloccata e lo stato della Knowledge base verrà impostato su in lavorazione. Entrambe le attività Gestione dominio e Individuazione informazioni saranno disponibili. Verrà di nuovo visualizzata la home page.  
  
-   **Annulla - Rimani nella schermata corrente**: la finestra popup verrà chiusa e verrà di nuovo visualizzata la schermata Gestione dominio.  
  
 **Annulla**  
 Fare clic per terminare l'attività Gestione dominio. Il lavorò verrà perso e sarà visualizzata di nuovo la home page di DQS.  
  
 **Close**  
 Fare clic per salvare il lavoro e tornare alla home page di DQS. La Knowledge Base verrà bloccata e lo stato della Knowledge Base nella relativa tabella nella schermata **Apri Knowledge Base** sarà **Gestione dominio**. Dopo avere fatto clic su **Chiudi**per eseguire l'attività Individuazione informazioni è necessario tornare alla schermata **Gestione dominio** , fare clic su **Fine**e quindi su **Sì** per pubblicare la Knowledge Base o su **No** per salvare il lavoro sulla Knowledge Base e uscire.  Per ulteriori informazioni sull'apertura di una Knowledge Base bloccata, vedere [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).  
  
  
