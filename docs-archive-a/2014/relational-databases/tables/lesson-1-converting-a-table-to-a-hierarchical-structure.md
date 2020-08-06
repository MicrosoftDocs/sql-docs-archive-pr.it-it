---
title: 'Lezione 1: Conversione di una tabella in una struttura gerarchica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- HierarchyID
ms.assetid: 5ee6f19a-6dd7-4730-a91c-bbed1bd77e0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 196a546093786f9be4b88536763b3150ae750f97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724475"
---
# <a name="lesson-1-converting-a-table-to-a-hierarchical-structure"></a><span data-ttu-id="2c48c-102">Lezione 1: Conversione di una tabella in una struttura gerarchica</span><span class="sxs-lookup"><span data-stu-id="2c48c-102">Lesson 1: Converting a Table to a Hierarchical Structure</span></span>
  <span data-ttu-id="2c48c-103">I clienti che hanno tabelle che utilizzano un self-join per esprimere relazioni gerarchiche possono convertire le tabelle in una struttura gerarchica utilizzando questa lezione come guida.</span><span class="sxs-lookup"><span data-stu-id="2c48c-103">Customers who have tables using self joins to express hierarchical relationships can convert their tables to a hierarchical structure using this lesson as a guide.</span></span> <span data-ttu-id="2c48c-104">È relativamente facile eseguire la migrazione da questa rappresentazione a `hierarchyid`.</span><span class="sxs-lookup"><span data-stu-id="2c48c-104">It is relatively easy to migrate from this representation to one using `hierarchyid`.</span></span> <span data-ttu-id="2c48c-105">Dopo la migrazione, gli utenti avranno una rappresentazione gerarchica compatta e facile da capire che può essere indicizzata in molti modi per eseguire query efficienti.</span><span class="sxs-lookup"><span data-stu-id="2c48c-105">After migration, users will have a compact and easy to understand hierarchical representation, which can be indexed in several ways for efficient queries.</span></span>  
  
 <span data-ttu-id="2c48c-106">In questa lezione, verrà esaminata una tabella esistente, verrà creata una nuova tabella contenente una colonna `hierarchyid`, verrà popolata la tabella con i dati della tabella di origine e infine verranno illustrate tre strategie di indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="2c48c-106">This lesson, examines an existing table, creates a new table containing a `hierarchyid` column, populates the table with the data from the source table, and then demonstrates three indexing strategies.</span></span> <span data-ttu-id="2c48c-107">In questa lezione sono inclusi gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c48c-107">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="2c48c-108">Esame della struttura corrente della tabella Employee</span><span class="sxs-lookup"><span data-stu-id="2c48c-108">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
-   [<span data-ttu-id="2c48c-109">Popolamento di una tabella con dati gerarchici esistenti</span><span class="sxs-lookup"><span data-stu-id="2c48c-109">Populating a Table with Existing Hierarchical Data</span></span>](lesson-1-2-populating-a-table-with-existing-hierarchical-data.md)  
  
-   [<span data-ttu-id="2c48c-110">Ottimizzazione della tabella NewOrg</span><span class="sxs-lookup"><span data-stu-id="2c48c-110">Optimizing the NewOrg Table</span></span>](lesson-1-3-optimizing-the-neworg-table.md)  
  
-   [<span data-ttu-id="2c48c-111">Riepilogo: Conversione di una tabella in una struttura gerarchica</span><span class="sxs-lookup"><span data-stu-id="2c48c-111">Summary: Converting a Table to a Hierarchical Structure</span></span>](lesson-1-4-summary-converting-a-table-to-a-hierarchical-structure.md)  
  
## <a name="prerequisites"></a><span data-ttu-id="2c48c-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2c48c-112">Prerequisites</span></span>  
 <span data-ttu-id="2c48c-113">Questa lezione richiede il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c48c-113">This lesson requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2c48c-114">Attività successiva della lezione</span><span class="sxs-lookup"><span data-stu-id="2c48c-114">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2c48c-115">Esame della struttura corrente della tabella Employee</span><span class="sxs-lookup"><span data-stu-id="2c48c-115">Examining the Current Structure of the Employee Table</span></span>](lesson-1-1-examining-the-current-structure-of-the-employee-table.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="2c48c-116">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="2c48c-116">Next Lesson</span></span>  
 [<span data-ttu-id="2c48c-117">Lezione 2: Creazione e gestione di dati in una tabella gerarchica</span><span class="sxs-lookup"><span data-stu-id="2c48c-117">Lesson 2: Creating and Managing Data in a Hierarchical Table</span></span>](lesson-2-creating-and-managing-data-in-a-hierarchical-table.md)  
  
  