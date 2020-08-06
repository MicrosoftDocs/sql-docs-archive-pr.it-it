---
title: Modificare le applicazioni in modo da prevedere valori bigint da sysperfinfo. cntr_value | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sysperfinfo
- bigint values [SQL Server]
ms.assetid: b0345303-6e9a-4078-8148-6e1bce207b8c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 108a9b981debc95e182b16847c39a03d4b242088
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724376"
---
# <a name="modify-applications-to-expect-bigint-values-from-sysperfinfocntr_value"></a><span data-ttu-id="20502-102">Modificare le applicazioni in modo da prevedere valori bigint da sysperfinfo.cntr_value</span><span class="sxs-lookup"><span data-stu-id="20502-102">Modify applications to expect bigint values from sysperfinfo.cntr_value</span></span>
  <span data-ttu-id="20502-103">sysperfinfo restituisce un `bigint` valore per la colonna cntr_value.</span><span class="sxs-lookup"><span data-stu-id="20502-103">sysperfinfo returns a `bigint` value for the cntr_value column.</span></span>  
  
## <a name="component"></a><span data-ttu-id="20502-104">Componente</span><span class="sxs-lookup"><span data-stu-id="20502-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="20502-105">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="20502-105">Corrective Action</span></span>  
 <span data-ttu-id="20502-106">Modificare le applicazioni che utilizzano sysperfinfo per assicurarsi che siano in grado di gestire i valori `bigint` della colonna cntr_value.</span><span class="sxs-lookup"><span data-stu-id="20502-106">Modify applications that use sysperfinfo to ensure that they can handle the `bigint` values of the cntr_value column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20502-107">sysperfinfo è una vista di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="20502-107">sysperfinfo is a compatibility view.</span></span> <span data-ttu-id="20502-108">Utilizzare invece la vista a gestione dinamica sys. dm_os_performance_counter.</span><span class="sxs-lookup"><span data-stu-id="20502-108">You should use the sys.dm_os_performance_counter dynamic management view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20502-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20502-109">See Also</span></span>  
 <span data-ttu-id="20502-110">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="20502-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="20502-111">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="20502-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
