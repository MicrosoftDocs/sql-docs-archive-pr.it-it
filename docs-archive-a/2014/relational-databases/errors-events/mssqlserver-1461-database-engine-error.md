---
title: MSSQLSERVER_1461 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636161"
---
# <a name="mssqlserver_1461"></a>MSSQLSERVER_1461
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|1461|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|DBM_SAFETY_MISMATCH|  
|Testo del messaggio|Rilevati livelli di protezione del mirroring del database diversi tra i server per il database "%.*ls". Verrà utilizzato il livello di protezione FULL.|  
  
## <a name="explanation"></a>Spiegazione  
 Le connessioni per il mirroring sono state interrotte quando il livello di protezione delle transazioni è stato modificato a causa dell'inconsistenza delle impostazioni di protezione delle transazioni nei database principale e mirror. Verrà utilizzata l'impostazione predefinita del livello di protezione FULL delle transazioni. La sessione verrà eseguita in modalità a protezione elevata.  
  
## <a name="user-action"></a>Azione dell'utente  
 Per disattivare la protezione delle transazioni, eseguire nuovamente l'istruzione ALTER DATABASE *nome_database* SET PARTNER SAFETY OFF nel database principale.  
  
  
