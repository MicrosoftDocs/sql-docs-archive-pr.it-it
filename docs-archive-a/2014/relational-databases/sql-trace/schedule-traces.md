---
title: Pianificare tracce | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- filters [SQL Server], events
- traces [SQL Server]
- traces [SQL Server], stopping
- events [SQL Server], filters
- scheduling traces [SQL Server]
- traces [SQL Server], scheduling
- stopping traces
ms.assetid: 620b79db-924b-4502-8af3-39efcfca245d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a698d88db35c84f7611293cf45807203c883865a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634970"
---
# <a name="schedule-traces"></a>Pianificare tracce
  Esistono due modi per pianificare le tracce in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. È possibile:  
  
-   Abilitare una data e un'ora di arresto della traccia  
  
-   Utilizzare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent per pianificare una traccia.  
  
## <a name="specifying-a-stop-time"></a>Specifica di una data e un'ora di arresto  
 È possibile specificare una data e un'ora di arresto della traccia se si utilizzano le stored procedure di [!INCLUDE[tsql](../../includes/tsql-md.md)] o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]. L'impostazione della data e dell'ora di arresto deve essere eseguita durante la configurazione originale della traccia.  
  
## <a name="scheduling-traces-by-using-sql-server-agent"></a>Pianificazione di tracce tramite SQL Server Agent  
 Il metodo migliore per pianificare le tracce consiste nell'avviare la traccia tramite [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e quindi specificare una data e un'ora di arresto per la traccia tramite la stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)]**sp_trace_setstatus** o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
 **Per impostare un filtro basato sulla data e sull'ora di fine per una traccia**  
  
 [Filtrare gli eventi in base all'ora di fine &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/filter-events-based-on-the-event-end-time-sql-server-profiler.md)  
  
 [sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
## <a name="see-also"></a>Vedere anche  
 [Automatizzazione delle attività amministrative &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md)  
  
  
