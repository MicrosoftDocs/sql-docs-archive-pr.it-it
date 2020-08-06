---
title: Visualizzare oggetti di pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, properties
- properties [Integration Services]
- Package Explorer window [Integration Services]
- packages [Integration Services], properties
- explorer view [Integration Services]
- SSIS packages, properties
- viewing package objects
- SQL Server Integration Services packages, properties
ms.assetid: a85c0245-0a68-4eb0-83b1-9b11df80bd10
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ffe46be35db26186f715b18ba6114732d130e02e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635109"
---
# <a name="view-package-objects"></a><span data-ttu-id="95dc5-102">Visualizzazione di oggetti di pacchetto</span><span class="sxs-lookup"><span data-stu-id="95dc5-102">View Package Objects</span></span>
  <span data-ttu-id="95dc5-103">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] è disponibile la scheda **Esplora pacchetti** , che consente di visualizzare i pacchetti in una modalità simile a quella di Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="95dc5-103">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the **Package Explorer** tab provides an explorer view of the package.</span></span> <span data-ttu-id="95dc5-104">La visualizzazione riflette la gerarchia dei contenitori dell'architettura di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95dc5-104">The view reflects the container hierarchy of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] architecture.</span></span> <span data-ttu-id="95dc5-105">Il contenitore del pacchetto si trova al livello principale della gerarchia. Espandendo il pacchetto è possibile visualizzare le connessioni, gli eseguibili, i gestori di eventi, i provider di log, i vincoli di precedenza e le variabili del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="95dc5-105">The package container is at the top of the hierarchy, and you expand the package to view the connections, executables, event handlers, log providers, precedence constraints, and variables in the package.</span></span>

 <span data-ttu-id="95dc5-106">Gli eseguibili, ovvero i contenitori e le attività nel pacchetto, possono includere gestori di eventi, vincoli di precedenza e variabili.</span><span class="sxs-lookup"><span data-stu-id="95dc5-106">The executables, which are the containers and tasks in the package, can include event handlers, precedence constraints, and variables.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="95dc5-107">supporta una gerarchia nidificata di contenitori. A loro volta, i contenitori Ciclo For, Ciclo Foreach e Sequenza possono includere altri eseguibili.</span><span class="sxs-lookup"><span data-stu-id="95dc5-107">supports a nested hierarchy of containers, and the For Loop, Foreach Loop, and Sequence containers can include other executables.</span></span>

 <span data-ttu-id="95dc5-108">Se un pacchetto include un flusso di dati, in **Esplora pacchetti** verranno visualizzate l'attività Flusso di dati e una cartella **Componenti** contenente l'elenco dei componenti del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="95dc5-108">If a package includes a data flow, the **Package Explorer** lists the Data Flow task and includes a **Components** folder that lists the data flow components.</span></span>

 <span data-ttu-id="95dc5-109">Dalla scheda **Esplora pacchetti** è possibile eliminare oggetti da un pacchetto e accedere alla finestra **Proprietà** per visualizzare le proprietà degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="95dc5-109">From the **Package Explorer** tab, you can delete objects in a package and access the **Properties** window to view object properties.</span></span>

 <span data-ttu-id="95dc5-110">Nella figura seguente viene illustrata l'albero di un semplice pacchetto.</span><span class="sxs-lookup"><span data-stu-id="95dc5-110">The following diagram shows a tree view of a simple package.</span></span>

 <span data-ttu-id="95dc5-111">![Screenshot della scheda Esplora pacchetti](media/packageexplorer.gif "Screenshot della scheda Esplora pacchetti")</span><span class="sxs-lookup"><span data-stu-id="95dc5-111">![Screenshot of the Package Explorer tab](media/packageexplorer.gif "Screenshot of the Package Explorer tab")</span></span>

### <a name="to-view-package-content"></a><span data-ttu-id="95dc5-112">Per visualizzare il contenuto di un pacchetto</span><span class="sxs-lookup"><span data-stu-id="95dc5-112">To view package content</span></span>

-   [<span data-ttu-id="95dc5-113">Visualizzazione degli oggetti dei pacchetti in Esplora pacchetti</span><span class="sxs-lookup"><span data-stu-id="95dc5-113">View Package Objects in Package Explorer</span></span>](../../2014/integration-services/view-package-objects-in-package-explorer.md)

## <a name="see-also"></a><span data-ttu-id="95dc5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95dc5-114">See Also</span></span>
 <span data-ttu-id="95dc5-115">[Integration Services attività](control-flow/integration-services-tasks.md) [Integration Services](control-flow/integration-services-containers.md) [vincoli di precedenza](control-flow/precedence-constraints.md) [Integration Services &#40;variabili SSIS](integration-services-ssis-variables.md)&#41; Integration Services i [gestori eventi &#40;SSIS](integration-services-ssis-event-handlers.md)&#41; [Integration Services la registrazione SSIS](performance/integration-services-ssis-logging.md) &#40;</span><span class="sxs-lookup"><span data-stu-id="95dc5-115">[Integration Services Tasks](control-flow/integration-services-tasks.md) [Integration Services Containers](control-flow/integration-services-containers.md) [Precedence Constraints](control-flow/precedence-constraints.md) [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) [Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) [Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md)</span></span>

