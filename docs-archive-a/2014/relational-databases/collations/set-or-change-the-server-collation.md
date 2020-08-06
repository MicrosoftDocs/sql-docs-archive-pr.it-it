---
title: Impostare o modificare le regole di confronto del server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- server collations [SQL Server]
- collations [SQL Server], server
ms.assetid: 3242deef-6f5f-4051-a121-36b3b4da851d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7be051c8cf63a272f2bf42fb54b1c45ed4160
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637903"
---
# <a name="set-or-change-the-server-collation"></a><span data-ttu-id="019e8-102">Impostazione o modifica di regole di confronto del server</span><span class="sxs-lookup"><span data-stu-id="019e8-102">Set or Change the Server Collation</span></span>
  <span data-ttu-id="019e8-103">Le regole di confronto del server costituiscono le regole di confronto predefinite per tutti i database di sistema installati con l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e per ogni database utente creato successivamente.</span><span class="sxs-lookup"><span data-stu-id="019e8-103">The server collation acts as the default collation for all system databases that are installed with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and also any newly created user databases.</span></span> <span data-ttu-id="019e8-104">Le regole di confronto del server vengono specificate durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="019e8-104">The server collation is specified during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="019e8-105">Per altre informazioni, vedere [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="019e8-105">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
## <a name="changing-the-server-collation"></a><span data-ttu-id="019e8-106">Modifica di regole di confronto del server</span><span class="sxs-lookup"><span data-stu-id="019e8-106">Changing the Server Collation</span></span>  
 <span data-ttu-id="019e8-107">La modifica delle regole di confronto predefinite per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può essere un'operazione complessa e richiede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="019e8-107">Changing the default collation for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be a complex operation and involves the following steps:</span></span>  
  
-   <span data-ttu-id="019e8-108">Assicurarsi che siano disponibili tutte le informazioni o gli script necessari per ricreare i database utente e tutti gli oggetti in essi contenuti.</span><span class="sxs-lookup"><span data-stu-id="019e8-108">Make sure you have all the information or scripts needed to re-create your user databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="019e8-109">Esportare tutti i dati usando uno strumento come [l'utilità bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="019e8-109">Export all your data using a tool such as the [bcp Utility](../../tools/bcp-utility.md).</span></span> <span data-ttu-id="019e8-110">Per altre informazioni, vedere [Importazione ed esportazione bulk di dati &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="019e8-110">For more information, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="019e8-111">Eliminare tutti i database utente.</span><span class="sxs-lookup"><span data-stu-id="019e8-111">Drop all the user databases.</span></span>  
  
-   <span data-ttu-id="019e8-112">Ricompilare il database master specificando le nuove regole di confronto nella proprietà SQLCOLLATION del comando **setup** .</span><span class="sxs-lookup"><span data-stu-id="019e8-112">Rebuild the master database specifying the new collation in the SQLCOLLATION property of the **setup** command.</span></span> <span data-ttu-id="019e8-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="019e8-113">For example:</span></span>  
  
    ```  
    Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName   
    /SQLSYSADMINACCOUNTS=accounts /[ SAPWD= StrongPassword ]   
    /SQLCOLLATION=CollationName  
    ```  
  
     <span data-ttu-id="019e8-114">Per altre informazioni, vedere [Ricompilare database di sistema](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="019e8-114">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="019e8-115">Creare tutti i database e tutti gli oggetti in essi contenuti.</span><span class="sxs-lookup"><span data-stu-id="019e8-115">Create all the databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="019e8-116">Importare tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="019e8-116">Import all your data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="019e8-117">Anziché modificare le regole di confronto predefinite di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile specificare regole di confronto predefinite per ogni nuovo database creato.</span><span class="sxs-lookup"><span data-stu-id="019e8-117">Instead of changing the default collation of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can specify a default collation for each new database you create.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="019e8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="019e8-118">See Also</span></span>  
 <span data-ttu-id="019e8-119">[Regole di confronto e supporto Unicode](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="019e8-119">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="019e8-120">[Impostare o modificare le regole di confronto del database](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="019e8-120">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 <span data-ttu-id="019e8-121">[Impostare o modificare le regole di confronto delle colonne](set-or-change-the-column-collation.md) </span><span class="sxs-lookup"><span data-stu-id="019e8-121">[Set or Change the Column Collation](set-or-change-the-column-collation.md) </span></span>  
 [<span data-ttu-id="019e8-122">Ricompilare database di sistema</span><span class="sxs-lookup"><span data-stu-id="019e8-122">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  