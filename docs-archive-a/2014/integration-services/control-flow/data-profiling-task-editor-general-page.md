---
title: Editor attività Profiling dati (pagina Generale) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cfcdf472f817d3dd688a5f867ac74d46835ab91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629970"
---
# <a name="data-profiling-task-editor-general-page"></a><span data-ttu-id="2cfdf-102">Editor attività Profiling dati (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="2cfdf-102">Data Profiling Task Editor (General Page)</span></span>
  <span data-ttu-id="2cfdf-103">Usare la pagina **Generale** di **Editor attività Profiling dati** per configurare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cfdf-103">Use the **General** page of the **Data Profiling Task Editor** to configure the following options:</span></span>  
  
-   <span data-ttu-id="2cfdf-104">Specificare la destinazione per l'output del profilo.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-104">Specify the destination for the profile output.</span></span>  
  
-   <span data-ttu-id="2cfdf-105">Utilizzare le impostazioni predefinite per semplificare l'attività di profiling di una singola tabella o vista.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-105">Use the default settings to simplify the task of profiling a single table or view.</span></span>  
  
 <span data-ttu-id="2cfdf-106">Per altre informazioni sull'uso dell'attività Profiling dati, vedere [Impostazione dell'attività Profiling dati](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="2cfdf-106">For more information about how to use the Data Profiling task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="2cfdf-107">Per altre informazioni sull'uso del Visualizzatore profilo dati per analizzare l'output dell'attività Profiling dati, vedere [Visualizzatore profilo dati](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="2cfdf-107">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
 <span data-ttu-id="2cfdf-108">**Per aprire la pagina Generale in Editor attività Profiling dati**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-108">**To open the General page of the Data Profiling Task Editor**</span></span>  
  
1.  <span data-ttu-id="2cfdf-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenente l'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that has the Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="2cfdf-110">Nella scheda **Flusso di controllo** fare doppio clic sull'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-110">On the **Control Flow** tab, double-click the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="2cfdf-111">In **Editor attività Profiling dati**fare clic su **Generale**.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-111">In the **Data Profiling Task Editor**, click **General**.</span></span>  
  
## <a name="data-profiling-options"></a><span data-ttu-id="2cfdf-112">Opzioni di profiling dei dati</span><span class="sxs-lookup"><span data-stu-id="2cfdf-112">Data Profiling Options</span></span>  
 <span data-ttu-id="2cfdf-113">**Timeout**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-113">**Timeout**</span></span>  
 <span data-ttu-id="2cfdf-114">Specifica il numero di secondi dopo il quale attivare il timeout dell'attività Profiling dati e arrestarne l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-114">Specify the number of seconds after which the Data Profiling task should timeout and stop running.</span></span> <span data-ttu-id="2cfdf-115">Il valore predefinito è 0, che non specifica alcun timeout.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-115">The default value is 0, which indicates no timeout.</span></span>  
  
## <a name="destination-options"></a><span data-ttu-id="2cfdf-116">Opzioni destinazione</span><span class="sxs-lookup"><span data-stu-id="2cfdf-116">Destination Options</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2cfdf-117">Il file di output potrebbe contenere dati sensibili sul database e i dati inclusi nel database.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-117">The output file might contain sensitive data about your database and the data that database contains.</span></span> <span data-ttu-id="2cfdf-118">Per suggerimenti su come migliorare la sicurezza di questo file, vedere [Accesso ai file utilizzati dai pacchetti](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="2cfdf-118">For suggestions about how to make this file more secure, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="2cfdf-119">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-119">**DestinationType**</span></span>  
 <span data-ttu-id="2cfdf-120">Consente di specificare se salvare l'output del profilo dei dati in un file o una variabile:</span><span class="sxs-lookup"><span data-stu-id="2cfdf-120">Specify whether to save the data profile output to a file or a variable:</span></span>  
  
|<span data-ttu-id="2cfdf-121">valore</span><span class="sxs-lookup"><span data-stu-id="2cfdf-121">Value</span></span>|<span data-ttu-id="2cfdf-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cfdf-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2cfdf-123">**FileConnection**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-123">**FileConnection**</span></span>|<span data-ttu-id="2cfdf-124">Consente di salvare l'output del profilo in un file nel percorso specificato in una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-124">Save the profile output to a file in the location that is specified in a File connection manager.</span></span><br /><br /> <span data-ttu-id="2cfdf-125">Nota: è possibile specificare la gestione connessione file da usare tramite l'opzione **Destination** .</span><span class="sxs-lookup"><span data-stu-id="2cfdf-125">Note: You specify which File connection manager to use in the **Destination** option.</span></span>|  
|<span data-ttu-id="2cfdf-126">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-126">**Variable**</span></span>|<span data-ttu-id="2cfdf-127">Consente di salvare l'output del profilo in una variabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-127">Save the profile output to a package variable.</span></span><br /><br /> <span data-ttu-id="2cfdf-128">Nota: è possibile specificare la variabile del pacchetto da usare tramite l'opzione **Destination** .</span><span class="sxs-lookup"><span data-stu-id="2cfdf-128">Note: You specify which package variable to use in the **Destination** option.</span></span>|  
  
 <span data-ttu-id="2cfdf-129">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-129">**Destination**</span></span>  
 <span data-ttu-id="2cfdf-130">Consente di specificare la gestione connessione file o la variabile del pacchetto contenente l'output del profilo dei dati:</span><span class="sxs-lookup"><span data-stu-id="2cfdf-130">Specify which File connection manager or package variable contains the data profile output:</span></span>  
  
-   <span data-ttu-id="2cfdf-131">Se l'opzione **DestinationType** è impostata su **FileConnection**, l'opzione **Destination** visualizza le gestioni connessione file disponibili.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-131">If the **DestinationType** option is set to **FileConnection**, the **Destination** option displays the available File connection managers.</span></span> <span data-ttu-id="2cfdf-132">Selezionare una delle gestioni connessione oppure fare clic su \<New File connection> per creare una nuova gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-132">Select one of these connection managers, or select \<New File connection> to create a new File connection manager.</span></span>  
  
-   <span data-ttu-id="2cfdf-133">Se l'opzione **DestinationType** è impostata su **Variable**, l'opzione **Destination** visualizza le variabili del pacchetto disponibili nell'elenco **Destination** .</span><span class="sxs-lookup"><span data-stu-id="2cfdf-133">If the **DestinationType** option is set to **Variable**, the **Destination** option displays the available package variables in the **Destination** list.</span></span> <span data-ttu-id="2cfdf-134">Selezionare una delle variabili oppure fare clic su \<New Variable> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-134">Select one of these variables, or select \<New Variable> to create a new variable.</span></span>  
  
 <span data-ttu-id="2cfdf-135">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-135">**OverwriteDestination**</span></span>  
 <span data-ttu-id="2cfdf-136">Consente di specificare se sovrascrivere il file di output, se presente.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-136">Specify whether to overwrite the output file if it already exists.</span></span> <span data-ttu-id="2cfdf-137">Il valore predefinito è **False**.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-137">The default value is **False**.</span></span> <span data-ttu-id="2cfdf-138">Il valore di questa proprietà viene utilizzato solo quando l'opzione DestinationType è impostata su FileConnection.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-138">The value of this property is used only when the DestinationType option is set to FileConnection.</span></span> <span data-ttu-id="2cfdf-139">Quando l'opzione DestinationType è impostata su Variable, l'attività sovrascrive sempre il valore precedente della variabile.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-139">When the DestinationType option is set to Variable, the task always overwrites the previous value of the variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2cfdf-140">Se si tenta di eseguire l'attività Profiling dati più di una volta senza modificare il nome del file di output o impostare il valore della proprietà **OverwriteDestination** su **True**, l'attività restituirà un errore e un messaggio indicante che il file di output è già presente.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-140">If you try to run the Data Profiling task more than once without changing the output file name or changing the value of the **OverwriteDestination** property to **True**, the task fails with the message that the output file already exists.</span></span>  
  
## <a name="other-options"></a><span data-ttu-id="2cfdf-141">Altre opzioni</span><span class="sxs-lookup"><span data-stu-id="2cfdf-141">Other Options</span></span>  
 <span data-ttu-id="2cfdf-142">**Profilo rapido**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-142">**Quick Profile**</span></span>  
 <span data-ttu-id="2cfdf-143">Consente di visualizzare l'opzione **Form profilo rapido singola tabella**.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-143">Display the **Single Table Quick Profile Form**.</span></span> <span data-ttu-id="2cfdf-144">Questo form semplifica l'attività di profiling di una singola tabella o vista tramite le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-144">This form simplifies the task of profiling a single table or view by using default settings.</span></span> <span data-ttu-id="2cfdf-145">Per altre informazioni, vedere [Form profilo rapido singola tabella &#40;Attività Profiling dati&#41;](single-table-quick-profile-form-data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="2cfdf-145">For more information, see [Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span></span>  
  
 <span data-ttu-id="2cfdf-146">**Apri Visualizzatore profilo**</span><span class="sxs-lookup"><span data-stu-id="2cfdf-146">**Open Profile Viewer**</span></span>  
 <span data-ttu-id="2cfdf-147">Consente di aprire il Visualizzatore profilo dati.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-147">Opens the Data Profile Viewer.</span></span> <span data-ttu-id="2cfdf-148">Il Visualizzatore profilo dati autonomo visualizza l'output del profilo dei dati dall'attività Profiling dati.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-148">The stand-alone Data Profile Viewer displays data profile output from the Data Profiling task.</span></span> <span data-ttu-id="2cfdf-149">È possibile visualizzare l'output del profilo dei dati dopo avere eseguito l'attività Profiling dati nel pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] e aver calcolato i profili dati.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-149">You can view the data profile output after you have run the Data Profiling task inside the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package and computed the data profiles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2cfdf-150">È anche possibile aprire il Visualizzatore profilo dati eseguendo DataProfileViewer.exe nella cartella *\<drive>* :\Programmi (x86) | Programmi\Microsoft SQL Server\110\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="2cfdf-150">You can also open the Data Profile Viewer by running the DataProfileViewer.exe in the folder, *\<drive>*:\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfdf-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cfdf-151">See Also</span></span>  
 <span data-ttu-id="2cfdf-152">[Form profilo rapido singola tabella &#40;Attività Profiling dati&#41;](single-table-quick-profile-form-data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="2cfdf-152">[Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span></span>  
 [<span data-ttu-id="2cfdf-153">Editor attività Profiling dati &#40;pagina Richieste profilo&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfdf-153">Data Profiling Task Editor &#40;Profile Requests Page&#41;</span></span>](data-profiling-task-editor-profile-requests-page.md)  
  
  
