---
title: Classe di evento QN:Subscription | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], QN:Subscription
ms.assetid: 4916167e-8541-43b4-900e-ec8e6adcbc34
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e25bdf8fd8745bf939cab50c4b7e43316cf59d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635003"
---
# <a name="qnsubscription-event-class"></a><span data-ttu-id="b8a77-102">Classe di evento QN:Subscription</span><span class="sxs-lookup"><span data-stu-id="b8a77-102">QN:Subscription Event Class</span></span>
  <span data-ttu-id="b8a77-103">L'evento QN:Subscription fornisce informazioni sulle sottoscrizioni di notifica.</span><span class="sxs-lookup"><span data-stu-id="b8a77-103">The QN:Subscription event reports information on notification subscriptions.</span></span>  
  
## <a name="qnsubscription-event-class-data-columns"></a><span data-ttu-id="b8a77-104">Colonne dati della classe di evento QN:Subscription</span><span class="sxs-lookup"><span data-stu-id="b8a77-104">QN:Subscription Event Class Data Columns</span></span>  
  
|<span data-ttu-id="b8a77-105">Colonna di dati</span><span class="sxs-lookup"><span data-stu-id="b8a77-105">Data column</span></span>|<span data-ttu-id="b8a77-106">Type</span><span class="sxs-lookup"><span data-stu-id="b8a77-106">Type</span></span>|<span data-ttu-id="b8a77-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8a77-107">Description</span></span>|<span data-ttu-id="b8a77-108">Numero di colonna</span><span class="sxs-lookup"><span data-stu-id="b8a77-108">Column number</span></span>|<span data-ttu-id="b8a77-109">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="b8a77-109">Filterable</span></span>|  
|-----------------|----------|-----------------|-------------------|----------------|  
|<span data-ttu-id="b8a77-110">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="b8a77-110">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-111">Nome dell'applicazione client in cui è stata creata la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8a77-111">The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8a77-112">Questa colonna viene popolata con i valori passati dall'applicazione e non con il nome visualizzato del programma.</span><span class="sxs-lookup"><span data-stu-id="b8a77-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="b8a77-113">10</span><span class="sxs-lookup"><span data-stu-id="b8a77-113">10</span></span>|<span data-ttu-id="b8a77-114">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-114">Yes</span></span>|  
|<span data-ttu-id="b8a77-115">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="b8a77-115">ClientProcessID</span></span>|`int`|<span data-ttu-id="b8a77-116">ID assegnato dal computer host al processo in cui è in esecuzione l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="b8a77-116">The ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="b8a77-117">Questa colonna di dati viene popolata se l'ID del processo client viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="b8a77-117">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="b8a77-118">9</span><span class="sxs-lookup"><span data-stu-id="b8a77-118">9</span></span>|<span data-ttu-id="b8a77-119">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-119">Yes</span></span>|  
|<span data-ttu-id="b8a77-120">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="b8a77-120">DatabaseID</span></span>|`int`|<span data-ttu-id="b8a77-121">ID del database specificato dall'istruzione USE *database* oppure ID del database predefinito, se per una determinata istanza non viene eseguita alcuna istruzione USE *database*.</span><span class="sxs-lookup"><span data-stu-id="b8a77-121">The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="b8a77-122">viene visualizzato il nome del database se la colonna di dati ServerName viene acquisita nella traccia e il server è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b8a77-122">displays the name of the database if the Server Name data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="b8a77-123">Determinare il valore per un database utilizzando la funzione DB_ID.</span><span class="sxs-lookup"><span data-stu-id="b8a77-123">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="b8a77-124">3</span><span class="sxs-lookup"><span data-stu-id="b8a77-124">3</span></span>|<span data-ttu-id="b8a77-125">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-125">Yes</span></span>|  
|<span data-ttu-id="b8a77-126">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="b8a77-126">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-127">Nome del database in cui viene eseguita l'istruzione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b8a77-127">The name of the database in which the user statement is running.</span></span>|<span data-ttu-id="b8a77-128">35</span><span class="sxs-lookup"><span data-stu-id="b8a77-128">35</span></span>|<span data-ttu-id="b8a77-129">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-129">Yes</span></span>|  
|<span data-ttu-id="b8a77-130">EventClass</span><span class="sxs-lookup"><span data-stu-id="b8a77-130">EventClass</span></span>|`int`|<span data-ttu-id="b8a77-131">Tipo di evento = 199.</span><span class="sxs-lookup"><span data-stu-id="b8a77-131">Type of event = 199.</span></span>|<span data-ttu-id="b8a77-132">27</span><span class="sxs-lookup"><span data-stu-id="b8a77-132">27</span></span>|<span data-ttu-id="b8a77-133">No</span><span class="sxs-lookup"><span data-stu-id="b8a77-133">No</span></span>|  
|<span data-ttu-id="b8a77-134">EventSequence</span><span class="sxs-lookup"><span data-stu-id="b8a77-134">EventSequence</span></span>|`int`|<span data-ttu-id="b8a77-135">Numero di sequenza dell'evento.</span><span class="sxs-lookup"><span data-stu-id="b8a77-135">Sequence number for this event.</span></span>|<span data-ttu-id="b8a77-136">51</span><span class="sxs-lookup"><span data-stu-id="b8a77-136">51</span></span>|<span data-ttu-id="b8a77-137">No</span><span class="sxs-lookup"><span data-stu-id="b8a77-137">No</span></span>|  
|<span data-ttu-id="b8a77-138">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="b8a77-138">EventSubClass</span></span>|`nvarchar`|<span data-ttu-id="b8a77-139">Tipo di sottoclasse di evento in cui sono disponibili informazioni aggiuntive su ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="b8a77-139">The type of event subclass, providing further information about each event class.</span></span> <span data-ttu-id="b8a77-140">Questa colonna può contenere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8a77-140">This column may contain the following values:</span></span><br /><br /> <span data-ttu-id="b8a77-141">Subscription registered: indica quando la sottoscrizione di notifica delle query viene registrata correttamente nel database.</span><span class="sxs-lookup"><span data-stu-id="b8a77-141">Subscription registered: Indicates when the query notification subscription is successfully registered in the database.</span></span><br /><br /> <span data-ttu-id="b8a77-142">Subscription Rewound: indica quando [!INCLUDE[ssDE](../../includes/ssde-md.md)] riceve una richiesta di sottoscrizione che corrisponde esattamente a una sottoscrizione esistente.</span><span class="sxs-lookup"><span data-stu-id="b8a77-142">Subscription rewound: Indicates when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] receives a subscription request that exactly matches an existing subscription.</span></span> <span data-ttu-id="b8a77-143">In tal caso, [!INCLUDE[ssDE](../../includes/ssde-md.md)] imposta il valore di timeout della sottoscrizione esistente sul timeout specificato nella nuova richiesta di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="b8a77-143">In this case, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] sets the time-out value of the existing subscription to the time-out specified in the new subscription request.</span></span><br /><br /> <span data-ttu-id="b8a77-144">Subscription fired: indica quando una sottoscrizione di notifica genera un messaggio di notifica.</span><span class="sxs-lookup"><span data-stu-id="b8a77-144">Subscription fired: Indicates when a notification subscription produces a notification message.</span></span><br /><br /> <span data-ttu-id="b8a77-145">Generazione non riuscita con errore Broker: indica quando un messaggio di notifica ha esito negativo a causa di un [!INCLUDE[ssSB](../../includes/sssb-md.md)] errore.</span><span class="sxs-lookup"><span data-stu-id="b8a77-145">Firing failed with broker error: Indicates when a notification message fails due to a [!INCLUDE[ssSB](../../includes/sssb-md.md)] error.</span></span><br /><br /> <span data-ttu-id="b8a77-146">Attivazione non riuscita senza Broker Error: indica quando un messaggio di notifica ha esito negativo, ma non a causa di un [!INCLUDE[ssSB](../../includes/sssb-md.md)] errore.</span><span class="sxs-lookup"><span data-stu-id="b8a77-146">Firing failed without broker error: Indicates when a notification message fails but is not due to a [!INCLUDE[ssSB](../../includes/sssb-md.md)] error.</span></span><br /><br /> <span data-ttu-id="b8a77-147">Broker Error intercettated: indica che ha [!INCLUDE[ssSB](../../includes/sssb-md.md)] recapitato un errore nella conversazione utilizzata dalla notifica di query.</span><span class="sxs-lookup"><span data-stu-id="b8a77-147">Broker error intercepted: Indicates that [!INCLUDE[ssSB](../../includes/sssb-md.md)] delivered an error in the conversation that the query notification uses.</span></span><br /><br /> <span data-ttu-id="b8a77-148">Tentativo di eliminazione della sottoscrizione: indica che il ha [!INCLUDE[ssDE](../../includes/ssde-md.md)] provato a eliminare una sottoscrizione scaduta per liberare risorse.</span><span class="sxs-lookup"><span data-stu-id="b8a77-148">Subscription deletion attempt: Indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] attempted to delete an expired subscription to free up resources.</span></span><br /><br /> <span data-ttu-id="b8a77-149">Subscription deletion failed: Indica che il tentativo di eliminazione di una sottoscrizione scaduta non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="b8a77-149">Subscription deletion failed: Indicates that the attempt to delete an expired subscription has failed.</span></span> <span data-ttu-id="b8a77-150">[!INCLUDE[ssDE](../../includes/ssde-md.md)] ripianificherà automaticamente la sottoscrizione per l'eliminazione allo scopo di liberare risorse.</span><span class="sxs-lookup"><span data-stu-id="b8a77-150">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] will automatically reschedule the subscription for deletion to free up resources.</span></span><br /><br /> <span data-ttu-id="b8a77-151">Subscription destroyed: indica che è stata [!INCLUDE[ssDE](../../includes/ssde-md.md)] eliminata correttamente una sottoscrizione scaduta</span><span class="sxs-lookup"><span data-stu-id="b8a77-151">Subscription destroyed: Indicates that the [!INCLUDE[ssDE](../../includes/ssde-md.md)] successfully deleted an expired subscription</span></span>|<span data-ttu-id="b8a77-152">21</span><span class="sxs-lookup"><span data-stu-id="b8a77-152">21</span></span>|<span data-ttu-id="b8a77-153">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-153">Yes</span></span>|  
|<span data-ttu-id="b8a77-154">GroupID</span><span class="sxs-lookup"><span data-stu-id="b8a77-154">GroupID</span></span>|`int`|<span data-ttu-id="b8a77-155">ID del gruppo del carico di lavoro in cui viene generato l'evento di Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="b8a77-155">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="b8a77-156">66</span><span class="sxs-lookup"><span data-stu-id="b8a77-156">66</span></span>|<span data-ttu-id="b8a77-157">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-157">Yes</span></span>|  
|<span data-ttu-id="b8a77-158">HostName</span><span class="sxs-lookup"><span data-stu-id="b8a77-158">HostName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-159">Nome del computer in cui è in esecuzione il client.</span><span class="sxs-lookup"><span data-stu-id="b8a77-159">The name of the computer on which the client is running.</span></span> <span data-ttu-id="b8a77-160">Questa colonna di dati viene popolata se il nome host viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="b8a77-160">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="b8a77-161">Per determinare il nome host, usare la funzione HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="b8a77-161">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="b8a77-162">8</span><span class="sxs-lookup"><span data-stu-id="b8a77-162">8</span></span>|<span data-ttu-id="b8a77-163">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-163">Yes</span></span>|  
|<span data-ttu-id="b8a77-164">IsSystem</span><span class="sxs-lookup"><span data-stu-id="b8a77-164">IsSystem</span></span>|`int`|<span data-ttu-id="b8a77-165">Indica se l'evento è stato generato per un processo di sistema o un processo utente.</span><span class="sxs-lookup"><span data-stu-id="b8a77-165">Indicates whether the event occurred on a system process or a user process.</span></span><br /><br /> <span data-ttu-id="b8a77-166">0 = utente</span><span class="sxs-lookup"><span data-stu-id="b8a77-166">0 = user</span></span><br /><br /> <span data-ttu-id="b8a77-167">1 = sistema</span><span class="sxs-lookup"><span data-stu-id="b8a77-167">1 = system</span></span>|<span data-ttu-id="b8a77-168">60</span><span class="sxs-lookup"><span data-stu-id="b8a77-168">60</span></span>|<span data-ttu-id="b8a77-169">No</span><span class="sxs-lookup"><span data-stu-id="b8a77-169">No</span></span>|  
|<span data-ttu-id="b8a77-170">LoginName</span><span class="sxs-lookup"><span data-stu-id="b8a77-170">LoginName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-171">Nome dell'account di accesso dell'utente (account di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenziali di accesso di Windows nel formato DOMINIO\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="b8a77-171">The name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the Windows login credentials in the form of DOMAIN\Username).</span></span>|<span data-ttu-id="b8a77-172">11</span><span class="sxs-lookup"><span data-stu-id="b8a77-172">11</span></span>|<span data-ttu-id="b8a77-173">No</span><span class="sxs-lookup"><span data-stu-id="b8a77-173">No</span></span>|  
|<span data-ttu-id="b8a77-174">LoginSID</span><span class="sxs-lookup"><span data-stu-id="b8a77-174">LoginSID</span></span>|`image`|<span data-ttu-id="b8a77-175">ID di sicurezza (SID) dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="b8a77-175">The security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="b8a77-176">Queste informazioni sono disponibili nella vista del catalogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="b8a77-176">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="b8a77-177">Il SID è univoco per ogni account di accesso nel server.</span><span class="sxs-lookup"><span data-stu-id="b8a77-177">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="b8a77-178">41</span><span class="sxs-lookup"><span data-stu-id="b8a77-178">41</span></span>|<span data-ttu-id="b8a77-179">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-179">Yes</span></span>|  
|<span data-ttu-id="b8a77-180">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="b8a77-180">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-181">Dominio di Windows a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="b8a77-181">The Windows domain to which the user belongs.</span></span>|<span data-ttu-id="b8a77-182">7</span><span class="sxs-lookup"><span data-stu-id="b8a77-182">7</span></span>|<span data-ttu-id="b8a77-183">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-183">Yes</span></span>|  
|<span data-ttu-id="b8a77-184">NTUserName</span><span class="sxs-lookup"><span data-stu-id="b8a77-184">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-185">Nome dell'utente proprietario della connessione che ha generato questo evento.</span><span class="sxs-lookup"><span data-stu-id="b8a77-185">The name of the user that owns the connection that generated this event.</span></span>|<span data-ttu-id="b8a77-186">6</span><span class="sxs-lookup"><span data-stu-id="b8a77-186">6</span></span>|<span data-ttu-id="b8a77-187">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-187">Yes</span></span>|  
|<span data-ttu-id="b8a77-188">RequestID</span><span class="sxs-lookup"><span data-stu-id="b8a77-188">RequestID</span></span>|`int`|<span data-ttu-id="b8a77-189">Identificatore della richiesta contenente l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b8a77-189">Identifier of the request that contains the statement.</span></span>|<span data-ttu-id="b8a77-190">49</span><span class="sxs-lookup"><span data-stu-id="b8a77-190">49</span></span>|<span data-ttu-id="b8a77-191">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-191">Yes</span></span>|  
|<span data-ttu-id="b8a77-192">ServerName</span><span class="sxs-lookup"><span data-stu-id="b8a77-192">ServerName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-193">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracciata.</span><span class="sxs-lookup"><span data-stu-id="b8a77-193">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="b8a77-194">26</span><span class="sxs-lookup"><span data-stu-id="b8a77-194">26</span></span>|<span data-ttu-id="b8a77-195">No</span><span class="sxs-lookup"><span data-stu-id="b8a77-195">No</span></span>|  
|<span data-ttu-id="b8a77-196">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="b8a77-196">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="b8a77-197">Nome dell'account di accesso dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="b8a77-197">Login name of the user that originated the session.</span></span> <span data-ttu-id="b8a77-198">Se ad esempio un'applicazione si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'account di accesso Login1 ed esegue un'istruzione con l'account di accesso Login2, SessionLoginName indica "Login1" e LoginName indica "Login2".</span><span class="sxs-lookup"><span data-stu-id="b8a77-198">For example, if an application connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and executes a statement as Login2, SessionLoginName shows "Login1" and LoginName shows "Login2".</span></span> <span data-ttu-id="b8a77-199">In questa colonna sono visualizzati sia gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che quelli di Windows.</span><span class="sxs-lookup"><span data-stu-id="b8a77-199">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="b8a77-200">64</span><span class="sxs-lookup"><span data-stu-id="b8a77-200">64</span></span>|<span data-ttu-id="b8a77-201">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-201">Yes</span></span>|  
|<span data-ttu-id="b8a77-202">SPID</span><span class="sxs-lookup"><span data-stu-id="b8a77-202">SPID</span></span>|`int`|<span data-ttu-id="b8a77-203">ID della sessione in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="b8a77-203">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="b8a77-204">12</span><span class="sxs-lookup"><span data-stu-id="b8a77-204">12</span></span>|<span data-ttu-id="b8a77-205">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-205">Yes</span></span>|  
|<span data-ttu-id="b8a77-206">StartTime</span><span class="sxs-lookup"><span data-stu-id="b8a77-206">StartTime</span></span>|`datetime`|<span data-ttu-id="b8a77-207">Ora di inizio dell'evento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="b8a77-207">Time at which the event started, if available.</span></span>|<span data-ttu-id="b8a77-208">14</span><span class="sxs-lookup"><span data-stu-id="b8a77-208">14</span></span>|<span data-ttu-id="b8a77-209">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-209">Yes</span></span>|  
|<span data-ttu-id="b8a77-210">TextData</span><span class="sxs-lookup"><span data-stu-id="b8a77-210">TextData</span></span>|`ntext`|<span data-ttu-id="b8a77-211">Restituisce un documento XML contenente informazioni specifiche per questo evento.</span><span class="sxs-lookup"><span data-stu-id="b8a77-211">Returns an XML document containing information specific to this event.</span></span> <span data-ttu-id="b8a77-212">Questo documento è conforme XML Schema disponibile nella pagina [Schema di eventi di SQL Server Profiler correlati alle notifiche delle query](https://go.microsoft.com/fwlink/?LinkId=63331) .</span><span class="sxs-lookup"><span data-stu-id="b8a77-212">This document conforms to the XML schema available at the [SQL Server Query Notification Profiler Event Schema](https://go.microsoft.com/fwlink/?LinkId=63331) page.</span></span>|<span data-ttu-id="b8a77-213">1</span><span class="sxs-lookup"><span data-stu-id="b8a77-213">1</span></span>|<span data-ttu-id="b8a77-214">Sì</span><span class="sxs-lookup"><span data-stu-id="b8a77-214">Yes</span></span>|  
  
  