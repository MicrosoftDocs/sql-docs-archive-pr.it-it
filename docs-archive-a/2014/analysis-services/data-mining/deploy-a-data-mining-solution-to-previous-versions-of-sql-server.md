---
title: Distribuire una soluzione di data mining a versioni precedenti di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- backward compatibility [Analysis Services]
- holdout [data mining]
- deploy [Analysis Services]
- time series [Analysis Services]
- deploying [Analysis Services - data mining]
- synchronization [Analysis Services]
- deployment [Analysis Services]
ms.assetid: 2715c245-f206-43af-8bf5-e6bd2585477a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f09a37c078cf58f24db9a08e3ddcb68cb2638717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636477"
---
# <a name="deploy-a-data-mining-solution-to-previous-versions-of-sql-server"></a><span data-ttu-id="b9310-102">Distribuire una soluzione di data mining in versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b9310-102">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>
  <span data-ttu-id="b9310-103">In questa sezione vengono descritti i problemi di compatibilità noti che possono verificarsi quando si tenta di distribuire in un database che utilizza SQL Server 2005 Analysis Services una struttura o un modello di data mining creato in un'istanza di [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] oppure quando si distribuiscono in un'istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]modelli creati in SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="b9310-103">This section describes known compatibility issues that may arise when you attempt to deploy a data mining model or data mining structure that was created in an instance of [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to a database that uses SQL Server 2005 Analysis Services, or when you deploy models created in SQL Server 2005 to an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="b9310-104">La distribuzione in un'istanza di SQL Server 2000 Analysis Services non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b9310-104">Deployment to an instance of SQL Server 2000 Analysis Services is not supported.</span></span>  
  
 [<span data-ttu-id="b9310-105">Distribuzione di modelli Time Series</span><span class="sxs-lookup"><span data-stu-id="b9310-105">Deploying Time Series Models</span></span>](#bkmk_TimeSeries)  
  
 [<span data-ttu-id="b9310-106">Distribuzione di modelli con dati di controllo</span><span class="sxs-lookup"><span data-stu-id="b9310-106">Deploying Models with Holdout</span></span>](#bkmk_Holdout)  
  
 [<span data-ttu-id="b9310-107">Distribuzione di modelli con filtri</span><span class="sxs-lookup"><span data-stu-id="b9310-107">Deploying Models with Filters</span></span>](#bkmk_Filter)  
  
 [<span data-ttu-id="b9310-108">Ripristino da backup di database</span><span class="sxs-lookup"><span data-stu-id="b9310-108">Restoring from Database Backups</span></span>](#bkmk_Backup)  
  
 [<span data-ttu-id="b9310-109">Utilizzo della sincronizzazione del database</span><span class="sxs-lookup"><span data-stu-id="b9310-109">Using Database Synchronization</span></span>](#bkmk_Synch)  
  
##  <a name="deploying-times-series-models"></a><a name="bkmk_TimeSeries"></a> <span data-ttu-id="b9310-110">Distribuzione di modelli Time Series</span><span class="sxs-lookup"><span data-stu-id="b9310-110">Deploying Times Series Models</span></span>  
 <span data-ttu-id="b9310-111">In SQL Server 2008 l'algoritmo Microsoft Time Series è stato migliorato mediante l'aggiunta di un secondo algoritmo complementare, ARIMA.</span><span class="sxs-lookup"><span data-stu-id="b9310-111">The Microsoft Time Series algorithm was enhanced in SQL Server 2008 by the addition of a second, complementary algorithm, ARIMA.</span></span> <span data-ttu-id="b9310-112">Per altre informazioni sulle modifiche apportate all'algoritmo Time Series, vedere [Algoritmo Microsoft Time Series](microsoft-time-series-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="b9310-112">For more information about the changes in the time series algorithm, see [Microsoft Time Series Algorithm](microsoft-time-series-algorithm.md).</span></span>  
  
 <span data-ttu-id="b9310-113">I modelli di data mining Time Series che utilizzano il nuovo algoritmo ARIMA possono pertanto presentare un comportamento diverso quando vengono distribuiti in un'istanza di SQL Server 2005 Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="b9310-113">Therefore, time series mining models that use the new ARIMA algorithm may behave differently when deployed to an instance of SQL Server 2005 Analysis Services.</span></span>  
  
 <span data-ttu-id="b9310-114">Se è stato impostato in modo esplicito il parametro PREDICTION_SMOOTHING per controllare la combinazione della stima dei modelli ARTXP e ARIMA, quando il modello viene distribuito in un'istanza di SQL Server 2005, in Analysis Services viene generato un errore per segnalare che il parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="b9310-114">If you have explicitly set the parameter PREDICTION_SMOOTHING to control the mixture of ARTXP and ARIMA models in prediction, when you deploy this model to an instance of SQL Server 2005, Analysis Services will raise an error stating that the parameter is not valid.</span></span> <span data-ttu-id="b9310-115">Per evitare l'errore, è necessario eliminare il parametro PREDICTION_SMOOTHING e convertire i modelli in un modello esclusivamente ARTXP.</span><span class="sxs-lookup"><span data-stu-id="b9310-115">To prevent this error, you must delete the PREDICTION_SMOOTHING parameter and convert the models to a pure ARTXP model.</span></span>  
  
 <span data-ttu-id="b9310-116">Viceversa, se si distribuisce in un'istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]un modello Time Series creato con SQL Server 2005 Analysis Services, quando si apre il modello di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], i file di definizione vengono prima convertiti nel nuovo formato e due nuovi parametri vengono aggiunti per impostazione predefinita a tutti i modelli Time Series.</span><span class="sxs-lookup"><span data-stu-id="b9310-116">Conversely, if you deploy a time series model that was created using SQL Server 2005 Analysis Services to an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], when you open the mining model in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the definition files are first converted to the new format, and two new parameters are added by default to all time series models.</span></span> <span data-ttu-id="b9310-117">Il parametro FORECAST_METHOD viene aggiunto con valore predefinito MIXED e il parametro PREDICTION_SMOOTHING viene aggiunto con valore predefinito 0,5.</span><span class="sxs-lookup"><span data-stu-id="b9310-117">The parameter FORECAST_METHOD is added with the default value of MIXED, and the parameter PREDICTION_SMOOTHING is added with the default value of 0.5.</span></span> <span data-ttu-id="b9310-118">Fino a quando non si rielabora il modello, tuttavia, il modello continua a utilizzare solo ARTXP per le previsioni.</span><span class="sxs-lookup"><span data-stu-id="b9310-118">However, the model will continue to use only ARTXP for forecasting until you reprocess the model.</span></span> <span data-ttu-id="b9310-119">Non appena si rielabora il modello, la stima cambia per utilizzare sia ARIMA sia ARTXP.</span><span class="sxs-lookup"><span data-stu-id="b9310-119">As soon as you reprocess the model, prediction changes to use both ARIMA and ARTXP.</span></span>  
  
 <span data-ttu-id="b9310-120">Per evitare di modificare il modello, è pertanto necessario limitarsi a esplorare il modello senza mai elaborarlo.</span><span class="sxs-lookup"><span data-stu-id="b9310-120">Therefore, if you wish to avoid changing the model, you should only browse the model and never process it.</span></span> <span data-ttu-id="b9310-121">In alternativa, è possibile impostare in modo esplicito i parametri FORECAST_METHOD o PREDICTION_SMOOTHING.</span><span class="sxs-lookup"><span data-stu-id="b9310-121">Alternatively, you could explicitly set the FORECAST_METHOD or PREDICTION_SMOOTHING parameters.</span></span>  
  
 <span data-ttu-id="b9310-122">Per informazioni dettagliate sulla configurazione dei modelli misti, vedere [Riferimento tecnico per l'algoritmo Microsoft Time Series](microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="b9310-122">For detailed information about configuring mixed models, see [Microsoft Time Series Algorithm Technical Reference](microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="b9310-123">Se viene utilizzato il provider dati di SqlClient 10 come provider per l'origine dei dati del modello, è necessario modificare anche la definizione dell'origine dati per specificare la versione precedente di SQL Server Native Client.</span><span class="sxs-lookup"><span data-stu-id="b9310-123">If the provider that is used for the model's data source is SQL Client Data Provider 10, you must also modify the data source definition to specify the previous version of the SQL Server Native Client.</span></span> <span data-ttu-id="b9310-124">In caso contrario, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] viene generato un errore indicante che il provider non è registrato.</span><span class="sxs-lookup"><span data-stu-id="b9310-124">Otherwise, [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] generates an error stating that the provider is not registered.</span></span>  
  
##  <a name="deploying-models-with-holdout"></a><a name="bkmk_Holdout"></a><span data-ttu-id="b9310-125">Distribuzione di modelli con i supporti</span><span class="sxs-lookup"><span data-stu-id="b9310-125">Deploying Models with Holdout</span></span>  
 <span data-ttu-id="b9310-126">Se si utilizza [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] per creare una struttura di data mining che contiene una partizione di dati di controllo utilizzata per testare i modelli di data mining, è possibile distribuire la struttura di data mining in un'istanza di SQL Server 2005, ma le informazioni sulle partizioni andranno perse.</span><span class="sxs-lookup"><span data-stu-id="b9310-126">If you use [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to create a mining structure that contains a holdout partition used for testing data mining models, the mining structure can be deployed to an instance of SQL Server 2005, but the partition information will be lost.</span></span>  
  
 <span data-ttu-id="b9310-127">Quando si apre la struttura di data mining in SQL Server 2005 Analysis Services, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] viene generato un errore e la struttura viene rigenerata per rimuovere la partizione di dati di controllo.</span><span class="sxs-lookup"><span data-stu-id="b9310-127">When you open the mining structure in SQL Server 2005 Analysis Services, [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] raises an error, and then regenerates the structure to remove the holdout partition.</span></span>  
  
 <span data-ttu-id="b9310-128">Dopo la ricompilazione della struttura, la dimensione della partizione di dati di dati non è più disponibile nella Finestra Proprietà; Tuttavia, il valore \<ddl100_100:HoldoutMaxPercent> 30 \</ddl100_100:HoldoutMaxPercent> ) potrebbe essere ancora presente nel file script ASSL.</span><span class="sxs-lookup"><span data-stu-id="b9310-128">After the structure has been rebuilt, the size of the holdout partition is no longer available in the Properties window; however, the value \<ddl100_100:HoldoutMaxPercent>30\</ddl100_100:HoldoutMaxPercent>) may still be present in the ASSL script file.</span></span>  
  
##  <a name="deploying-models-with-filters"></a><a name="bkmk_Filter"></a><span data-ttu-id="b9310-129">Distribuzione di modelli con filtri</span><span class="sxs-lookup"><span data-stu-id="b9310-129">Deploying Models with Filters</span></span>  
 <span data-ttu-id="b9310-130">Se si utilizza [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] per applicare un filtro a un modello di data mining, è possibile distribuire il modello in un'istanza di SQL Server 2005, ma il filtro non verrà applicato.</span><span class="sxs-lookup"><span data-stu-id="b9310-130">If you use [!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] to apply a filter to a mining model, the model can be deployed to an instance of SQL Server 2005, but the filter will not be applied.</span></span>  
  
 <span data-ttu-id="b9310-131">Quando si apre il modello di data mining, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] viene generato un errore e il modello viene rigenerato per rimuovere il filtro.</span><span class="sxs-lookup"><span data-stu-id="b9310-131">When you open the mining model, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] raises an error, and then regenerates the model to remove the filter.</span></span>  
  
##  <a name="restoring-from-database-backups"></a><a name="bkmk_Backup"></a> <span data-ttu-id="b9310-132">Ripristino dai backup del database</span><span class="sxs-lookup"><span data-stu-id="b9310-132">Restoring from Database Backups</span></span>  
 <span data-ttu-id="b9310-133">Non è possibile ripristinare in un'istanza di SQL Server 2005 un backup di database creato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b9310-133">You cannot restore a database backup that was created in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to an instance of SQL Server 2005.</span></span> <span data-ttu-id="b9310-134">In caso contrario, in SQL Server Management Studio viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="b9310-134">If you do so, SQL Server Management Studio generates an error.</span></span>  
  
 <span data-ttu-id="b9310-135">Se si crea il backup di un database di SQL Server 2005 Analysis Services e lo si ripristina in un'istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], tutti i modelli Time Series vengono modificati come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="b9310-135">If you create a backup of a SQL Server 2005 Analysis Services database and restore this backup on an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], all time series models are modified as described in the previous section.</span></span>  
  
##  <a name="using-database-synchronization"></a><a name="bkmk_Synch"></a><span data-ttu-id="b9310-136">Utilizzo della sincronizzazione del database</span><span class="sxs-lookup"><span data-stu-id="b9310-136">Using Database Synchronization</span></span>  
 <span data-ttu-id="b9310-137">La sincronizzazione del database da [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] a SQL Server 2005 non è supportata.</span><span class="sxs-lookup"><span data-stu-id="b9310-137">Database synchronization is not supported from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to SQL Server 2005.</span></span>  
  
 <span data-ttu-id="b9310-138">Se si tenta di sincronizzare un database di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , il server restituisce un errore e la sincronizzazione del database non riesce.</span><span class="sxs-lookup"><span data-stu-id="b9310-138">If you attempt to synchronize a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] database, the server returns an error and database synchronization fails.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9310-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9310-139">See Also</span></span>  
 [<span data-ttu-id="b9310-140">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="b9310-140">Analysis Services Backward Compatibility</span></span>](../analysis-services-backward-compatibility.md)  
  
  