---
title: MSSQLSERVER_17130 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17130 (Database Engine error)
ms.assetid: 7ce6afca-221d-402f-89df-da7e74a339a8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b63be325273e4df33d837ec1548ed46701323977
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715356"
---
# <a name="mssqlserver_17130"></a>MSSQLSERVER_17130
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|17130|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|INIT_NOLOCKSPACE|  
|Testo del messaggio|Memoria insufficiente per il numero configurato di blocchi. Verrà tentato l'avvio con una tabella hash di blocchi più piccola, con possibili conseguenze sulle prestazioni. Per configurare più memoria per questa istanza del Motore di database, contattare l'amministratore.|  
  
## <a name="explanation"></a>Spiegazione  
 Memoria insufficiente per le dimensioni desiderate della tabella hash di Gestione blocchi.  Verrà eseguito un tentativo di allocare una tabella hash di dimensioni minori.  
  
## <a name="user-action"></a>Azione dell'utente  
 Verificare i parametri di configurazione della memoria del server (min server memory/max server memory) e il numero di richieste di memoria e fornire una quantità maggiore di memoria a SQL Server.  
  
  
