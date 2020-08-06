---
title: Progettazione di aggregazioni (Analysis Services-multidimensionale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- aggregations [Analysis Services], partitions
- partitions [Analysis Services], aggregations
ms.assetid: 3072b7e0-6961-42ad-a287-16f391f2cec4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 18d8ea1adb645868a11b70966ba3be2ed1764fbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637460"
---
# <a name="designing-aggregations-analysis-services---multidimensional"></a><span data-ttu-id="d02d4-102">Progettazione di aggregazioni (Analysis Services - Multidimensionale)</span><span class="sxs-lookup"><span data-stu-id="d02d4-102">Designing Aggregations (Analysis Services - Multidimensional)</span></span>
  <span data-ttu-id="d02d4-103">Le aggregazioni sono riepiloghi precalcolati dei dati del cubo che consentono a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] di fornire rapidamente le risposte alle query.</span><span class="sxs-lookup"><span data-stu-id="d02d4-103">Aggregations are precalculated summaries of cube data that help enable [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to provide rapid query responses.</span></span>  
  
 <span data-ttu-id="d02d4-104">Per impostare le opzioni di archiviazione e progettare le aggregazioni per una partizione, è possibile utilizzare Progettazione guidata aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-104">To set storage options and design aggregations for a partition, use the Aggregation Design Wizard.</span></span> <span data-ttu-id="d02d4-105">Questa procedura guidata viene eseguita su una singola partizione alla volta di un gruppo di misure in modo da consentire la selezione di opzioni e progettazioni diverse per ogni partizione.</span><span class="sxs-lookup"><span data-stu-id="d02d4-105">The wizard operates on a single partition of a measure group at a time so that you can select different options and designs for each partition.</span></span> <span data-ttu-id="d02d4-106">La procedura guidata consente di eseguire in modo semplificato i passaggi necessari per configurare l'archiviazione e progettare l'aggregazione per una partizione.</span><span class="sxs-lookup"><span data-stu-id="d02d4-106">The wizard takes you through steps to configure storage and design aggregation for a partition.</span></span> <span data-ttu-id="d02d4-107">Per ulteriori informazioni sulla configurazione dell'archiviazione, vedere.</span><span class="sxs-lookup"><span data-stu-id="d02d4-107">For more information about configuring storage, see.</span></span>  
  
 <span data-ttu-id="d02d4-108">Selezionare un metodo per il controllo del numero di aggregazioni che verranno progettate dalla procedura guidata e quindi eseguire automaticamente il processo di progettazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-108">Select a method for controlling the number of aggregations the wizard will design, and then let the wizard design the aggregations.</span></span>  
  
 <span data-ttu-id="d02d4-109">L'obiettivo è la progettazione di un numero ottimale di aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-109">The goal is to design the optimal number of aggregations.</span></span> <span data-ttu-id="d02d4-110">Tale numero deve consentire non solo di ottenere tempi di risposta soddisfacenti, ma anche di impedire la creazione di partizioni con dimensioni eccessive.</span><span class="sxs-lookup"><span data-stu-id="d02d4-110">This number should not only provide satisfactory response time, but also prevent excessive partition size.</span></span> <span data-ttu-id="d02d4-111">Un numero maggiore di aggregazioni produce tempi di risposta più brevi ma richiede anche uno spazio di archiviazione maggiore e tempi di calcolo più lunghi.</span><span class="sxs-lookup"><span data-stu-id="d02d4-111">A greater number of aggregations produces faster response times but it also requires more storage space and may take longer to compute.</span></span> <span data-ttu-id="d02d4-112">Inoltre, a mano a mano che la procedura guidata progetta nuove aggregazioni, le aggregazioni precedenti generano miglioramenti delle prestazioni decisamente superiori rispetto alle nuove.</span><span class="sxs-lookup"><span data-stu-id="d02d4-112">Moreover, as the wizard designs more and more aggregations, earlier aggregations produce considerably larger performance gains than later aggregations.</span></span> <span data-ttu-id="d02d4-113">Anche la riduzione delle aggregazioni di minore utilità contribuisce a migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-113">Reduction in less useful aggregations increases performance as well.</span></span> <span data-ttu-id="d02d4-114">È possibile controllare il numero di aggregazioni progettate automaticamente utilizzando uno dei metodi seguenti disponibili nella procedura guidata:</span><span class="sxs-lookup"><span data-stu-id="d02d4-114">You can control the number of aggregations the wizard designs by one of the following methods available in the wizard:</span></span>  
  
-   <span data-ttu-id="d02d4-115">Specificare un limite per lo spazio di archiviazione delle aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-115">Specify a storage space limit for the aggregations.</span></span>  
  
-   <span data-ttu-id="d02d4-116">Specificare un limite per il miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-116">Specify a performance gain limit.</span></span>  
  
-   <span data-ttu-id="d02d4-117">Arrestare manualmente la procedura guidata quando la curva del raffronto tra prestazioni e dimensioni visualizzata inizia a stabilizzarsi su un miglioramento delle prestazioni accettabile.</span><span class="sxs-lookup"><span data-stu-id="d02d4-117">Stop the wizard manually when the displayed performance versus size curve starts to level off at an acceptable performance gain.</span></span>  
  
-   <span data-ttu-id="d02d4-118">Scegliere di non progettare aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="d02d4-118">Choose not to design aggregations.</span></span>  
  
 <span data-ttu-id="d02d4-119">Per configurare l'archiviazione, la procedura guidata deve connettersi a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d02d4-119">To design storage, the wizard must be able to connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] on the target server.</span></span> <span data-ttu-id="d02d4-120">Se [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non viene eseguito nel server di destinazione o il processo di configurazione dell'archiviazione non riesce a connettersi in altro modo al server di destinazione, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d02d4-120">The wizard will display an error message if [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not running on the target server or if the storage design process is otherwise unable to connect to the target server.</span></span>  
  
 <span data-ttu-id="d02d4-121">Il passaggio finale della procedura guidata consente di scegliere se eseguire immediatamente l'elaborazione o posticiparla.</span><span class="sxs-lookup"><span data-stu-id="d02d4-121">The final step of the wizard allows you to process or defer processing.</span></span> <span data-ttu-id="d02d4-122">In caso di elaborazione immediata, vengono create le aggregazioni progettate con la procedura guidata. Se invece si posticipa il processo, le aggregazioni progettate vengono salvate per la futura elaborazione, consentendo tuttavia di proseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d02d4-122">Processing creates the aggregations you design with the wizard, while deferring processing saves the designed aggregations for future processing, thus allowing design activities to continue without processing.</span></span> <span data-ttu-id="d02d4-123">A seconda delle dimensioni della partizione, l'elaborazione potrebbe richiedere tempi lunghi.</span><span class="sxs-lookup"><span data-stu-id="d02d4-123">Depending on the size of the partition, processing may take considerable time.</span></span> <span data-ttu-id="d02d4-124">Se necessario, è possibile scegliere di interrompere l'elaborazione di una partizione.</span><span class="sxs-lookup"><span data-stu-id="d02d4-124">If you choose, you can interrupt processing a partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02d4-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d02d4-125">See Also</span></span>  
 [<span data-ttu-id="d02d4-126">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="d02d4-126">Aggregations and Aggregation Designs</span></span>](../multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  