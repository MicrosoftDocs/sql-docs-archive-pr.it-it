---
title: MSSQLSERVER_2546 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2546 (Database Engine error)
ms.assetid: c8f0e1b4-c7c4-45f2-9221-746714172313
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c1c5f64ca0daba413f2b71c05f5b8e57b2d55df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713192"
---
# <a name="mssqlserver_2546"></a><span data-ttu-id="7f1e7-102">MSSQLSERVER_2546</span><span class="sxs-lookup"><span data-stu-id="7f1e7-102">MSSQLSERVER_2546</span></span>
    
## <a name="details"></a><span data-ttu-id="7f1e7-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="7f1e7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f1e7-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="7f1e7-104">Product Name</span></span>|<span data-ttu-id="7f1e7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7f1e7-105">SQL Server</span></span>|  
|<span data-ttu-id="7f1e7-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="7f1e7-106">Event ID</span></span>|<span data-ttu-id="7f1e7-107">2546</span><span class="sxs-lookup"><span data-stu-id="7f1e7-107">2546</span></span>|  
|<span data-ttu-id="7f1e7-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="7f1e7-108">Event Source</span></span>|<span data-ttu-id="7f1e7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7f1e7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7f1e7-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7f1e7-110">Component</span></span>|<span data-ttu-id="7f1e7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7f1e7-111">SQLEngine</span></span>|  
|<span data-ttu-id="7f1e7-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="7f1e7-112">Symbolic Name</span></span>|<span data-ttu-id="7f1e7-113">DBCC_INDEX_MARKED_DISABLED</span><span class="sxs-lookup"><span data-stu-id="7f1e7-113">DBCC_INDEX_MARKED_DISABLED</span></span>|  
|<span data-ttu-id="7f1e7-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="7f1e7-114">Message Text</span></span>|<span data-ttu-id="7f1e7-115">L'indice 'INDEX_NAME' della tabella 'OBJECT_NAME' è contrassegnato come disabilitato.</span><span class="sxs-lookup"><span data-stu-id="7f1e7-115">Index 'INDEX_NAME' on table 'OBJECT_NAME' is marked as disabled.</span></span> <span data-ttu-id="7f1e7-116">Ricompilare l'indice per riportarlo online.</span><span class="sxs-lookup"><span data-stu-id="7f1e7-116">Rebuild the index to bring it online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7f1e7-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="7f1e7-117">Explanation</span></span>  
 <span data-ttu-id="7f1e7-118">L'indice specificato è contrassegnato come offline oppure è disabilitato e</span><span class="sxs-lookup"><span data-stu-id="7f1e7-118">The specified index is marked as offline or is disabled.</span></span> <span data-ttu-id="7f1e7-119">pertanto non può essere controllato.</span><span class="sxs-lookup"><span data-stu-id="7f1e7-119">Therefore, this index cannot be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7f1e7-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="7f1e7-120">User Action</span></span>  
 <span data-ttu-id="7f1e7-121">Ricompilare l'indice utilizzando ALTER INDEX.</span><span class="sxs-lookup"><span data-stu-id="7f1e7-121">Rebuild the index by using ALTER INDEX.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f1e7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f1e7-122">See Also</span></span>  
 <span data-ttu-id="7f1e7-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7f1e7-123">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 [<span data-ttu-id="7f1e7-124">Riorganizzare e ricompilare gli indici</span><span class="sxs-lookup"><span data-stu-id="7f1e7-124">Reorganize and Rebuild Indexes</span></span>](../indexes/indexes.md)  
  
  
