---
title: Configurare le istanze del motore di database (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 84e36fcb-2c78-48e8-8e4b-bf784a3ee557
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af7408ff66d1f0e41369ba095ce51ea590d316e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638105"
---
# <a name="configure-database-engine-instances-sql-server"></a><span data-ttu-id="ddc60-102">Configurare le istanze del motore di database (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ddc60-102">Configure Database Engine Instances (SQL Server)</span></span>
  <span data-ttu-id="ddc60-103">È necessario configurare ogni istanza di [!INCLUDE[ssDE](../../includes/ssde-md.md)] per soddisfare i requisiti di prestazione e disponibilità definiti per i database ospitati dall'istanza.</span><span class="sxs-lookup"><span data-stu-id="ddc60-103">Each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] must be configured to meet the performance and availability requirements defined for the databases hosted by the instance.</span></span> <span data-ttu-id="ddc60-104">[!INCLUDE[ssDE](../../includes/ssde-md.md)] include opzioni di configurazione che controllano i comportamenti quale utilizzo della risorsa e la disponibilità di funzionalità come il controllo o il trigger recursion.</span><span class="sxs-lookup"><span data-stu-id="ddc60-104">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] includes configuration options that control behaviors such as resource usage and the availability of features such as auditing or trigger recursion.</span></span>  
  
## <a name="instance-configuration"></a><span data-ttu-id="ddc60-105">Configurazione istanza</span><span class="sxs-lookup"><span data-stu-id="ddc60-105">Instance Configuration</span></span>  
 <span data-ttu-id="ddc60-106">Quando un database viene distribuito in produzione spesso esiste un contratto sul livello di servizio (Service Level Agreement, SLA) che definisce aree come i livelli di prestazioni richiesti dal database e il livello di disponibilità richiesto del database.</span><span class="sxs-lookup"><span data-stu-id="ddc60-106">When a database is deployed into production there is often a service level agreement (SLA) defining areas such as the levels of performance required from the database and the required availability level of the database.</span></span> <span data-ttu-id="ddc60-107">I termini del contratto sul livello di servizio in genere fornisce i requisiti di configurazione per l'istanza.</span><span class="sxs-lookup"><span data-stu-id="ddc60-107">The terms of the SLA typically drive configuration requirements for the instance.</span></span>  
  
 <span data-ttu-id="ddc60-108">Un'istanza viene configurata generalmente immediatamente dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="ddc60-108">An instance is usually configured immediately after it has been installed.</span></span> <span data-ttu-id="ddc60-109">La configurazione iniziale è solitamente determinata dai requisiti del contratto sul livello di servizio dei tipi di database studiato per essere distribuito all'istanza.</span><span class="sxs-lookup"><span data-stu-id="ddc60-109">The initial configuration is usually determined by the SLA requirements of the types of databases planned to be deployed to the instance.</span></span> <span data-ttu-id="ddc60-110">Dopo la distribuzione dei database, gli amministratori del database controllano le prestazioni dell'istanza e regolano le impostazioni di configurazione in base alle necessità se la metrica delle prestazioni mostra che l'istanza non sta soddisfacendo i requisiti del contratto del livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="ddc60-110">After the databases have been deployed, the database administrators monitor the performance of the instance and adjust the configuration settings as needed if the performance metrics show the instance is not meeting the SLA requirements.</span></span>  
  
## <a name="configuration-tasks"></a><span data-ttu-id="ddc60-111">Attività di configurazione</span><span class="sxs-lookup"><span data-stu-id="ddc60-111">Configuration Tasks</span></span>  
  
|<span data-ttu-id="ddc60-112">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="ddc60-112">Task Description</span></span>|<span data-ttu-id="ddc60-113">Argomento</span><span class="sxs-lookup"><span data-stu-id="ddc60-113">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ddc60-114">Si descrivono le varie opzioni di configurazione dell'istanza e come visualizzare o modificare queste opzioni.</span><span class="sxs-lookup"><span data-stu-id="ddc60-114">Describes the various instance configuration options and how to view or change these options.</span></span>|[<span data-ttu-id="ddc60-115">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc60-115">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)|  
|<span data-ttu-id="ddc60-116">Si descrive come visualizzare e configurare i percorsi predefiniti dei nuovi file di dati e di log nell'istanza.</span><span class="sxs-lookup"><span data-stu-id="ddc60-116">Describes how to view and configure the default locations of new data and log files in the instance.</span></span>|[<span data-ttu-id="ddc60-117">Visualizzare o modificare i percorsi predefiniti per i file di dati e di log &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc60-117">View or Change the Default Locations for Data and Log Files &#40;SQL Server Management Studio&#41;</span></span>](view-or-change-the-default-locations-for-data-and-log-files.md)|  
|<span data-ttu-id="ddc60-118">Si descrive come configurare SQL Server per l'utilizzo di Soft-NUMA</span><span class="sxs-lookup"><span data-stu-id="ddc60-118">Describes how to configure SQL Server to use soft-NUMA.</span></span>|[<span data-ttu-id="ddc60-119">Configurare SQL Server per l'uso di &#40;soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc60-119">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)|  
|<span data-ttu-id="ddc60-120">Si descrive come eseguire il mapping di una porta TCP/IP all'affinità del nodo NUMA (non-uniform memory access).</span><span class="sxs-lookup"><span data-stu-id="ddc60-120">Describes how to map a TCP/IP port to non-uniform memory access (NUMA) node affinity.</span></span>|[<span data-ttu-id="ddc60-121">Eseguire il mapping delle porte TCP/IP ai nodi NUMA &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc60-121">Map TCP IP Ports to NUMA Nodes &#40;SQL Server&#41;</span></span>](map-tcp-ip-ports-to-numa-nodes-sql-server.md)|  
|<span data-ttu-id="ddc60-122">Si descrive come abilitare i criteri di Blocco di pagine in memoria di Windows.</span><span class="sxs-lookup"><span data-stu-id="ddc60-122">Describes how to enable the Windows Lock Pages In Memory policy.</span></span> <span data-ttu-id="ddc60-123">Con questi criteri è possibile determinare gli account autorizzati a utilizzare un processo per mantenere i dati nella memoria fisica, impedendo al sistema di eseguire il paging dei dati nella memoria virtuale su disco.</span><span class="sxs-lookup"><span data-stu-id="ddc60-123">This policy determines which accounts can use a process to keep data in physical memory, preventing the system from paging the data to virtual memory on disk.</span></span>|[<span data-ttu-id="ddc60-124">Abilitare l'opzione Blocco di pagine in memoria &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc60-124">Enable the Lock Pages in Memory Option &#40;Windows&#41;</span></span>](enable-the-lock-pages-in-memory-option-windows.md)|  
  
## <a name="see-also"></a><span data-ttu-id="ddc60-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddc60-125">See Also</span></span>  
 [<span data-ttu-id="ddc60-126">Istanze del motore di database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ddc60-126">Database Engine Instances &#40;SQL Server&#41;</span></span>](database-engine-instances-sql-server.md)  
  
  