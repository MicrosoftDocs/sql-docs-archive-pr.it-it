---
title: Registrazione per pacchetti con bilanciamento del carico in server remoti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], remote packages
ms.assetid: fd571567-b625-4f9a-8b7e-42c5c588b11b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b45fa6607d6edc1559d8ebcbbbc7598e11eac408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628812"
---
# <a name="logging-for-load-balanced-packages-on-remote-servers"></a>Registrazione per pacchetti con bilanciamento del carico in server remoti
  La gestione dei log di tutti i pacchetti figlio in esecuzione su più server risulta più semplice se tutti i pacchetti figlio utilizzano lo stesso provider di log e scrivono nella stessa destinazione. Per creare un file di log comune per tutti i pacchetti figlio, è possibile configurare i pacchetti figlio in modo da registrare i propri eventi in un provider di log di tipo SQL Server. È possibile configurare tutti i pacchetti in modo che utilizzino lo stesso database, lo stesso server e la stessa istanza del server.  
  
 Per visualizzare tutti i file di log, l'amministratore deve semplicemente accedere a un server e visualizzare il file di log per tutti i pacchetti figlio.  
  
## <a name="related-tasks"></a>Attività correlate  
 Per informazioni su come abilitare la registrazione in un pacchetto, vedere [Abilitare la registrazione di pacchetti in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Registrazione di Integration Services &#40;SSIS&#41;](performance/integration-services-ssis-logging.md)  
  
  
