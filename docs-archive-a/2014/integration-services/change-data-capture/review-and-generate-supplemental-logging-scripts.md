---
title: Rivedere e generare script di registrazione supplementare | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626842"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a>Rivedere e generare script di registrazione supplementare
  Usare la scheda **Scripts** per eseguire o rieseguire uno script nel database di origine Oracle per la configurazione della registrazione supplementare.  
  
 Prima di eseguire gli script selezionare una delle opzioni seguenti:  
  
 **Include changes in this session**  
 Selezionare questa opzione per eseguire lo script nelle nuove tabelle aggiunte all'istanza di CDC o in quelle modificate tramite l'editor delle proprietà.  
  
> [!NOTE]  
>  Se le tabelle dell'istanza di CDC non sono state modificate, lo script di registrazione supplementare Oracle sarà vuoto.  
  
 **Include all tables/capture instances**  
 Selezionare questa opzione per eseguire lo script in tutte le tabelle e le istanze di acquisizione dell'istanza di CDC.  
  
 Dopo avere selezionato una di queste opzioni, eseguire lo script di registrazione supplementare.  
  
### <a name="to-run-the-supplemental-logging-scripts"></a>Per eseguire gli script di registrazione supplementare  
  
1.  Fare clic su **Run Script** per eseguire lo script di registrazione supplementare nelle tabelle definite per l'istanza di CDC. Tramite questo script verranno scritte tutte le colonne di interesse nei log delle transazioni durante la registrazione delle operazioni UPDATE nelle tabelle acquisite. Lo script viene in genere esaminato ed eseguito da un amministratore di sistema Oracle.  
  
2.  Quando si eseguono gli script di registrazione supplementare, viene visualizzata la finestra di dialogo Oracle Credentials for Running Script in cui immettere un nome utente e una password Oracle validi. Per informazioni su come fornire le credenziali Oracle appropriate, vedere [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).  
  
 Se necessario, è anche possibile eseguire gli script manualmente tramite SQL * Plus.  
  
### <a name="to-run-the-scripts-manually"></a>Per eseguire gli script manualmente  
  
1.  Scegliere **Copy** per incollare lo script negli Appunti. Aprire SQL* Plus e accedere alla directory contenente il database di origine Oracle. Incollare lo script in SQL\*Plus per eseguirlo.  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a>Per salvare lo script di registrazione supplementare in un file di testo  
  
1.  Scegliere **Save as** e accedere al percorso in cui si desidera salvare il file.  
  
2.  Assegnare un nome al file e scegliere **Save** per salvarlo.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura di modifica delle proprietà dell'istanza di CDC](how-to-edit-the-cdc-instance-properties.md)   
 [Credenziali Oracle per l'esecuzione di script](oracle-credentials-for-running-script.md)  
  
  
