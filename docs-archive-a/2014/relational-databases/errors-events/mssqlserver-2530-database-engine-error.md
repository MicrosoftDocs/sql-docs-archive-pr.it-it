---
title: MSSQLSERVER_2530 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 5d4be07a-38a5-4b25-819c-4dcb4636cc15
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 30b57aae907d6f0acc4d1c0e6021bf936621c69e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624234"
---
# <a name="mssqlserver_2530"></a>MSSQLSERVER_2530
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|2530|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|DBCC_INDEX_IS_OFFLINE|  
|Testo del messaggio|L'indice "%.*ls" sulla tabella "%.\*ls" è disabilitato.|  
  
## <a name="explanation"></a>Spiegazione  
 L'istruzione DBCC non può proseguire perché l'indice specificato è disabilitato. Dopo che un indice viene disabilitato, resta in questo stato fino a quando non viene ricompilato o eliminato e quindi ricreato.  
  
## <a name="user-action"></a>Azione dell'utente  
  
1.  Abilitare l'indice disabilitato utilizzando uno dei metodi seguenti:  
  
    -   Istruzione ALTER INDEX con la clausola REBUILD  
  
    -   Istruzione CREATE INDEX con la clausola DROP_EXISTING  
  
    -   DBCC DBREINDEX  
  
2.  Rieseguire l'istruzione DBCC.  
  
## <a name="see-also"></a>Vedere anche  
 [Abilita indici e vincoli](../indexes/enable-indexes-and-constraints.md)   
 [ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql)   
 [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)   
 [DBCC DBREINDEX &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-dbreindex-transact-sql)  
  
  
