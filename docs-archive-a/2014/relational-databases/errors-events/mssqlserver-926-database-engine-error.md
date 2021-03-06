---
title: MSSQLSERVER_926 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627746"
---
# <a name="mssqlserver_926"></a>MSSQLSERVER_926
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|926|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|DB_SUSPECT|  
|Testo del messaggio|Impossibile aprire il database '%.*ls' perché durante il processo di recupero è stato contrassegnato come SUSPECT. Per ulteriori informazioni, vedere il registro errori di SQL Server.|  
  
## <a name="explanation"></a>Spiegazione  
 Il database è contrassegnato come sospetto a causa dell'esito negativo del processo di recupero che consente di impostare il database in uno stato consistente a livello di transazioni. Questo tipo di errore può verificarsi durante le operazioni seguenti:  
  
-   Avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
-   Collegamento di un database.  
  
-   Utilizzo delle procedure RESTORE DATABASE o RESTORE LOG.  
  
## <a name="user-action"></a>Azione dell'utente  
 Esaminare il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per individuare la causa dell'errore. Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stato riavviato dopo il recupero non riuscito, esaminare i log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti per individuare le cause del problema.  
  
 Se il recupero non è riuscito a causa di un errore di I/O persistente, una pagina incompleta o un altro possibile errore hardware, risolvere il problema hardware sottostante e ripristinare il database utilizzando un backup. Se non sono disponibili backup, valutare la possibilità di utilizzare le opzioni DBCC CHECKDB.  
  
 Se non è possibile risolvere il problema, rivolgersi al supporto tecnico. Tenere a disposizione il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per eventuali verifiche.  
  
## <a name="see-also"></a>Vedere anche  
 [Backup e ripristino di database SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md)   
 [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql)   
 [sys.sysdatabase &#40;&#41;Transact-SQL](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql)   
 [Collegamento e scollegamento di un database &#40;SQL Server&#41;](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
