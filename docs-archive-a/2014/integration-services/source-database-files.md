---
title: File di database di origine | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferdatabasetask.sourcedbfiles.f1
ms.assetid: 7dc6bfeb-37c1-45e8-a705-a87564922265
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31f0c0e0c633ead0c093bdc8e1f20c9b8f23cc28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726023"
---
# <a name="source-database-files"></a>File di database di origine
  Utilizzare la finestra di dialogo **File di database di origine** per visualizzare i nomi e i percorsi dei file di database nel server di origine oppure per specificare il percorso di condivisione dei file in rete per l'attività Trasferisci database. Per altre informazioni su questa attività, vedere [Attività Trasferisci database](control-flow/transfer-database-task.md).  
  
 Per popolare questa finestra di dialogo con i nomi e i percorsi dei file di database nel server di origine, impostare innanzitutto le opzioni **SourceConnection** e **SourceDatabaseName** nelle pagine **Database** della finestra di dialogo **Editor attività Trasferisci database** .  
  
## <a name="options"></a>Opzioni  
 **File di origine**  
 Nomi dei file di database nel server di origine che verranno trasferiti. Il valore**File di origine** è di sola lettura.  
  
 **Cartella di origine**  
 Cartella nel server di origine in cui si trovano i file di database da trasferire. Il valore**Cartella di origine** è di sola lettura.  
  
 **Condivisione file di rete**  
 Cartella di rete condivisa nel server di origine da cui verranno trasferiti i file di database. Utilizzare **Condivisione file di rete** quando si trasferisce un database in modalità offline impostando l'opzione **DatabaseOffline** per **Metodo** nella pagina **Database** della finestra di dialogo **Editor attività Trasferisci database** .  
  
 Digitare il percorso della condivisione file di rete oppure fare clic sul pulsante Sfoglia **(...)** per individuarlo.  
  
 Quando si trasferisce un database in modalità offline, i rispettivi file vengono copiati nel percorso specificato in **Condivisione file di rete** nel server di origine prima di essere trasferiti al server di destinazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor attività Trasferisci database &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md)   
 [Editor attività Trasferisci database &#40;pagina Database&#41;](../../2014/integration-services/transfer-database-task-editor-databases-page.md)  
  
  
