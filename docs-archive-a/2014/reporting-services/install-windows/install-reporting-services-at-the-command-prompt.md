---
title: Installazione del prompt dei comandi di Reporting Services modalità SharePoint e modalità nativa | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 048169b3-512c-41e4-895a-0416eff41268
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2b2101c40c5136e89d4e30d9551187a2b63672da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711744"
---
# <a name="command-prompt-installation-of-reporting-services-sharepoint-mode-and-native-mode"></a><span data-ttu-id="b4b78-102">Installazione dal prompt dei comandi delle modalità SharePoint e nativa di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b4b78-102">Command Prompt Installation of Reporting Services SharePoint Mode and Native Mode</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="b4b78-103">supporta l'installazione da riga di comando dal programma di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b4b78-103">supports a command-line installation from the SQL Server setup program.</span></span> <span data-ttu-id="b4b78-104">In questo argomento sono contenuti numerosi esempi di installazioni da riga di comando specifiche di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4b78-104">This topic contains several examples of command-line installations that are specific to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="b4b78-105">Per una descrizione completa delle opzioni della riga di comando disponibili per tutti i componenti SQL Server, vedere [Install SQL Server 2014 dal prompt dei comandi](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="b4b78-105">For a complete description of the command-line options available for all SQL Server components, see [Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="b4b78-106">In questo argomento non vengono descritte le opzioni della riga di comando per il componente aggiuntivo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per i prodotti SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4b78-106">This topic does not describe command-line options for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products.</span></span> <span data-ttu-id="b4b78-107">Per informazioni sull'installazione dalla riga di comando del componente aggiuntivo, vedere [Installare il componente aggiuntivo utilizzando il file di installazione rssharepoint.msi](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md#bkmk_install_rssharepoint).</span><span class="sxs-lookup"><span data-stu-id="b4b78-107">For information on command installation of the add-in, see [Install the add-in using the installation file rsSharePoint.msi](install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md#bkmk_install_rssharepoint).</span></span>  
  
 <span data-ttu-id="b4b78-108">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità SharePoint | [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modalità nativa</span><span class="sxs-lookup"><span data-stu-id="b4b78-108">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode | [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode</span></span>  
  
## <a name="rsinstallmode-native-mode"></a><span data-ttu-id="b4b78-109">RSINSTALLMODE (modalità nativa)</span><span class="sxs-lookup"><span data-stu-id="b4b78-109">RSINSTALLMODE (Native Mode)</span></span>  
 <span data-ttu-id="b4b78-110">L'impostazione di input primaria per l'installazione di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è **/RSINSTALLMODE** .</span><span class="sxs-lookup"><span data-stu-id="b4b78-110">The primary input setting for installing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is the **/RSINSTALLMODE** input setting.</span></span> <span data-ttu-id="b4b78-111">All'impostazione sono associate due opzioni: **DefaultNativeMode** e **FilesOnlyMode**</span><span class="sxs-lookup"><span data-stu-id="b4b78-111">The setting has two options: **DefaultNativeMode** and **FilesOnlyMode**</span></span>  
  
 <span data-ttu-id="b4b78-112">Se l'installazione include il motore di database di SQL Server, l'opzione predefinita di RSINSTALLMODE è DefaultNativeMode. In caso contrario, l'opzione predefinita di RSINSTALLMODE è FilesOnlyMode. Se si sceglie DefaultNativeMode, ma nell'installazione non è incluso il motore di database di SQL Server, RSINSTALLMODE viene impostato automaticamente su FilesOnlyMode.</span><span class="sxs-lookup"><span data-stu-id="b4b78-112">If the installation includes the SQL Server Database engine, the default RSINSTALLMODE is DefaultNativeMode.If the installation does not include the SQL Server Database engine, the default RSINSTALLMODE is FilesOnlyMode.If you choose DefaultNativeMode but the installation does not include the SQL Server Database engine, the installation automatically changes the RSINSTALLMODE to FilesOnlyMode.</span></span> <span data-ttu-id="b4b78-113">Per ulteriori informazioni sulle impostazioni di input, vedere [Install SQL Server 2014 dal prompt dei comandi](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="b4b78-113">For more information on the input settings, see [Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
## <a name="rsshpinstallmode-sharepoint-mode"></a><span data-ttu-id="b4b78-114">RSSHPINSTALLMODE (modalità SharePoint)</span><span class="sxs-lookup"><span data-stu-id="b4b78-114">RSSHPINSTALLMODE (SharePoint Mode)</span></span>  
 <span data-ttu-id="b4b78-115">L'impostazione di input per installare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint è **/RSSHPINSTALLMODE**.</span><span class="sxs-lookup"><span data-stu-id="b4b78-115">The input setting to install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode is **/RSSHPINSTALLMODE**.</span></span> <span data-ttu-id="b4b78-116">L'impostazione di input dispone di un'opzione, SharePointFilesOnlyMode</span><span class="sxs-lookup"><span data-stu-id="b4b78-116">The input setting has one option: SharePointFilesOnlyMode.</span></span> <span data-ttu-id="b4b78-117">che consente di installare tutti i file necessari per la modalità SharePoint. Dopo l'installazione sarà necessario procedere alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="b4b78-117">The option installs all the files needed for SharePoint mode but, configuration is required following installation.</span></span> <span data-ttu-id="b4b78-118">I passaggi aggiuntivi della configurazione vengono completati utilizzando Amministrazione centrale SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4b78-118">The additional configuration steps are completed using SharePoint Central Administration.</span></span> <span data-ttu-id="b4b78-119">Per altre informazioni, vedere [Installare la modalità SharePoint di Reporting Services per SharePoint 2010](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="b4b78-119">For more information, see [Install Reporting Services SharePoint Mode for SharePoint 2010](../../sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span>  
  
## <a name="examples-of-sharepoint-mode-installation"></a><span data-ttu-id="b4b78-120">Esempi di installazione in modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="b4b78-120">Examples of SharePoint Mode Installation</span></span>  
 <span data-ttu-id="b4b78-121">Nell'esempio seguente vengono installati SQL Server, il servizio del motore di database e [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint, nonché il componente aggiuntivo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] per SharePoint (RS_SHPWFE).</span><span class="sxs-lookup"><span data-stu-id="b4b78-121">The following example installs SQL Server the database engine service and [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode as well as the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint (RS_SHPWFE).</span></span>  
  
```  
setup /q /ACTION=install /FEATURES=SQL, RS_SHP, RS_SHPWFE,TOOLS /INSTANCENAME=MSSQLSERVER /SQLSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" /RSSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /SQLSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE" /AGTSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE"  
```  
  
 <span data-ttu-id="b4b78-122">Nell'esempio seguente viene installata solo [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4b78-122">The following example installs only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>  
  
```  
Setup.exe /q /ACTION="Install" /IACCEPTSQLSERVERLICENSETERMS /FEATURES="RS_SHP" /INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDWOWDIR="C:\Program Files (x86)\Microsoft SQL Server" /INSTALLSQLDATADIR="C:\Program Files\Microsoft SQL Server" /SECURITYMODE="SQL" /SAPWD="*****" /PID="[Your PID Value]" /SQLSYSADMINACCOUNTS="[Account Name]" "AutoSql Admin Group" /ASSYSADMINACCOUNTS="[Account Name]" /UPDATEENABLED="False"  
  
```  
  
 <span data-ttu-id="b4b78-123">Nell'esempio seguente vengono installate tutte le funzionalità di SQL Server, incluse le modalità nativa e Sharepoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4b78-123">The following example installs all of the SQL Server features, including both [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode and SharePoint mode.</span></span>  
  
```  
Setup.exe /q /ACTION="Install" /INSTANCENAME="MSSQLSERVER" /FEATURES="SQLEngine,Replication,SNAC,SNAC_SDK,Browser,Writer,AS,IS,MDS,Adv_SSMS,BC,BOL,Conn,SDK,DReplay_CTLR,DReplay_CLT, RS_SHP,RS_SHPWFE,DQC,BIDS,FullText, RS,DQ,SSMS" /INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDWOWDIR="C:\Program Files (x86)\Microsoft SQL Server" /INSTALLSQLDATADIR="C:\Program Files\Microsoft SQL Server" /SQLSVCACCOUNT="[Account Name]" /SQLSVCPASSWORD="********" /AGTSVCACCOUNT="[Account Nam]" /AGTSVCPASSWORD="********" /CTLRSVCACCOUNT="[Account Nam]" /CTLRSVCPASSWORD="********" /CLTSVCACCOUNT="[Account Nam]" /CLTSVCPASSWORD="********" /ASSVCACCOUNT="[Account Nam]" /ASSVCPASSWORD="********" /RSSVCACCOUNT="[Account Nam]" /RSSVCPASSWORD="********" /FTSVCACCOUNT="[Account Nam]" /FTSVCPASSWORD="********" /SECURITYMODE="SQL" /SAPWD="********" /PID="[Your PID Value]" /SQLSYSADMINACCOUNTS="[Account Nam]" "AutoSql Admin Group" /ASSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /RSSHPINSTALLMODE="SharePointFilesOnlyMode" /RSINSTALLMODE="DefaultNativeMode"  
```  
  
## <a name="examples-of-sharepoint-mode-upgrade"></a><span data-ttu-id="b4b78-124">Esempi di aggiornamento della modalità SharePoint</span><span class="sxs-lookup"><span data-stu-id="b4b78-124">Examples of SharePoint Mode Upgrade</span></span>  
 <span data-ttu-id="b4b78-125">Nell'esempio seguente viene aggiornata la modalità SharePoint di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4b78-125">The following example upgrades [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="b4b78-126">**RSUPGRADEPASSWORD** è la password dell'account del servizio del server di report esistente.</span><span class="sxs-lookup"><span data-stu-id="b4b78-126">**RSUPGRADEPASSWORD** is the password of the existing Report Server service account.</span></span> <span data-ttu-id="b4b78-127">RSUPGRADEPASSWORD è un campo obbligatorio in un scenario di aggiornamento a meno che l'account del servizio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sia un account predefinito.</span><span class="sxs-lookup"><span data-stu-id="b4b78-127">RSUPGRADEPASSWORD is a required field in an upgrade scenario unless the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service account is a built-in account.</span></span>  
  
```  
Setup.exe /q /ACTION="Upgrade" /INSTANCENAME="MSSQLSERVER" /PID="[PID value]" /FTSVCACCOUNT="[DOMAIN\ACCOUNT]" /FTSVCPASSWORD="[ACCOUNTPASSSWORD]" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /RSUPGRADEPASSWORD="******"  
```  
  
 <span data-ttu-id="b4b78-128">L'esempio seguente può essere utilizzato per aggiornare un'installazione della modalità SharePoint basata sull'architettura del servizio di SharePoint condivisa.</span><span class="sxs-lookup"><span data-stu-id="b4b78-128">The following example can be used to upgrade a SharePoint Mode installation that is based on the SharePoint shared service architecture.</span></span> <span data-ttu-id="b4b78-129">Nell'esempio viene utilizzata l'opzione ALLOWUPGRADEFORSSRSSHAREPOINTMODE,</span><span class="sxs-lookup"><span data-stu-id="b4b78-129">The example uses switch ALLOWUPGRADEFORSSRSSHAREPOINTMODE.</span></span> <span data-ttu-id="b4b78-130">L'opzione non è necessaria per aggiornare le versioni precedenti che non sono basate sull'architettura di servizi condivisi:</span><span class="sxs-lookup"><span data-stu-id="b4b78-130">The switch is not needed for upgrading older versions that are not based on the shared service architecture:</span></span>  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
```  
Setup.exe /q /ACTION="Upgrade" /INSTANCENAME="MSSQLSERVER" /PID="[Your PID Value]" /FTSVCACCOUNT="[ACCOUNT Name]" /FTSVCPASSWORD="****" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /ALLOWUPGRADEFORSSRSSHAREPOINTMODE="True"  
```  
  
## <a name="examples-of-native-mode-installation"></a><span data-ttu-id="b4b78-131">Esempi di installazione in modalità nativa</span><span class="sxs-lookup"><span data-stu-id="b4b78-131">Examples of Native Mode Installation</span></span>  
  
```  
Setup.exe /q /ACTION="Install" /INSTANCENAME="MSSQLSERVER" /FEATURES="SQLEngine,Replication,SNAC,SNAC_SDK,Browser,Writer,AS,IS,MDS,Adv_SSMS,BC,BOL,Conn,SDK,DReplay_CTLR,DReplay_CLT,DQC,BIDS,FullText, RS,DQ,SSMS" /INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDDIR="C:\Program Files\Microsoft SQL Server" /INSTALLSHAREDWOWDIR="C:\Program Files (x86)\Microsoft SQL Server" /INSTALLSQLDATADIR="C:\Program Files\Microsoft SQL Server" /SQLSVCACCOUNT="[Account Name]" /SQLSVCPASSWORD="********" /AGTSVCACCOUNT="[Account Nam]" /AGTSVCPASSWORD="********" /CTLRSVCACCOUNT="[Account Nam]" /CTLRSVCPASSWORD="********" /CLTSVCACCOUNT="[Account Nam]" /CLTSVCPASSWORD="********" /ASSVCACCOUNT="[Account Nam]" /ASSVCPASSWORD="********" /RSSVCACCOUNT="[Account Nam]" /RSSVCPASSWORD="********" /FTSVCACCOUNT="[Account Nam]" /FTSVCPASSWORD="********" /SECURITYMODE="SQL" /SAPWD="********" /PID="[Your PID Value]" /SQLSYSADMINACCOUNTS="[Account Nam]" "AutoSql Admin Group" /ASSYSADMINACCOUNTS="BUILTIN\ADMINISTRATORS" /UPDATEENABLED="False" /IACCEPTSQLSERVERLICENSETERMS /RSINSTALLMODE="DefaultNativeMode"  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4b78-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4b78-132">See Also</span></span>  
 <span data-ttu-id="b4b78-133">[Installare SQL Server 2014 dal prompt dei comandi](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="b4b78-133">[Install SQL Server 2014 from the Command Prompt](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="b4b78-134">[Parametri SysPrep](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md#SysPrep) </span><span class="sxs-lookup"><span data-stu-id="b4b78-134">[SysPrep Parameters](../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md#SysPrep) </span></span>  
 [<span data-ttu-id="b4b78-135">Installazione di PowerPivot dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="b4b78-135">Install PowerPivot from the Command Prompt</span></span>](../../sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
  