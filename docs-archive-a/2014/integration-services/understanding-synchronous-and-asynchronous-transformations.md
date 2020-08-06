---
title: Informazioni sulle trasformazioni sincrone e asincrone | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], synchronous and asynchronous
- asynchronous transformations [Integration Services]
- data flow components [Integration Services], synchronous and asynchronous
- synchronous transformations [Integration Services]
ms.assetid: 0bc2bda5-3f8a-49c2-aaf1-01dbe4c3ebba
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386d3786cb969ad93a92b8ebae2a41f046fb39bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625450"
---
# <a name="understanding-synchronous-and-asynchronous-transformations"></a><span data-ttu-id="6a809-102">Informazioni sulle trasformazioni sincrone e asincrone</span><span class="sxs-lookup"><span data-stu-id="6a809-102">Understanding Synchronous and Asynchronous Transformations</span></span>
  <span data-ttu-id="6a809-103">La differenza tra una trasformazione sincrona e una asincrona in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] può essere definita più facilmente iniziando con una descrizione della trasformazione sincrona.</span><span class="sxs-lookup"><span data-stu-id="6a809-103">To understand the difference between a synchronous and an asynchronous transformation in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], it is easiest to start with an understanding of a synchronous transformation.</span></span> <span data-ttu-id="6a809-104">Se la trasformazione sincrona non soddisfa le esigenze specifiche, è possibile che la progettazione richieda una trasformazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="6a809-104">If a synchronous transformation does not meet your needs, your design might require an asynchronous transformation.</span></span>

## <a name="synchronous-transformations"></a><span data-ttu-id="6a809-105">Trasformazioni sincrone</span><span class="sxs-lookup"><span data-stu-id="6a809-105">Synchronous Transformations</span></span>
 <span data-ttu-id="6a809-106">Tramite una trasformazione sincrona le righe in ingresso vengono elaborate e passate nel flusso di dati una alla volta.</span><span class="sxs-lookup"><span data-stu-id="6a809-106">A synchronous transformation processes incoming rows and passes them on in the data flow one row at a time.</span></span> <span data-ttu-id="6a809-107">L'output è sincrono con l'input, ovvero si verifica contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6a809-107">Output is synchronous with input, meaning that it occurs at the same time.</span></span> <span data-ttu-id="6a809-108">Pertanto, per elaborare una determinata riga, non sono necessarie informazioni su altre righe nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="6a809-108">Therefore, to process a given row, the transformation does not need information about other rows in the data set.</span></span> <span data-ttu-id="6a809-109">Nell'implementazione effettiva le righe vengono raggruppate in buffer mentre vengono passate da un componente al successivo, ma tali buffer sono trasparenti per l'utente ed è possibile presupporre che ogni riga venga elaborata separatamente.</span><span class="sxs-lookup"><span data-stu-id="6a809-109">In the actual implementation, rows are grouped into buffers as they pass from one component to the next, but these buffers are transparent to the user, and you can assume that each row is processed separately.</span></span>

 <span data-ttu-id="6a809-110">Un esempio di una trasformazione sincrona è la trasformazione Conversione dati.</span><span class="sxs-lookup"><span data-stu-id="6a809-110">An example of a synchronous transformation is the Data Conversion transformation.</span></span> <span data-ttu-id="6a809-111">Per ogni riga in ingresso, il valore nella colonna specificata viene convertito e la riga viene inviata.</span><span class="sxs-lookup"><span data-stu-id="6a809-111">For each incoming row, it converts the value in the specified column and sends the row on its way.</span></span> <span data-ttu-id="6a809-112">Ogni operazione di conversione discreta è indipendente da tutte le altre righe del set di dati.</span><span class="sxs-lookup"><span data-stu-id="6a809-112">Each discrete conversion operation is independent of all the other rows in the data set.</span></span>

 <span data-ttu-id="6a809-113">Per specificare una trasformazione sincrona durante la creazione di script e la programmazione in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], cercare l'ID dell'input di un componente e assegnarlo alla proprietà `SynchronousInputID` degli output del componente.</span><span class="sxs-lookup"><span data-stu-id="6a809-113">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] scripting and programming, you specify a synchronous transformation by looking up the ID of a component's input and assigning it to the `SynchronousInputID` property of the component's outputs.</span></span> <span data-ttu-id="6a809-114">In questo modo al motore flusso di dati viene indicato di elaborare ogni riga dall'input e di inviarla automaticamente agli output specificati.</span><span class="sxs-lookup"><span data-stu-id="6a809-114">This tells the data flow engine to process each row from the input and send each row automatically to the specified outputs.</span></span> <span data-ttu-id="6a809-115">Se si desidera che ogni riga venga inviata a ogni output, non è necessario scrivere codice aggiuntivo per l'output dei dati.</span><span class="sxs-lookup"><span data-stu-id="6a809-115">If you want every row to go to every output, you do not have to write any additional code to output the data.</span></span> <span data-ttu-id="6a809-116">Se si utilizza la proprietà `ExclusionGroup` per specificare che le righe devono essere inviate solo a un gruppo di output, così come nella trasformazione Suddivisione condizionale, è necessario chiamare il metodo `DirectRow` per selezionare la destinazione appropriata per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="6a809-116">If you use the `ExclusionGroup` property to specify that rows should only go to one or another of a group of outputs, as in the Conditional Split transformation, you must call the `DirectRow` method to select the appropriate destination for each row.</span></span> <span data-ttu-id="6a809-117">Se si dispone di un output degli errori, è necessario chiamare `DirectErrorRow` per inviare le righe con problemi all'output degli errori anziché all'output predefinito.</span><span class="sxs-lookup"><span data-stu-id="6a809-117">When you have an error output, you must call `DirectErrorRow` to send rows with problems to the error output instead of the default output.</span></span>

## <a name="asynchronous-transformations"></a><span data-ttu-id="6a809-118">Trasformazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="6a809-118">Asynchronous Transformations</span></span>
 <span data-ttu-id="6a809-119">La progettazione potrebbe richiedere una trasformazione asincrona quando non è possibile elaborare ogni riga in modo indipendente da tutte le altre.</span><span class="sxs-lookup"><span data-stu-id="6a809-119">You might decide that your design requires an asynchronous transformation when it is not possible to process each row independently of all other rows.</span></span> <span data-ttu-id="6a809-120">In altri termini, non è possibile passare ogni riga nel flusso di dati quando viene elaborata, ma è invece necessario eseguire l'output dei dati in modo asincrono, ovvero in un momento diverso, rispetto all'input.</span><span class="sxs-lookup"><span data-stu-id="6a809-120">In other words, you cannot pass each row along in the data flow as it is processed, but instead must output data asynchronously, or at a different time, than the input.</span></span> <span data-ttu-id="6a809-121">Negli scenari seguenti è ad esempio necessaria una trasformazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="6a809-121">For example, the following scenarios require an asynchronous transformation:</span></span>

-   <span data-ttu-id="6a809-122">Il componente deve acquisire più buffer di dati prima di eseguire l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6a809-122">The component has to acquire multiple buffers of data before it can perform its processing.</span></span> <span data-ttu-id="6a809-123">Un esempio è la trasformazione Ordinamento, in cui il componente deve elaborare il set completo di righe in una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="6a809-123">An example is the Sort transformation, where the component has to process the complete set of rows in a single operation.</span></span>

-   <span data-ttu-id="6a809-124">Il componente deve combinare righe da più input.</span><span class="sxs-lookup"><span data-stu-id="6a809-124">The component has to combine rows from multiple inputs.</span></span> <span data-ttu-id="6a809-125">Un esempio è la trasformazione Unione, in cui il componente deve esaminare più righe da ogni input e quindi unirle in base all'ordinamento definito.</span><span class="sxs-lookup"><span data-stu-id="6a809-125">An example is the Merge transformation, where the component has to examine multiple rows from each input and then merge them in sorted order.</span></span>

-   <span data-ttu-id="6a809-126">Non esiste una corrispondenza uno-a-uno tra righe di input e righe di output.</span><span class="sxs-lookup"><span data-stu-id="6a809-126">There is no one-to-one correspondence between input rows and output rows.</span></span> <span data-ttu-id="6a809-127">Un esempio è la trasformazione Aggregazione, in cui il componente deve aggiungere una riga all'output per mantenere i valori di aggregazione calcolati.</span><span class="sxs-lookup"><span data-stu-id="6a809-127">An example is the Aggregate transformation, where the component has to add a row to the output to hold the computed aggregate values.</span></span>

 <span data-ttu-id="6a809-128">Per specificare una trasformazione asincrona durante la creazione di script e la programmazione in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], assegnare il valore 0 alla proprietà `SynchronousInputID` degli output del componente.</span><span class="sxs-lookup"><span data-stu-id="6a809-128">In [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] scripting and programming, you specify an asynchronous transformation by assigning a value of 0 to the `SynchronousInputID` property of the component's outputs.</span></span> <span data-ttu-id="6a809-129">.</span><span class="sxs-lookup"><span data-stu-id="6a809-129">.</span></span> <span data-ttu-id="6a809-130">In questo modo si indica al motore flusso di dati di non inviare automaticamente ogni riga agli output.</span><span class="sxs-lookup"><span data-stu-id="6a809-130">This tells the data flow engine not to send each row automatically to the outputs.</span></span> <span data-ttu-id="6a809-131">È quindi necessario scrivere codice per inviare ogni riga in modo esplicito all'output appropriato aggiungendola al nuovo buffer di output creato per l'output di una trasformazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="6a809-131">Then you must write code to send each row explicitly to the appropriate output by adding it to the new output buffer that is created for the output of an asynchronous transformation.</span></span>

> [!NOTE]
>  <span data-ttu-id="6a809-132">Poiché un componente di origine deve anche aggiungere in modo esplicito ogni riga che legge dall'origine dati ai propri buffer di output, un'origine è simile a una trasformazione con output asincroni.</span><span class="sxs-lookup"><span data-stu-id="6a809-132">Since a source component must also explicitly add each row that it reads from the data source to its output buffers, a source resembles a transformation with asynchronous outputs.</span></span>

 <span data-ttu-id="6a809-133">È anche possibile creare una trasformazione asincrona che emula una trasformazione sincrona copiando in modo esplicito ogni riga di input nell'output.</span><span class="sxs-lookup"><span data-stu-id="6a809-133">It would also be possible to create an asynchronous transformation that emulates a synchronous transformation by explicitly copying each input row to the output.</span></span> <span data-ttu-id="6a809-134">Tramite questo approccio, è possibile rinominare le colonne o convertire tipi o formati di dati.</span><span class="sxs-lookup"><span data-stu-id="6a809-134">By using this approach, you could rename columns or convert data types or formats.</span></span> <span data-ttu-id="6a809-135">Con questo approccio si verifica tuttavia una riduzione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6a809-135">However this approach degrades performance.</span></span> <span data-ttu-id="6a809-136">È possibile ottenere gli stessi risultati con prestazioni più elevate utilizzando i componenti integrati di Integration Services, ad esempio Copia colonna o Conversione dati.</span><span class="sxs-lookup"><span data-stu-id="6a809-136">You can achieve the same results with better performance by using built-in Integration Services components, such as Copy Column or Data Conversion.</span></span>

<span data-ttu-id="6a809-137">![Integration Services icona (piccola)](media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="6a809-137">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="6a809-138">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="6a809-138">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="6a809-139">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="6a809-139">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="6a809-140">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="6a809-140">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a809-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a809-141">See Also</span></span>
 <span data-ttu-id="6a809-142">[Creazione di una trasformazione sincrona con il componente script](data-flow/transformations/script-component.md) [creazione di una trasformazione asincrona con il componente script](extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md) [sviluppo di un componente di trasformazione personalizzato con output sincroni](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [sviluppo di un componente di trasformazione personalizzato con output asincroni](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)</span><span class="sxs-lookup"><span data-stu-id="6a809-142">[Creating a Synchronous Transformation with the Script Component](data-flow/transformations/script-component.md) [Creating an Asynchronous Transformation with the Script Component](extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md) [Developing a Custom Transformation Component with Synchronous Outputs](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-synchronous-outputs.md) [Developing a Custom Transformation Component with Asynchronous Outputs](extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md)</span></span>

