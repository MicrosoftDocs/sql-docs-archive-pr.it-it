---
title: Eseguire Monitoraggio di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], running
- Windows System Monitor [SQL Server], running
- remote procedure calls [SQL Server]
- starting Windows NT System Monitor
- RPC
ms.assetid: 05297984-bc8d-43df-829c-032387f7ea61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dd0baf32402d69e36dc5120d0259b2f8d689897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723711"
---
# <a name="run-system-monitor"></a><span data-ttu-id="07ef6-102">Eseguire Monitoraggio di sistema</span><span class="sxs-lookup"><span data-stu-id="07ef6-102">Run System Monitor</span></span>
  <span data-ttu-id="07ef6-103">Monitoraggio di sistema utilizza chiamate di procedura remota (RPC, Remote Procedure Call) per raccogliere informazioni da Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07ef6-103">System Monitor uses remote procedure calls (RPCs) to collect information from Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="07ef6-104">Qualunque utente che dispone di autorizzazioni di Microsoft Windows per l'esecuzione di Monitoraggio di sistema può utilizzare tale programma per monitorare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07ef6-104">Any user who has Microsoft Windows permissions to run System Monitor can use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07ef6-105">Se si utilizza Monitoraggio di sistema o Performance Monitor, non sarà possibile connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eseguita in Microsoft Windows 98.</span><span class="sxs-lookup"><span data-stu-id="07ef6-105">When using System Monitor or Performance Monitor, you cannot connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on Windows 98.</span></span>  
  
 <span data-ttu-id="07ef6-106">Analogamente a tutti gli strumenti di monitoraggio delle prestazioni, Monitoraggio di sistema determina un peggioramento delle prestazioni del sistema durante il monitoraggio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07ef6-106">As with all performance monitoring tools, expect some performance overhead when you use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="07ef6-107">L'overhead effettivo di un'istanza specifica varia a seconda della piattaforma hardware, del numero di contatori e dell'intervallo di aggiornamento selezionato.</span><span class="sxs-lookup"><span data-stu-id="07ef6-107">The actual overhead in any specific instance depends on the hardware platform, the number of counters, and the selected update interval.</span></span> <span data-ttu-id="07ef6-108">L'integrazione di Monitoraggio di sistema con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è stata tuttavia progettata in modo da ridurre al minimo eventuali peggioramenti delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="07ef6-108">However, the integration of System Monitor with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is designed to minimize any reduction in performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07ef6-109">Se sono stati selezionati contatori delle prestazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da monitorare nello snap-in di Monitoraggio di sistema, tali contatori verranno visualizzati anche se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="07ef6-109">If you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performance counters to monitor in the System Monitor snap-in, you will see the counters even if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running.</span></span>  
  
 <span data-ttu-id="07ef6-110">Per informazioni sull'avvio di Monitoraggio di sistema, vedere [Avvio di Monitoraggio di sistema &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span><span class="sxs-lookup"><span data-stu-id="07ef6-110">For information about starting System Monitor, see [Start System Monitor &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span></span>  
  
  
