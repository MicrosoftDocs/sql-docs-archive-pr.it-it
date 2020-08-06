---
title: MSSQLSERVER_7937 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7937 (Database Engine error)
ms.assetid: 7dcc61a3-975d-4662-8a4e-c153e26b36c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44f299f9c7773e38dad483d084f2b097166460ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635641"
---
# <a name="mssqlserver_7937"></a><span data-ttu-id="5f1fd-102">MSSQLSERVER_7937</span><span class="sxs-lookup"><span data-stu-id="5f1fd-102">MSSQLSERVER_7937</span></span>
    
## <a name="details"></a><span data-ttu-id="5f1fd-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5f1fd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f1fd-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5f1fd-104">Product Name</span></span>|<span data-ttu-id="5f1fd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5f1fd-105">SQL Server</span></span>|  
|<span data-ttu-id="5f1fd-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5f1fd-106">Event ID</span></span>|<span data-ttu-id="5f1fd-107">7937</span><span class="sxs-lookup"><span data-stu-id="5f1fd-107">7937</span></span>|  
|<span data-ttu-id="5f1fd-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5f1fd-108">Event Source</span></span>|<span data-ttu-id="5f1fd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5f1fd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5f1fd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5f1fd-110">Component</span></span>|<span data-ttu-id="5f1fd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5f1fd-111">SQLEngine</span></span>|  
|<span data-ttu-id="5f1fd-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5f1fd-112">Symbolic Name</span></span>|<span data-ttu-id="5f1fd-113">DBCC2_FS_MISSING_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="5f1fd-113">DBCC2_FS_MISSING_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="5f1fd-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5f1fd-114">Message Text</span></span>|<span data-ttu-id="5f1fd-115">Errore di tabella: impossibile trovare la directory FileStream per l'ID di colonna C_ID, ID di oggetto O_ID, ID di indice I_ID, ID di partizione PN_ID.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-115">Table error: Filestream directory for column ID C_ID of object ID O_ID, index ID I_ID, partition ID PN_ID was not found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5f1fd-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5f1fd-116">Explanation</span></span>  
 <span data-ttu-id="5f1fd-117">La colonna specificata esiste in una partizione, ma nello spazio dati FILESTREAM non è stato possibile individuare la directory FILESTREAM corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-117">The specified column exists in a partition; however, its corresponding FILESTREAM directory was not found in the FILESTREAM dataspace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5f1fd-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5f1fd-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="5f1fd-119">Individuare errori hardware</span><span class="sxs-lookup"><span data-stu-id="5f1fd-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="5f1fd-120">Eseguire gli strumenti di diagnostica hardware e risolvere eventuali problemi.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="5f1fd-121">Esaminare inoltre il registro di sistema di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows e il registro delle applicazioni, nonché il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per stabilire se l'errore è dovuto a un problema hardware.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="5f1fd-122">Risolvere tutti i problemi relativi all'hardware indicati nei log.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="5f1fd-123">In caso di problemi persistenti che provocano il danneggiamento dei dati, provare a sostituire i vari componenti hardware per isolare il problema.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="5f1fd-124">Verificare che nel sistema non sia abilitata la memorizzazione nella cache in scrittura sul controller del disco.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="5f1fd-125">Se si ritiene che il problema sia dovuto alla memorizzazione nella cache in scrittura, rivolgersi al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="5f1fd-126">Infine, potrebbe essere conveniente passare a un nuovo sistema hardware.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="5f1fd-127">A tale scopo può essere necessario riformattare le unità disco e reinstallare il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="5f1fd-128">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="5f1fd-128">Restore from Backup</span></span>  
 <span data-ttu-id="5f1fd-129">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="5f1fd-130">Eseguire DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="5f1fd-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="5f1fd-131">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-131">Not applicable.</span></span> <span data-ttu-id="5f1fd-132">L'errore non può essere corretto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5f1fd-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="5f1fd-133">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f1fd-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  