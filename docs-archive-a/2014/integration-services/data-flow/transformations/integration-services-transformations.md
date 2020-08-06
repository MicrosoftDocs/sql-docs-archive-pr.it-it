---
title: Trasformazioni di Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transformations [Integration Services], listed
- transformations [Integration Services], types
- transformations [Integration Services]
- data flow [Integration Services], transformations
- business intelligence transformations [Integration Services]
- join transformations
- split transformations [Integration Services]
- custom transformations [Integration Services]
- row transformations [Integration Services]
- rowset transformations [Integration Services]
ms.assetid: c70c4f6e-82dd-4948-b923-fd5193f67f7e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: df6e5b96ece2c36067ab316bfacff8ce1046e0e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636307"
---
# <a name="integration-services-transformations"></a><span data-ttu-id="64efa-102">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="64efa-102">Integration Services Transformations</span></span>
  <span data-ttu-id="64efa-103">Le trasformazioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sono i componenti nel flusso di dati di un pacchetto che aggregano, uniscono, distribuiscono e modificano i dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] transformations are the components in the data flow of a package that aggregate, merge, distribute, and modify data.</span></span> <span data-ttu-id="64efa-104">Le trasformazioni possono inoltre eseguire operazioni di ricerca e generare set di dati campione.</span><span class="sxs-lookup"><span data-stu-id="64efa-104">Transformations can also perform lookup operations and generate sample datasets.</span></span> <span data-ttu-id="64efa-105">In questa sezione vengono descritte le trasformazioni incluse in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] , illustrandone il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="64efa-105">This section describes the transformations that [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes and explains how they work.</span></span>  
  
## <a name="business-intelligence-transformations"></a><span data-ttu-id="64efa-106">Trasformazioni di Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="64efa-106">Business Intelligence Transformations</span></span>  
 <span data-ttu-id="64efa-107">Le trasformazioni seguenti eseguono operazioni di Business Intelligence quali la pulitura dei dati, il text mining e l'esecuzione di query di stima basate su un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="64efa-107">The following transformations perform business intelligence operations such as cleaning data, mining text, and running data mining prediction queries.</span></span>  
  
|<span data-ttu-id="64efa-108">Trasformazione</span><span class="sxs-lookup"><span data-stu-id="64efa-108">Transformation</span></span>|<span data-ttu-id="64efa-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64efa-109">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="64efa-110">Trasformazione Dimensione a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="64efa-110">Slowly Changing Dimension Transformation</span></span>](slowly-changing-dimension-transformation.md)|<span data-ttu-id="64efa-111">Trasformazione che configura l'aggiornamento di una dimensione a modifica lenta.</span><span class="sxs-lookup"><span data-stu-id="64efa-111">The transformation that configures the updating of a slowly changing dimension.</span></span>|  
|[<span data-ttu-id="64efa-112">Trasformazione Raggruppamento fuzzy</span><span class="sxs-lookup"><span data-stu-id="64efa-112">Fuzzy Grouping Transformation</span></span>](fuzzy-grouping-transformation.md)|<span data-ttu-id="64efa-113">Trasformazione che standardizza i valori nei dati delle colonne.</span><span class="sxs-lookup"><span data-stu-id="64efa-113">The transformation that standardizes values in column data.</span></span>|  
|[<span data-ttu-id="64efa-114">Trasformazione Ricerca fuzzy</span><span class="sxs-lookup"><span data-stu-id="64efa-114">Fuzzy Lookup Transformation</span></span>](lookup-transformation.md)|<span data-ttu-id="64efa-115">Trasformazione che ricerca valori in una tabella di riferimento utilizzando una corrispondenza fuzzy.</span><span class="sxs-lookup"><span data-stu-id="64efa-115">The transformation that looks up values in a reference table using a fuzzy match.</span></span>|  
|[<span data-ttu-id="64efa-116">Trasformazione Estrazione termini</span><span class="sxs-lookup"><span data-stu-id="64efa-116">Term Extraction Transformation</span></span>](term-extraction-transformation.md)|<span data-ttu-id="64efa-117">Trasformazione che estrae termini da un testo.</span><span class="sxs-lookup"><span data-stu-id="64efa-117">The transformation that extracts terms from text.</span></span>|  
|[<span data-ttu-id="64efa-118">Trasformazione Ricerca termini</span><span class="sxs-lookup"><span data-stu-id="64efa-118">Term Lookup Transformation</span></span>](term-lookup-transformation.md)|<span data-ttu-id="64efa-119">Trasformazione che ricerca termini in una tabella di riferimento e conta i termini estratti dal testo.</span><span class="sxs-lookup"><span data-stu-id="64efa-119">The transformation that looks up terms in a reference table and counts terms extracted from text.</span></span>|  
|[<span data-ttu-id="64efa-120">Trasformazione Query di data mining</span><span class="sxs-lookup"><span data-stu-id="64efa-120">Data Mining Query Transformation</span></span>](data-mining-query-transformation.md)|<span data-ttu-id="64efa-121">Trasformazione che esegue query di stima di data mining.</span><span class="sxs-lookup"><span data-stu-id="64efa-121">The transformation that runs data mining prediction queries.</span></span>|  
|[<span data-ttu-id="64efa-122">Trasformazione DQS Cleansing</span><span class="sxs-lookup"><span data-stu-id="64efa-122">DQS Cleansing Transformation</span></span>](dqs-cleansing-transformation.md)|<span data-ttu-id="64efa-123">Trasformazione che corregge i dati di un'origine dati connessa applicando regole create per tale origine dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-123">The transformation that corrects data from a connected data source by applying rules that were created for the data source.</span></span>|  
  
## <a name="row-transformations"></a><span data-ttu-id="64efa-124">Trasformazioni a livello di riga</span><span class="sxs-lookup"><span data-stu-id="64efa-124">Row Transformations</span></span>  
 <span data-ttu-id="64efa-125">Le trasformazioni elencate di seguito consentono di aggiornare i valori delle colonne e di creare nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="64efa-125">The following transformations update column values and create new columns.</span></span> <span data-ttu-id="64efa-126">La trasformazione viene applicata a tutte le righe dell'input.</span><span class="sxs-lookup"><span data-stu-id="64efa-126">The transformation is applied to each row in the transformation input.</span></span>  
  
|<span data-ttu-id="64efa-127">Trasformazione</span><span class="sxs-lookup"><span data-stu-id="64efa-127">Transformation</span></span>|<span data-ttu-id="64efa-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64efa-128">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="64efa-129">Trasformazione Mappa caratteri</span><span class="sxs-lookup"><span data-stu-id="64efa-129">Character Map Transformation</span></span>](character-map-transformation.md)|<span data-ttu-id="64efa-130">Trasformazione che applica funzioni per i valori stringa a dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="64efa-130">The transformation that applies string functions to character data.</span></span>|  
|[<span data-ttu-id="64efa-131">Trasformazione Copia colonna</span><span class="sxs-lookup"><span data-stu-id="64efa-131">Copy Column Transformation</span></span>](copy-column-transformation.md)|<span data-ttu-id="64efa-132">Trasformazione che aggiunge copie delle colonne di input al proprio output.</span><span class="sxs-lookup"><span data-stu-id="64efa-132">The transformation that adds copies of input columns to the transformation output.</span></span>|  
|[<span data-ttu-id="64efa-133">Trasformazione Conversione dati</span><span class="sxs-lookup"><span data-stu-id="64efa-133">Data Conversion Transformation</span></span>](data-conversion-transformation.md)|<span data-ttu-id="64efa-134">Trasformazione che converte il tipo di dati di una colonna in un tipo di dati diverso.</span><span class="sxs-lookup"><span data-stu-id="64efa-134">The transformation that converts the data type of a column to a different data type.</span></span>|  
|[<span data-ttu-id="64efa-135">Trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="64efa-135">Derived Column Transformation</span></span>](derived-column-transformation.md)|<span data-ttu-id="64efa-136">Trasformazione che popola colonne con risultati di espressioni.</span><span class="sxs-lookup"><span data-stu-id="64efa-136">The transformation that populates columns with the results of expressions.</span></span>|  
|[<span data-ttu-id="64efa-137">Trasformazione Esporta colonna</span><span class="sxs-lookup"><span data-stu-id="64efa-137">Export Column Transformation</span></span>](export-column-transformation.md)|<span data-ttu-id="64efa-138">Trasformazione che inserisce in un file dati esportati da un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-138">The transformation that inserts data from a data flow into a file.</span></span>|  
|[<span data-ttu-id="64efa-139">Trasformazione Importa colonna</span><span class="sxs-lookup"><span data-stu-id="64efa-139">Import Column Transformation</span></span>](import-column-transformation.md)|<span data-ttu-id="64efa-140">Trasformazione che legge dati da un file e li aggiunge a un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-140">The transformation that reads data from a file and adds it to a data flow.</span></span>|  
|[<span data-ttu-id="64efa-141">Componente script</span><span class="sxs-lookup"><span data-stu-id="64efa-141">Script Component</span></span>](script-component.md)|<span data-ttu-id="64efa-142">Trasformazione che utilizza script per estrarre, trasformare o caricare dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-142">The transformation that uses script to extract, transform, or load data.</span></span>|  
|[<span data-ttu-id="64efa-143">Trasformazione Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="64efa-143">OLE DB Command Transformation</span></span>](ole-db-command-transformation.md)|<span data-ttu-id="64efa-144">Trasformazione che esegue comandi SQL per ogni riga di un flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-144">The transformation that runs SQL commands for each row in a data flow.</span></span>|  
  
## <a name="rowset-transformations"></a><span data-ttu-id="64efa-145">Trasformazioni a livello di set di righe</span><span class="sxs-lookup"><span data-stu-id="64efa-145">Rowset Transformations</span></span>  
 <span data-ttu-id="64efa-146">Le trasformazioni seguenti creano nuovi set di righe.</span><span class="sxs-lookup"><span data-stu-id="64efa-146">The following transformations create new rowsets.</span></span> <span data-ttu-id="64efa-147">Il set di righe può includere valori aggregati e ordinati, set di righe campione o set di righe trasformati tramite Pivot o UnPivot.</span><span class="sxs-lookup"><span data-stu-id="64efa-147">The rowset can include aggregate and sorted values, sample rowsets, or pivoted and unpivoted rowsets.</span></span>  
  
|<span data-ttu-id="64efa-148">Trasformazione</span><span class="sxs-lookup"><span data-stu-id="64efa-148">Transformation</span></span>|<span data-ttu-id="64efa-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64efa-149">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="64efa-150">Trasformazione Aggregazione</span><span class="sxs-lookup"><span data-stu-id="64efa-150">Aggregate Transformation</span></span>](aggregate-transformation.md)|<span data-ttu-id="64efa-151">Trasformazione che esegue aggregazioni quali AVERAGE, SUM e COUNT.</span><span class="sxs-lookup"><span data-stu-id="64efa-151">The transformation that performs aggregations such as AVERAGE, SUM, and COUNT.</span></span>|  
|[<span data-ttu-id="64efa-152">Trasformazione Ordinamento</span><span class="sxs-lookup"><span data-stu-id="64efa-152">Sort Transformation</span></span>](sort-transformation.md)|<span data-ttu-id="64efa-153">Trasformazione che ordina i dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-153">The transformation that sorts data.</span></span>|  
|[<span data-ttu-id="64efa-154">Trasformazione Campionamento percentuale</span><span class="sxs-lookup"><span data-stu-id="64efa-154">Percentage Sampling Transformation</span></span>](percentage-sampling-transformation.md)|<span data-ttu-id="64efa-155">Trasformazione che consente di creare un set di dati campione utilizzando una percentuale per specificare le dimensioni del campione.</span><span class="sxs-lookup"><span data-stu-id="64efa-155">The transformation that creates a sample data set using a percentage to specify the sample size.</span></span>|  
|[<span data-ttu-id="64efa-156">Trasformazione Campionamento righe</span><span class="sxs-lookup"><span data-stu-id="64efa-156">Row Sampling Transformation</span></span>](row-sampling-transformation.md)|<span data-ttu-id="64efa-157">Trasformazione che consente di creare un set di dati campione specificando il numero di righe del campione.</span><span class="sxs-lookup"><span data-stu-id="64efa-157">The transformation that creates a sample data set by specifying the number of rows in the sample.</span></span>|  
|[<span data-ttu-id="64efa-158">Trasformazione pivot</span><span class="sxs-lookup"><span data-stu-id="64efa-158">Pivot Transformation</span></span>](pivot-transformation.md)|<span data-ttu-id="64efa-159">Trasformazione che crea una versione meno normalizzata di una tabella normalizzata.</span><span class="sxs-lookup"><span data-stu-id="64efa-159">The transformation that creates a less normalized version of a normalized table.</span></span>|  
|[<span data-ttu-id="64efa-160">Trasformazione UnPivot</span><span class="sxs-lookup"><span data-stu-id="64efa-160">Unpivot Transformation</span></span>](unpivot-transformation.md)|<span data-ttu-id="64efa-161">Trasformazione che crea una versione più normalizzata di una tabella non normalizzata.</span><span class="sxs-lookup"><span data-stu-id="64efa-161">The transformation that creates a more normalized version of a nonnormalized table.</span></span>|  
  
## <a name="split-and-join-transformations"></a><span data-ttu-id="64efa-162">Trasformazioni di divisione e di unione</span><span class="sxs-lookup"><span data-stu-id="64efa-162">Split and Join Transformations</span></span>  
 <span data-ttu-id="64efa-163">Le trasformazioni seguenti distribuiscono le righe tra output diversi, creano copie degli input della trasformazione, uniscono più input in un singolo output ed eseguono operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="64efa-163">The following transformations distribute rows to different outputs, create copies of the transformation inputs, join multiple inputs into one output, and perform lookup operations.</span></span>  
  
|<span data-ttu-id="64efa-164">Trasformazione</span><span class="sxs-lookup"><span data-stu-id="64efa-164">Transformation</span></span>|<span data-ttu-id="64efa-165">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64efa-165">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="64efa-166">Trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="64efa-166">Conditional Split Transformation</span></span>](conditional-split-transformation.md)|<span data-ttu-id="64efa-167">Trasformazione che indirizza righe di dati verso output diversi.</span><span class="sxs-lookup"><span data-stu-id="64efa-167">The transformation that routes data rows to different outputs.</span></span>|  
|[<span data-ttu-id="64efa-168">Trasformazione Multicast</span><span class="sxs-lookup"><span data-stu-id="64efa-168">Multicast Transformation</span></span>](multicast-transformation.md)|<span data-ttu-id="64efa-169">Trasformazione che distribuisce set di dati tra più output.</span><span class="sxs-lookup"><span data-stu-id="64efa-169">The transformation that distributes data sets to multiple outputs.</span></span>|  
|[<span data-ttu-id="64efa-170">Trasformazione Unione input multipli</span><span class="sxs-lookup"><span data-stu-id="64efa-170">Union All Transformation</span></span>](union-all-transformation.md)|<span data-ttu-id="64efa-171">Trasformazione che unisce più set di dati.</span><span class="sxs-lookup"><span data-stu-id="64efa-171">The transformation that merges multiple data sets.</span></span>|  
|[<span data-ttu-id="64efa-172">Trasformazione Unione</span><span class="sxs-lookup"><span data-stu-id="64efa-172">Merge Transformation</span></span>](merge-transformation.md)|<span data-ttu-id="64efa-173">Trasformazione che unisce due set di dati ordinati.</span><span class="sxs-lookup"><span data-stu-id="64efa-173">The transformation that merges two sorted data sets.</span></span>|  
|[<span data-ttu-id="64efa-174">Trasformazione Merge join</span><span class="sxs-lookup"><span data-stu-id="64efa-174">Merge Join Transformation</span></span>](merge-join-transformation.md)|<span data-ttu-id="64efa-175">Trasformazione che unisce due set di dati utilizzando un join di tipo FULL, LEFT o INNER.</span><span class="sxs-lookup"><span data-stu-id="64efa-175">The transformation that joins two data sets using a FULL, LEFT, or INNER join.</span></span>|  
|[<span data-ttu-id="64efa-176">Trasformazione Ricerca</span><span class="sxs-lookup"><span data-stu-id="64efa-176">Lookup Transformation</span></span>](lookup-transformation.md)|<span data-ttu-id="64efa-177">Trasformazione che esegue la ricerca di valori in una tabella di riferimento utilizzando una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="64efa-177">The transformation that looks up values in a reference table using an exact match.</span></span>|  
|[<span data-ttu-id="64efa-178">Trasformazione Cache</span><span class="sxs-lookup"><span data-stu-id="64efa-178">Cache Transform</span></span>](cache-transform.md)|<span data-ttu-id="64efa-179">Trasformazione che scrive dati da un'origine dati connessa nel flusso di dati a una gestione connessione cache che salva i dati in un file di cache.</span><span class="sxs-lookup"><span data-stu-id="64efa-179">The transformation that writes data from a connected data source in the data flow to a Cache connection manager that saves the data to a cache file.</span></span> <span data-ttu-id="64efa-180">La trasformazione Ricerca esegue ricerche sui dati nel file di cache.</span><span class="sxs-lookup"><span data-stu-id="64efa-180">The Lookup transformation performs lookups on the data in the cache file.</span></span>|  
|[<span data-ttu-id="64efa-181">Trasformazione Distribuzione di dati bilanciati</span><span class="sxs-lookup"><span data-stu-id="64efa-181">Balanced Data Distributor Transformation</span></span>](balanced-data-distributor-transformation.md)|<span data-ttu-id="64efa-182">Tramite la trasformazione vengono distribuiti in modo uniforme i buffer di righe in entrata negli output di thread distinti per migliorare le prestazioni di pacchetti SSIS in esecuzione in server a più processori e più core.</span><span class="sxs-lookup"><span data-stu-id="64efa-182">The transformation distributes buffers of incoming rows uniformly across outputs on separate threads to improve performance of SSIS packages running on multi-core and multi-processor servers.</span></span>|  
  
## <a name="auditing-transformations"></a><span data-ttu-id="64efa-183">Trasformazioni di controllo</span><span class="sxs-lookup"><span data-stu-id="64efa-183">Auditing Transformations</span></span>  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="64efa-184">include le trasformazioni seguenti per l'aggiunta di informazioni di controllo e il conteggio delle righe.</span><span class="sxs-lookup"><span data-stu-id="64efa-184">includes the following transformations to add audit information and count rows.</span></span>  
  
|<span data-ttu-id="64efa-185">Trasformazione</span><span class="sxs-lookup"><span data-stu-id="64efa-185">Transformation</span></span>|<span data-ttu-id="64efa-186">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64efa-186">Description</span></span>|  
|--------------------|-----------------|  
|[<span data-ttu-id="64efa-187">Trasformazione Controllo</span><span class="sxs-lookup"><span data-stu-id="64efa-187">Audit Transformation</span></span>](audit-transformation.md)|<span data-ttu-id="64efa-188">Trasformazione che rende le informazioni sull'ambiente disponibili a un flusso di dati in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="64efa-188">The transformation that makes information about the environment available to the data flow in a package.</span></span>|  
|[<span data-ttu-id="64efa-189">Trasformazione Conteggio righe</span><span class="sxs-lookup"><span data-stu-id="64efa-189">Row Count Transformation</span></span>](row-count-transformation.md)|<span data-ttu-id="64efa-190">Trasformazione che conta le righe al suo interno e archivia il totale in una variabile.</span><span class="sxs-lookup"><span data-stu-id="64efa-190">The transformation that counts rows as they move through it and stores the final count in a variable.</span></span>|  
  
## <a name="custom-transformations"></a><span data-ttu-id="64efa-191">Trasformazioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="64efa-191">Custom Transformations</span></span>  
 <span data-ttu-id="64efa-192">È inoltre possibile creare trasformazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="64efa-192">You can also write custom transformations.</span></span> <span data-ttu-id="64efa-193">Per altre informazioni, vedere [Sviluppo di un componente di trasformazione personalizzato con output sincroni](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) e [Sviluppo di un componente di trasformazione personalizzato con output asincroni](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="64efa-193">For more information, see [Developing a Custom Transformation Component with Synchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) and [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span>  
  
  