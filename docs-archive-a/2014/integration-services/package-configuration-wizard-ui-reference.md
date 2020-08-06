---
title: Guida di riferimento all'interfaccia utente della configurazione guidata pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.configwizard.selectobjects.f1
- sql12.dts.configwizard.selecconfigtype.f1
- sql12.dts.configwizard.finishdtsconfiguration.f1
- sql12.dts.configwizard.welcome.f1
ms.assetid: adca6938-6d5a-40ec-950e-dceb79d044fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 222c5f58ca4e942dd23909b433ab346c500fceed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636795"
---
# <a name="package-configuration-wizard-ui-reference"></a><span data-ttu-id="8aca9-102">Riferimento all'interfaccia utente della Configurazione guidata pacchetti</span><span class="sxs-lookup"><span data-stu-id="8aca9-102">Package Configuration Wizard UI Reference</span></span>
  <span data-ttu-id="8aca9-103">Usare la **Configurazione guidata pacchetto** per creare configurazioni tramite cui è possibile aggiornare le proprietà di un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e i relativi oggetti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-103">Use the **Package Configuration Wizard** to create configurations that update the properties of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and its objects at run time.</span></span> <span data-ttu-id="8aca9-104">Questa procedura guidata viene eseguita quando si aggiunge una nuova configurazione o se ne modifica una esistente nella finestra di dialogo **Libreria configurazioni pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="8aca9-104">This wizard runs when you add a new configuration or modify an existing one in the **Package Configurations Organizer** dialog box.</span></span> <span data-ttu-id="8aca9-105">Per aprire la finestra di dialogo **Libreria configurazioni pacchetto** , selezionare **Configurazioni pacchetto** nel menu **SSIS** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aca9-105">To open the **Package Configurations Organizer** dialog box, select **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="8aca9-106">Per altre informazioni, vedere [Creazione di configurazioni dei pacchetti](../../2014/integration-services/create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="8aca9-106">For more information, see [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8aca9-107">Le configurazioni sono disponibili per il modello di distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8aca9-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="8aca9-108">I parametri vengono utilizzati al posto delle configurazioni per il modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8aca9-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="8aca9-109">Con il modello di distribuzione del progetto è possibile distribuire i progetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8aca9-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="8aca9-110">Per altre informazioni sui modelli di distribuzione, vedere [Distribuzione di progetti e pacchetti](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="8aca9-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="8aca9-111">Nelle sezioni seguenti vengono descritte le pagine della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-111">The following sections describe pages of the Wizard.</span></span>  
  
## <a name="welcome-to-the-package-configuration-wizard-page"></a><span data-ttu-id="8aca9-112">Pagina della Configurazione guidata pacchetto</span><span class="sxs-lookup"><span data-stu-id="8aca9-112">Welcome to the Package Configuration Wizard Page</span></span>  
 <span data-ttu-id="8aca9-113">Usare la **Configurazione guidata SSIS** per creare configurazioni in grado di aggiornare le proprietà di un pacchetto e i relativi oggetti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-113">Use the **SSIS Configuration Wizard** to create configurations that update the properties of a package and its objects at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="8aca9-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8aca9-114">Options</span></span>  
 <span data-ttu-id="8aca9-115">**Non visualizzare più questa pagina**</span><span class="sxs-lookup"><span data-stu-id="8aca9-115">**Don't show this page again**</span></span>  
 <span data-ttu-id="8aca9-116">Consente di evitare la visualizzazione della pagina di benvenuto alla successiva apertura della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-116">Skip the welcome page the next time you open the wizard.</span></span>  
  
 <span data-ttu-id="8aca9-117">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="8aca9-117">**Next**</span></span>  
 <span data-ttu-id="8aca9-118">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-118">Go the next page in the wizard.</span></span>  
  
## <a name="select-configuration-type-page"></a><span data-ttu-id="8aca9-119">Pagina Selezione tipo di configurazione</span><span class="sxs-lookup"><span data-stu-id="8aca9-119">Select Configuration Type Page</span></span>  
 <span data-ttu-id="8aca9-120">Usare la pagina **Selezione tipo di configurazione** per specificare il tipo di configurazione da creare.</span><span class="sxs-lookup"><span data-stu-id="8aca9-120">Use the **Select Configuration Type** page to specify the type of configuration to create.</span></span>  
  
 <span data-ttu-id="8aca9-121">Per altre informazioni sulla selezione del tipo di configurazione da usare, vedere [Configurazioni di pacchetto](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="8aca9-121">If you need additional information to determine which type of configuration to use, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="8aca9-122">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="8aca9-122">Static Options</span></span>  
 <span data-ttu-id="8aca9-123">**Tipo configurazione**</span><span class="sxs-lookup"><span data-stu-id="8aca9-123">**Configuration type**</span></span>  
 <span data-ttu-id="8aca9-124">Selezionare una delle opzioni seguenti per impostare il tipo di origine in cui archiviare la configurazione:</span><span class="sxs-lookup"><span data-stu-id="8aca9-124">Select the type of source in which to store the configuration, using the following options:</span></span>  
  
|<span data-ttu-id="8aca9-125">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-125">Value</span></span>|<span data-ttu-id="8aca9-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-127">**File di configurazione XML**</span><span class="sxs-lookup"><span data-stu-id="8aca9-127">**XML configuration file**</span></span>|<span data-ttu-id="8aca9-128">Consente di archiviare la configurazione come file in formato XML.</span><span class="sxs-lookup"><span data-stu-id="8aca9-128">Store the configuration as an XML file.</span></span> <span data-ttu-id="8aca9-129">Tramite la selezione di questo valore le opzioni dinamiche vengono visualizzate nella sezione **Tipo configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8aca9-129">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="8aca9-130">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-130">**Environment variable**</span></span>|<span data-ttu-id="8aca9-131">Consente di archiviare la configurazione in una delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8aca9-131">Store the configuration in one of the environment variables.</span></span> <span data-ttu-id="8aca9-132">Tramite la selezione di questo valore le opzioni dinamiche vengono visualizzate nella sezione **Tipo configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8aca9-132">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="8aca9-133">**Voce del Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="8aca9-133">**Registry entry**</span></span>|<span data-ttu-id="8aca9-134">Consente di archiviare la configurazione nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="8aca9-134">Store the configuration in the Registry.</span></span> <span data-ttu-id="8aca9-135">Tramite la selezione di questo valore le opzioni dinamiche vengono visualizzate nella sezione **Tipo configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8aca9-135">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="8aca9-136">**Variabile pacchetto padre**</span><span class="sxs-lookup"><span data-stu-id="8aca9-136">**Parent package variable**</span></span>|<span data-ttu-id="8aca9-137">Consente di archiviare la configurazione come variabile nel pacchetto contenente l'attività.</span><span class="sxs-lookup"><span data-stu-id="8aca9-137">Store the configuration as a variable in the package that contains the task.</span></span>  <span data-ttu-id="8aca9-138">Tramite la selezione di questo valore le opzioni dinamiche vengono visualizzate nella sezione **Tipo configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8aca9-138">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="8aca9-139">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8aca9-139">**SQL Server**</span></span>|<span data-ttu-id="8aca9-140">Consente di archiviare la configurazione in una tabella in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aca9-140">Store the configuration in a table in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8aca9-141">Tramite la selezione di questo valore le opzioni dinamiche vengono visualizzate nella sezione **Tipo configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8aca9-141">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
  
 <span data-ttu-id="8aca9-142">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="8aca9-142">**Next**</span></span>  
 <span data-ttu-id="8aca9-143">Consente di visualizzare la pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-143">View the next page in the wizard sequence.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="8aca9-144">Opzioni dinamiche</span><span class="sxs-lookup"><span data-stu-id="8aca9-144">Dynamic Options</span></span>  
  
#### <a name="configuration-type-option--xml-configuration-file"></a><span data-ttu-id="8aca9-145">Opzione tipo di configurazione = File di configurazione XML</span><span class="sxs-lookup"><span data-stu-id="8aca9-145">Configuration Type Option = XML Configuration File</span></span>  
 <span data-ttu-id="8aca9-146">**Usa le impostazioni di configurazione specificate di seguito**</span><span class="sxs-lookup"><span data-stu-id="8aca9-146">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="8aca9-147">Consente di specificare le impostazioni da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8aca9-147">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="8aca9-148">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-148">Value</span></span>|<span data-ttu-id="8aca9-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-150">**Nome file di configurazione**</span><span class="sxs-lookup"><span data-stu-id="8aca9-150">**Configuration file name**</span></span>|<span data-ttu-id="8aca9-151">Consente di digitare il percorso del file di configurazione generato dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-151">Type the path of the configuration file that the wizard generates.</span></span>|  
|<span data-ttu-id="8aca9-152">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="8aca9-152">**Browse**</span></span>|<span data-ttu-id="8aca9-153">Usare la finestra di dialogo **Selezionare il percorso del file di configurazione** per impostare il percorso del file di configurazione generato dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-153">Use the **Select Configuration File Location** dialog box to specify the path of the configuration file that the wizard generates.</span></span> <span data-ttu-id="8aca9-154">Se il file non esiste, verrà creato durante la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-154">If the file does not exist, it is created by the wizard.</span></span>|  
  
 <span data-ttu-id="8aca9-155">**Percorso della configurazione memorizzato in una variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-155">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="8aca9-156">Consente di specificare la variabile di ambiente in cui memorizzare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-156">Use to specify the environment variable in which to store the configuration.</span></span>  
  
|<span data-ttu-id="8aca9-157">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-157">Value</span></span>|<span data-ttu-id="8aca9-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-158">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-159">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-159">**Environment variable**</span></span>|<span data-ttu-id="8aca9-160">Consente di selezionare una variabile di ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8aca9-160">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--environment-variable"></a><span data-ttu-id="8aca9-161">Opzione tipo di configurazione = Variabile di ambiente</span><span class="sxs-lookup"><span data-stu-id="8aca9-161">Configuration Type Option = Environment Variable</span></span>  
 <span data-ttu-id="8aca9-162">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-162">**Environment variable**</span></span>  
 <span data-ttu-id="8aca9-163">Consente di selezionare la variabile di ambiente contenente le informazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-163">Select the environment variable that contains the configuration information.</span></span>  
  
#### <a name="configuration-type-option--registry-entry"></a><span data-ttu-id="8aca9-164">Opzione tipo di configurazione = Voce del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="8aca9-164">Configuration Type Option = Registry Entry</span></span>  
 <span data-ttu-id="8aca9-165">**Usa le impostazioni di configurazione specificate di seguito**</span><span class="sxs-lookup"><span data-stu-id="8aca9-165">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="8aca9-166">Consente di specificare le impostazioni da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8aca9-166">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="8aca9-167">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-167">Value</span></span>|<span data-ttu-id="8aca9-168">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-169">**Voce del Registro di sistema**</span><span class="sxs-lookup"><span data-stu-id="8aca9-169">**Registry entry**</span></span>|<span data-ttu-id="8aca9-170">Digitare la chiave del Registro di sistema contenente le informazioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="8aca9-170">Type the Registry key that contains the configuration information.</span></span> <span data-ttu-id="8aca9-171">Il formato è \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="8aca9-171">The format is \<registry key>.</span></span><br /><br /> <span data-ttu-id="8aca9-172">È necessario che la chiave del Registro di sistema esista già in HKEY_CURRENT_USER e che il suo valore sia denominato Value.</span><span class="sxs-lookup"><span data-stu-id="8aca9-172">The Registry key must already exist in HKEY_CURRENT_USER and have a value named Value.</span></span> <span data-ttu-id="8aca9-173">Il valore può essere un DWORD o una stringa.</span><span class="sxs-lookup"><span data-stu-id="8aca9-173">The value can be a DWORD or a string.</span></span><br /><br /> <span data-ttu-id="8aca9-174">Se si vuole usare una chiave del Registro di sistema che non si trova nella radice HKEY_CURRENT_USER, per identificare la chiave usare il formato \<Registry key\registry key\\...>.</span><span class="sxs-lookup"><span data-stu-id="8aca9-174">If you want to use a Registry key is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span>|  
  
 <span data-ttu-id="8aca9-175">**Percorso della configurazione memorizzato in una variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-175">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="8aca9-176">Consente di specificare la variabile di ambiente in cui memorizzare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-176">Use to specify the environment variable to store the configuration in.</span></span>  
  
|<span data-ttu-id="8aca9-177">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-177">Value</span></span>|<span data-ttu-id="8aca9-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-179">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-179">**Environment variable**</span></span>|<span data-ttu-id="8aca9-180">Consente di selezionare una variabile di ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8aca9-180">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--parent-package-variable"></a><span data-ttu-id="8aca9-181">Opzione tipo di configurazione = Variabile pacchetto padre</span><span class="sxs-lookup"><span data-stu-id="8aca9-181">Configuration Type Option = Parent Package Variable</span></span>  
 <span data-ttu-id="8aca9-182">**Usa le impostazioni di configurazione specificate di seguito**</span><span class="sxs-lookup"><span data-stu-id="8aca9-182">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="8aca9-183">Consente di specificare le impostazioni da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8aca9-183">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="8aca9-184">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-184">Value</span></span>|<span data-ttu-id="8aca9-185">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-185">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-186">**Variabile padre**</span><span class="sxs-lookup"><span data-stu-id="8aca9-186">**Parent variable**</span></span>|<span data-ttu-id="8aca9-187">Consente di specificare la variabile inclusa nel pacchetto padre contenente le informazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-187">Specify the variable in the parent package that contains the configuration information.</span></span>|  
  
 <span data-ttu-id="8aca9-188">**Percorso della configurazione memorizzato in una variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-188">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="8aca9-189">Consente di specificare la variabile di ambiente in cui viene memorizzata la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-189">Use to specify the environment variable that stores the configuration.</span></span>  
  
|<span data-ttu-id="8aca9-190">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-190">Value</span></span>|<span data-ttu-id="8aca9-191">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-191">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-192">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-192">**Environment variable**</span></span>|<span data-ttu-id="8aca9-193">Consente di selezionare una variabile di ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8aca9-193">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-options--sql-server"></a><span data-ttu-id="8aca9-194">Opzione tipo di configurazione = SQL Server</span><span class="sxs-lookup"><span data-stu-id="8aca9-194">Configuration Type Options = SQL Server</span></span>  
 <span data-ttu-id="8aca9-195">**Usa le impostazioni di configurazione specificate di seguito**</span><span class="sxs-lookup"><span data-stu-id="8aca9-195">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="8aca9-196">Consente di specificare le impostazioni da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8aca9-196">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="8aca9-197">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-197">Value</span></span>|<span data-ttu-id="8aca9-198">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-198">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-199">**Connection**</span><span class="sxs-lookup"><span data-stu-id="8aca9-199">**Connection**</span></span>|<span data-ttu-id="8aca9-200">Consente di selezionare una connessione nell'elenco o di creare una nuova connessione facendo clic su **Nuova** .</span><span class="sxs-lookup"><span data-stu-id="8aca9-200">Select a connection from the list, or click **New** to create a new connection.</span></span>|  
|<span data-ttu-id="8aca9-201">**Tabella configurazione**</span><span class="sxs-lookup"><span data-stu-id="8aca9-201">**Configuration table**</span></span>|<span data-ttu-id="8aca9-202">Consente di selezionare una tabella esistente o di creare una nuova tabella facendo clic su **Nuova** per scrivere un'apposita istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="8aca9-202">Select an existing table, or click **New** to write a SQL statement that creates a new table.</span></span>|  
|<span data-ttu-id="8aca9-203">**Filtro configurazione**</span><span class="sxs-lookup"><span data-stu-id="8aca9-203">**Configuration filter**</span></span>|<span data-ttu-id="8aca9-204">Consente di selezionare un nome esistente o di digitarne uno nuovo per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-204">Select an existing configuration name or type a new name.</span></span><br /><br /> <span data-ttu-id="8aca9-205">È possibile memorizzare nella stessa tabella molteplici configurazioni di SQL Server, ciascuna delle quali può includere più elementi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-205">Many SQL Server configurations can be stored in the same table, and each configuration can include multiple configuration items.</span></span><br /><br /> <span data-ttu-id="8aca9-206">Questo valore definito dall'utente è memorizzato nella tabella per identificare gli elementi della configurazione appartenenti a una configurazione specifica.</span><span class="sxs-lookup"><span data-stu-id="8aca9-206">This user-defined value is stored in the table to identify configuration items that belong to a particular configuration</span></span>|  
  
 <span data-ttu-id="8aca9-207">**Percorso della configurazione memorizzato in una variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-207">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="8aca9-208">Consente di specificare la variabile di ambiente in cui è memorizzata la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-208">Use to specify the environment variable where the configuration is stored.</span></span>  
  
|<span data-ttu-id="8aca9-209">valore</span><span class="sxs-lookup"><span data-stu-id="8aca9-209">Value</span></span>|<span data-ttu-id="8aca9-210">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aca9-210">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8aca9-211">**Variabile di ambiente**</span><span class="sxs-lookup"><span data-stu-id="8aca9-211">**Environment variable**</span></span>|<span data-ttu-id="8aca9-212">Consente di selezionare una variabile di ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8aca9-212">Select an environment variable from the list.</span></span>|  
  
## <a name="select-objects-to-export-page"></a><span data-ttu-id="8aca9-213">Pagina Selezione oggetti da esportare</span><span class="sxs-lookup"><span data-stu-id="8aca9-213">Select Objects to Export Page</span></span>  
 <span data-ttu-id="8aca9-214">Usare la pagina **Selezione proprietà di destinazione o Selezione proprietà da esportare** per specificare le proprietà degli oggetti incluse nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-214">Use the **Select Target Property or Select Properties to Export** page to specify the object properties that the configuration contains.</span></span> <span data-ttu-id="8aca9-215">La possibilità di selezionare più impostazioni è disponibile solo se si seleziona il tipo di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="8aca9-215">The ability to select multiple properties is available only if you select the XML configuration type.</span></span>  
  
### <a name="options"></a><span data-ttu-id="8aca9-216">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8aca9-216">Options</span></span>  
 <span data-ttu-id="8aca9-217">**Oggetti**</span><span class="sxs-lookup"><span data-stu-id="8aca9-217">**Objects**</span></span>  
 <span data-ttu-id="8aca9-218">Consente di espandere la gerarchia del pacchetto e di selezionare le proprietà da esportare.</span><span class="sxs-lookup"><span data-stu-id="8aca9-218">Expand the package hierarchy and select the properties to export.</span></span>  
  
 <span data-ttu-id="8aca9-219">**Attributi proprietà**</span><span class="sxs-lookup"><span data-stu-id="8aca9-219">**Property attributes**</span></span>  
 <span data-ttu-id="8aca9-220">Consente di visualizzare gli attributi di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="8aca9-220">View the attributes of a property.</span></span>  
  
 <span data-ttu-id="8aca9-221">**Avanti**</span><span class="sxs-lookup"><span data-stu-id="8aca9-221">**Next**</span></span>  
 <span data-ttu-id="8aca9-222">Consente di passare alla pagina successiva della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="8aca9-222">Go to the next page in the wizard.</span></span>  
  
## <a name="completing-the-wizard-page"></a><span data-ttu-id="8aca9-223">Pagina Completamento procedura guidata</span><span class="sxs-lookup"><span data-stu-id="8aca9-223">Completing the Wizard Page</span></span>  
 <span data-ttu-id="8aca9-224">La pagina **Completamento procedura guidata** consente di assegnare un nome per le impostazioni di configurazione e visualizzazione usate dalla procedura guidata per creare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-224">Use the **Completing the Wizard** page to provide a name for the configuration and view settings used by the wizard to create the configuration.</span></span> <span data-ttu-id="8aca9-225">Dopo il completamento della procedura guidata, verrà visualizzato **Libreria configurazioni pacchetto** in cui sono elencate tutte le configurazioni per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8aca9-225">After the wizard completes, the **Package Configurations Organizer** is displayed, which lists all configurations for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="8aca9-226">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8aca9-226">Options</span></span>  
 <span data-ttu-id="8aca9-227">**Nome configurazione**</span><span class="sxs-lookup"><span data-stu-id="8aca9-227">**Configuration name**</span></span>  
 <span data-ttu-id="8aca9-228">Consente di digitare il nome della configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-228">Type the name of the configuration.</span></span>  
  
 <span data-ttu-id="8aca9-229">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="8aca9-229">**Preview**</span></span>  
 <span data-ttu-id="8aca9-230">Consente di visualizzare le impostazioni utilizzate dalla procedura guidata per creare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="8aca9-230">View the settings used by the wizard to create the configuration.</span></span>  
  
 <span data-ttu-id="8aca9-231">**Fine**</span><span class="sxs-lookup"><span data-stu-id="8aca9-231">**Finish**</span></span>  
 <span data-ttu-id="8aca9-232">Consente di creare la configurazione e uscire dalla **Configurazione guidata pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="8aca9-232">Create the configuration and exit the **Package Configuration Wizard**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aca9-233">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8aca9-233">See Also</span></span>  
 [<span data-ttu-id="8aca9-234">Creazione di configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="8aca9-234">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  