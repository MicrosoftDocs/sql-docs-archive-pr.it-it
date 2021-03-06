---
title: Restrizioni relative alle connessioni normali e di contesto | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629872"
---
# <a name="restrictions-on-regular-and-context-connections"></a>Restrizioni relative alle connessioni normali e di contesto
  In questo argomento vengono illustrate le restrizioni associate all'esecuzione del codice nel [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] processo tramite il contesto e le connessioni regolari.  
  
## <a name="restrictions-on-context-connections"></a>Restrizioni relative alle connessioni di contesto  
 Quando si sviluppa l'applicazione, tenere presenti le restrizioni seguenti che si applicano alle connessioni di contesto:  
  
-   È possibile tenere aperta una sola connessione di contesto per volta per una determinata connessione. Se vengono eseguite contemporaneamente più istruzioni in connessioni separate, ognuna di esse può avere la propria connessione di contesto. La restrizione non influisce sulle richieste simultanee provenienti da connessioni diverse ma solo su una specifica richiesta in una determinata connessione.  
  
-   Non è supportato il servizio MARS (Multiple Active Result Sets).  
  
-   La classe `SqlBulkCopy` non funziona.  
  
-   Non è supportata l'esecuzione di batch di aggiornamenti.  
  
-   Non è possibile utilizzare `SqlNotificationRequest` con comandi che vengono eseguiti su una connessione di contesto.  
  
-   Non è supportato l'annullamento di comandi che vengono eseguiti su una connessione di contesto. Il metodo `SqlCommand.Cancel` ignora la richiesta senza avvisare.  
  
-   Quando si utilizza "context connection=true", non è possibile utilizzare altre parole chiave della stringa di connessione.  
  
-   La proprietà `SqlConnection.DataSource` restituisce null invece del nome dell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se la stringa di connessione per l'oggetto `SqlConnection` è "context connection=true".  
  
-   L'impostazione della proprietà `SqlCommand.CommandTimeout` non ha effetto quando il comando viene eseguito su una connessione di contesto.  
  
## <a name="restrictions-on-regular-connections"></a>Restrizioni relative alle connessioni normali  
 Quando si sviluppa l'applicazione, tenere presenti le restrizioni seguenti che si applicano alle connessioni normali:  
  
-   Non è supportata l'esecuzione asincrona di comandi su server interni. Se si include "async=true" nella stringa di connessione di un comando, quindi si esegue il comando, viene generata l'eccezione `System.NotSupportedException`. Viene visualizzato il messaggio "Asynchronous Processing non è supportato se eseguito in un processo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]".  
  
-   Non è supportato l'oggetto `SqlDependency`.  
  
## <a name="see-also"></a>Vedere anche  
 [Connessione di contesto](context-connection.md)  
  
  
