---
title: Disinstallare Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 5c764a00-d4bc-465d-b32e-e4efce052ce4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2870f7f84ea626b96560af586602996de3657276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628139"
---
# <a name="uninstall-reporting-services"></a><span data-ttu-id="ad173-102">Disinstallare Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ad173-102">Uninstall Reporting Services</span></span>
  <span data-ttu-id="ad173-103">La disinstallazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non rimuove il contenuto creato o la configurazione modificata.</span><span class="sxs-lookup"><span data-stu-id="ad173-103">Uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not remove the content you have created or configuration you have modified.</span></span> <span data-ttu-id="ad173-104">Se tuttavia è presente contenuto che sarà necessario dopo la disinstallazione, è consigliabile crearne copie prima di avviare il processo di disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="ad173-104">However, if there is content you need after the uninstall is complete, it is recommended you make copies of content before you begin the uninstallation process.</span></span>

## <a name="uninstall-sharepoint-mode"></a><span data-ttu-id="ad173-105">Disinstallare la modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="ad173-105">Uninstall SharePoint Mode</span></span>
 <span data-ttu-id="ad173-106">Quando si disinstalla la modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , vengono rimossi gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad173-106">When you uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode, the following are removed:</span></span>

-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ad173-107">e proxy del servizio.</span><span class="sxs-lookup"><span data-stu-id="ad173-107">service and service proxy.</span></span>

-   <span data-ttu-id="ad173-108">File utilizzati per l'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad173-108">Files used for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span>

 <span data-ttu-id="ad173-109">Le applicazioni del servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] non vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="ad173-109">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications are not removed.</span></span> <span data-ttu-id="ad173-110">Se le applicazioni del servizio non sono più necessarie, eliminarle mediante Windows PowerShell o Amministrazione centrale SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad173-110">If you no longer want the service applications, delete them by using Windows PowerShell or SharePoint Central Administration.</span></span>

 <span data-ttu-id="ad173-111">Gli elementi del report e i metadati correlati non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="ad173-111">The report items and related meta data are not removed.</span></span> <span data-ttu-id="ad173-112">Queste informazioni sono contenute nei database del contenuto e di configurazione correlati alle applicazioni del servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad173-112">This information is contained in the content and configuration databases related to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="ad173-113">I database non vengono rimossi ed è possibile eseguirne manualmente la migrazione a un'altra installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad173-113">The databases are not removed and you can manually migrate the databases to another installation of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="ad173-114">Se le informazioni non sono più necessarie, eliminare i database.</span><span class="sxs-lookup"><span data-stu-id="ad173-114">If you no longer want the information, delete the databases.</span></span> <span data-ttu-id="ad173-115">Per ulteriori informazioni, vedere [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="ad173-115">For more information, see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>

 <span data-ttu-id="ad173-116">Di seguito sono riportati nomi di esempio dei tre database di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] che non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="ad173-116">The following are example names of the three [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] databases that are not removed.</span></span>

-   <span data-ttu-id="ad173-117">**Database del server di report:** ReportingService_7f616e2d253040e8ab5653b3c09a065e</span><span class="sxs-lookup"><span data-stu-id="ad173-117">**Report server database:** ReportingService_7f616e2d253040e8ab5653b3c09a065e</span></span>

-   <span data-ttu-id="ad173-118">**Database temporaneo del server di report:** ReportingService_7f616e2d253040e8ab5653b3c09a065eTempDB</span><span class="sxs-lookup"><span data-stu-id="ad173-118">**Report server temp database:** ReportingService_7f616e2d253040e8ab5653b3c09a065eTempDB</span></span>

-   <span data-ttu-id="ad173-119">**Database di avvisi del server di report:** ReportingService_7f616e2d253040e8ab5653b3c09a065e_Alerting</span><span class="sxs-lookup"><span data-stu-id="ad173-119">**Report server alerting database:** ReportingService_7f616e2d253040e8ab5653b3c09a065e_Alerting</span></span>

### <a name="uninstall-the-add-in-for-sharepoint-products"></a><span data-ttu-id="ad173-120">Disinstallare il componente aggiuntivo per Prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad173-120">Uninstall the Add-in for SharePoint Products.</span></span>
 <span data-ttu-id="ad173-121">Quando si disinstalla il componente aggiuntivo da un computer, è possibile scegliere di disinstallare solo i file o rimuovere anche la funzionalità [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dalla farm.</span><span class="sxs-lookup"><span data-stu-id="ad173-121">When you uninstall the add-in from a computer, you can choose to only uninstall the files or to also remove the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] feature from the farm.</span></span> <span data-ttu-id="ad173-122">Per informazioni sulla disinstallazione del [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] componente aggiuntivo per prodotti SharePoint, vedere [installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;SharePoint 2010 e sharepoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="ad173-122">For information on uninstalling the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>

## <a name="uninstall-native-mode"></a><span data-ttu-id="ad173-123">Disinstallare la modalità nativa</span><span class="sxs-lookup"><span data-stu-id="ad173-123">Uninstall Native Mode</span></span>
 <span data-ttu-id="ad173-124">Quando si disinstalla la modalità nativa [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , tutto ciò che è stato **creato** o **modificato** dopo l'installazione viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="ad173-124">When you uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] native mode, anything that was **created** or **modified** after the installation is left in place.</span></span> <span data-ttu-id="ad173-125">Ad esempio, file di database, file di log, file di configurazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ed elementi di contenuto quali report e file di origine dati.</span><span class="sxs-lookup"><span data-stu-id="ad173-125">For example database files, log files, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration files, and content items such as reports and datasource files.</span></span>

 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ad173-126">è una funzionalità dell'istanza, pertanto non è elencata in Programmi e funzionalità nel Pannello di controllo di Windows.</span><span class="sxs-lookup"><span data-stu-id="ad173-126">is an instance feature and therefore is not listed in Windows Control Panel, Programs and Features.</span></span> <span data-ttu-id="ad173-127">Per disinstallare la modalità nativa [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="ad173-127">To uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode:</span></span>

1.  <span data-ttu-id="ad173-128">Nel Pannello di controllo di Windows fare clic su **Programmi e funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="ad173-128">In Windows Control Panel, click **Programs and Features**.</span></span>

2.  <span data-ttu-id="ad173-129">In **Programmi e funzionalità** selezionare **Microsoft SQL Server 2012**.</span><span class="sxs-lookup"><span data-stu-id="ad173-129">In **Programs and Features** select **Microsoft SQL Server 2012**.</span></span>

3.  <span data-ttu-id="ad173-130">Nella disinstallazione guidata selezionare l'istanza che include la funzionalità [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]**RS**.</span><span class="sxs-lookup"><span data-stu-id="ad173-130">In the uninstall wizard, select the instance that includes the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance feature **RS**.</span></span>

     <span data-ttu-id="ad173-131">![rs_nativemode_uninstall_selectinstance](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectinstance.gif "rs_nativemode_uninstall_selectinstance")</span><span class="sxs-lookup"><span data-stu-id="ad173-131">![rs_nativemode_uninstall_selectinstance](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectinstance.gif "rs_nativemode_uninstall_selectinstance")</span></span>

4.  <span data-ttu-id="ad173-132">Dopo aver selezionato l'istanza, selezionare la funzionalità [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad173-132">After you select the instance, select the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] feature.</span></span>

     <span data-ttu-id="ad173-133">![rs_nativemode_uninstall_selectfeatures](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectfeatures.gif "rs_nativemode_uninstall_selectfeatures")</span><span class="sxs-lookup"><span data-stu-id="ad173-133">![rs_nativemode_uninstall_selectfeatures](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectfeatures.gif "rs_nativemode_uninstall_selectfeatures")</span></span>

5.  <span data-ttu-id="ad173-134">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="ad173-134">Complete the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad173-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad173-135">See Also</span></span>
 <span data-ttu-id="ad173-136">[Disinstallare un'istanza esistente di SQL Server &#40;il programma di installazione&#41;](../../../2014/sql-server/install/uninstall-an-existing-instance-of-sql-server-setup.md) [installare o disinstallare il componente aggiuntivo PowerPivot per SharePoint &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013) [installare o disinstallare il componente aggiuntivo Reporting Services per SharePoint &#40;sharepoint 2010 e SharePoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)</span><span class="sxs-lookup"><span data-stu-id="ad173-136">[Uninstall an Existing Instance of SQL Server &#40;Setup&#41;](../../../2014/sql-server/install/uninstall-an-existing-instance-of-sql-server-setup.md) [Install or Uninstall the PowerPivot for SharePoint Add-in &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013) [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)</span></span>

