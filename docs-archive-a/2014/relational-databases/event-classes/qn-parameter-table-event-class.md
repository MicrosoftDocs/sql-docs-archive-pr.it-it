---
title: Classe di evento QN:Parameter Table | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], QN:Parameter Table
ms.assetid: 292da1ed-4c7e-4bd2-9b84-b9ee09917724
author: stevestein
ms.author: sstein
ms.openlocfilehash: bacae36c98ada99778a0d83261bf28ff70222f88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635008"
---
# <a name="qnparameter-table-event-class"></a><span data-ttu-id="80efd-102">Classe di evento QN:Parameter Table</span><span class="sxs-lookup"><span data-stu-id="80efd-102">QN:Parameter Table Event Class</span></span>
  <span data-ttu-id="80efd-103">L'evento QN:Parameter table fornisce informazioni sulle operazioni necessarie per creare ed eliminare le tabelle interne in cui sono archiviate le informazioni sui parametri, nonché per mantenere i conteggi dei riferimenti corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="80efd-103">The QN:Parameter table event reports information about the operations required to create, keep reference counts for, and drop the internal tables that store parameter information.</span></span> <span data-ttu-id="80efd-104">Questo evento indica inoltre l'attività interna per reimpostare il conteggio di utilizzi relativo a una tabella di parametri.</span><span class="sxs-lookup"><span data-stu-id="80efd-104">This event also reports the internal activity to reset the usage count for a parameter table.</span></span>  
  
## <a name="qnparameter-table-event-class-data-columns"></a><span data-ttu-id="80efd-105">Colonne di dati della classe di evento QN:Parameter table</span><span class="sxs-lookup"><span data-stu-id="80efd-105">QN:Parameter table Event Class Data Columns</span></span>  
  
|<span data-ttu-id="80efd-106">Colonna di dati</span><span class="sxs-lookup"><span data-stu-id="80efd-106">Data column</span></span>|<span data-ttu-id="80efd-107">Type</span><span class="sxs-lookup"><span data-stu-id="80efd-107">Type</span></span>|<span data-ttu-id="80efd-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80efd-108">Description</span></span>|<span data-ttu-id="80efd-109">Numero di colonna</span><span class="sxs-lookup"><span data-stu-id="80efd-109">Column number</span></span>|<span data-ttu-id="80efd-110">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="80efd-110">Filterable</span></span>|  
|-----------------|----------|-----------------|-------------------|----------------|  
|<span data-ttu-id="80efd-111">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="80efd-111">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="80efd-112">Nome dell'applicazione client in cui è stata creata la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80efd-112">The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="80efd-113">Questa colonna viene popolata con i valori passati dall'applicazione e non con il nome visualizzato del programma.</span><span class="sxs-lookup"><span data-stu-id="80efd-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="80efd-114">10</span><span class="sxs-lookup"><span data-stu-id="80efd-114">10</span></span>|<span data-ttu-id="80efd-115">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-115">Yes</span></span>|  
|<span data-ttu-id="80efd-116">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="80efd-116">ClientProcessID</span></span>|`int`|<span data-ttu-id="80efd-117">ID assegnato dal computer host al processo in cui è in esecuzione l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="80efd-117">The ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="80efd-118">Questa colonna di dati viene popolata se l'ID del processo client viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="80efd-118">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="80efd-119">9</span><span class="sxs-lookup"><span data-stu-id="80efd-119">9</span></span>|<span data-ttu-id="80efd-120">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-120">Yes</span></span>|  
|<span data-ttu-id="80efd-121">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="80efd-121">DatabaseID</span></span>|`int`|<span data-ttu-id="80efd-122">ID del database specificato dall'istruzione USE *database* oppure ID del database predefinito, se per una determinata istanza non viene eseguita alcuna istruzione USE *database*.</span><span class="sxs-lookup"><span data-stu-id="80efd-122">The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="80efd-123">viene visualizzato il nome del database se la colonna di dati ServerName viene acquisita nella traccia e il server è disponibile.</span><span class="sxs-lookup"><span data-stu-id="80efd-123">displays the name of the database if the Server Name data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="80efd-124">Determinare il valore per un database utilizzando la funzione DB_ID.</span><span class="sxs-lookup"><span data-stu-id="80efd-124">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="80efd-125">3</span><span class="sxs-lookup"><span data-stu-id="80efd-125">3</span></span>|<span data-ttu-id="80efd-126">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-126">Yes</span></span>|  
|<span data-ttu-id="80efd-127">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="80efd-127">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="80efd-128">Nome del database in cui viene eseguita l'istruzione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="80efd-128">The name of the database in which the user statement is running.</span></span>|<span data-ttu-id="80efd-129">35</span><span class="sxs-lookup"><span data-stu-id="80efd-129">35</span></span>|<span data-ttu-id="80efd-130">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-130">Yes</span></span>|  
|<span data-ttu-id="80efd-131">EventClass</span><span class="sxs-lookup"><span data-stu-id="80efd-131">EventClass</span></span>|`Int`|<span data-ttu-id="80efd-132">Tipo di evento = 200.</span><span class="sxs-lookup"><span data-stu-id="80efd-132">Type of event = 200.</span></span>|<span data-ttu-id="80efd-133">27</span><span class="sxs-lookup"><span data-stu-id="80efd-133">27</span></span>|<span data-ttu-id="80efd-134">No</span><span class="sxs-lookup"><span data-stu-id="80efd-134">No</span></span>|  
|<span data-ttu-id="80efd-135">EventSequence</span><span class="sxs-lookup"><span data-stu-id="80efd-135">EventSequence</span></span>|`int`|<span data-ttu-id="80efd-136">Numero di sequenza dell'evento.</span><span class="sxs-lookup"><span data-stu-id="80efd-136">Sequence number for this event.</span></span>|<span data-ttu-id="80efd-137">51</span><span class="sxs-lookup"><span data-stu-id="80efd-137">51</span></span>|<span data-ttu-id="80efd-138">No</span><span class="sxs-lookup"><span data-stu-id="80efd-138">No</span></span>|  
|<span data-ttu-id="80efd-139">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="80efd-139">EventSubClass</span></span>|`nvarchar`|<span data-ttu-id="80efd-140">Tipo di sottoclasse di evento in cui sono disponibili informazioni aggiuntive su ogni classe di evento.</span><span class="sxs-lookup"><span data-stu-id="80efd-140">The type of event subclass, providing further information about each event class.</span></span> <span data-ttu-id="80efd-141">Questa colonna può contenere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="80efd-141">This column may contain the following values:</span></span><br /><br /> <span data-ttu-id="80efd-142">Table created: indica che nel database è stata creata una tabella di parametri.</span><span class="sxs-lookup"><span data-stu-id="80efd-142">Table created: Indicates a parameter table has been created in the database.</span></span><br /><br /> <span data-ttu-id="80efd-143">Table drop attempt: indica che il database ha provato a eliminare automaticamente una tabella di parametri inutilizzata per liberare risorse.</span><span class="sxs-lookup"><span data-stu-id="80efd-143">Table drop attempt: Indicates that the database has attempted to automatically drop an unused parameter table to free resources.</span></span><br /><br /> <span data-ttu-id="80efd-144">Table drop attempt failed: indica che il database ha provato a eliminare una tabella di parametri inutilizzata e che l'operazione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="80efd-144">Table drop attempt failed: Indicates that the database tried to drop an unused parameter table and failed.</span></span> <span data-ttu-id="80efd-145">In [!INCLUDE[ssDE](../../includes/ssde-md.md)] verrà automaticamente ripianificata l'eliminazione della tabella di parametri per liberare risorse.</span><span class="sxs-lookup"><span data-stu-id="80efd-145">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] will automatically reschedule deletion of the parameter table to free up resources.</span></span><br /><br /> <span data-ttu-id="80efd-146">Table dropped: indica che il database ha eliminato correttamente una tabella di parametri.</span><span class="sxs-lookup"><span data-stu-id="80efd-146">Table dropped: Indicates that the database successfully dropped a parameter table.</span></span><br /><br /> <span data-ttu-id="80efd-147">Table pinned: indica che la tabella di parametri è stata contrassegnata per l'utilizzo corrente dall'elaborazione interna.</span><span class="sxs-lookup"><span data-stu-id="80efd-147">Table pinned: Indicates that the parameter table is marked for current usage by internal processing.</span></span><br /><br /> <span data-ttu-id="80efd-148">Table unpinned: indica che la tabella di parametri è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="80efd-148">Table unpinned: Indicates that the parameter table has been unpinned.</span></span> <span data-ttu-id="80efd-149">L'elaborazione interna non richiede più l'utilizzo della tabella.</span><span class="sxs-lookup"><span data-stu-id="80efd-149">Internal processing has finished using the table.</span></span><br /><br /> <span data-ttu-id="80efd-150">Number of users incremented: indica che il numero di sottoscrizioni di notifica delle query che fanno riferimento a una tabella di parametri è aumentato.</span><span class="sxs-lookup"><span data-stu-id="80efd-150">Number of users incremented: Indicates that the number of query notification subscriptions that reference a parameter table has increased.</span></span><br /><br /> <span data-ttu-id="80efd-151">Number of users decremented: indica che il numero di sottoscrizioni di notifica delle query che fanno riferimento a una tabella di parametri è diminuito.</span><span class="sxs-lookup"><span data-stu-id="80efd-151">Number of users decremented: Indicates that the number of query notification subscriptions that reference a parameter table has decreased.</span></span><br /><br /> <span data-ttu-id="80efd-152">LRU counter reset: indica che il conteggio degli utilizzi per la tabella di parametri è stato reimpostato.</span><span class="sxs-lookup"><span data-stu-id="80efd-152">LRU counter reset: Indicates that the usage count for the parameter table has been reset.</span></span><br /><br /> <span data-ttu-id="80efd-153">Cleanup task started: indica quando è stata avviata la pulizia per tutte le sottoscrizioni in questa tabella di parametri.</span><span class="sxs-lookup"><span data-stu-id="80efd-153">Cleanup task started: Indicates when cleanup for all subscriptions in this parameter table has started.</span></span> <span data-ttu-id="80efd-154">In genere, questa operazione ha inizio all'avvio del database o all'eliminazione di una tabella sottostante le sottoscrizioni di questa tabella di parametri.</span><span class="sxs-lookup"><span data-stu-id="80efd-154">This occurs when the database starts up or when a table underlying the subscriptions of this parameter table is dropped.</span></span><br /><br /> <span data-ttu-id="80efd-155">Cleanup task finished: indica quando è stata terminata la pulizia per tutte le sottoscrizioni in questa tabella di parametri.</span><span class="sxs-lookup"><span data-stu-id="80efd-155">Cleanup task finished: Indicates when cleanup for all subscriptions in this parameter table has finished.</span></span>|<span data-ttu-id="80efd-156">21</span><span class="sxs-lookup"><span data-stu-id="80efd-156">21</span></span>|<span data-ttu-id="80efd-157">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-157">Yes</span></span>|  
|<span data-ttu-id="80efd-158">GroupID</span><span class="sxs-lookup"><span data-stu-id="80efd-158">GroupID</span></span>|`int`|<span data-ttu-id="80efd-159">ID del gruppo del carico di lavoro in cui viene generato l'evento di Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="80efd-159">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="80efd-160">66</span><span class="sxs-lookup"><span data-stu-id="80efd-160">66</span></span>|<span data-ttu-id="80efd-161">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-161">Yes</span></span>|  
|<span data-ttu-id="80efd-162">HostName</span><span class="sxs-lookup"><span data-stu-id="80efd-162">HostName</span></span>|`nvarchar`|<span data-ttu-id="80efd-163">Nome del computer in cui è in esecuzione il client.</span><span class="sxs-lookup"><span data-stu-id="80efd-163">The name of the computer on which the client is running.</span></span> <span data-ttu-id="80efd-164">Questa colonna di dati viene popolata se il nome host viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="80efd-164">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="80efd-165">Per determinare il nome host, usare la funzione HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="80efd-165">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="80efd-166">8</span><span class="sxs-lookup"><span data-stu-id="80efd-166">8</span></span>|<span data-ttu-id="80efd-167">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-167">Yes</span></span>|  
|<span data-ttu-id="80efd-168">IsSystem</span><span class="sxs-lookup"><span data-stu-id="80efd-168">IsSystem</span></span>|`int`|<span data-ttu-id="80efd-169">Indica se l'evento è stato generato per un processo di sistema o un processo utente.</span><span class="sxs-lookup"><span data-stu-id="80efd-169">Indicates whether the event occurred on a system process or a user process.</span></span><br /><br /> <span data-ttu-id="80efd-170">0 = utente</span><span class="sxs-lookup"><span data-stu-id="80efd-170">0 = user</span></span><br /><br /> <span data-ttu-id="80efd-171">1 = sistema</span><span class="sxs-lookup"><span data-stu-id="80efd-171">1 = system</span></span>|<span data-ttu-id="80efd-172">60</span><span class="sxs-lookup"><span data-stu-id="80efd-172">60</span></span>|<span data-ttu-id="80efd-173">No</span><span class="sxs-lookup"><span data-stu-id="80efd-173">No</span></span>|  
|<span data-ttu-id="80efd-174">LoginName</span><span class="sxs-lookup"><span data-stu-id="80efd-174">LoginName</span></span>|`nvarchar`|<span data-ttu-id="80efd-175">Nome dell'account di accesso dell'utente (account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sicurezza di o credenziali di accesso di Windows nel formato *dominio* \\ *nomeutente*).</span><span class="sxs-lookup"><span data-stu-id="80efd-175">The name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the Windows login credentials in the form of *DOMAIN*\\*Username*).</span></span>|<span data-ttu-id="80efd-176">11</span><span class="sxs-lookup"><span data-stu-id="80efd-176">11</span></span>|<span data-ttu-id="80efd-177">No</span><span class="sxs-lookup"><span data-stu-id="80efd-177">No</span></span>|  
|<span data-ttu-id="80efd-178">LoginSID</span><span class="sxs-lookup"><span data-stu-id="80efd-178">LoginSID</span></span>|`image`|<span data-ttu-id="80efd-179">ID di sicurezza (SID) dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="80efd-179">The security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="80efd-180">Queste informazioni sono disponibili nella vista del catalogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="80efd-180">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="80efd-181">Il SID è univoco per ogni account di accesso nel server.</span><span class="sxs-lookup"><span data-stu-id="80efd-181">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="80efd-182">41</span><span class="sxs-lookup"><span data-stu-id="80efd-182">41</span></span>|<span data-ttu-id="80efd-183">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-183">Yes</span></span>|  
|<span data-ttu-id="80efd-184">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="80efd-184">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="80efd-185">Dominio di Windows a cui appartiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="80efd-185">The Windows domain to which the user belongs.</span></span>|<span data-ttu-id="80efd-186">7</span><span class="sxs-lookup"><span data-stu-id="80efd-186">7</span></span>|<span data-ttu-id="80efd-187">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-187">Yes</span></span>|  
|<span data-ttu-id="80efd-188">NTUserName</span><span class="sxs-lookup"><span data-stu-id="80efd-188">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="80efd-189">Nome dell'utente proprietario della connessione che ha generato questo evento.</span><span class="sxs-lookup"><span data-stu-id="80efd-189">The name of the user that owns the connection that generated this event.</span></span>|<span data-ttu-id="80efd-190">6</span><span class="sxs-lookup"><span data-stu-id="80efd-190">6</span></span>|<span data-ttu-id="80efd-191">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-191">Yes</span></span>|  
|<span data-ttu-id="80efd-192">RequestID</span><span class="sxs-lookup"><span data-stu-id="80efd-192">RequestID</span></span>|`int`|<span data-ttu-id="80efd-193">Identificatore della richiesta contenente l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="80efd-193">Identifier of the request that contains the statement.</span></span>|<span data-ttu-id="80efd-194">49</span><span class="sxs-lookup"><span data-stu-id="80efd-194">49</span></span>|<span data-ttu-id="80efd-195">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-195">Yes</span></span>|  
|<span data-ttu-id="80efd-196">ServerName</span><span class="sxs-lookup"><span data-stu-id="80efd-196">ServerName</span></span>|`nvarchar`|<span data-ttu-id="80efd-197">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracciata.</span><span class="sxs-lookup"><span data-stu-id="80efd-197">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="80efd-198">26</span><span class="sxs-lookup"><span data-stu-id="80efd-198">26</span></span>|<span data-ttu-id="80efd-199">No</span><span class="sxs-lookup"><span data-stu-id="80efd-199">No</span></span>|  
|<span data-ttu-id="80efd-200">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="80efd-200">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="80efd-201">Nome dell'account di accesso dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="80efd-201">Login name of the user that originated the session.</span></span> <span data-ttu-id="80efd-202">Se ad esempio un'applicazione si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'account di accesso Login1 ed esegue un'istruzione con l'account di accesso Login2, SessionLoginName indica "Login1" e LoginName indica "Login2".</span><span class="sxs-lookup"><span data-stu-id="80efd-202">For example, if an application connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and executes a statement as Login2, SessionLoginName shows "Login1" and LoginName shows "Login2".</span></span> <span data-ttu-id="80efd-203">In questa colonna sono visualizzati sia gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che quelli di Windows.</span><span class="sxs-lookup"><span data-stu-id="80efd-203">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="80efd-204">64</span><span class="sxs-lookup"><span data-stu-id="80efd-204">64</span></span>|<span data-ttu-id="80efd-205">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-205">Yes</span></span>|  
|<span data-ttu-id="80efd-206">SPID</span><span class="sxs-lookup"><span data-stu-id="80efd-206">SPID</span></span>|`int`|<span data-ttu-id="80efd-207">ID della sessione in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="80efd-207">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="80efd-208">12</span><span class="sxs-lookup"><span data-stu-id="80efd-208">12</span></span>|<span data-ttu-id="80efd-209">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-209">Yes</span></span>|  
|<span data-ttu-id="80efd-210">StartTime</span><span class="sxs-lookup"><span data-stu-id="80efd-210">StartTime</span></span>|`datetime`|<span data-ttu-id="80efd-211">Ora di inizio dell'evento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="80efd-211">Time at which the event started, if available.</span></span>|<span data-ttu-id="80efd-212">14</span><span class="sxs-lookup"><span data-stu-id="80efd-212">14</span></span>|<span data-ttu-id="80efd-213">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-213">Yes</span></span>|  
|<span data-ttu-id="80efd-214">TextData</span><span class="sxs-lookup"><span data-stu-id="80efd-214">TextData</span></span>|`ntext`|<span data-ttu-id="80efd-215">Restituisce un documento XML contenente informazioni specifiche per questo evento.</span><span class="sxs-lookup"><span data-stu-id="80efd-215">Returns an XML document containing information specific to this event.</span></span> <span data-ttu-id="80efd-216">Questo documento è conforme XML Schema disponibile nella pagina [Schema di eventi di SQL Server Profiler correlati alle notifiche delle query](https://go.microsoft.com/fwlink/?LinkId=63331) .</span><span class="sxs-lookup"><span data-stu-id="80efd-216">This document conforms to the XML schema available at the [SQL Server Query Notification Profiler Event Schema](https://go.microsoft.com/fwlink/?LinkId=63331) page.</span></span>|<span data-ttu-id="80efd-217">1</span><span class="sxs-lookup"><span data-stu-id="80efd-217">1</span></span>|<span data-ttu-id="80efd-218">Sì</span><span class="sxs-lookup"><span data-stu-id="80efd-218">Yes</span></span>|  
  
  