---
title: Abilitare e disabilitare la funzionalità Report personali | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deactivated My Reports folder
- folders [Reporting Services], My Reports
- activated My Reports folder
- My Reports folder [Reporting Services]
- disabling My Reports folder
ms.assetid: 16c76e82-9fd4-417c-9ed3-a7d5bcd1dba2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ef9b48744365b981d11b0e5ae20dc654f2d131d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630287"
---
# <a name="enable-and-disable-my-reports"></a><span data-ttu-id="73bdc-102">Abilitare e disabilitare la funzionalità Report personali</span><span class="sxs-lookup"><span data-stu-id="73bdc-102">Enable and Disable My Reports</span></span>
  <span data-ttu-id="73bdc-103">La caratteristica Report personali consente di assegnare spazio di archiviazione personale nel database del server di report. Gli utenti possono servirsi di tale spazio di archiviazione per salvare i propri report in una cartella privata.</span><span class="sxs-lookup"><span data-stu-id="73bdc-103">The My Reports feature allocates personal storage in the report server database so that users can save reports that they own in a private folder.</span></span> <span data-ttu-id="73bdc-104">L'amministratore del server di report può attivare o disabilitare questa caratteristica oppure modificarne il funzionamento cambiando le impostazioni di sicurezza che determinano i vari tipi di operazioni che gli utenti possono eseguire in questa area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="73bdc-104">As a report server administrator, you can enable or disable this feature or change how the feature works by modifying the security settings that control what users can do with this workspace.</span></span>  
  
 <span data-ttu-id="73bdc-105">La caratteristica Report personali è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="73bdc-105">The My Reports feature is disabled by default.</span></span> <span data-ttu-id="73bdc-106">È possibile abilitarla o disabilitarla per tutti gli utenti, ma non solo per alcuni.</span><span class="sxs-lookup"><span data-stu-id="73bdc-106">You can either enable or disable the feature for all users, but you cannot enable it for a subset of users.</span></span> <span data-ttu-id="73bdc-107">Questa caratteristica può rivelarsi utile per la maggior parte degli utenti e delle organizzazioni. Tuttavia, per verificare se è adatta alla propria organizzazione, è consigliabile analizzarne i vantaggi e gli svantaggi illustrati più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="73bdc-107">Most users and organizations find this feature valuable; study the advantages and disadvantages presented later in this topic to determine whether it is a good fit for your organization.</span></span>  
  
## <a name="how-to-enable-and-disable-my-reports"></a><span data-ttu-id="73bdc-108">Come abilitare e disabilitare la funzionalità Report personali</span><span class="sxs-lookup"><span data-stu-id="73bdc-108">How to Enable and Disable My Reports</span></span>  
 <span data-ttu-id="73bdc-109">Per abilitare Report personali tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connettersi all'istanza del server di report e aprire la pagina **Proprietà server** .</span><span class="sxs-lookup"><span data-stu-id="73bdc-109">To enable My Reports by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the report server instance and open the **Server Properties** page.</span></span> <span data-ttu-id="73bdc-110">Quindi, nella scheda **Generale** selezionare l'opzione **Abilita una cartella Report personali per ogni utente** .</span><span class="sxs-lookup"><span data-stu-id="73bdc-110">Then on the **General** tab, select the **Enable a My Reports folder for each user** option.</span></span>  
  
 <span data-ttu-id="73bdc-111">La definizione di ruolo utilizzata per la funzionalità Report personali determina le azioni supportate nell'area di lavoro Report personali.</span><span class="sxs-lookup"><span data-stu-id="73bdc-111">The role definition used for My Reports determines what actions are supported in the My Reports workspace.</span></span> <span data-ttu-id="73bdc-112">Ad esempio, se per il ruolo Report personali non viene selezionata l'attività "Creazione di report collegati", gli utenti appartenenti a questo ruolo non potranno creare report collegati nelle cartelle Report personali.</span><span class="sxs-lookup"><span data-stu-id="73bdc-112">For example, if the My Reports role excludes "Create linked reports," users cannot create linked reports in the My Reports folders.</span></span> <span data-ttu-id="73bdc-113">Per altre informazioni, vedere [Proteggere i report personali](../security/secure-my-reports.md).</span><span class="sxs-lookup"><span data-stu-id="73bdc-113">For more information, see [Secure My Reports](../security/secure-my-reports.md).</span></span>  
  
 <span data-ttu-id="73bdc-114">Per disattivare Report personali, deselezionare **Abilita una cartella Report personali per ogni utente**.</span><span class="sxs-lookup"><span data-stu-id="73bdc-114">To deactivate My Reports, clear **Enable a My Reports folder for each user**.</span></span> <span data-ttu-id="73bdc-115">Se si disattiva la funzionalità Report personali, per gli utenti non verrà più visualizzato alcun riferimento alla cartella Report personali.</span><span class="sxs-lookup"><span data-stu-id="73bdc-115">Deactivating My Reports removes for users all visible indications of the My Reports folder.</span></span> <span data-ttu-id="73bdc-116">Le cartelle in cui sono effettivamente archiviati i dati, ovvero le sottocartelle di Cartelle utenti, devono essere eliminate manualmente dopo la disabilitazione della caratteristica.</span><span class="sxs-lookup"><span data-stu-id="73bdc-116">The folders that provide actual storage (that is, the subfolders in Users Folders) must be deleted manually once the feature is disabled.</span></span>  
  
### <a name="when-my-reports-is-activated"></a><span data-ttu-id="73bdc-117">Quando la funzionalità Report personali è attivata</span><span class="sxs-lookup"><span data-stu-id="73bdc-117">When My Reports Is Activated</span></span>  
 <span data-ttu-id="73bdc-118">Quando questa caratteristica è attivata, per gli utenti viene visualizzata la cartella Report personali al di sotto della cartella radice Home.</span><span class="sxs-lookup"><span data-stu-id="73bdc-118">Once the feature is activated, users see a My Reports folder located under the root folder, Home.</span></span> <span data-ttu-id="73bdc-119">Oltre alla cartella Report personali, per gli amministratori del server di report verrà visualizzata la cartella Cartelle utenti contenente una sottocartella per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="73bdc-119">In addition to a My Reports folder, report server administrators also see a Users Folders folder that contains the subfolder for each user.</span></span>  
  
 <span data-ttu-id="73bdc-120">Quando questa caratteristica è attivata, non è possibile eliminare Cartelle utenti e le relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="73bdc-120">While the feature is activated, Users Folders and its subfolders cannot be deleted.</span></span> <span data-ttu-id="73bdc-121">Inoltre, "Report personali" diventa un nome riservato per le cartelle create sotto il nodo radice (Home).</span><span class="sxs-lookup"><span data-stu-id="73bdc-121">Furthermore, the name "My Reports" becomes a reserved name for folders created under the root node (Home).</span></span>  
  
 <span data-ttu-id="73bdc-122">Se si attiva la funzionalità Report personali dopo averla disattivata, verrà creata automaticamente una nuova cartella Cartelle utenti se tale cartella non esiste già.</span><span class="sxs-lookup"><span data-stu-id="73bdc-122">If you activate My Reports after it has been deactivated, the report server creates a new Users Folders folder if one does not already exist.</span></span> <span data-ttu-id="73bdc-123">Se tale cartella esiste, verrà creata automaticamente una nuova sottocartella per ogni utente che accederà alla cartella Report personali.</span><span class="sxs-lookup"><span data-stu-id="73bdc-123">If Users Folders exists, the report server adds new subfolders as users log on to their My Reports folders.</span></span>  
  
### <a name="when-my-reports-is-deactivated"></a><span data-ttu-id="73bdc-124">Quando la funzionalità Report personali è disattivata</span><span class="sxs-lookup"><span data-stu-id="73bdc-124">When My Reports Is Deactivated</span></span>  
 <span data-ttu-id="73bdc-125">Quando questa caratteristica è disattivata, il nome "Report personali" non è più riservato, pertanto gli utenti possono creare una cartella personale denominata Report personali nella cartella Home.</span><span class="sxs-lookup"><span data-stu-id="73bdc-125">Once the feature is deactivated, the name "My Reports" is no longer reserved; users can create a personal folder named My Reports under the Home folder.</span></span> <span data-ttu-id="73bdc-126">Inoltre, non viene più eseguito il reindirizzamento da Report personali alle sottocartelle Report personali specifiche dell'utente.</span><span class="sxs-lookup"><span data-stu-id="73bdc-126">In addition, redirection from My Reports to user-specific My Reports subfolders is no longer performed.</span></span> <span data-ttu-id="73bdc-127">Infine, non funzioneranno più tutti i collegamenti che includono una cartella Report personali specifica dell'utente nell'indirizzo URL.</span><span class="sxs-lookup"><span data-stu-id="73bdc-127">Lastly, any report links that include a user-specific My Reports folder in the URL address will no longer work.</span></span>  
  
## <a name="choosing-to-use-my-reports"></a><span data-ttu-id="73bdc-128">Vantaggi e svantaggi della funzionalità Report personali</span><span class="sxs-lookup"><span data-stu-id="73bdc-128">Choosing to Use My Reports</span></span>  
 <span data-ttu-id="73bdc-129">Prima di decidere se utilizzare o meno la funzionalità Report personali, è necessario stabilire se dedicare risorse del server all'area di lavoro degli utenti.</span><span class="sxs-lookup"><span data-stu-id="73bdc-129">Deciding whether to use My Reports depends on whether you want to dedicate server resources to support a user workspace.</span></span> <span data-ttu-id="73bdc-130">Report personali è una potente caratteristica che consente agli utenti di disporre di informazioni che permettono loro di eseguire le attività lavorative in modo più semplice.</span><span class="sxs-lookup"><span data-stu-id="73bdc-130">My Reports is a powerful feature that allows users to have control over information resources that help them do their jobs.</span></span> <span data-ttu-id="73bdc-131">Consente inoltre di gestire report che non sono stati creati per un utilizzo generico.</span><span class="sxs-lookup"><span data-stu-id="73bdc-131">It also provides a way for users to work with reports that are not intended for general use.</span></span> <span data-ttu-id="73bdc-132">Uno dei motivi più importanti per utilizzare la funzionalità Report personali è rappresentato dal fatto che offre caratteristiche di sicurezza e semplicità di gestione agli utenti che progettano e modificano i report.</span><span class="sxs-lookup"><span data-stu-id="73bdc-132">One of the most compelling reasons to use My Reports is that it provides secure, manageable support for the segment of users who need to author and review reports.</span></span> <span data-ttu-id="73bdc-133">Senza questa caratteristica, potrebbe essere necessario creare cartelle e criteri di sicurezza per diversi utenti in base alle necessità specifiche.</span><span class="sxs-lookup"><span data-stu-id="73bdc-133">Without this feature, you may find yourself creating folders and security policies for various users on an ad hoc basis.</span></span> <span data-ttu-id="73bdc-134">Se cambiano gli utenti e le loro esigenze, la quantità di cartelle e di criteri di sicurezza aumenta di conseguenza e ciò può determinare difficoltà di gestione.</span><span class="sxs-lookup"><span data-stu-id="73bdc-134">As users and user needs change, this approach results in ever-increasing numbers of folders and policies that are difficult to maintain over time.</span></span>  
  
 <span data-ttu-id="73bdc-135">Si noti che, se si attiva la funzionalità Report personali, viene creata automaticamente una cartella Report personali per ogni utente con account di dominio che fa clic sul collegamento Report personali, anche se tale utente non desidera o non necessita di una cartella Report personali.</span><span class="sxs-lookup"><span data-stu-id="73bdc-135">Note that if you do activate My Reports, the report server creates a My Reports folder for every user with a domain account who clicks the My Reports link, even if the user does not want or need a My Reports folder.</span></span> <span data-ttu-id="73bdc-136">Non esiste una soluzione per determinare quali cartelle sono in uso.</span><span class="sxs-lookup"><span data-stu-id="73bdc-136">There is no systematic way to determine which folders are being used.</span></span> <span data-ttu-id="73bdc-137">È necessario controllare le cartelle manualmente per verificare se contengono dati.</span><span class="sxs-lookup"><span data-stu-id="73bdc-137">You must review the folders manually to see whether they contain anything.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bdc-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73bdc-138">See Also</span></span>  
 <span data-ttu-id="73bdc-139">[Protezione dei report](../security/secure-my-reports.md) </span><span class="sxs-lookup"><span data-stu-id="73bdc-139">[Secure My Reports](../security/secure-my-reports.md) </span></span>  
 [<span data-ttu-id="73bdc-140">Gestione contenuto del server di report &#40;modalità nativa SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="73bdc-140">Report Server Content Management &#40;SSRS Native Mode&#41;</span></span>](report-server-content-management-ssrs-native-mode.md)  
  
  