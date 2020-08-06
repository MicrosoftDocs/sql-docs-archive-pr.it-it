---
title: Classe di evento User Error Message | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- User Error Message event class
ms.assetid: d7594261-ccd9-487c-9678-11875ba57fb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: d23a8ee66cafc4bef1f258e40dbe51274a308eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637359"
---
# <a name="user-error-message-event-class"></a><span data-ttu-id="8ff62-102">User Error Message - classe di evento</span><span class="sxs-lookup"><span data-stu-id="8ff62-102">User Error Message Event Class</span></span>
  <span data-ttu-id="8ff62-103">La classe di evento User Error Message visualizza il messaggio di errore nella stessa forma visualizzata all'utente in caso di errore o eccezione.</span><span class="sxs-lookup"><span data-stu-id="8ff62-103">The User Error Message event class displays the error message as seen by the user in the case of an error or exception.</span></span> <span data-ttu-id="8ff62-104">Il testo del messaggio di errore viene visualizzato nel campo TextData.</span><span class="sxs-lookup"><span data-stu-id="8ff62-104">The error message text appears in the TextData field.</span></span>  
  
## <a name="user-error-message-event-class-data-columns"></a><span data-ttu-id="8ff62-105">Colonne di dati della classe di evento User Error Message</span><span class="sxs-lookup"><span data-stu-id="8ff62-105">User Error Message Event Class Data Columns</span></span>  
  
|<span data-ttu-id="8ff62-106">Nome colonna di dati</span><span class="sxs-lookup"><span data-stu-id="8ff62-106">Data column name</span></span>|`Data type`|<span data-ttu-id="8ff62-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ff62-107">Description</span></span>|<span data-ttu-id="8ff62-108">ID colonna</span><span class="sxs-lookup"><span data-stu-id="8ff62-108">Column ID</span></span>|<span data-ttu-id="8ff62-109">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="8ff62-109">Filterable</span></span>|  
|----------------------|-------------------|-----------------|---------------|----------------|  
|<span data-ttu-id="8ff62-110">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="8ff62-110">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-111">Nome dell'applicazione client in cui è stata creata la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ff62-111">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8ff62-112">Questa colonna viene popolata con i valori passati dall'applicazione e non con il nome visualizzato del programma.</span><span class="sxs-lookup"><span data-stu-id="8ff62-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="8ff62-113">10</span><span class="sxs-lookup"><span data-stu-id="8ff62-113">10</span></span>|<span data-ttu-id="8ff62-114">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-114">Yes</span></span>|  
|<span data-ttu-id="8ff62-115">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="8ff62-115">ClientProcessID</span></span>|`int`|<span data-ttu-id="8ff62-116">ID assegnato dal computer host al processo in cui è in esecuzione l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="8ff62-116">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="8ff62-117">Questa colonna di dati viene popolata se tramite il client viene indicato l'ID del processo client.</span><span class="sxs-lookup"><span data-stu-id="8ff62-117">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="8ff62-118">9</span><span class="sxs-lookup"><span data-stu-id="8ff62-118">9</span></span>|<span data-ttu-id="8ff62-119">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-119">Yes</span></span>|  
|<span data-ttu-id="8ff62-120">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="8ff62-120">DatabaseID</span></span>|`int`|<span data-ttu-id="8ff62-121">ID del database specificato nell'istruzione di *database* USE oppure il database predefinito se per un'istanza specifica l'istruzione di *database* USE non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="8ff62-121">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="8ff62-122">visualizza il nome del database se la colonna di dati ServerName è acquisita nella traccia e il server è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8ff62-122">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="8ff62-123">Determinare il valore per un database utilizzando la funzione DB_ID.</span><span class="sxs-lookup"><span data-stu-id="8ff62-123">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="8ff62-124">3</span><span class="sxs-lookup"><span data-stu-id="8ff62-124">3</span></span>|<span data-ttu-id="8ff62-125">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-125">Yes</span></span>|  
|<span data-ttu-id="8ff62-126">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="8ff62-126">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-127">Nome del database nel quale viene eseguita l'istruzione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8ff62-127">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="8ff62-128">35</span><span class="sxs-lookup"><span data-stu-id="8ff62-128">35</span></span>|<span data-ttu-id="8ff62-129">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-129">Yes</span></span>|  
|<span data-ttu-id="8ff62-130">Errore</span><span class="sxs-lookup"><span data-stu-id="8ff62-130">Error</span></span>|`int`|<span data-ttu-id="8ff62-131">Numero di errore di un evento specifico.</span><span class="sxs-lookup"><span data-stu-id="8ff62-131">Error number of a given event.</span></span> <span data-ttu-id="8ff62-132">Corrisponde spesso al numero di errore archiviato nella vista del catalogo sys.messages.</span><span class="sxs-lookup"><span data-stu-id="8ff62-132">Often this is the error number stored in the sys.messages catalog view.</span></span>|<span data-ttu-id="8ff62-133">31</span><span class="sxs-lookup"><span data-stu-id="8ff62-133">31</span></span>|<span data-ttu-id="8ff62-134">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-134">Yes</span></span>|  
|<span data-ttu-id="8ff62-135">EventClass</span><span class="sxs-lookup"><span data-stu-id="8ff62-135">EventClass</span></span>|`int`|<span data-ttu-id="8ff62-136">Tipo di evento = 162.</span><span class="sxs-lookup"><span data-stu-id="8ff62-136">Type of event = 162.</span></span>|<span data-ttu-id="8ff62-137">27</span><span class="sxs-lookup"><span data-stu-id="8ff62-137">27</span></span>|<span data-ttu-id="8ff62-138">No</span><span class="sxs-lookup"><span data-stu-id="8ff62-138">No</span></span>|  
|<span data-ttu-id="8ff62-139">EventSequence</span><span class="sxs-lookup"><span data-stu-id="8ff62-139">EventSequence</span></span>|`int`|<span data-ttu-id="8ff62-140">Sequenza di un determinato evento all'interno della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8ff62-140">Sequence of a given event within the request.</span></span>|<span data-ttu-id="8ff62-141">51</span><span class="sxs-lookup"><span data-stu-id="8ff62-141">51</span></span>|<span data-ttu-id="8ff62-142">No</span><span class="sxs-lookup"><span data-stu-id="8ff62-142">No</span></span>|  
|<span data-ttu-id="8ff62-143">GroupID</span><span class="sxs-lookup"><span data-stu-id="8ff62-143">GroupID</span></span>|`int`|<span data-ttu-id="8ff62-144">ID del gruppo del carico di lavoro in cui viene generato l'evento di Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="8ff62-144">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="8ff62-145">66</span><span class="sxs-lookup"><span data-stu-id="8ff62-145">66</span></span>|<span data-ttu-id="8ff62-146">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-146">Yes</span></span>|  
|<span data-ttu-id="8ff62-147">HostName</span><span class="sxs-lookup"><span data-stu-id="8ff62-147">HostName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-148">Nome del computer in cui viene eseguito il client.</span><span class="sxs-lookup"><span data-stu-id="8ff62-148">Name of the computer on which the client is running.</span></span> <span data-ttu-id="8ff62-149">Questa colonna di dati viene popolata se il client fornisce il nome host.</span><span class="sxs-lookup"><span data-stu-id="8ff62-149">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="8ff62-150">Per determinare il nome host, usare la funzione HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="8ff62-150">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="8ff62-151">8</span><span class="sxs-lookup"><span data-stu-id="8ff62-151">8</span></span>|<span data-ttu-id="8ff62-152">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-152">Yes</span></span>|  
|<span data-ttu-id="8ff62-153">IsSystem</span><span class="sxs-lookup"><span data-stu-id="8ff62-153">IsSystem</span></span>|`int`|<span data-ttu-id="8ff62-154">Indica se l'evento è stato generato per un processo di sistema o un processo utente.</span><span class="sxs-lookup"><span data-stu-id="8ff62-154">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="8ff62-155">1 = sistema, 0 = utente.</span><span class="sxs-lookup"><span data-stu-id="8ff62-155">1 = system, 0 = user.</span></span>|<span data-ttu-id="8ff62-156">60</span><span class="sxs-lookup"><span data-stu-id="8ff62-156">60</span></span>|<span data-ttu-id="8ff62-157">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-157">Yes</span></span>|  
|<span data-ttu-id="8ff62-158">LoginName</span><span class="sxs-lookup"><span data-stu-id="8ff62-158">LoginName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-159">Nome dell'account di accesso dell'utente (account di accesso di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenziali di accesso di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows nel formato DOMINIO\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="8ff62-159">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="8ff62-160">11</span><span class="sxs-lookup"><span data-stu-id="8ff62-160">11</span></span>|<span data-ttu-id="8ff62-161">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-161">Yes</span></span>|  
|<span data-ttu-id="8ff62-162">LoginSid</span><span class="sxs-lookup"><span data-stu-id="8ff62-162">LoginSid</span></span>|`image`|<span data-ttu-id="8ff62-163">ID di sicurezza (SID) dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="8ff62-163">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="8ff62-164">Queste informazioni sono disponibili nella vista del catalogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="8ff62-164">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="8ff62-165">Il SID è univoco per ogni account di accesso nel server.</span><span class="sxs-lookup"><span data-stu-id="8ff62-165">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="8ff62-166">41</span><span class="sxs-lookup"><span data-stu-id="8ff62-166">41</span></span>|<span data-ttu-id="8ff62-167">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-167">Yes</span></span>|  
|<span data-ttu-id="8ff62-168">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="8ff62-168">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-169">Dominio Windows di appartenenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8ff62-169">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="8ff62-170">7</span><span class="sxs-lookup"><span data-stu-id="8ff62-170">7</span></span>|<span data-ttu-id="8ff62-171">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-171">Yes</span></span>|  
|<span data-ttu-id="8ff62-172">NTUserName</span><span class="sxs-lookup"><span data-stu-id="8ff62-172">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-173">Nome utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="8ff62-173">Windows user name.</span></span>|<span data-ttu-id="8ff62-174">6</span><span class="sxs-lookup"><span data-stu-id="8ff62-174">6</span></span>|<span data-ttu-id="8ff62-175">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-175">Yes</span></span>|  
|<span data-ttu-id="8ff62-176">RequestID</span><span class="sxs-lookup"><span data-stu-id="8ff62-176">RequestID</span></span>|`int`|<span data-ttu-id="8ff62-177">ID della richiesta contenente l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8ff62-177">The ID of the request containing the statement.</span></span>|<span data-ttu-id="8ff62-178">49</span><span class="sxs-lookup"><span data-stu-id="8ff62-178">49</span></span>|<span data-ttu-id="8ff62-179">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-179">Yes</span></span>|  
|<span data-ttu-id="8ff62-180">ServerName</span><span class="sxs-lookup"><span data-stu-id="8ff62-180">ServerName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-181">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracciata.</span><span class="sxs-lookup"><span data-stu-id="8ff62-181">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="8ff62-182">26</span><span class="sxs-lookup"><span data-stu-id="8ff62-182">26</span></span>|<span data-ttu-id="8ff62-183">No</span><span class="sxs-lookup"><span data-stu-id="8ff62-183">No</span></span>|  
|<span data-ttu-id="8ff62-184">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="8ff62-184">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="8ff62-185">Nome dell'account di accesso dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="8ff62-185">Login name of the user who originated the session.</span></span> <span data-ttu-id="8ff62-186">Se ad esempio si stabilisce la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'account di accesso Login1 e si esegue un'istruzione con l'account di accesso Login2, SessionLoginName indica Login1 e LoginName indica Login2.</span><span class="sxs-lookup"><span data-stu-id="8ff62-186">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="8ff62-187">In questa colonna sono visualizzati sia gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che quelli di Windows.</span><span class="sxs-lookup"><span data-stu-id="8ff62-187">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="8ff62-188">64</span><span class="sxs-lookup"><span data-stu-id="8ff62-188">64</span></span>|<span data-ttu-id="8ff62-189">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-189">Yes</span></span>|  
|<span data-ttu-id="8ff62-190">Gravità</span><span class="sxs-lookup"><span data-stu-id="8ff62-190">Severity</span></span>|`int`|<span data-ttu-id="8ff62-191">Livello di gravità dell'errore o dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8ff62-191">Severity level of the error or exception.</span></span>|<span data-ttu-id="8ff62-192">20</span><span class="sxs-lookup"><span data-stu-id="8ff62-192">20</span></span>|<span data-ttu-id="8ff62-193">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-193">Yes</span></span>|  
|<span data-ttu-id="8ff62-194">SPID</span><span class="sxs-lookup"><span data-stu-id="8ff62-194">SPID</span></span>|`int`|<span data-ttu-id="8ff62-195">ID della sessione in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="8ff62-195">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="8ff62-196">12</span><span class="sxs-lookup"><span data-stu-id="8ff62-196">12</span></span>|<span data-ttu-id="8ff62-197">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-197">Yes</span></span>|  
|<span data-ttu-id="8ff62-198">StartTime</span><span class="sxs-lookup"><span data-stu-id="8ff62-198">StartTime</span></span>|`datetime`|<span data-ttu-id="8ff62-199">Ora di inizio dell'evento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="8ff62-199">Time at which the event started, if available.</span></span>|<span data-ttu-id="8ff62-200">14</span><span class="sxs-lookup"><span data-stu-id="8ff62-200">14</span></span>|<span data-ttu-id="8ff62-201">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-201">Yes</span></span>|  
|<span data-ttu-id="8ff62-202">State</span><span class="sxs-lookup"><span data-stu-id="8ff62-202">State</span></span>|`int`|<span data-ttu-id="8ff62-203">Equivalente a un codice di stato dell'errore.</span><span class="sxs-lookup"><span data-stu-id="8ff62-203">Equivalent to an error state code.</span></span>|<span data-ttu-id="8ff62-204">30</span><span class="sxs-lookup"><span data-stu-id="8ff62-204">30</span></span>|<span data-ttu-id="8ff62-205">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-205">Yes</span></span>|  
|<span data-ttu-id="8ff62-206">TextData</span><span class="sxs-lookup"><span data-stu-id="8ff62-206">TextData</span></span>|`ntext`|<span data-ttu-id="8ff62-207">Testo del messaggio di errore o dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8ff62-207">Text of the error message or exception.</span></span>|<span data-ttu-id="8ff62-208">1</span><span class="sxs-lookup"><span data-stu-id="8ff62-208">1</span></span>|<span data-ttu-id="8ff62-209">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-209">Yes</span></span>|  
|<span data-ttu-id="8ff62-210">TransactionID</span><span class="sxs-lookup"><span data-stu-id="8ff62-210">TransactionID</span></span>|`bigint`|<span data-ttu-id="8ff62-211">ID della transazione assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="8ff62-211">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="8ff62-212">4</span><span class="sxs-lookup"><span data-stu-id="8ff62-212">4</span></span>|<span data-ttu-id="8ff62-213">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-213">Yes</span></span>|  
|<span data-ttu-id="8ff62-214">XactSequence</span><span class="sxs-lookup"><span data-stu-id="8ff62-214">XactSequence</span></span>|`bigint`|<span data-ttu-id="8ff62-215">Token utilizzato per descrivere la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="8ff62-215">Token that describes the current transaction.</span></span>|<span data-ttu-id="8ff62-216">50</span><span class="sxs-lookup"><span data-stu-id="8ff62-216">50</span></span>|<span data-ttu-id="8ff62-217">Sì</span><span class="sxs-lookup"><span data-stu-id="8ff62-217">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ff62-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ff62-218">See Also</span></span>  
 [<span data-ttu-id="8ff62-219">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8ff62-219">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  