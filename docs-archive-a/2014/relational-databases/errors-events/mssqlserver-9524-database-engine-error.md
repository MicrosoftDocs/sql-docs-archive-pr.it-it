---
title: MSSQLSERVER_9524 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627743"
---
# <a name="mssqlserver_9524"></a>MSSQLSERVER_9524
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|9254|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|XMLERR_INVALID_COLUMNSET_XML|  
|Testo del messaggio|Il contenuto XML fornito non è conforme al formato XML richiesto per i set di colonne di tipo sparse.|  
  
## <a name="explanation"></a>Spiegazione  
 È stato eseguito il tentativo di modificare un set di colonne. Il contenuto XML di un set di colonne deve soddisfare le restrizioni del formato relativo. Il formato generale di un set di colonne è il seguente:  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 Per ulteriori informazioni sui set di colonne, vedere l'argomento "Utilizzo di set di colonne" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="user-action"></a>Azione dell'utente  
 Correggere il formato del codice XML per il set di colonne nell'istruzione.  
  
  
