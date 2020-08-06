---
title: Riferimenti alle raccolte predefinite Globals e Users (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 5f5e1149-c967-454d-9a63-18ec4a33d985
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8ada59244c2b1c49bc0be6f679b8eb4affc487ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636590"
---
# <a name="built-in-globals-and-users-references-report-builder-and-ssrs"></a><span data-ttu-id="c4b0f-102">Riferimenti alle raccolte predefinite Globals e Users (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="c4b0f-102">Built-in Globals and Users References (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c4b0f-103">La raccolta di campi predefinita, in cui sono incluse le raccolte `Globals` e `User`, rappresenta i valori globali forniti da Reporting Services durante l'elaborazione di un report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-103">The Built-in fields collection, which includes both the `Globals` and the `User` collections, represent global values provided by Reporting Services when a report is processed.</span></span> <span data-ttu-id="c4b0f-104">La raccolta `Globals` fornisce valori come il nome del report, l'ora di inizio dell'elaborazione e i numeri di pagina correnti per l'intestazione o il piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-104">The `Globals` collection provides values such as the name of the report, the time when report processing began, and current page numbers for the report header or footer.</span></span> <span data-ttu-id="c4b0f-105">La raccolta `User` fornisce le impostazioni relative a ID utente e lingua.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-105">The `User` collection provides the user identifier and language settings.</span></span> <span data-ttu-id="c4b0f-106">Questi valori possono essere usati nelle espressioni per filtrare i risultati in un report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-106">These values can be used in expressions to filter results in a report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="using-the-globals-collection"></a><span data-ttu-id="c4b0f-107">Utilizzo della raccolta Globals</span><span class="sxs-lookup"><span data-stu-id="c4b0f-107">Using the Globals Collection</span></span>  
 <span data-ttu-id="c4b0f-108">La raccolta `Globals` contiene le variabili globali per il report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-108">The `Globals` collection contains the global variables for the report.</span></span> <span data-ttu-id="c4b0f-109">Nell'area di progettazione queste variabili sono precedute dal prefisso & (e commerciale), ad esempio `[&ReportName]`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-109">On the design surface, these variables appear prefixed by an & (ampersand), for example, `[&ReportName]`.</span></span> <span data-ttu-id="c4b0f-110">Nella tabella seguente vengono descritti i membri della raccolta `Globals`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-110">The following table describes the members of the `Globals` collection.</span></span>  
  
|<span data-ttu-id="c4b0f-111">**Membro**</span><span class="sxs-lookup"><span data-stu-id="c4b0f-111">**Member**</span></span>|<span data-ttu-id="c4b0f-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c4b0f-112">**Type**</span></span>|<span data-ttu-id="c4b0f-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c4b0f-113">**Description**</span></span>|  
|----------------|--------------|---------------------|  
|<span data-ttu-id="c4b0f-114">ExecutionTime</span><span class="sxs-lookup"><span data-stu-id="c4b0f-114">ExecutionTime</span></span>|`DateTime`|<span data-ttu-id="c4b0f-115">Data e ora di inizio dell'esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-115">The date and time that the report began to run.</span></span>|  
|<span data-ttu-id="c4b0f-116">PageNumber</span><span class="sxs-lookup"><span data-stu-id="c4b0f-116">PageNumber</span></span>|`Integer`|<span data-ttu-id="c4b0f-117">Numero di pagina corrente relativo a interruzioni di pagina che ne determinano la reimpostazione.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-117">The current page number relative to page breaks that reset the page number.</span></span> <span data-ttu-id="c4b0f-118">All'inizio dell'elaborazione del report, il valore è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-118">At the beginning of report processing, the initial value is set to 1.</span></span> <span data-ttu-id="c4b0f-119">Il numero di pagina aumenta per ogni pagina di cui è stato eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-119">The page number increments for each rendered page.</span></span><br /><br /> <span data-ttu-id="c4b0f-120">Per numerare le pagine all'interno di interruzioni di pagina per un rettangolo, un'area dati, un gruppo di aree dati o una mappa, nella proprietà PageBreak impostare la proprietà ResetPageNumber su `True` .</span><span class="sxs-lookup"><span data-stu-id="c4b0f-120">To number pages within page breaks for a rectangle, a data region, a data region group, or a map, on the PageBreak property, set the ResetPageNumber property to `True`.</span></span> <span data-ttu-id="c4b0f-121">Non supportato dai gruppi di gerarchie di colonna Tablix.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-121">Not supported on tablix column hierarchy groups.</span></span><br /><br /> <span data-ttu-id="c4b0f-122">La proprietà PageNumber può essere usata solo in espressioni presenti in un'intestazione o un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-122">PageNumber can only be used in an expression in a page header or page footer.</span></span>|  
|<span data-ttu-id="c4b0f-123">ReportFolder</span><span class="sxs-lookup"><span data-stu-id="c4b0f-123">ReportFolder</span></span>|`String`|<span data-ttu-id="c4b0f-124">Percorso completo della cartella contenente il report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-124">The full path to the folder containing the report.</span></span> <span data-ttu-id="c4b0f-125">Non include l'URL del server di report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-125">This does not include the report server URL.</span></span>|  
|<span data-ttu-id="c4b0f-126">ReportName</span><span class="sxs-lookup"><span data-stu-id="c4b0f-126">ReportName</span></span>|`String`|<span data-ttu-id="c4b0f-127">Nome del report archiviato nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-127">The name of the report as it is stored in the report server database.</span></span>|  
|<span data-ttu-id="c4b0f-128">ReportServerUrl</span><span class="sxs-lookup"><span data-stu-id="c4b0f-128">ReportServerUrl</span></span>|`String`|<span data-ttu-id="c4b0f-129">URL del server di report in cui il report è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-129">The URL of the report server on which the report is being run.</span></span>|  
|<span data-ttu-id="c4b0f-130">TotalPages</span><span class="sxs-lookup"><span data-stu-id="c4b0f-130">TotalPages</span></span>|`Integer`|<span data-ttu-id="c4b0f-131">Numero totale di pagine relativo alle interruzioni di pagina che determinano la reimpostazione di PageNumber.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-131">The total number of pages relative to page breaks that reset PageNumber.</span></span> <span data-ttu-id="c4b0f-132">Se non sono impostate interruzioni di pagina, questo valore corrisponde a OverallTotalPages.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-132">If no page breaks are set, this value is the same as OverallTotalPages.</span></span><br /><br /> <span data-ttu-id="c4b0f-133">La proprietà TotalPages può essere usata solo in espressioni presenti in un'intestazione o un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-133">TotalPages can only be used in an expression in a page header or page footer.</span></span>|  
|<span data-ttu-id="c4b0f-134">PageName</span><span class="sxs-lookup"><span data-stu-id="c4b0f-134">PageName</span></span>|`String`|<span data-ttu-id="c4b0f-135">Nome della pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-135">The name of the page.</span></span> <span data-ttu-id="c4b0f-136">All'inizio dell'elaborazione del report, il valore viene impostato da una proprietà del report, InitialPageName.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-136">At the beginning of report processing, the initial value is set from InitialPageName, a report property.</span></span> <span data-ttu-id="c4b0f-137">Quando ciascun elemento del report viene elaborato, questo valore viene sostituito con il valore corrispondente di PageName da un rettangolo, un'area dati, un gruppo di aree dati o una mappa.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-137">As each report item is processed, this value is replaced by the corresponding value of PageName from a rectangle, a data region, a data region group, or a map.</span></span> <span data-ttu-id="c4b0f-138">Non supportato dai gruppi di gerarchie di colonna Tablix.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-138">Not supported on tablix column hierarchy groups.</span></span><br /><br /> <span data-ttu-id="c4b0f-139">La proprietà PageName può essere usata solo in espressioni presenti in un'intestazione o un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-139">PageName can only be used in an expression in a page header or page footer.</span></span>|  
|<span data-ttu-id="c4b0f-140">OverallPageNumber</span><span class="sxs-lookup"><span data-stu-id="c4b0f-140">OverallPageNumber</span></span>|`Integer`|<span data-ttu-id="c4b0f-141">Numero della pagina corrente per l'intero report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-141">The page number of the current page for the entire report.</span></span> <span data-ttu-id="c4b0f-142">ResetPageNumber non ha effetto su questo valore.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-142">This value is not affected by ResetPageNumber.</span></span><br /><br /> <span data-ttu-id="c4b0f-143">La proprietà OverallPageNumber può essere usata solo in espressioni presenti in un'intestazione o un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-143">OverallPageNumber can only be used in an expression in a page header or page footer.</span></span>|  
|<span data-ttu-id="c4b0f-144">OverallTotalPages</span><span class="sxs-lookup"><span data-stu-id="c4b0f-144">OverallTotalPages</span></span>|`Integer`|<span data-ttu-id="c4b0f-145">Numero complessivo di pagine per l'intero report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-145">The total number pages for the entire report.</span></span> <span data-ttu-id="c4b0f-146">ResetPageNumber non ha effetto su questo valore.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-146">This value is not affected by ResetPageNumber.</span></span><br /><br /> <span data-ttu-id="c4b0f-147">La proprietà OverallTotalPages può essere usata solo in espressioni presenti in un'intestazione o un piè di pagina.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-147">OverallTotalPages can only be used in an expression in a page header or page footer.</span></span>|  
|<span data-ttu-id="c4b0f-148">RenderFormat</span><span class="sxs-lookup"><span data-stu-id="c4b0f-148">RenderFormat</span></span>|`RenderFormat`|<span data-ttu-id="c4b0f-149">Informazioni sulla richiesta di rendering corrente.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-149">Information about the current rendering request.</span></span><br /><br /> <span data-ttu-id="c4b0f-150">Per altre informazioni, vedere "RenderFormat" nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-150">For more information, see "RenderFormat" in the next section.</span></span>|  
  
 <span data-ttu-id="c4b0f-151">I membri della raccolta `Globals` restituiscono una variante.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-151">Members of the `Globals` collection return a variant.</span></span> <span data-ttu-id="c4b0f-152">Se si desidera usare un membro di questa raccolta in un'espressione che richiede un tipo di dati specifico, è necessario eseguire dapprima il cast della variabile.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-152">If you want to use a member of this collection in an expression that requires a specific data type, you must first cast the variable.</span></span> <span data-ttu-id="c4b0f-153">Per convertire, ad esempio, la variante relativa alla data e all'ora di esecuzione in un formato di data, usare `=CDate(Globals!ExecutionTime)`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-153">For example, to convert the execution time variant into a Date format, use `=CDate(Globals!ExecutionTime)`.</span></span> <span data-ttu-id="c4b0f-154">Per altre informazioni, vedere [Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c4b0f-154">For more information, see [Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
### <a name="renderformat"></a><span data-ttu-id="c4b0f-155">RenderFormat</span><span class="sxs-lookup"><span data-stu-id="c4b0f-155">RenderFormat</span></span>  
 <span data-ttu-id="c4b0f-156">Nella tabella seguente vengono descritti i membri per `RenderFormat`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-156">The following table describes the members for `RenderFormat`.</span></span>  
  
|<span data-ttu-id="c4b0f-157">Membro</span><span class="sxs-lookup"><span data-stu-id="c4b0f-157">Member</span></span>|<span data-ttu-id="c4b0f-158">Type</span><span class="sxs-lookup"><span data-stu-id="c4b0f-158">Type</span></span>|<span data-ttu-id="c4b0f-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4b0f-159">Description</span></span>|  
|------------|----------|-----------------|  
|<span data-ttu-id="c4b0f-160">Nome</span><span class="sxs-lookup"><span data-stu-id="c4b0f-160">Name</span></span>|`String`|<span data-ttu-id="c4b0f-161">Nome del renderer come registrato nel file di configurazione RSReportServer.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-161">The name of the renderer as registered in the RSReportServer configuration file.</span></span><br /><br /> <span data-ttu-id="c4b0f-162">Disponibile durante determinate parti del ciclo di elaborazione/rendering del report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-162">Available during specific parts of the report processing/rendering cycle.</span></span>|  
|<span data-ttu-id="c4b0f-163">IsInteractive</span><span class="sxs-lookup"><span data-stu-id="c4b0f-163">IsInteractive</span></span>|`Boolean`|<span data-ttu-id="c4b0f-164">Specifica se nella richiesta di rendering corrente è usato un formato di rendering interattivo.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-164">Whether the current rendering request uses an interactive rendering format.</span></span>|  
|<span data-ttu-id="c4b0f-165">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="c4b0f-165">DeviceInfo</span></span>|<span data-ttu-id="c4b0f-166">Raccolta nome/valore di sola lettura</span><span class="sxs-lookup"><span data-stu-id="c4b0f-166">Read-only name/value collection</span></span>|<span data-ttu-id="c4b0f-167">Coppie chiave/valore per i parametri deviceinfo per la richiesta di rendering corrente.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-167">Key/value pairs for deviceinfo parameters for the current rendering request.</span></span><br /><br /> <span data-ttu-id="c4b0f-168">È possibile specificare i valori stringa usando la chiave o un indice nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-168">String values can be specified by using either the key or an index into the collection.</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="c4b0f-169">Esempi</span><span class="sxs-lookup"><span data-stu-id="c4b0f-169">Examples</span></span>  
 <span data-ttu-id="c4b0f-170">Negli esempi seguenti viene illustrato come utilizzare un riferimento alla raccolta `Globals` in un'espressione:</span><span class="sxs-lookup"><span data-stu-id="c4b0f-170">The following examples show how to use a reference to the `Globals` collection in an expression:</span></span>  
  
-   <span data-ttu-id="c4b0f-171">L'espressione seguente, inserita in una casella di testo nel piè di pagina di un report, restituisce il numero di pagina e le pagine totali del report:</span><span class="sxs-lookup"><span data-stu-id="c4b0f-171">This expression, placed in a text box in the footer of a report, provides the page number and total pages in the report:</span></span>  
  
     `=Globals.PageNumber & " of " & Globals.TotalPages`  
  
-   <span data-ttu-id="c4b0f-172">Questa espressione restituisce il nome e l'ora di esecuzione del report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-172">This expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="c4b0f-173">Il tempo viene formattato con la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] stringa di formattazione per la data breve:</span><span class="sxs-lookup"><span data-stu-id="c4b0f-173">The time is formatted with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  
  
     `=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")`  
  
-   <span data-ttu-id="c4b0f-174">Con questa espressione, inserita nella finestra di dialogo **Visibilità colonne** per una colonna selezionata, viene visualizzata la colonna solo quando il report viene esportato in Excel.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-174">This expression, placed in the **Column Visibility** dialog box for a selected column, displays the column only when the report is exported to Excel.</span></span> <span data-ttu-id="c4b0f-175">In caso contrario, è nascosta.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-175">Otherwise, the column is hidden.</span></span>  
  
     <span data-ttu-id="c4b0f-176">`EXCELOPENXML` si riferisce al formato di Excel incluso in Office 2007.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-176">`EXCELOPENXML` refers to the format of Excel that is included in Office 2007.</span></span> <span data-ttu-id="c4b0f-177">`EXCEL` si fa riferimento al formato di Excel incluso in Office 2003.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-177">`EXCEL` refers to the format of Excel that is included in Office 2003.</span></span>  
  
     `=IIF(Globals!RenderFormat.Name = "EXCELOPENXML" OR Globals!RenderFormat.Name = "EXCEL", false, true)`  
  
## <a name="using-the-user-collection"></a><span data-ttu-id="c4b0f-178">Utilizzo della raccolta User</span><span class="sxs-lookup"><span data-stu-id="c4b0f-178">Using the User Collection</span></span>  
 <span data-ttu-id="c4b0f-179">La raccolta `User` contiene i dati relativi all'utente che esegue il report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-179">The `User` collection contains data about the user who is running the report.</span></span> <span data-ttu-id="c4b0f-180">È possibile usare questa raccolta per filtrare i dati visualizzati in un report, per mostrare, ad esempio, solo quelli dell'utente corrente o visualizzare l'ID utente nel titolo del report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-180">You can use this collection to filter the data that appears in a report, for example, showing only the data of the current user, or to display the UserID, for example, in a report title.</span></span> <span data-ttu-id="c4b0f-181">Nell'area di progettazione queste variabili sono precedute dal prefisso & (e commerciale), ad esempio `[&UserID]`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-181">On the design surface, these variables appear prefixed by an & (ampersand), for example, `[&UserID]`.</span></span>  
  
 <span data-ttu-id="c4b0f-182">Nella tabella seguente vengono descritti i membri della raccolta `User`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-182">The following table describes the members of the `User` collection.</span></span>  
  
|<span data-ttu-id="c4b0f-183">**Member**</span><span class="sxs-lookup"><span data-stu-id="c4b0f-183">**Member**</span></span>|<span data-ttu-id="c4b0f-184">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c4b0f-184">**Type**</span></span>|<span data-ttu-id="c4b0f-185">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c4b0f-185">**Description**</span></span>|  
|----------------|--------------|---------------------|  
|`Language`|`String`|<span data-ttu-id="c4b0f-186">Lingua dell'utente che esegue il report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-186">The language of the user running the report.</span></span> <span data-ttu-id="c4b0f-187">Ad esempio: `en-US`.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-187">For example, `en-US`.</span></span>|  
|`UserID`|`String`|<span data-ttu-id="c4b0f-188">ID dell'utente che esegue il report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-188">The ID of the user running the report.</span></span> <span data-ttu-id="c4b0f-189">Se si usa l'autenticazione di Windows, questo valore corrisponde all'account di dominio dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-189">If you are using Windows Authentication, this value is the domain account of the current user.</span></span> <span data-ttu-id="c4b0f-190">Il valore è determinato dall'estensione di sicurezza di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , che può usare l'autenticazione di Windows o quella personalizzata.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-190">The value is determined by the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] security extension, which can use Windows Authentication or custom authentication.</span></span>|  
  
 <span data-ttu-id="c4b0f-191">Per altre informazioni sul supporto di più lingue in un report, vedere "Considerazioni sulla progettazione di soluzioni per distribuzioni multilingue o globali" nella documentazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] inclusa nella [documentazione online di SQL Server](https://go.microsoft.com/fwlink/?LinkId=120955).</span><span class="sxs-lookup"><span data-stu-id="c4b0f-191">For more information about supporting multiple languages in a report, see "Solution Design Considerations for Multi-Lingual or Global Deployments" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?LinkId=120955).</span></span>  
  
### <a name="using-locale-settings"></a><span data-ttu-id="c4b0f-192">Utilizzo delle impostazioni locali</span><span class="sxs-lookup"><span data-stu-id="c4b0f-192">Using Locale Settings</span></span>  
 <span data-ttu-id="c4b0f-193">È possibile utilizzare espressioni per fare riferimento alle impostazioni locali in un computer client tramite il valore `User.Language`, in modo da determinare la modalità di visualizzazione di un report all'utente.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-193">You can use expressions to refer to the locale settings on a client computer through the `User.Language` value to determine how a report appears to the user.</span></span> <span data-ttu-id="c4b0f-194">È possibile, ad esempio, creare un report in cui venga usata un'espressione di query diversa basata sul valore delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-194">For example, you can create a report that uses a different query expression based on the locale value.</span></span> <span data-ttu-id="c4b0f-195">La query può essere modificata per recuperare informazioni localizzate da una colonna diversa, a seconda della lingua restituita.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-195">The query may change to retrieve localized information from a different column depending on the language returned.</span></span> <span data-ttu-id="c4b0f-196">È inoltre possibile usare un'espressione per modificare le impostazioni relative alla lingua del report o degli elementi del report in base a questa variabile.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-196">You can also use an expression in the language settings of the report or report items based on this variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c4b0f-197">Benché sia possibile modificare le impostazioni relative alla lingua di un report, è necessario assicurarsi che tale modifica non causi problemi di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-197">While you can change the language settings of a report, you must be careful about any display issues this may cause.</span></span> <span data-ttu-id="c4b0f-198">La modifica delle impostazioni locali del report potrebbe ad esempio comportare la modifica del formato della data nel report, ma anche la modifica del formato della valuta.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-198">For example, changing the locale setting of the report can change the date format in the report, but it can also change the currency format.</span></span> <span data-ttu-id="c4b0f-199">A meno che non sia previsto un processo di conversione per la valuta, in questi casi è possibile che nel report venga visualizzato il simbolo di valuta errato.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-199">Unless there is a conversion process for the currency, this may cause the incorrect currency symbol to be displayed in the report.</span></span> <span data-ttu-id="c4b0f-200">Per evitare tale problema, impostare le informazioni sulla lingua nei singoli elementi da modificare oppure impostare una lingua specifica per l'elemento contenente i dati relativi alla valuta.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-200">To avoid this, set the language information about the individual items that you want to change, or set the item with the currency data to a specific language.</span></span>  
  
### <a name="identifying-userid-for-snapshot-or-history-reports"></a><span data-ttu-id="c4b0f-201">Identificazione di UserID per i report relativi a snapshot o cronologia</span><span class="sxs-lookup"><span data-stu-id="c4b0f-201">Identifying UserID for Snapshot or History Reports</span></span>  
 <span data-ttu-id="c4b0f-202">Nei report che includono la variabile *User!UserID* è talvolta possibile che non vengano inclusi i dati specifici dell'utente che sta visualizzando il report.</span><span class="sxs-lookup"><span data-stu-id="c4b0f-202">In some cases, reports that include the *User!UserID* variable will fail to show report data that is specific to the current user who is viewing the report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b0f-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4b0f-203">See Also</span></span>  
 <span data-ttu-id="c4b0f-204">[Espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4b0f-204">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4b0f-205">[Finestra di dialogo espressione &#40;Generatore report&#41;](../expression-dialog-box-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c4b0f-205">[Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md) </span></span>  
 <span data-ttu-id="c4b0f-206">[Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4b0f-206">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c4b0f-207">[Formattazione di numeri e date &#40;Generatore report e SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4b0f-207">[Formatting Numbers and Dates &#40;Report Builder and SSRS&#41;](formatting-numbers-and-dates-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c4b0f-208">Esempi di espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4b0f-208">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  