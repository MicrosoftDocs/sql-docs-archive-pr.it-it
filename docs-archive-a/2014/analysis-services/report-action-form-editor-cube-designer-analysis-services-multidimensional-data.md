---
title: Editor dei form delle azioni report (scheda azioni, Progettazione cubi) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.actionexpression.reportaction.f1
ms.assetid: cebfdd07-e376-46d6-86ef-b6f816a2f360
author: minewiskan
ms.author: owend
ms.openlocfilehash: a6e417f666ec5e6827763257eff19294e21543b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630096"
---
# <a name="report-action-form-editor-actions-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="2c921-102">Editor dei form delle azioni report (scheda Azioni, Progettazione cubi) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="2c921-102">Report Action Form Editor (Actions Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2c921-103">Usare il riquadro **Editor dei form delle azioni report** nella scheda **Azioni** in Progettazione cubi per modificare l'azione del report selezionata nel riquadro **Libreria azioni** .</span><span class="sxs-lookup"><span data-stu-id="2c921-103">Use the **Report Action Form Editor** pane on the **Actions** tab in Cube Designer to modify the report action selected in the **Action Organizer** pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2c921-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2c921-104">Options</span></span>  
 <span data-ttu-id="2c921-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2c921-105">**Name**</span></span>  
 <span data-ttu-id="2c921-106">Consente di digitare il nome dell'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-106">Type the name of the action.</span></span>  
  
 <span data-ttu-id="2c921-107">**Destinazione azione**</span><span class="sxs-lookup"><span data-stu-id="2c921-107">**Action Target**</span></span>  
 <span data-ttu-id="2c921-108">Espandere la finestra per visualizzare le opzioni **Tipo di destinazione** e **Oggetti di destinazione** .</span><span class="sxs-lookup"><span data-stu-id="2c921-108">Expand to view the **Target type** and **Target object** options.</span></span>  
  
 <span data-ttu-id="2c921-109">**Tipo di destinazione**</span><span class="sxs-lookup"><span data-stu-id="2c921-109">**Target type**</span></span>  
 <span data-ttu-id="2c921-110">Consente di selezionare il tipo di oggetto a cui associare l'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-110">Select the type of object to which the action is to be associated.</span></span> <span data-ttu-id="2c921-111">Il server restituisce al client solo le azioni del tipo specificato relative all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2c921-111">The server returns to the client only those actions that apply to the object of the specified type.</span></span> <span data-ttu-id="2c921-112">L'azione è disponibile per il client se il valore di **Condizione** viene soddisfatto e se sono selezionati gli oggetti specificati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2c921-112">The action is available to the client if the **Condition** is met and if the objects specified in the following table are selected.</span></span>  
  
|<span data-ttu-id="2c921-113">Valore</span><span class="sxs-lookup"><span data-stu-id="2c921-113">Value</span></span>|<span data-ttu-id="2c921-114">Oggetto selezionato</span><span class="sxs-lookup"><span data-stu-id="2c921-114">Selected Object</span></span>|  
|-----------|---------------------|  
|<span data-ttu-id="2c921-115">Membri dell'attributo</span><span class="sxs-lookup"><span data-stu-id="2c921-115">Attribute members</span></span>|<span data-ttu-id="2c921-116">In **Oggetto di destinazione**è selezionato un membro dell'attributo da un livello basato sull'attributo.</span><span class="sxs-lookup"><span data-stu-id="2c921-116">A member is selected from a level based on the attribute in **Target object**.</span></span><br /><br /> <span data-ttu-id="2c921-117">Nota: altre gerarchie utente che usano l'attributo selezionato ereditano l'azione del report.</span><span class="sxs-lookup"><span data-stu-id="2c921-117">Note: Other user hierarchies that use the selected attribute inherit the report action.</span></span>|  
|<span data-ttu-id="2c921-118">Celle</span><span class="sxs-lookup"><span data-stu-id="2c921-118">Cells</span></span>|<span data-ttu-id="2c921-119">In **Oggetto di destinazione** è selezionato il set denominato.</span><span class="sxs-lookup"><span data-stu-id="2c921-119">The named set in **Target object** is selected.</span></span> <span data-ttu-id="2c921-120">Selezionare **Tutte le celle** per selezionare tutte le celle del cubo.</span><span class="sxs-lookup"><span data-stu-id="2c921-120">Select **All cells** to select all of the cells in the cube.</span></span>|  
|<span data-ttu-id="2c921-121">Cubo</span><span class="sxs-lookup"><span data-stu-id="2c921-121">Cube</span></span>|<span data-ttu-id="2c921-122">In **Oggetto di destinazione** è selezionato il cubo.</span><span class="sxs-lookup"><span data-stu-id="2c921-122">The cube in **Target object** is selected.</span></span> <span data-ttu-id="2c921-123">Selezionare CURRENTCUBE per utilizzare il cubo corrente.</span><span class="sxs-lookup"><span data-stu-id="2c921-123">Select CURRENTCUBE to use the current cube.</span></span><br /><br /> <span data-ttu-id="2c921-124">Nota: l'uso di CURRENTCUBE garantisce maggiore portabilità nel caso in cui il cubo venga rinominato o l'azione venga copiata in altri cubi.</span><span class="sxs-lookup"><span data-stu-id="2c921-124">Note: Using CURRENTCUBE provides additional portability in cases where the cube may be renamed or the action copied to other cubes.</span></span> <span data-ttu-id="2c921-125">È consigliabile utilizzare CURRENTCUBE per rappresentare il cubo corrente.</span><span class="sxs-lookup"><span data-stu-id="2c921-125">It is recommended that you use CURRENTCUBE to represent the current cube.</span></span>|  
|<span data-ttu-id="2c921-126">Membri della dimensione</span><span class="sxs-lookup"><span data-stu-id="2c921-126">Dimension members</span></span>|<span data-ttu-id="2c921-127">In **Oggetto di destinazione** è selezionato un membro della dimensione.</span><span class="sxs-lookup"><span data-stu-id="2c921-127">A member of the dimension in **Target object** is selected.</span></span>|  
|<span data-ttu-id="2c921-128">Gerarchia</span><span class="sxs-lookup"><span data-stu-id="2c921-128">Hierarchy</span></span>|<span data-ttu-id="2c921-129">In **Oggetto di destinazione** è selezionata la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2c921-129">The hierarchy in **Target object** is selected.</span></span>|  
|<span data-ttu-id="2c921-130">Membri della gerarchia</span><span class="sxs-lookup"><span data-stu-id="2c921-130">Hierarchy members</span></span>|<span data-ttu-id="2c921-131">In **Oggetto di destinazione** è selezionato un membro della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="2c921-131">A member within the hierarchy in **Target object** is selected.</span></span>|  
|<span data-ttu-id="2c921-132">Level</span><span class="sxs-lookup"><span data-stu-id="2c921-132">Level</span></span>|<span data-ttu-id="2c921-133">In **Oggetto di destinazione** è selezionato il livello.</span><span class="sxs-lookup"><span data-stu-id="2c921-133">The level in **Target object** is selected.</span></span>|  
|<span data-ttu-id="2c921-134">Membri del livello</span><span class="sxs-lookup"><span data-stu-id="2c921-134">Level members</span></span>|<span data-ttu-id="2c921-135">In **Oggetto di destinazione** è selezionato un membro del livello.</span><span class="sxs-lookup"><span data-stu-id="2c921-135">A member within the level in **Target object** is selected.</span></span>|  
  
 <span data-ttu-id="2c921-136">**Oggetto di destinazione**</span><span class="sxs-lookup"><span data-stu-id="2c921-136">**Target object**</span></span>  
 <span data-ttu-id="2c921-137">Consente di selezionare l'oggetto a cui associare l'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-137">Select the object to which the action is to be associated.</span></span> <span data-ttu-id="2c921-138">L'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] restituisce nel client solo le azioni applicabili all'oggetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="2c921-138">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance returns to the client only those actions that apply to the selected object.</span></span> <span data-ttu-id="2c921-139">L'elenco degli oggetti disponibili è vincolato dall'opzione selezionata in **Tipo di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="2c921-139">The list of available objects is constrained by the choice of **Target type**.</span></span>  
  
 <span data-ttu-id="2c921-140">**Condizione (facoltativa)**</span><span class="sxs-lookup"><span data-stu-id="2c921-140">**Condition (Optional)**</span></span>  
 <span data-ttu-id="2c921-141">Consente di immettere l'espressione MDX (Multidimensional Expression) che descrive una condizione facoltativa, usata insieme a **Oggetto di destinazione**, per vincolare ulteriormente la disponibilità dell'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-141">Enter the Multidimensional Expressions (MDX) expression that describes an optional condition, used in conjunction with **Target object**, which further restricts when the action is available.</span></span> <span data-ttu-id="2c921-142">L'espressione deve restituire un valore booleano il quale, se è True, indica che l'azione è disponibile.</span><span class="sxs-lookup"><span data-stu-id="2c921-142">The expression must return a Boolean value that, if true, indicates the action is available.</span></span>  
  
 <span data-ttu-id="2c921-143">Trascinare gli elementi selezionati dal riquadro **Strumenti di calcolo** alla casella di questa opzione per includere la sintassi MDX per l'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="2c921-143">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="2c921-144">**Server di report**</span><span class="sxs-lookup"><span data-stu-id="2c921-144">**Report Server**</span></span>  
 <span data-ttu-id="2c921-145">Espandere la finestra per visualizzare le opzioni **Nome server**, **Percorso server**e **Formato report** .</span><span class="sxs-lookup"><span data-stu-id="2c921-145">Expand to view the **Server name**, **Server path**, and **Report format** options.</span></span>  
  
 <span data-ttu-id="2c921-146">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="2c921-146">**Server name**</span></span>  
 <span data-ttu-id="2c921-147">Consente di digitare il nome dell' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] istanza in cui l'azione esegue il report.</span><span class="sxs-lookup"><span data-stu-id="2c921-147">Type the name of the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instance on which the action runs the report.</span></span>  
  
 <span data-ttu-id="2c921-148">**Percorso server**</span><span class="sxs-lookup"><span data-stu-id="2c921-148">**Server path**</span></span>  
 <span data-ttu-id="2c921-149">Consente di digitare il percorso del report nell'istanza di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c921-149">Type the path to the report on the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] instance.</span></span> <span data-ttu-id="2c921-150">Ad esempio, digitare **Vendite/VenditeAnnualiPerCategoria**.</span><span class="sxs-lookup"><span data-stu-id="2c921-150">For example, type **Sales/YearlySalesByCategory**.</span></span>  
  
 <span data-ttu-id="2c921-151">**Formato report**</span><span class="sxs-lookup"><span data-stu-id="2c921-151">**Report format**</span></span>  
 <span data-ttu-id="2c921-152">Consente di selezionare il formato in cui viene restituito il report.</span><span class="sxs-lookup"><span data-stu-id="2c921-152">Select the format in which the report is returned.</span></span> <span data-ttu-id="2c921-153">Nella tabella seguente vengono descritti i formati disponibili.</span><span class="sxs-lookup"><span data-stu-id="2c921-153">The following table describes the available formats.</span></span>  
  
|<span data-ttu-id="2c921-154">Valore</span><span class="sxs-lookup"><span data-stu-id="2c921-154">Value</span></span>|<span data-ttu-id="2c921-155">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c921-155">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2c921-156">HTML5</span><span class="sxs-lookup"><span data-stu-id="2c921-156">HTML5</span></span>|<span data-ttu-id="2c921-157">Il report viene restituito in un formato conforme a HTML 5.0.</span><span class="sxs-lookup"><span data-stu-id="2c921-157">Report is returned in an HTML 5.0-compliant format.</span></span>|  
|<span data-ttu-id="2c921-158">HTML3</span><span class="sxs-lookup"><span data-stu-id="2c921-158">HTML3</span></span>|<span data-ttu-id="2c921-159">Il report viene restituito in un formato conforme a HTML 3.2.</span><span class="sxs-lookup"><span data-stu-id="2c921-159">Report is returned in an HTML 3.2-compliant format.</span></span>|  
|<span data-ttu-id="2c921-160">Excel</span><span class="sxs-lookup"><span data-stu-id="2c921-160">Excel</span></span>|<span data-ttu-id="2c921-161">Il report viene restituito come file di cartella di lavoro (XLS) di [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel.</span><span class="sxs-lookup"><span data-stu-id="2c921-161">Report is returned as a [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel workbook (.xls) file.</span></span>|  
|<span data-ttu-id="2c921-162">PDF</span><span class="sxs-lookup"><span data-stu-id="2c921-162">PDF</span></span>|<span data-ttu-id="2c921-163">Il report viene restituito come file Adobe PDF con estensione pdf.</span><span class="sxs-lookup"><span data-stu-id="2c921-163">Report is returned as an Adobe Portable Document Format (.pdf) file.</span></span>|  
  
 <span data-ttu-id="2c921-164">**Parametri (facoltativi)**</span><span class="sxs-lookup"><span data-stu-id="2c921-164">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="2c921-165">Espandere la finestra per visualizzare una griglia in cui è possibile immettere i parametri del report specificati in **Report**.</span><span class="sxs-lookup"><span data-stu-id="2c921-165">Expand to view a grid in which report parameters can be supplied for the report specified in **Report**.</span></span> <span data-ttu-id="2c921-166">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c921-166">The grid contains the following columns:</span></span>  
  
|<span data-ttu-id="2c921-167">Colonna</span><span class="sxs-lookup"><span data-stu-id="2c921-167">Column</span></span>|<span data-ttu-id="2c921-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c921-168">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2c921-169">**Nome parametro**</span><span class="sxs-lookup"><span data-stu-id="2c921-169">**Parameter Name**</span></span>|<span data-ttu-id="2c921-170">Consente di digitare il nome del parametro del report da passare al report.</span><span class="sxs-lookup"><span data-stu-id="2c921-170">Type the name of the report parameter to be passed to the report.</span></span>|  
|<span data-ttu-id="2c921-171">**Valore parametro**</span><span class="sxs-lookup"><span data-stu-id="2c921-171">**Parameter Value**</span></span>|<span data-ttu-id="2c921-172">Consente di digitare il valore del parametro del report da passare al report.</span><span class="sxs-lookup"><span data-stu-id="2c921-172">Type the value of the report parameter to be passed to the report.</span></span><br /><br /> <span data-ttu-id="2c921-173">Fare clic sul pulsante con i puntini di sospensione (**...**) per visualizzare la finestra di dialogo **Generatore MDX** e creare un'espressione MDX che restituisca il valore del parametro del report.</span><span class="sxs-lookup"><span data-stu-id="2c921-173">Click the ellipsis button (**...**) to display the **MDX Builder** dialog box and create an MDX expression that provides the value of the report parameter.</span></span> <span data-ttu-id="2c921-174">Per altre informazioni sulla finestra di dialogo **Generatore MDX**, vedere [Generatore MDX &#40;Analysis Services - Dati multidimensionali&#41;](mdx-builder-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2c921-174">For more information about the **MDX Builder** dialog box, see [MDX Builder &#40;Analysis Services - Multidimensional Data&#41;](mdx-builder-analysis-services-multidimensional-data.md).</span></span><br /><br /> <span data-ttu-id="2c921-175">Se il parametro è impostato su un'espressione MDX, tale espressione viene valutata quando l'azione viene eseguita, altrimenti viene passata al report senza alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="2c921-175">If the parameter is set to an MDX expression, then the expression is evaluated when the action is run, otherwise it is passed to the report without modification.</span></span>|  
  
 <span data-ttu-id="2c921-176">**Proprietà aggiuntive**</span><span class="sxs-lookup"><span data-stu-id="2c921-176">**Additional Properties**</span></span>  
 <span data-ttu-id="2c921-177">Espandere la finestra per visualizzare le opzioni **Chiamata**, **Applicazione**, **Descrizione**, **Didascalia**e **Didascalia MDX** .</span><span class="sxs-lookup"><span data-stu-id="2c921-177">Expand to view the **Invocation**, **Application**, **Description**, **Caption**, and **Caption Is MDX** options.</span></span>  
  
 <span data-ttu-id="2c921-178">**Chiamata**</span><span class="sxs-lookup"><span data-stu-id="2c921-178">**Invocation**</span></span>  
 <span data-ttu-id="2c921-179">Consente di selezionare l'impostazione che indica quando eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-179">Select the setting that indicates when the action should be carried out.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c921-180">Questa opzione costituisce solo un'indicazione per un'applicazione client relativa al momento in cui eseguire un'azione e non controlla direttamente la chiamata dell'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-180">This option only provides a recommendation to a client application as to when to execute an action, and does not directly control the invocation of the action.</span></span>  
  
 <span data-ttu-id="2c921-181">Nella tabella seguente vengono descritte le impostazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="2c921-181">The following table describes the available settings.</span></span>  
  
|<span data-ttu-id="2c921-182">Valore</span><span class="sxs-lookup"><span data-stu-id="2c921-182">Value</span></span>|<span data-ttu-id="2c921-183">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c921-183">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2c921-184">Batch</span><span class="sxs-lookup"><span data-stu-id="2c921-184">Batch</span></span>|<span data-ttu-id="2c921-185">L'azione deve essere eseguita come parte di un'operazione batch o di un' [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] attività.</span><span class="sxs-lookup"><span data-stu-id="2c921-185">The action should run as part of a batch operation or a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] task.</span></span>|  
|<span data-ttu-id="2c921-186">Interattività</span><span class="sxs-lookup"><span data-stu-id="2c921-186">Interactive</span></span>|<span data-ttu-id="2c921-187">L'azione viene eseguita in seguito alla chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2c921-187">The action runs when the user invokes the action.</span></span>|  
|<span data-ttu-id="2c921-188">Su apertura</span><span class="sxs-lookup"><span data-stu-id="2c921-188">On Open</span></span>|<span data-ttu-id="2c921-189">L'azione viene eseguita quando il cubo viene aperto per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="2c921-189">The action runs when the cube is first opened.</span></span>|  
  
 <span data-ttu-id="2c921-190">**Applicazione**</span><span class="sxs-lookup"><span data-stu-id="2c921-190">**Application**</span></span>  
 <span data-ttu-id="2c921-191">Consente di digitare il nome dell'applicazione in grado di interpretare la stringa restituita da **Espressione azione**.</span><span class="sxs-lookup"><span data-stu-id="2c921-191">Type the name of the application that can interpret the string returned by **Action expression**.</span></span>  
  
 <span data-ttu-id="2c921-192">È inoltre possibile utilizzare questa opzione per identificare l'applicazione client che utilizza con maggiore frequenza questa azione, oltre a visualizzare icone appropriate accanto all'azione in un menu a comparsa.</span><span class="sxs-lookup"><span data-stu-id="2c921-192">You can also use this option to identify which client application most commonly uses this action, as well as to display appropriate icons next to the action in a pop-up menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c921-193">Questa opzione costituisce solo un'indicazione per un'applicazione client relativa a quale client deve eseguire un'azione e non controlla direttamente l'accesso all'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-193">This option only provides a recommendation to a client application as to what client application should execute an action, and does not directly control access to the action.</span></span> <span data-ttu-id="2c921-194">Nelle applicazioni devono essere nascoste le azioni associate ad altre applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="2c921-194">Client applications should hide any actions that are associated with other client applications.</span></span>  
  
 <span data-ttu-id="2c921-195">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2c921-195">**Description**</span></span>  
 <span data-ttu-id="2c921-196">Consente di digitare la descrizione facoltativa dell'azione.</span><span class="sxs-lookup"><span data-stu-id="2c921-196">Type the optional description of the action.</span></span>  
  
 <span data-ttu-id="2c921-197">**Sottotitolo**</span><span class="sxs-lookup"><span data-stu-id="2c921-197">**Caption**</span></span>  
 <span data-ttu-id="2c921-198">Consente di digitare la didascalia da visualizzare per l'azione nell'applicazione client se l'opzione **Didascalia MDX** è impostata su **False**.</span><span class="sxs-lookup"><span data-stu-id="2c921-198">Type the caption to be displayed for the action in the client application if **Caption Is MDX** is set to **False**.</span></span>  
  
 <span data-ttu-id="2c921-199">Digitare l'espressione MDX che restituisce una stringa per la didascalia se l'opzione **Didascalia MDX** è impostata su **True**.</span><span class="sxs-lookup"><span data-stu-id="2c921-199">Type the MDX expression that returns a string for the caption if **Caption Is MDX** is set to **True**.</span></span>  
  
 <span data-ttu-id="2c921-200">**Didascalia MDX**</span><span class="sxs-lookup"><span data-stu-id="2c921-200">**Caption is MDX**</span></span>  
 <span data-ttu-id="2c921-201">Selezionare **False** per indicare che **Didascalia** contiene una stringa letterale che rappresenta una didascalia da visualizzare per l'azione nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="2c921-201">Select **False** to indicate that **Caption** contains a literal string representing a caption to be displayed for the action in the client application.</span></span>  
  
 <span data-ttu-id="2c921-202">Selezionare **True** per indicare che **Didascalia** contiene un'espressione MDX che restituisce una stringa che rappresenta una didascalia da visualizzare per l'azione nell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="2c921-202">Select **True** to indicate that **Caption** contains an MDX expression that returns a string representing a caption to be displayed for the action in the client application.</span></span> <span data-ttu-id="2c921-203">L'espressione MDX deve essere risolta prima che l'azione venga restituita all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="2c921-203">The MDX expression must be resolved before the action is returned to the client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c921-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c921-204">See Also</span></span>  
 <span data-ttu-id="2c921-205">[Azioni &#40;Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2c921-205">[Actions &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="2c921-206">[Barra degli strumenti &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2c921-206">[Toolbar &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-actions-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="2c921-207">[Libreria azioni &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2c921-207">[Action Organizer &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="2c921-208">[Strumenti di calcolo &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2c921-208">[Calculation Tools &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-actions-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="2c921-209">[Editor dei form delle azioni &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2c921-209">[Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](action-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2c921-210">Editor dei form delle azioni drill-through &#40;scheda azioni, Progettazione cubi&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="2c921-210">Drillthrough Action Form Editor &#40;Actions Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](drillthrough-action-form-editor-cube-designer-analysis-services-multidimensional-data.md)  
  
  