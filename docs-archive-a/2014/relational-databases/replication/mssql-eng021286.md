---
title: MSSQL_ENG021286 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021286 error
ms.assetid: b63620b7-1c6d-46f7-90ea-3a8e99af8de4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 592c788b563046e5949217c94006de2d4755f049
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714180"
---
# <a name="mssql_eng021286"></a>MSSQL_ENG021286
    
## <a name="message-details"></a>Dettagli messaggio  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|21286|  
|Origine evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbolico||  
|Testo del messaggio|La tabella dei conflitti '%s' non esiste.|  
  
## <a name="explanation"></a>Spiegazione  
 Questo errore si verifica se la tabella dei conflitti relativa a un articolo elencato in [sysmergearticles &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/sysmergearticles-transact-sql) in realtà non esiste. Questo errore può verificarsi quando si tenta di aggiungere o di eliminare una colonna da una tabella pubblicata per la replica di tipo merge.  
  
## <a name="user-action"></a>Azione dell'utente  
 Eseguire [DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database con la tabella dei conflitti mancante per verificare che non siano presenti problemi di coerenza dei dati.  
  
 Se in un Sottoscrittore manca la tabella dei conflitti, eliminare la sottoscrizione e ricrearla. Se in un server di pubblicazione manca la tabella dei conflitti, eliminare tutte le sottoscrizioni, eliminare la pubblicazione e quindi ricreare la pubblicazione e tutte le sottoscrizioni. Per altre informazioni, vedere [Pubblicare dati e oggetti di database](publish/publish-data-and-database-objects.md) e [Sottoscrivere le pubblicazioni](subscribe-to-publications.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md)  
  
  
