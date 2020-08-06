---
title: Finestra di dialogo Proprietà database (SSAS-multidimensionale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.databaseproperties.f1
ms.assetid: 70f000b7-917f-4699-b142-7a0d13ff767c
author: minewiskan
ms.author: owend
ms.openlocfilehash: a465c333557f19e9572cd9c2b1f7c80aaf4ab5bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711132"
---
# <a name="database-properties-dialog-box-ssas---multidimensional"></a><span data-ttu-id="5344b-102">Finestra di dialogo Proprietà database (SSAS - Multidimensionale)</span><span class="sxs-lookup"><span data-stu-id="5344b-102">Database Properties Dialog Box (SSAS - Multidimensional)</span></span>
  <span data-ttu-id="5344b-103">Utilizzare la finestra di dialogo **Proprietà database** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per impostare le proprietà di un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5344b-103">Use the **Database Properties** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to set the properties of a database in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="5344b-104">Per visualizzare la finestra di dialogo **Proprietà database** è possibile fare clic con il pulsante destro del mouse su un database in Esplora oggetti e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5344b-104">You can display the **Database Properties** dialog box by right-clicking a database in Object Explorer and selecting **Properties**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5344b-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5344b-105">Options</span></span>  
  
|<span data-ttu-id="5344b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="5344b-106">Term</span></span>|<span data-ttu-id="5344b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="5344b-107">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="5344b-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5344b-108">**Name**</span></span>|<span data-ttu-id="5344b-109">Consente di modificare il nome del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-109">Type to change the name of the database.</span></span>|  
|<span data-ttu-id="5344b-110">**ID**</span><span class="sxs-lookup"><span data-stu-id="5344b-110">**ID**</span></span>|<span data-ttu-id="5344b-111">Consente di visualizzare l'identificatore del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-111">Displays the identifier of the database.</span></span>|  
|<span data-ttu-id="5344b-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5344b-112">**Description**</span></span>|<span data-ttu-id="5344b-113">Consente di modificare la descrizione del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-113">Type to change the description of the database.</span></span>|  
|<span data-ttu-id="5344b-114">**Timestamp creazione**</span><span class="sxs-lookup"><span data-stu-id="5344b-114">**Create Timestamp**</span></span>|<span data-ttu-id="5344b-115">Consente di visualizzare la data e l'ora di creazione del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-115">Displays the date and time the database was created.</span></span>|  
|<span data-ttu-id="5344b-116">**Ultimo aggiornamento schema**</span><span class="sxs-lookup"><span data-stu-id="5344b-116">**Last Schema Update**</span></span>|<span data-ttu-id="5344b-117">Consente di visualizzare la data e l'ora dell'ultimo aggiornamento dei metadati del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-117">Displays the date and time the metadata for the database was last updated.</span></span>|  
|<span data-ttu-id="5344b-118">**Ultimo aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="5344b-118">**Last Update**</span></span>|<span data-ttu-id="5344b-119">Consente di visualizzare la data e l'ora dell'ultimo aggiornamento dei dati del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-119">Displays the date and time the data for the database was last updated.</span></span>|  
|<span data-ttu-id="5344b-120">**Impostazioni di rappresentazione origine dati**</span><span class="sxs-lookup"><span data-stu-id="5344b-120">**Data Source Impersonation Info**</span></span>|<span data-ttu-id="5344b-121">Consente di selezionare le informazioni di rappresentazione utilizzate dal database per la connessione e l'interazione con le origini dei dati contenute nel database.</span><span class="sxs-lookup"><span data-stu-id="5344b-121">Select the impersonation information used by the database when connecting to and interacting with data sources contained by the database.</span></span> <span data-ttu-id="5344b-122">I valori validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5344b-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5344b-123">**ImpersonateAccount** (usare un nome utente e una password specifici di Windows).</span><span class="sxs-lookup"><span data-stu-id="5344b-123">**ImpersonateAccount** (use a specific Windows user name and password).</span></span><br /><br /> <span data-ttu-id="5344b-124">**ImpersonateService** (usare l'account del servizio).</span><span class="sxs-lookup"><span data-stu-id="5344b-124">**ImpersonateService** (use the service account).</span></span><br /><br /> <span data-ttu-id="5344b-125">**ImpersonateCurrentUser** (usare le credenziali dell'utente corrente).</span><span class="sxs-lookup"><span data-stu-id="5344b-125">**ImpersonateCurrentUser** (use the credentials of the current user).</span></span><br /><br /> <span data-ttu-id="5344b-126">**Default** (usare l'account del servizio per le operazioni MOLAP e l'utente corrente per il data mining).</span><span class="sxs-lookup"><span data-stu-id="5344b-126">**Default** (use the service account for MOLAP operations and current user for data mining).</span></span><br /><br /> <span data-ttu-id="5344b-127">Sebbene sia possibile definire le impostazioni di rappresentazione dell'origine dati al livello del database, questa operazione influirebbe unicamente sulle origini dati per cui è stato specificato **Eredita** per le impostazioni della rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="5344b-127">Although you can set data source impersonation settings at the database level, doing so will only affect those data sources that specify **Inherit** for their impersonation settings.</span></span> <span data-ttu-id="5344b-128">Le impostazioni di rappresentazione specificate direttamente sull'origine dati eseguiranno sempre l'override delle impostazioni specificate al livello del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-128">Impersonation settings specified directly on the data source will always override any settings that are specified at the database level.</span></span><br /><br /> <span data-ttu-id="5344b-129">Quando si sceglie un'opzione di rappresentazione, considerare i tipi di operazioni che dovranno essere supportati.</span><span class="sxs-lookup"><span data-stu-id="5344b-129">When choosing an impersonation option, consider the types of operations that will need to be supported.</span></span> <span data-ttu-id="5344b-130">Alcune operazioni, ad esempio l'elaborazione, non possono essere eseguite da</span><span class="sxs-lookup"><span data-stu-id="5344b-130">Some operations, such as processing, cannot be performed by</span></span>|  
|<span data-ttu-id="5344b-131">**Ultima elaborazione**</span><span class="sxs-lookup"><span data-stu-id="5344b-131">**Last Processed**</span></span>|<span data-ttu-id="5344b-132">Consente di visualizzare la data e l'ora dell'ultima elaborazione del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-132">Displays the date and time the database was last processed.</span></span>|  
|<span data-ttu-id="5344b-133">**Dimensioni stimate**</span><span class="sxs-lookup"><span data-stu-id="5344b-133">**Estimated Size**</span></span>|<span data-ttu-id="5344b-134">Consente di visualizzare le dimensioni stimate del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-134">Displays the estimated size of the database.</span></span>|  
|<span data-ttu-id="5344b-135">**Percorso di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="5344b-135">**Storage Location**</span></span>|<span data-ttu-id="5344b-136">Specifica la posizione del database.</span><span class="sxs-lookup"><span data-stu-id="5344b-136">Specifies the location of the database.</span></span> <span data-ttu-id="5344b-137">Se il database si trova nella directory dati predefinita, questo valore sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="5344b-137">If the database is located in the default Data directory, this value will be empty.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5344b-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5344b-138">See Also</span></span>  
 <span data-ttu-id="5344b-139">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="5344b-139">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="5344b-140">Database modelli multidimensionali &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="5344b-140">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-models/multidimensional-model-databases-ssas.md)  
  
  