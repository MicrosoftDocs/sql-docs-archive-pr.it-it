---
title: Importare un file BACPAC per creare un nuovo database utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.importdac.progress.f1
- sql12.swb. importdac.settings.f1
- sql12.swb.importdac.storagebrowser.f1
- sql12.swb. importdac.summary.f1
- sql12.swb.importdac.results.f1
- sql12.swb. importdac.progress.f1
- sql12.swb.importdac.welcome.f1
- sql12.swb.importdac.settings.f1
- sql12.swb. importdac.results.f1
- sql12.swb.importdac.summary.f1
helpviewer_keywords:
- Data-tier application
- SQL Server DAC
- Migrate database
- DAC
ms.assetid: 736d8d9a-39f1-4bf8-b81f-2e56c134d12e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 66e71453f38fe15f295fceaf63b5edba5ab5ff43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635653"
---
# <a name="import-a-bacpac-file-to-create-a-new-user-database"></a><span data-ttu-id="e4e7d-102">Importare un file BACPAC per creare un nuovo database utente</span><span class="sxs-lookup"><span data-stu-id="e4e7d-102">Import a BACPAC File to Create a New User Database</span></span>
  <span data-ttu-id="e4e7d-103">Importare un file dell'applicazione livello dati (DAC), con estensione bacpac, per creare una copia del database originale, completo dei dati, in una nuova istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] o in [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e7d-103">Import a data-tier application (DAC) file - a .bacpac file - to create a copy of the original database, with the data, on a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)].</span></span> <span data-ttu-id="e4e7d-104">Le operazioni di importazione ed esportazione possono essere combinate per eseguire la migrazione di un'applicazione livello dati o database tra istanze o per creare un backup logico, quale la creazione di una copia locale di un database distribuito in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e7d-104">Export-import operations can be combined to migrate a DAC or database between instances, or to create a logical backup, such as creating an on-premise copy of a database deployed in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="e4e7d-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4e7d-105">Before You Begin</span></span>  
 <span data-ttu-id="e4e7d-106">Il processo di importazione compila una nuova applicazione livello dati in due fasi.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-106">The import process builds a new DAC in two stages.</span></span>  
  
1.  <span data-ttu-id="e4e7d-107">L'importazione crea una nuova applicazione livello dati con database associato utilizzando la definizione dell'applicazione livello dati archiviata nel file di esportazione, con le stesse modalità con cui una distribuzione dell'applicazione livello dati crea una nuova applicazione livello dati dalla definizione in un file del pacchetto di applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-107">The import creates a new DAC and associated database using the DAC definition stored in the export file, the same way a DAC deploy creates a new DAC from the definition in a DAC package file.</span></span>  
  
2.  <span data-ttu-id="e4e7d-108">Durante l'importazione viene eseguita la copia bulk di dati dal file di esportazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-108">The import bulk copies in the data from the export file.</span></span>  
  
 
## <a name="sql-server-utility"></a><span data-ttu-id="e4e7d-109">Utilità SQL Server</span><span class="sxs-lookup"><span data-stu-id="e4e7d-109">SQL Server Utility</span></span>  
 <span data-ttu-id="e4e7d-110">Se si importa un'applicazione livello dati in un'istanza gestita del Motore di database, il pacchetto di applicazione livello dati importato viene incorporato in Utilità SQL Server al successivo invio del set di raccolta dell'utilità dall'istanza al punto di controllo dell'utilità.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-110">If you import a DAC to a managed instance of the Database Engine, the imported DAC is incorporated into the SQL Server Utility the next time the utility collection set is sent from the instance to the utility control point.</span></span> <span data-ttu-id="e4e7d-111">L'applicazione livello dati sarà quindi presente nel nodo **Deployed Data-tier Applications** (Applicazioni livello dati distribuite) in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** e segnalata nella pagina dei dettagli **Deployed Data-tier Applications** (Applicazioni livello dati distribuite).</span><span class="sxs-lookup"><span data-stu-id="e4e7d-111">The DAC will then be present in the **Deployed Data-tier Applications** node of the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] **Utility Explorer** and reported in the **Deployed Data-tier Applications** details page.</span></span>  
  
## <a name="database-options-and-settings"></a><span data-ttu-id="e4e7d-112">Opzioni e impostazioni del database</span><span class="sxs-lookup"><span data-stu-id="e4e7d-112">Database Options and Settings</span></span>  
 <span data-ttu-id="e4e7d-113">Per impostazione predefinita, il database creato durante l'importazione disporrà di tutte le impostazioni predefinite dall'istruzione CREATE DATABASE, con l'eccezione delle regole di confronto del database e del livello di compatibilità che vengono impostati sui valori definiti nel file di esportazione dell'applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-113">By default, the database created during the import will have all of the default settings from the CREATE DATABASE statement, except that the database collation and compatibility level are set to the values defined in the DAC export file.</span></span> <span data-ttu-id="e4e7d-114">In un file di esportazione dell'applicazione livello dati vengono utilizzati i valori del database originale.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-114">A DAC export file uses the values from the original database.</span></span>  
  
 <span data-ttu-id="e4e7d-115">Alcune opzioni del database, ad esempio TRUSTWORTHY, DB_CHAINING e HONOR_BROKER_PRIORITY, non possono essere modificate durante il processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-115">Some database options, such as TRUSTWORTHY, DB_CHAINING, and HONOR_BROKER_PRIORITY, cannot be adjusted as part of the import process.</span></span> <span data-ttu-id="e4e7d-116">Le proprietà fisiche, ad esempio il numero di filegroup o i numeri e le dimensioni dei file, non possono essere modificate durante il processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-116">Physical properties, such as the number of filegroups, or the numbers and sizes of files cannot be altered as part of the import process.</span></span> <span data-ttu-id="e4e7d-117">Al termine dell'importazione, è possibile usare l'istruzione ALTER DATABASE, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell per personalizzare il database.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-117">After the import completes, you can use the ALTER DATABASE statement, [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell to tailor the database.</span></span> <span data-ttu-id="e4e7d-118">Per altre informazioni, vedere [Databases](../databases/databases.md).</span><span class="sxs-lookup"><span data-stu-id="e4e7d-118">For more information, see [Databases](../databases/databases.md).</span></span>  
  
## <a name="limitations-and-restrictions"></a><span data-ttu-id="e4e7d-119">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="e4e7d-119">Limitations and Restrictions</span></span>  
 <span data-ttu-id="e4e7d-120">È possibile importare un'applicazione livello dati in [!INCLUDE[ssSDS](../../includes/sssds-md.md)]o in un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)] in cui è in esecuzione [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-120">A DAC can be imported to [!INCLUDE[ssSDS](../../includes/sssds-md.md)], or an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 4 (SP4) or later.</span></span> <span data-ttu-id="e4e7d-121">Se si esporta un'applicazione livello dati da una versione successiva, è possibile che nell'applicazione in questione siano contenuti oggetti non supportati da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e7d-121">If you export a DAC from a higher version, the DAC may contain objects not supported by [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="e4e7d-122">Non è possibile distribuire tali applicazioni livello dati a istanze di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e7d-122">You cannot deploy those DACs to instances of [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4e7d-123">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="e4e7d-123">Prerequisites</span></span>  
 <span data-ttu-id="e4e7d-124">È consigliabile evitare di importare file di esportazione dell'applicazione livello dati provenienti da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-124">We recommend that you do not import a DAC export file from unknown or untrusted sources.</span></span> <span data-ttu-id="e4e7d-125">Tali file potrebbero contenere codice dannoso che potrebbe eseguire codice Transact-SQL indesiderato o causare errori modificando lo schema.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-125">Such files could contain malicious code that might execute unintended Transact-SQL code or cause errors by modifying the schema.</span></span> <span data-ttu-id="e4e7d-126">Prima di usare un file di esportazione proveniente da un'origine sconosciuta o non attendibile, decomprimere l'applicazione livello dati e controllare il codice, ad esempio le stored procedure e altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-126">Before you use an export file from an unknown or untrusted source, unpack the DAC and examine the code, like stored procedures and other user-defined code.</span></span> <span data-ttu-id="e4e7d-127">Per altre informazioni su come eseguire questi controlli, vedere [Validate a DAC Package](validate-a-dac-package.md).</span><span class="sxs-lookup"><span data-stu-id="e4e7d-127">For more information about how to perform these checks, see [Validate a DAC Package](validate-a-dac-package.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="e4e7d-128">Security</span><span class="sxs-lookup"><span data-stu-id="e4e7d-128">Security</span></span>  
 <span data-ttu-id="e4e7d-129">Per migliorare la sicurezza, gli account di accesso dell'autenticazione di SQL Server vengono archiviati in un file di esportazione dell'applicazione livello dati senza password.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-129">To improve security, SQL Server Authentication logins are stored in a DAC export file without a password.</span></span> <span data-ttu-id="e4e7d-130">Quando il file viene importato, l'account di accesso viene creato come account disabilitato con una password generata.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-130">When the file is imported, the login is created as a disabled login with a generated password.</span></span> <span data-ttu-id="e4e7d-131">Per abilitare gli account di accesso, è necessario accedere usando un account che dispone dell'autorizzazione ALTER ANY LOGIN e usare ALTER LOGIN per abilitare l'account di accesso e assegnare una nuova password che può essere comunicata all'utente.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-131">To enable the logins, log in using a login that has ALTER ANY LOGIN permission and use ALTER LOGIN to enable the login and assign a new password that can be communicated to the user.</span></span> <span data-ttu-id="e4e7d-132">Questa operazione non è necessaria per gli account di accesso dell'autenticazione di Windows, in quanto le relative password non sono gestite da SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-132">This is not needed for Windows Authentication logins because their passwords are not managed by SQL Server.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="e4e7d-133">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e4e7d-133">Permissions</span></span>  
 <span data-ttu-id="e4e7d-134">Un'applicazione livello dati può essere importata unicamente da membri del ruolo predefinito del server **sysadmin** o **serveradmin** oppure tramite account di accesso nel ruolo predefinito del server **dbcreator** con autorizzazioni ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-134">A DAC can only be imported by members of the **sysadmin** or **serveradmin** fixed server roles, or by logins that are in the **dbcreator** fixed server role and have ALTER ANY LOGIN permissions.</span></span> <span data-ttu-id="e4e7d-135">È anche possibile importare un'applicazione livello dati con l'account dell'amministratore di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] predefinito denominato **sa** .</span><span class="sxs-lookup"><span data-stu-id="e4e7d-135">The built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator account named **sa** can also import a DAC.</span></span> <span data-ttu-id="e4e7d-136">L'importazione di un'applicazione livello dati con gli account di accesso in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] richiede l'appartenenza al ruolo loginmanager o serveradmin.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-136">Importing a DAC with logins to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the loginmanager or serveradmin roles.</span></span> <span data-ttu-id="e4e7d-137">L'importazione di un'applicazione livello dati senza account di accesso in [!INCLUDE[ssSDS](../../includes/sssds-md.md)] richiede l'appartenenza al ruolo dbmanager o serveradmin.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-137">Importing a DAC without logins to [!INCLUDE[ssSDS](../../includes/sssds-md.md)] requires membership in the dbmanager or serveradmin roles.</span></span>  
  
## <a name="using-the-import-data-tier-application-wizard"></a><span data-ttu-id="e4e7d-138">Utilizzo della procedura guidata Importa applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="e4e7d-138">Using the Import Data-tier Application Wizard</span></span>  
 <span data-ttu-id="e4e7d-139">**Per avviare la procedura guidata, effettuare i passaggi seguenti:**</span><span class="sxs-lookup"><span data-stu-id="e4e7d-139">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="e4e7d-140">Connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], locale o in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4e7d-140">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], whether on-premise or in [!INCLUDE[ssSDS](../../includes/sssds-md.md)].</span></span>  
  
2.  <span data-ttu-id="e4e7d-141">In **Esplora oggetti**fare clic con il pulsante destro del mouse su **Database**quindi scegliere la voce di menu **Importa applicazione livello dati** per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-141">In **Object Explorer**, right-click on **Databases**, and then select the **Import Data-tier Application** menu item to launch the wizard.</span></span>  
  
3.  <span data-ttu-id="e4e7d-142">Completare le finestre di dialogo della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-142">Complete the wizard dialogs:</span></span>  
  
    -   [<span data-ttu-id="e4e7d-143">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="e4e7d-143">Introduction Page</span></span>](#Introduction)  
  
    -   [<span data-ttu-id="e4e7d-144">Pagina Impostazioni di importazione</span><span class="sxs-lookup"><span data-stu-id="e4e7d-144">Import Settings Page</span></span>](#Import_settings)  
  
    -   [<span data-ttu-id="e4e7d-145">Pagina Impostazioni database</span><span class="sxs-lookup"><span data-stu-id="e4e7d-145">Database Settings Page</span></span>](#Database_settings)  
  
    -   [<span data-ttu-id="e4e7d-146">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e4e7d-146">Summary Page</span></span>](#Summary)  
  
    -   [<span data-ttu-id="e4e7d-147">Pagina Stato</span><span class="sxs-lookup"><span data-stu-id="e4e7d-147">Progress Page</span></span>](#Progress)  
  
    -   [<span data-ttu-id="e4e7d-148">Pagina Risultati</span><span class="sxs-lookup"><span data-stu-id="e4e7d-148">Results Page</span></span>](#Results)  
  
###  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="e4e7d-149">Pagina Introduzione</span><span class="sxs-lookup"><span data-stu-id="e4e7d-149">Introduction Page</span></span>  
 <span data-ttu-id="e4e7d-150">In questa pagina vengono descritti i passaggi per la procedura guidata Importa applicazione livello dati.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-150">This page describes the steps for the Data-tier Application Import Wizard.</span></span>  
  
 <span data-ttu-id="e4e7d-151">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="e4e7d-151">**Options**</span></span>  
  
-   <span data-ttu-id="e4e7d-152">**Non visualizzare più questa pagina**</span><span class="sxs-lookup"><span data-stu-id="e4e7d-152">**Do not show this page again.**</span></span> <span data-ttu-id="e4e7d-153">Selezionare la casella di controllo per evitare che la pagina Introduzione venga visualizzata nuovamente in futuro.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-153">- Click the check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="e4e7d-154">**Avanti**: passa alla pagina **Impostazioni di importazione**.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-154">**Next** - Proceeds to the **Import Settings** page.</span></span>  
  
-   <span data-ttu-id="e4e7d-155">**Annulla**: annulla l'operazione e chiude la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-155">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
###  <a name="import-settings-page"></a><a name="Import_settings"></a> <span data-ttu-id="e4e7d-156">Pagina Impostazioni di importazione</span><span class="sxs-lookup"><span data-stu-id="e4e7d-156">Import Settings Page</span></span>  
 <span data-ttu-id="e4e7d-157">Utilizzare questa pagina per specificare il percorso del file con estensione bacpac da importare.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-157">Use this page to specify the location of the .bacpac file to import.</span></span>  
  
-   <span data-ttu-id="e4e7d-158">**Importa da disco locale**: fare clic su **Sfoglia** per selezionare un percorso nel computer locale o specificare il percorso nell'apposito campo.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-158">**Import from local disk** - Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span> <span data-ttu-id="e4e7d-159">Il nome del percorso deve includere un nome file e l'estensione .bacpac.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-159">The path name must include a file name and the .bacpac extension.</span></span>  
  
-   <span data-ttu-id="e4e7d-160">**Importa da Azure** : importa un file BACPAC da un contenitore di Azure.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-160">**Import from Azure** - Imports a BACPAC file from an Azure container.</span></span> <span data-ttu-id="e4e7d-161">È necessario connettersi a un contenitore Azure per convalidare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-161">You must connect to an Azure container in order to validate this option.</span></span> <span data-ttu-id="e4e7d-162">Questa opzione richiede inoltre che si specifichi una directory locale per il file temporaneo.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-162">Note that this option also requires that you specify a local directory for the temporary file.</span></span> <span data-ttu-id="e4e7d-163">Il file temporaneo verrà creato nel percorso specificato, dove rimarrà una volta completata l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-163">The temporary file will be created at the specified location and will remain there after the operation completes.</span></span>  
  
     <span data-ttu-id="e4e7d-164">Quando si esplora Azure, sarà possibile passare tra contenitori all'interno di un solo account.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-164">When browsing Azure, you will be able to switch between containers within a single account.</span></span> <span data-ttu-id="e4e7d-165">È necessario specificare un solo file bacpac per continuare l'operazione di importazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-165">You must specify a single .bacpac file to continue the import operation.</span></span> <span data-ttu-id="e4e7d-166">È possibile ordinare colonne in base a **Nome**, **Dimensioni**o **Data modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-166">Note that you can sort columns by **Name**, **Size**, or **Date Modified**.</span></span>  
  
     <span data-ttu-id="e4e7d-167">Per continuare, specificare il file bacpac da importare, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-167">To continue, specify the .bacpac file to import, and then click **Open**.</span></span>  
  
###  <a name="database-settings-page"></a><a name="Database_settings"></a> <span data-ttu-id="e4e7d-168">Pagina Impostazioni database</span><span class="sxs-lookup"><span data-stu-id="e4e7d-168">Database Settings Page</span></span>  
 <span data-ttu-id="e4e7d-169">Usare questa pagina per specificare i dettagli del database che verrà creato.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-169">Use this page to specify details for the database that will be created.</span></span>  
  
 <span data-ttu-id="e4e7d-170">**Per un'istanza locale di SQL Server:**</span><span class="sxs-lookup"><span data-stu-id="e4e7d-170">**For a local instance of SQL Server:**</span></span>  
  
-   <span data-ttu-id="e4e7d-171">**Nome nuovo database**: specificare un nome per il database importato.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-171">**New database name** - Provide a name for the imported database.</span></span>  
  
-   <span data-ttu-id="e4e7d-172">**Percorso file di dati**: fornire una directory locale per i file di dati.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-172">**Data file path** - Provide a local directory for data files.</span></span> <span data-ttu-id="e4e7d-173">Fare clic su **Sfoglia** per selezionare un percorso nel computer locale oppure specificare il percorso nell'apposito campo.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-173">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span>  
  
-   <span data-ttu-id="e4e7d-174">**Percorso file di log**: specificare una directory locale per i file di log.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-174">**Log file path** - Provide a local directory for log files.</span></span> <span data-ttu-id="e4e7d-175">Fare clic su **Sfoglia** per selezionare un percorso nel computer locale oppure specificare il percorso nell'apposito campo.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-175">Click **Browse...** to navigate the local computer, or specify the path in the space provided.</span></span>  
  
 <span data-ttu-id="e4e7d-176">Scegliere **Avanti**per continuare.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-176">To continue, click **Next**.</span></span>  
  
 <span data-ttu-id="e4e7d-177">**Per un database SQL:**</span><span class="sxs-lookup"><span data-stu-id="e4e7d-177">**For a SQL Database:**</span></span>  
  
-   <span data-ttu-id="e4e7d-178">**Nome nuovo database** : specificare un nome per il database importato.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-178">**New database name** - Provide a name for the imported database.</span></span>  
  
-   <span data-ttu-id="e4e7d-179">\*\*Edizione di [!INCLUDE[ssSDS](../../includes/sssds-md.md)] \*\* -Specificare [!INCLUDE[ssSDS](../../includes/sssds-md.md)] business o [!INCLUDE[ssSDS](../../includes/sssds-md.md)] Web.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-179">**Edition of [!INCLUDE[ssSDS](../../includes/sssds-md.md)]** - Specify [!INCLUDE[ssSDS](../../includes/sssds-md.md)] Business or [!INCLUDE[ssSDS](../../includes/sssds-md.md)] Web.</span></span> <span data-ttu-id="e4e7d-180">Per altre informazioni sulle edizioni di [!INCLUDE[ssSDS](../../includes/sssds-md.md)], visitare il sito Web relativo al [database SQL](https://www.windowsazure.com/home/tour/database/) .</span><span class="sxs-lookup"><span data-stu-id="e4e7d-180">For more information about editions of [!INCLUDE[ssSDS](../../includes/sssds-md.md)], see this [SQL Database](https://www.windowsazure.com/home/tour/database/) web site.</span></span>  
  
-   <span data-ttu-id="e4e7d-181">**Dimensioni massime database (GB)** : usare il menu a discesa per specificare le dimensioni massime del database.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-181">**Maximum database size (GB)** - Use the drop-down menu to specify the maximum size for your database.</span></span>  
  
 <span data-ttu-id="e4e7d-182">Scegliere **Avanti**per continuare.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-182">To continue, click **Next**.</span></span>  
  
### <a name="validation-page"></a><span data-ttu-id="e4e7d-183">Pagina Convalida</span><span class="sxs-lookup"><span data-stu-id="e4e7d-183">Validation Page</span></span>  
 <span data-ttu-id="e4e7d-184">Usare questa pagina per esaminare gli eventuali problemi che impediscono l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-184">Use this page to review any issues that block the operation.</span></span> <span data-ttu-id="e4e7d-185">Per continuare, risolvere i problemi che causano il blocco, quindi fare clic su **Ripeti convalida** per assicurarsi che la convalida venga completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-185">To continue, resolve blocking issues and then click **Re-run Validation** to ensure that validation is successful.</span></span>  
  
 <span data-ttu-id="e4e7d-186">Scegliere **Avanti**per continuare.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-186">To continue, click **Next**.</span></span>  
  
###  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="e4e7d-187">Pagina Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e4e7d-187">Summary Page</span></span>  
 <span data-ttu-id="e4e7d-188">Utilizzare questa pagina per esaminare le impostazioni di origine e destinazione specificate per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-188">Use this page to review the specified source and target settings for the operation.</span></span> <span data-ttu-id="e4e7d-189">Per completare l'operazione di importazione utilizzando le impostazioni specificate, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-189">To complete the import operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="e4e7d-190">Per annullare l'operazione di importazione e chiudere la procedura guidata, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-190">To cancel the import operation and exit the wizard, click **Cancel**.</span></span>  
  
###  <a name="progress-page"></a><a name="Progress"></a> <span data-ttu-id="e4e7d-191">Pagina Stato</span><span class="sxs-lookup"><span data-stu-id="e4e7d-191">Progress Page</span></span>  
 <span data-ttu-id="e4e7d-192">In questa pagina viene visualizzato un indicatore di stato che indica lo stato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-192">This page displays a progress bar that indicates the status of the operation.</span></span> <span data-ttu-id="e4e7d-193">Per visualizzare lo stato dettagliato, fare clic sull'opzione **Visualizza dettagli** .</span><span class="sxs-lookup"><span data-stu-id="e4e7d-193">To view detailed status, click the **View details** option.</span></span>  
  
 <span data-ttu-id="e4e7d-194">Scegliere **Avanti**per continuare.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-194">To continue, click **Next**.</span></span>  
  
###  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="e4e7d-195">Pagina dei risultati</span><span class="sxs-lookup"><span data-stu-id="e4e7d-195">Results Page</span></span>  
 <span data-ttu-id="e4e7d-196">In questa pagina viene riportato l'esito positivo o negativo delle operazioni di impostazione e creazione del database, con l'indicazione dei risultati positivi o negativi di ogni azione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-196">This page reports the success or failure of the import and create database operations, showing the success or failure of each action.</span></span> <span data-ttu-id="e4e7d-197">Ogni azione che ha rilevato un errore avrà un collegamento nella colonna **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="e4e7d-197">Any action that encountered an error will have a link in the **Result** column.</span></span> <span data-ttu-id="e4e7d-198">Fare clic sul collegamento per visualizzare un report dell'errore relativo all'azione.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-198">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="e4e7d-199">Fare clic su **Chiudi** per uscire dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e4e7d-199">Click **Close** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e7d-200">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4e7d-200">See Also</span></span>  
 <span data-ttu-id="e4e7d-201">[Applicazioni livello dati](data-tier-applications.md) </span><span class="sxs-lookup"><span data-stu-id="e4e7d-201">[Data-tier Applications](data-tier-applications.md) </span></span>  
 [<span data-ttu-id="e4e7d-202">Esportazione di un'applicazione livello dati</span><span class="sxs-lookup"><span data-stu-id="e4e7d-202">Export a Data-tier Application</span></span>](export-a-data-tier-application.md)  
  