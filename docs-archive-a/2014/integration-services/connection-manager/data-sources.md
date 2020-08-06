---
title: Origini dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- data sources [Integration Services], about data sources
ms.assetid: 7ac81612-9822-470f-8d0f-a1dc96142fe3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a52889627dbe61254ac1359ae97f25ee8521b6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629974"
---
# <a name="data-sources"></a><span data-ttu-id="0a478-102">Origini dati</span><span class="sxs-lookup"><span data-stu-id="0a478-102">Data Sources</span></span>
  [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="0a478-103">include un oggetto della modalità progettazione che è possibile usare nei pacchetti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]: l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a478-103">includes a design-time object that you can use in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages: the data source.</span></span>  
  
 <span data-ttu-id="0a478-104">Un oggetto di origine dati è un riferimento a una connessione in cui sono inclusi almeno una stringa di connessione e l'identificatore di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a478-104">A data source object is a reference to a connection, and at a minimum, it includes a connection string and a data source identifier.</span></span> <span data-ttu-id="0a478-105">Può includere anche metadati aggiuntivi quali una descrizione, un nome, un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="0a478-105">It can also include additional metadata such a description, a name, a user name, and a password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a478-106">È possibile aggiungere le origini dati solo ai progetti configurati per utilizzare il modello di distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0a478-106">You can add data sources only to projects that are configured to use the package deployment model.</span></span> <span data-ttu-id="0a478-107">Se un progetto è configurato per utilizzare il modello di distribuzione del progetto, è possibile utilizzare le gestioni connessioni create a livello di progetto per condividere le connessioni anziché le origini dati.</span><span class="sxs-lookup"><span data-stu-id="0a478-107">If a project is configured to use the project deployment model, you use connection managers created at the project level to share connections, in place of using data sources.</span></span>  
>   
>  <span data-ttu-id="0a478-108">Per altre informazioni sui modelli di distribuzione, vedere [Distribuzione di progetti e pacchetti](../packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="0a478-108">For more information about the deployment models, see [Deployment of Projects and Packages](../packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span> <span data-ttu-id="0a478-109">Per altre informazioni sulla conversione di un progetto nel modello di distribuzione del progetto, vedere [Distribuire progetti nel server Integration Services](../deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a478-109">For more information about converting a project to the project deployment model, see [Deploy Projects to Integration Services Server](../deploy-projects-to-integration-services-server.md).</span></span>  
  
 <span data-ttu-id="0a478-110">L'utilizzo di origini dei dati nei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a478-110">The advantages of using data sources in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages include the following:</span></span>  
  
-   <span data-ttu-id="0a478-111">Poiché le origini dati hanno ambito di progetto, un'origine dati creata in un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è disponibile per tutti i pacchetti del progetto.</span><span class="sxs-lookup"><span data-stu-id="0a478-111">A data source has project scope, which means that a data source created in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project is available to all the packages in the project.</span></span> <span data-ttu-id="0a478-112">È inoltre possibile definire un'origine dei dati una sola volta e farvi riferimento da gestioni connessioni in più pacchetti.</span><span class="sxs-lookup"><span data-stu-id="0a478-112">A data source can be defined one time and then referenced by connection managers in multiple packages.</span></span>  
  
-   <span data-ttu-id="0a478-113">Le origini dei dati consentono di mantenere la sincronizzazione tra l'oggetto di origine dati e i relativi riferimenti nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="0a478-113">A data source offers synchronization between the data source object and its package references.</span></span> <span data-ttu-id="0a478-114">Se l'origine dei dati e i pacchetti che vi fanno riferimento risiedono nello stesso progetto, la proprietà relativa alla stringa di connessione dei riferimenti all'origine dei dati verrà automaticamente aggiornata quando l'origine dei dati viene modificata.</span><span class="sxs-lookup"><span data-stu-id="0a478-114">If the data source and the packages that reference it reside in the same project, the connection string property of the data source references is automatically updated when the data source changes.</span></span>  
  
## <a name="reference-data-sources"></a><span data-ttu-id="0a478-115">Riferimento a origini dati</span><span class="sxs-lookup"><span data-stu-id="0a478-115">Reference Data Sources</span></span>  
 <span data-ttu-id="0a478-116">Per aggiungere un oggetto origine dati a un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , fare clic con il pulsante destro del mouse sulla cartella **Origini dati** in **Esplora soluzioni** , quindi scegliere **Nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="0a478-116">To add a data source object to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project, right-click the **Data Sources** folder in **Solution Explorer** and then click **New Data Source**.</span></span> <span data-ttu-id="0a478-117">L'elemento verrà aggiunto alla cartella **Origini dati** .</span><span class="sxs-lookup"><span data-stu-id="0a478-117">The item is added to the **Data Sources** folder.</span></span> <span data-ttu-id="0a478-118">Se desidera utilizzare oggetti di origine dati creati in altri progetti, sarà prima necessario aggiungerli al progetto.</span><span class="sxs-lookup"><span data-stu-id="0a478-118">If you want to use data source objects that were created in other projects, you must first add them to the project.</span></span>  
  
 <span data-ttu-id="0a478-119">Per utilizzare un origine dei dati in un pacchetto è necessario aggiungere al pacchetto una gestione connessione che fa riferimento all'oggetto di origine dati.</span><span class="sxs-lookup"><span data-stu-id="0a478-119">You use a data source object in a package by adding a connection manager that references the data source object to the package.</span></span> <span data-ttu-id="0a478-120">La gestione connessione può essere aggiunta prima della compilazione del flusso di controllo e dei flussi di dati del pacchetto oppure in un passaggio della procedura di creazione.</span><span class="sxs-lookup"><span data-stu-id="0a478-120">You can add it to the package before you build the package control flow and data flows, or as a step in constructing the control flow or data flow.</span></span>  
  
 <span data-ttu-id="0a478-121">Un oggetto di origine dati rappresenta una semplice connessione a un'origine dei dati e consente di accedere agli oggetti nell'archivio dati a cui fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="0a478-121">A data source object represents a simple connection to a data source and provides access to the objects in the data store that it references.</span></span> <span data-ttu-id="0a478-122">Un oggetto origine dati che si connette al database di esempio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]AdventureWorks, ad esempio, include tutte e 60 le tabelle del database.</span><span class="sxs-lookup"><span data-stu-id="0a478-122">For example, a data source object that connects to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]AdventureWorks Sample Database includes all 60 tables from the database.</span></span>  
  
 <span data-ttu-id="0a478-123">Non esiste alcuna dipendenza tra un'origine dei dati e le gestioni connessioni che vi fanno riferimento.</span><span class="sxs-lookup"><span data-stu-id="0a478-123">There is no dependency between a data source and the connection managers that reference it.</span></span> <span data-ttu-id="0a478-124">Se un'origine dei dati non fa più parte di un progetto i pacchetti rimangono comunque validi, perché le informazioni relative all'origine dei dati, quali il tipo di connessione e la stringa di connessione, sono incluse nella definizione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0a478-124">If a data source is no longer part of the project, the packages continue to be valid, because information about the data source, such as its connection type and connection string, is included in the package definition.</span></span>  
  
  