---
title: Dati BLOB (Binary Large Object) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], design and implementation
ms.assetid: 97509274-c3f8-43e5-a37c-52f1ffe0961a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a663dedf34d75a21ee8df6b97979548c04abf7ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636238"
---
# <a name="binary-large-object-blob-data-sql-server"></a><span data-ttu-id="e9fbd-102">Dati BLOB (Binary Large Object) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e9fbd-102">Binary Large Object (Blob) Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e9fbd-103">fornisce soluzioni per l'archiviazione di file e documenti nel database o su dispositivi di archiviazione remoti.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-103">provides solutions for storing files and documents in the database or on remote storage devices.</span></span>  
  
##  <a name="in-this-section"></a><a name="section"></a> <span data-ttu-id="e9fbd-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e9fbd-104">In This Section</span></span>  
 [<span data-ttu-id="e9fbd-105">Confrontare opzioni per l'archiviazione di BLOB &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e9fbd-105">Compare Options for Storing Blobs &#40;SQL Server&#41;</span></span>](compare-options-for-storing-blobs-sql-server.md)  
 <span data-ttu-id="e9fbd-106">Confrontare i vantaggi di FILESTREAM, FileTable e Archivio BLOB remoti.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-106">Compare the advantages of FILESTREAM, FileTables, and Remote Blob Store.</span></span>  
  
 [<span data-ttu-id="e9fbd-107">FILESTREAM &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e9fbd-107">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 <span data-ttu-id="e9fbd-108">FILESTREAM consente l'archiviazione nel file system di dati non strutturati, ad esempio documenti e immagini, da parte delle applicazioni basate su [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9fbd-108">FILESTREAM enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-based applications to store unstructured data, such as documents and images, on the file system.</span></span> <span data-ttu-id="e9fbd-109">Le applicazioni possono sfruttare le numerose API di flusso e le prestazioni del file system e contemporaneamente mantenere la coerenza transazionale tra i dati non strutturati e i corrispondenti dati strutturati.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-109">Applications can leverage the rich streaming APIs and performance of the file system and at the same time maintain transactional consistency between the unstructured data and corresponding structured data.</span></span>  
  
 [<span data-ttu-id="e9fbd-110">FileTables &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e9fbd-110">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 <span data-ttu-id="e9fbd-111">La funzionalità FileTable fornisce supporto per lo spazio dei nomi dei file di Windows e la compatibilità con le applicazioni di Windows ai dati dei file archiviati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9fbd-111">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e9fbd-112">FileTable consente l'integrazione dei componenti di archiviazione e gestione dei dati da parte di un'applicazione e fornisce servizi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integrati, incluse la ricerca full-text e la ricerca semantica, su dati e metadati non strutturati.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-112">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="e9fbd-113">In altre parole, è possibile archiviare file e documenti in speciali tabelle denominate FileTable in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ma accedere a tali file e documenti da applicazioni di Windows come se questi fossero archiviati nel file system, senza apportare alcuna modifica alle applicazioni del client.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-113">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 [<span data-ttu-id="e9fbd-114">Archivio Blob remoto &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e9fbd-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
 <span data-ttu-id="e9fbd-115">Archivio BLOB remoti (RBS) per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente agli amministratori del database di archiviare oggetti BLOB (Binary Large Object) in soluzioni di archiviazione apposite anziché direttamente sul server.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-115">Remote BLOB store (RBS) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lets database administrators store binary large objects (BLOBs) in commodity storage solutions instead of directly on the server.</span></span> <span data-ttu-id="e9fbd-116">Ciò consente di risparmiare una considerevole quantità di spazio ed evita un inutile consumo di costose risorse hardware del server.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-116">This saves a significant amount of space and avoids wasting expensive server hardware resources.</span></span> <span data-ttu-id="e9fbd-117">RBS fornisce un set di librerie API che definiscono un modello standardizzato tramite cui le applicazioni accedono ai dati BLOB.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-117">RBS provides a set of API libraries that define a standardized model for applications to access BLOB data.</span></span> <span data-ttu-id="e9fbd-118">RBS include anche strumenti di manutenzione come Garbage Collection, per facilitare la gestione dei dati BLOB remoti.</span><span class="sxs-lookup"><span data-stu-id="e9fbd-118">RBS also includes maintenance tools, such as garbage collection, to help manage remote BLOB data.</span></span>  
  
 <span data-ttu-id="e9fbd-119">Tale componente è incluso nei supporti di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ma non viene installato dal programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9fbd-119">RBS is included on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
  