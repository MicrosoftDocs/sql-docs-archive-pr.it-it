---
title: Aggiungere un log per i contatori delle prestazioni del flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- performance counters [Integration Services]
- counters [Integration Services]
- logs [Integration Services], data flow counters
ms.assetid: b500d166-33ba-4b82-a92d-b0a333924e8d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 489bde1b0e5769f05d1063eb0af2376b659574de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721680"
---
# <a name="add-a-log-for-data-flow-performance-counters"></a>Aggiunta di un registro per i contatori delle prestazioni del flusso di dati
  In questo argomento viene descritta la procedura per l'aggiunta di un registro per i contatori delle prestazioni forniti dal motore del flusso di dati.  
  
> [!NOTE]  
>  se [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] viene installato in un computer che esegue [!INCLUDE[winxpsvr](../includes/winxpsvr-md.md)]e il computer viene aggiornato a [!INCLUDE[firstref_longhorn](../includes/firstref-longhorn-md.md)], il processo di aggiornamento rimuove i contatori delle prestazioni [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dal computer. Per ripristinare i contatori delle prestazioni [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nel computer, eseguire il programma di installazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] in modalità di ripristino.  
  
### <a name="to-add-logging-of-performance-counters"></a>Per attivare la creazione di registri dei contatori delle prestazioni  
  
1.  Nel **Pannello di controllo**fare clic su **Strumenti di amministrazione**nella visualizzazione classica. Nella visualizzazione Categoria fare clic su **Prestazioni e manutenzione** e quindi su **Strumenti di amministrazione**.  
  
2.  Fare clic su **Prestazioni**.  
  
3.  Nella finestra di dialogo **Prestazioni** espandere il nodo **Avvisi e registri di prestazioni**, fare clic con il pulsante destro del mouse su **Registri contatori**e quindi fare clic su **Nuove impostazioni registro**. Digitare il nome del registro, ad esempio **MioRegistro**.  
  
4.  Fare clic su **OK**.  
  
5.  Nella finestra di dialogo **MioRegistro** fare clic su **Aggiungi contatori**.  
  
6.  Fare clic su **Utilizza contatori del computer locale** per la registrazione dei contatori delle prestazioni nel computer locale oppure fare clic su **Seleziona contatori dal computer** , quindi selezionare un computer dall'elenco in cui registrare i contatori delle prestazioni.  
  
7.  Nella finestra di dialogo **Aggiungi contatori** selezionare **SQL Server:SSIS Pipeline** (SQL Server:Pipeline SSIS) nell'elenco **Oggetto prestazione** .  
  
8.  Per selezionare contatori delle prestazioni, eseguire una delle operazioni seguenti:  
  
    -   Selezionare **All Counters** (Tutti i contatori) per registrare tutti i contatori delle prestazioni.  
  
    -   Selezionare **Select counters in list** (Seleziona i contatori dall'elenco) e selezionare i contatori delle prestazioni da usare.  
  
9. Scegliere **Aggiungi**.  
  
10. Fare clic su **Close**.  
  
11. Nella finestra di dialogo **MioRegistro** esaminare l'elenco della registrazione dei contatori delle prestazioni nell'elenco **Contatori** .  
  
12. Per aggiungere altri contatori, ripetere i passaggi da 5 a 10.  
  
13. Fare clic su **OK**.  
  
    > [!NOTE]  
    >  Il servizio Avvisi e registri di prestazioni deve essere avviato in base a un account locale o un account di dominio appartenente al gruppo Administrators.  
  
## <a name="see-also"></a>Vedere anche  
 [Contatori delle prestazioni](performance/performance-counters.md)   
 [Visualizzare le voci di log nella finestra Registra eventi](../../2014/integration-services/view-log-entries-in-the-log-events-window.md)  
  
  
