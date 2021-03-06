---
title: Costrutti supportati su stored procedure compilate in modo nativo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 6b21f47e-bceb-4054-8b3c-9d39bb9583c0
author: rothja
ms.author: jroth
ms.openlocfilehash: f3bc7e28fa2a868ac39c6adbb2dea3cc5c3ace73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627258"
---
# <a name="supported-constructs-on-natively-compiled-stored-procedures"></a>Costrutti supportati su stored procedure compilate in modo nativo
  In questo argomento vengono illustrati i costrutti supportati nelle stored procedure compilate in modo nativo.  
  
 Per altre informazioni su costrutti non supportati, vedere [Costrutti Transact-SQL non supportati da OLTP in memoria](transact-sql-constructs-not-supported-by-in-memory-oltp.md).  
  
## <a name="procedure-ddl"></a>DLL di procedura  
 Sono supportati gli elementi seguenti:  
  
-   CREATE PROCEDURE  
  
-   DROP PROCEDURE  
  
-   SCHEMABINDING (obbligatorio per le stored procedure compilate in modo nativo)  
  
-   NATIVE_COMPILATION  
  
-   I parametri possono essere dichiarati come NOT NULL.  
  
-   Parametri con valori di tabella.  
  
## <a name="security"></a>Sicurezza  
 Sono supportati gli elementi seguenti:  
  
-   Per le procedure: EXECUTE AS OWNER, SELF e utente.  
  
-   Autorizzazioni GRANT e DENY per tabelle e procedure.  
  
## <a name="see-also"></a>Vedere anche  
 [Stored procedure compilate in modo nativo](natively-compiled-stored-procedures.md)  
  
  
