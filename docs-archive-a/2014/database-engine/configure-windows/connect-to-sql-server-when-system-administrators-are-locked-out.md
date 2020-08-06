---
title: Connettersi a SQL Server se gli amministratori di sistema sono bloccati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- connecting when locked out [SQL Server]
- locked out [SQL Server]
ms.assetid: c0c0082e-b867-480f-a54b-79f2a94ceb67
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 47b9659943e51a2d31a2354740660aebd652745c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630030"
---
# <a name="connect-to-sql-server-when-system-administrators-are-locked-out"></a><span data-ttu-id="de511-102">Connettersi a SQL Server se gli amministratori di sistema sono bloccati</span><span class="sxs-lookup"><span data-stu-id="de511-102">Connect to SQL Server When System Administrators Are Locked Out</span></span>
  <span data-ttu-id="de511-103">In questo argomento viene descritto come ottenere nuovamente l'accesso al [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="de511-103">This topic describes how you can regain access to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] as a system administrator.</span></span> <span data-ttu-id="de511-104">Un amministratore di sistema può perdere l'accesso a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="de511-104">A system administrator can lose access to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="de511-105">Tutti gli account di accesso membri del ruolo predefinito del server sysadmin sono stati rimossi per errore.</span><span class="sxs-lookup"><span data-stu-id="de511-105">All logins that are members of the sysadmin fixed server role have been removed by mistake.</span></span>  
  
-   <span data-ttu-id="de511-106">Tutti i gruppi di Windows membri del ruolo predefinito del server sysadmin sono stati rimossi per errore.</span><span class="sxs-lookup"><span data-stu-id="de511-106">All Windows Groups that are members of the sysadmin fixed server role have been removed by mistake.</span></span>  
  
-   <span data-ttu-id="de511-107">Gli account di accesso membri del ruolo predefinito del server sysadmin sono assegnati a utenti che hanno lasciato la società o che non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="de511-107">The logins that are members of the sysadmin fixed server role are for individuals who have left the company or who are not available.</span></span>  
  
-   <span data-ttu-id="de511-108">L'account sa è disabilitato o la password non è nota ad alcun utente.</span><span class="sxs-lookup"><span data-stu-id="de511-108">The sa account is disabled or no one knows the password.</span></span>  
  
 <span data-ttu-id="de511-109">Un metodo per ottenere nuovamente l'accesso consiste nel reinstallare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e nel collegare tutti i database alla nuova istanza.</span><span class="sxs-lookup"><span data-stu-id="de511-109">One way in which you can regain access is to reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and attach all the databases to the new instance.</span></span> <span data-ttu-id="de511-110">Questa soluzione richiede molto tempo. Per recuperare gli account di accesso, inoltre, può essere necessario ripristinare il database master da un backup.</span><span class="sxs-lookup"><span data-stu-id="de511-110">This solution is time-consuming; and, to recover the logins, it might require restoring the master database from a backup.</span></span> <span data-ttu-id="de511-111">Se il backup del database master è meno recente, potrebbe non contenere tutte le informazioni.</span><span class="sxs-lookup"><span data-stu-id="de511-111">If the backup of the master database is older, it might not have all the information.</span></span> <span data-ttu-id="de511-112">Se il backup del database master è più recente, potrebbe includere gli stessi account di accesso dell'istanza precedente e, pertanto, gli amministratori possono risultare ancora bloccati.</span><span class="sxs-lookup"><span data-stu-id="de511-112">If the backup of the master database is more recent, it might have the same logins as the previous instance; therefore, administrators will still be locked out.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="de511-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="de511-113">Resolution</span></span>  
 <span data-ttu-id="de511-114">Avviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità utente singolo usando l'opzione **-m** o **-f** .</span><span class="sxs-lookup"><span data-stu-id="de511-114">Start the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode by using either the **-m** or **-f** options.</span></span> <span data-ttu-id="de511-115">Qualsiasi membro del gruppo Administrators locale del computer potrà quindi connettersi all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] come membro del ruolo predefinito del server sysadmin.</span><span class="sxs-lookup"><span data-stu-id="de511-115">Any member of the computer's local Administrators group can then connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a member of the sysadmin fixed server role.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de511-116">Quando si avvia un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità utente singolo, arrestare innanzitutto il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="de511-116">When you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode, first stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service.</span></span> <span data-ttu-id="de511-117">In caso contrario, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent potrebbe eseguire per primo la connessione impedendo la connessione come secondo utente.</span><span class="sxs-lookup"><span data-stu-id="de511-117">Otherwise, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent might connect first and prevent you from connecting as a second user.</span></span>  
  
 <span data-ttu-id="de511-118">Quando si usa l'opzione **-m** con **SQLCMD** o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , è possibile limitare le connessioni a un'applicazione client specificata.</span><span class="sxs-lookup"><span data-stu-id="de511-118">When you use the **-m** option with **sqlcmd** or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can limit the connections to a specified client application.</span></span> <span data-ttu-id="de511-119">Ad esempio, **-m "sqlcmd"** limita le connessioni a una singola connessione e tale connessione deve identificarsi come programma client **SQLCMD** .</span><span class="sxs-lookup"><span data-stu-id="de511-119">For example, **-m"sqlcmd"** limits connections to a single connection and that connection must identify itself as the **sqlcmd** client program.</span></span> <span data-ttu-id="de511-120">Utilizzare questa opzione quando si avvia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità utente singolo e un'applicazione client sconosciuta accede all'unica connessione disponibile.</span><span class="sxs-lookup"><span data-stu-id="de511-120">Use this option when you are starting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode and an unknown client application is taking the only available connection.</span></span> <span data-ttu-id="de511-121">Per connettersi con l'editor di query in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], usare **-m"Microsoft SQL Server Management Studio - Query"** .</span><span class="sxs-lookup"><span data-stu-id="de511-121">To connect through the Query Editor in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], use **-m"Microsoft SQL Server Management Studio - Query"**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="de511-122">Non utilizzare tale opzione come caratteristica di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="de511-122">Do not use this option as a security feature.</span></span> <span data-ttu-id="de511-123">L'applicazione client fornisce il nome dell'applicazione client stessa e può indicare un nome falso come parte della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="de511-123">The client application provides the client application name, and can provide a false name as part of the connection string.</span></span>  
  
 <span data-ttu-id="de511-124">Per istruzioni dettagliate su come avviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in modalità utente singolo, vedere [Configurare le opzioni di avvio Server &#40;Gestione configurazione SQL Server&#41;](scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="de511-124">For step-by-step instructions about how to start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in single-user mode, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](scm-services-configure-server-startup-options.md).</span></span>  
  
## <a name="step-by-step-instructions"></a><span data-ttu-id="de511-125">Istruzioni dettagliate</span><span class="sxs-lookup"><span data-stu-id="de511-125">Step-By-Step Instructions</span></span>  
 <span data-ttu-id="de511-126">Nelle istruzioni seguenti viene illustrato il processo per la connessione a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in esecuzione in Windows 8 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="de511-126">The following instructions describe the process for connecting to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] running on Windows 8 or higher.</span></span> <span data-ttu-id="de511-127">Sono fornite delle lievi modifiche per le versioni precedenti di SQL Server o Windows.</span><span class="sxs-lookup"><span data-stu-id="de511-127">Slight adjustments for earlier versions of SQL Server or Windows are provided.</span></span> <span data-ttu-id="de511-128">Queste istruzioni devono essere eseguite quando si effettua l'accesso a Windows come membro del gruppo di amministratori locali e si presuppone che nel computer sia installato [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de511-128">These instructions must be performed while logged in to Windows as a member of the local administrators group, and they assume that [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] is installed on the computer.</span></span>  
  
1.  <span data-ttu-id="de511-129">Nella pagina iniziale avviare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de511-129">From the Start page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="de511-130">Selezionare **Server registrati** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="de511-130">On the **View** menu, select **Registered Servers**.</span></span> <span data-ttu-id="de511-131">Se il server non è ancora registrato, fare clic con il pulsante destro del mouse su **Gruppi di server locali**, scegliere **Attività**e quindi **Registra server locali**.</span><span class="sxs-lookup"><span data-stu-id="de511-131">(If your server is not already registered, right-click **Local Server Groups**, point to **Tasks**, and then click **Register Local Servers**.)</span></span>  
  
2.  <span data-ttu-id="de511-132">Nell'area Server registrati fare clic con il pulsante destro del mouse sul server e quindi scegliere **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="de511-132">In the Registered Servers area, right-click your server, and then click **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="de511-133">Dovrebbe essere visualizzata la richiesta di autorizzazione all'esecuzione come amministratore. Successivamente, aprire il programma Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="de511-133">This should ask for permission to run as administrator, and then open the Configuration Manager program.</span></span>  
  
3.  <span data-ttu-id="de511-134">Chiudere [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de511-134">Close [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="de511-135">Nel riquadro a sinistra di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionare **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="de511-135">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, select **SQL Server Services**.</span></span> <span data-ttu-id="de511-136">Nel riquadro a destra individuare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de511-136">In the right-pane, find your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="de511-137">Nell'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è incluso **(MSSQLSERVER)** dopo il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="de511-137">(The default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includes **(MSSQLSERVER)** after the computer name.</span></span> <span data-ttu-id="de511-138">Le istanze denominate vengono visualizzate in maiuscolo con lo stesso nome presente in Server registrati. Fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="de511-138">Named instances appear in upper case with the same name that they have in Registered Servers.) Right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="de511-139">Nella scheda **parametri di avvio** , nella casella **specificare un parametro di avvio** , digitare `-m` e quindi fare clic su `Add` .</span><span class="sxs-lookup"><span data-stu-id="de511-139">On the **Startup Parameters** tab, in the **Specify a startup parameter** box, type `-m` and then click `Add`.</span></span> <span data-ttu-id="de511-140">.</span><span class="sxs-lookup"><span data-stu-id="de511-140">(That's a dash then lower case letter m.)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de511-141">In alcune versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è presente alcuna scheda **Parametri di avvio** . In questo caso, nella scheda **Avanzate** fare doppio clic su **Parametri di avvio**.</span><span class="sxs-lookup"><span data-stu-id="de511-141">For some earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] there is no **Startup Parameters** tab. In that case, on the **Advanced** tab, double-click **Startup Parameters**.</span></span> <span data-ttu-id="de511-142">I parametri vengono visualizzati in una finestra molto piccola.</span><span class="sxs-lookup"><span data-stu-id="de511-142">The parameters open up in a very small window.</span></span> <span data-ttu-id="de511-143">Fare attenzione a non modificare nessuno dei parametri esistenti.</span><span class="sxs-lookup"><span data-stu-id="de511-143">Be careful not to change any of the existing parameters.</span></span> <span data-ttu-id="de511-144">Al termine, aggiungere un nuovo parametro `;-m` (cioè un punto e virgola seguito da un trattino e una lettera m minuscola), quindi fare clic su `OK`</span><span class="sxs-lookup"><span data-stu-id="de511-144">At the very end, add a new parameter `;-m` and then click `OK`.</span></span> <span data-ttu-id="de511-145">.</span><span class="sxs-lookup"><span data-stu-id="de511-145">(That's a semi-colon then a dash then lower case letter m.)</span></span>  
  
6.  <span data-ttu-id="de511-146">Fare clic su, quindi, `OK` dopo il messaggio di riavvio, fare clic con il pulsante destro del mouse sul nome del server e quindi scegliere **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="de511-146">Click `OK`, and after the message to restart, right-click your server name, and then click **Restart**.</span></span>  
  
7.  <span data-ttu-id="de511-147">Dopo il riavvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , il server sarà in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="de511-147">After [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has restarted your server will be in single-user mode.</span></span> <span data-ttu-id="de511-148">Accertarsi che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non sia in esecuzione,</span><span class="sxs-lookup"><span data-stu-id="de511-148">Make sure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is not running.</span></span> <span data-ttu-id="de511-149">altrimenti l'unica connessione presente non sarà più disponibile a causa del relativo utilizzo da parte di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="de511-149">If started, it will take your only connection.</span></span>  
  
8.  <span data-ttu-id="de511-150">Nella schermata iniziale di Windows 8 fare clic con il pulsante destro del mouse sull'icona di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de511-150">On the Windows 8 start screen, right-click the icon for [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="de511-151">Nella parte inferiore della schermata selezionare **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="de511-151">At the bottom of the screen, select **Run as administrator**.</span></span> <span data-ttu-id="de511-152">(le credenziali di amministratore verranno passate in SSMS).</span><span class="sxs-lookup"><span data-stu-id="de511-152">(This will pass your administrator credentials to SSMS.)</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de511-153">Per le versioni precedenti di Windows, l'opzione **Esegui come amministratore** viene visualizzata come sottomenu.</span><span class="sxs-lookup"><span data-stu-id="de511-153">For earlier versions of Windows, the **Run as administrator** option appears as a sub-menu.</span></span>  
  
     <span data-ttu-id="de511-154">In alcune configurazioni, tramite SSMS si tenterà di stabilire diverse connessioni.</span><span class="sxs-lookup"><span data-stu-id="de511-154">In some configurations, SSMS will attempt to make several connections.</span></span> <span data-ttu-id="de511-155">Non sarà possibile stabilire più connessioni poiché [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in modalità utente singolo.</span><span class="sxs-lookup"><span data-stu-id="de511-155">Multiple connections will fail because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is in single-user mode.</span></span> <span data-ttu-id="de511-156">È possibile scegliere di effettuare una delle azioni</span><span class="sxs-lookup"><span data-stu-id="de511-156">You can select one of the following actions to perform.</span></span> <span data-ttu-id="de511-157">riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="de511-157">Do one of the following.</span></span>  
  
    1.  <span data-ttu-id="de511-158">Effettuare la connessione con Esplora oggetti mediante l'autenticazione di Windows (in cui sono incluse le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="de511-158">Connect with Object Explorer using Windows Authentication (which includes your Administrator credentials).</span></span> <span data-ttu-id="de511-159">Espandere **Sicurezza**, **Account di accesso**e fare doppio clic sul proprio account di accesso.</span><span class="sxs-lookup"><span data-stu-id="de511-159">Expand **Security**, expand **Logins**, and double-click your own login.</span></span> <span data-ttu-id="de511-160">Nella pagina **ruoli server** selezionare `sysadmin` e quindi fare clic su `OK` .</span><span class="sxs-lookup"><span data-stu-id="de511-160">On the **Server Roles** page, select `sysadmin`, and then click `OK`.</span></span>  
  
    2.  <span data-ttu-id="de511-161">Anziché effettuare la connessione con Esplora oggetti, utilizzare una finestra Query tramite l'autenticazione di Windows (in cui sono incluse le credenziali di amministratore)</span><span class="sxs-lookup"><span data-stu-id="de511-161">Instead of connecting with Object Explorer, connect with a Query Window using Windows Authentication (which includes your Administrator credentials).</span></span> <span data-ttu-id="de511-162">(È possibile connettersi in questo modo solo se non si è connessi con Esplora oggetti). Eseguire codice come il seguente per aggiungere un nuovo account di accesso con autenticazione di Windows che sia un membro del `sysadmin` ruolo predefinito del server.</span><span class="sxs-lookup"><span data-stu-id="de511-162">(You can only connect this way if you did not connect with Object Explorer.) Execute code such as the following to add a new Windows Authentication login that is a member of the `sysadmin` fixed server role.</span></span> <span data-ttu-id="de511-163">Nell'esempio seguente viene aggiunto un utente di dominio denominato `CONTOSO\PatK`.</span><span class="sxs-lookup"><span data-stu-id="de511-163">The following example adds a domain user named `CONTOSO\PatK`.</span></span>  
  
        ```  
        CREATE LOGIN [CONTOSO\PatK] FROM WINDOWS;  
        ALTER SERVER ROLE sysadmin ADD MEMBER [CONTOSO\PatK];  
        ```  
  
    3.  <span data-ttu-id="de511-164">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione nella modalità di autenticazione mista, effettuare la connessione con una finestra Query utilizzando l'autenticazione di Windows (in cui sono incluse le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="de511-164">If your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running in mixed authentication mode, connect with a Query Window using Windows Authentication (which includes your Administrator credentials).</span></span> <span data-ttu-id="de511-165">Eseguire codice simile al seguente per creare un nuovo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account di accesso con autenticazione di che sia membro del `sysadmin` ruolo predefinito del server.</span><span class="sxs-lookup"><span data-stu-id="de511-165">Execute code such as the following to create a new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication login that is a member of the `sysadmin` fixed server role.</span></span>  
  
        ```  
        CREATE LOGIN TempLogin WITH PASSWORD = '************';  
        ALTER SERVER ROLE sysadmin ADD MEMBER TempLogin;  
        ```  
  
        > [!WARNING]  
        >  <span data-ttu-id="de511-166">Sostituire \*\*\*\*\*\*\*\*\*\*\*\* con una password complessa.</span><span class="sxs-lookup"><span data-stu-id="de511-166">Replace \*\*\*\*\*\*\*\*\*\*\*\* with a strong password.</span></span>  
  
    4.  <span data-ttu-id="de511-167">Se il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione in modalità di autenticazione mista e si desidera reimpostare la password dell' `sa` account, connettersi con una finestra query utilizzando l'autenticazione di Windows (che include le credenziali di amministratore).</span><span class="sxs-lookup"><span data-stu-id="de511-167">If your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running in mixed authentication mode and you want to reset the password of the `sa` account, connect with a Query Window using Windows Authentication (which includes your Administrator credentials).</span></span> <span data-ttu-id="de511-168">Modificare la password dell' `sa` account con la sintassi seguente.</span><span class="sxs-lookup"><span data-stu-id="de511-168">Change the password of the `sa` account with the following syntax.</span></span>  
  
        ```  
        ALTER LOGIN sa WITH PASSWORD = '************';  
        ```  
  
        > [!WARNING]  
        >  <span data-ttu-id="de511-169">Sostituire \*\*\*\*\*\*\*\*\*\*\*\* con una password complessa.</span><span class="sxs-lookup"><span data-stu-id="de511-169">Replace \*\*\*\*\*\*\*\*\*\*\*\* with a strong password.</span></span>  
  
9. <span data-ttu-id="de511-170">Tramite i passaggi seguenti viene ora di nuovo impostata la modalità multiutente per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de511-170">The following steps now change [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] back to multi-user mode.</span></span> <span data-ttu-id="de511-171">Chiudere SSMS.</span><span class="sxs-lookup"><span data-stu-id="de511-171">Close SSMS.</span></span>  
  
10. <span data-ttu-id="de511-172">Nel riquadro a sinistra di Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionare **Servizi di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="de511-172">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the left pane, select **SQL Server Services**.</span></span> <span data-ttu-id="de511-173">Nel riquadro a destra fare clic con il pulsante destro del mouse sull'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="de511-173">In the right-pane, right-click the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="de511-174">Nella casella **parametri esistenti** della scheda **parametri di avvio** selezionare `-m` e quindi fare clic su `Remove` .</span><span class="sxs-lookup"><span data-stu-id="de511-174">On the **Startup Parameters** tab, in the **Existing parameters** box, select `-m` and then click `Remove`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="de511-175">In alcune versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è presente alcuna scheda **Parametri di avvio** . In questo caso, nella scheda **Avanzate** fare doppio clic su **Parametri di avvio**.</span><span class="sxs-lookup"><span data-stu-id="de511-175">For some earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] there is no **Startup Parameters** tab. In that case, on the **Advanced** tab, double-click **Startup Parameters**.</span></span> <span data-ttu-id="de511-176">I parametri vengono visualizzati in una finestra molto piccola.</span><span class="sxs-lookup"><span data-stu-id="de511-176">The parameters open up in a very small window.</span></span> <span data-ttu-id="de511-177">Rimuovere il `;-m` valore aggiunto in precedenza, quindi fare clic su `OK` .</span><span class="sxs-lookup"><span data-stu-id="de511-177">Remove the `;-m` which you added earlier, and then click `OK`.</span></span>  
  
12. <span data-ttu-id="de511-178">Fare clic con il pulsante destro del mouse sul nome del server e quindi scegliere **Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="de511-178">Right-click your server name, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="de511-179">A questo punto si dovrebbe essere in grado di connettersi normalmente con uno degli account che ora è un membro del `sysadmin` ruolo predefinito del server.</span><span class="sxs-lookup"><span data-stu-id="de511-179">Now you should be able to connect normally with one of the accounts which is now a member of the `sysadmin` fixed server role.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de511-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de511-180">See Also</span></span>  
 <span data-ttu-id="de511-181">[Avvio di SQL Server in modalità utente singolo](start-sql-server-in-single-user-mode.md) </span><span class="sxs-lookup"><span data-stu-id="de511-181">[Start SQL Server in Single-User Mode](start-sql-server-in-single-user-mode.md) </span></span>  
 [<span data-ttu-id="de511-182">Opzioni di avvio del servizio del motore di database</span><span class="sxs-lookup"><span data-stu-id="de511-182">Database Engine Service Startup Options</span></span>](database-engine-service-startup-options.md)  
  
  