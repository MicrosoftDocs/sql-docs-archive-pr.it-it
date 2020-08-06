---
title: Monitorare l'uso del disco | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database monitoring [SQL Server], disk usage
- disks [SQL Server]
- monitoring performance [SQL Server], disk usage
- server performance [SQL Server], disk usage
- monitoring [SQL Server], disk activity
- excess paging [SQL Server]
- tuning databases [SQL Server], disk usage
- I/O [SQL Server], monitoring
- disks [SQL Server], monitoring activity
- isolating disk activity [SQL Server]
- database performance [SQL Server], disk usage
- monitoring server performance [SQL Server], disk usage
ms.assetid: 1525449c-ea7d-4222-b294-1ba1fe99c9ac
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 51479b024864322d34dc3b0208e29e93d7454184
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723724"
---
# <a name="monitor-disk-usage"></a><span data-ttu-id="96ebe-102">Monitoraggio dell'utilizzo del disco</span><span class="sxs-lookup"><span data-stu-id="96ebe-102">Monitor Disk Usage</span></span>
  <span data-ttu-id="96ebe-103">In Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono utilizzate le chiamate di input/output (I/O) del sistema operativo Microsoft Windows per eseguire operazioni di lettura e scrittura sul disco.</span><span class="sxs-lookup"><span data-stu-id="96ebe-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses Microsoft Windows operating system input/output (I/O) calls to perform read and write operations on your disk.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="96ebe-104">gestisce i tempi e le modalità di esecuzione delle operazioni di I/O, ma è il sistema operativo Windows a eseguire le operazioni di I/O sottostanti.</span><span class="sxs-lookup"><span data-stu-id="96ebe-104">manages when and how disk I/O is performed, but the Windows operating system performs the underlying I/O operations.</span></span> <span data-ttu-id="96ebe-105">Il sottosistema di I/O include il bus di sistema, le schede dei controller dei dischi, i dischi, le unità a nastro, l'unità CD-ROM e numerosi altri dispositivi di I/O.</span><span class="sxs-lookup"><span data-stu-id="96ebe-105">The I/O subsystem includes the system bus, disk controller cards, disks, tape drives, CD-ROM drive, and many other I/O devices.</span></span> <span data-ttu-id="96ebe-106">L'attività di I/O su disco rappresenta frequentemente la causa di colli di bottiglia in un sistema.</span><span class="sxs-lookup"><span data-stu-id="96ebe-106">Disk I/O is frequently the cause of bottlenecks in a system.</span></span>  
  
 <span data-ttu-id="96ebe-107">Il monitoraggio dell'attività del disco si concentra su due aree:</span><span class="sxs-lookup"><span data-stu-id="96ebe-107">Monitoring disk activity involves two areas of focus:</span></span>  
  
-   <span data-ttu-id="96ebe-108">Monitoraggio dell'I/O su disco e rilevamento del paging eccessivo</span><span class="sxs-lookup"><span data-stu-id="96ebe-108">Monitoring Disk I/O and Detecting Excess Paging</span></span>  
  
-   <span data-ttu-id="96ebe-109">Isolamento dell'attività del disco creata da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96ebe-109">Isolating Disk Activity That [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Creates</span></span>  
  
 <span data-ttu-id="96ebe-110">Per ulteriori informazioni, vedere [monitoraggio dell'utilizzo del disco](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span><span class="sxs-lookup"><span data-stu-id="96ebe-110">For more information see, [Monitoring Disk Usage](https://social.technet.microsoft.com/wiki/contents/articles/monitoring-disk-usage.aspx)</span></span>  
  
  
