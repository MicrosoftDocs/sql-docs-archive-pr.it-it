---
title: Classe di evento Showplan Statistics Profile | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Showplan Statistics Profile event class
ms.assetid: fa9e1330-a217-491c-ad7c-2c1c4015d1bb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 393f30252d2689deb63d1bd540d6db3673f84f73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637857"
---
# <a name="showplan-statistics-profile-event-class"></a><span data-ttu-id="f835a-102">Showplan Statistics Profile - classe di evento</span><span class="sxs-lookup"><span data-stu-id="f835a-102">Showplan Statistics Profile Event Class</span></span>
  <span data-ttu-id="f835a-103">La classe di evento Showplan Statistics Profile viene generata quando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esegue un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="f835a-103">The Showplan Statistics Profile event class occurs when [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an SQL statement.</span></span> <span data-ttu-id="f835a-104">Le informazioni incluse sono tuttavia un sottoinsieme delle informazioni disponibili nelle classi di evento Showplan XML Statistics.</span><span class="sxs-lookup"><span data-stu-id="f835a-104">The information included is a subset of the information available in the Showplan XML Statistics Profile event class.</span></span>  
  
 <span data-ttu-id="f835a-105">Nella classe di evento Showplan Statistics Profile vengono visualizzati i dati completi della fase di compilazione e le tracce che contengono Showplan Statistics Profile possono causare una riduzione significativa delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f835a-105">The Showplan Statistics Profile event class displays complete compile-time data; traces that contain Showplan Statistics Profile may incur significant performance overhead.</span></span> <span data-ttu-id="f835a-106">Per ridurre al minimo tale rischio, limitare l'utilizzo di questa classe di evento alle tracce che consentono di monitorare problemi specifici per brevi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="f835a-106">To minimize this, limit use of this event class to traces monitoring specific problems for brief periods of time.</span></span>  
  
 <span data-ttu-id="f835a-107">Quando si include la classe di evento Showplan Statistics Profile in una traccia, è necessario selezionare la colonna di dati BinaryData.</span><span class="sxs-lookup"><span data-stu-id="f835a-107">When the Showplan Statistics Profile event class is included in a trace, the BinaryData data column must be selected.</span></span> <span data-ttu-id="f835a-108">In caso contrario, le informazioni relative a questa classe di evento non verranno visualizzate nella traccia.</span><span class="sxs-lookup"><span data-stu-id="f835a-108">If it is not, information for this event class will not be displayed in the trace.</span></span>  
  
## <a name="showplan-statistics-profile-event-class-data-columns"></a><span data-ttu-id="f835a-109">Colonne di dati della classe di evento Showplan Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="f835a-109">Showplan Statistics Profile Event Class Data Columns</span></span>  
  
|<span data-ttu-id="f835a-110">Nome colonna di dati</span><span class="sxs-lookup"><span data-stu-id="f835a-110">Data column name</span></span>|<span data-ttu-id="f835a-111">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f835a-111">Data type</span></span>|<span data-ttu-id="f835a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f835a-112">Description</span></span>|<span data-ttu-id="f835a-113">ID colonna</span><span class="sxs-lookup"><span data-stu-id="f835a-113">Column ID</span></span>|<span data-ttu-id="f835a-114">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="f835a-114">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="f835a-115">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="f835a-115">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="f835a-116">Nome dell'applicazione client in cui è stata creata la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f835a-116">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f835a-117">Questa colonna viene popolata con i valori passati dall'applicazione e non con il nome visualizzato del programma.</span><span class="sxs-lookup"><span data-stu-id="f835a-117">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="f835a-118">10</span><span class="sxs-lookup"><span data-stu-id="f835a-118">10</span></span>|<span data-ttu-id="f835a-119">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-119">Yes</span></span>|  
|<span data-ttu-id="f835a-120">BinaryData</span><span class="sxs-lookup"><span data-stu-id="f835a-120">BinaryData</span></span>|`image`|<span data-ttu-id="f835a-121">Costo stimato della query.</span><span class="sxs-lookup"><span data-stu-id="f835a-121">Estimated cost of the query.</span></span>|<span data-ttu-id="f835a-122">2</span><span class="sxs-lookup"><span data-stu-id="f835a-122">2</span></span>|<span data-ttu-id="f835a-123">No</span><span class="sxs-lookup"><span data-stu-id="f835a-123">No</span></span>|  
|<span data-ttu-id="f835a-124">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="f835a-124">ClientProcessID</span></span>|`int`|<span data-ttu-id="f835a-125">ID assegnato dal computer host al processo in cui è in esecuzione l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="f835a-125">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="f835a-126">Questa colonna di dati viene popolata se l'ID del processo client viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="f835a-126">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="f835a-127">9</span><span class="sxs-lookup"><span data-stu-id="f835a-127">9</span></span>|<span data-ttu-id="f835a-128">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-128">Yes</span></span>|  
|<span data-ttu-id="f835a-129">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="f835a-129">DatabaseID</span></span>|`int`|<span data-ttu-id="f835a-130">ID del database specificato nell'istruzione di *database* USE oppure il database predefinito se per un'istanza specifica l'istruzione di *database* USE non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="f835a-130">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="f835a-131">visualizza il nome del database se la colonna di dati ServerName è acquisita nella traccia e il server è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f835a-131">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="f835a-132">Determinare il valore per un database utilizzando la funzione DB_ID.</span><span class="sxs-lookup"><span data-stu-id="f835a-132">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="f835a-133">3</span><span class="sxs-lookup"><span data-stu-id="f835a-133">3</span></span>|<span data-ttu-id="f835a-134">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-134">Yes</span></span>|  
|<span data-ttu-id="f835a-135">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="f835a-135">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="f835a-136">Nome del database nel quale viene eseguita l'istruzione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f835a-136">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="f835a-137">35</span><span class="sxs-lookup"><span data-stu-id="f835a-137">35</span></span>|<span data-ttu-id="f835a-138">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-138">Yes</span></span>|  
|<span data-ttu-id="f835a-139">EventClass</span><span class="sxs-lookup"><span data-stu-id="f835a-139">EventClass</span></span>|`int`|<span data-ttu-id="f835a-140">Tipo di evento = 98.</span><span class="sxs-lookup"><span data-stu-id="f835a-140">Type of Event = 98.</span></span>|<span data-ttu-id="f835a-141">27</span><span class="sxs-lookup"><span data-stu-id="f835a-141">27</span></span>|<span data-ttu-id="f835a-142">No</span><span class="sxs-lookup"><span data-stu-id="f835a-142">No</span></span>|  
|<span data-ttu-id="f835a-143">EventSequence</span><span class="sxs-lookup"><span data-stu-id="f835a-143">EventSequence</span></span>|`int`|<span data-ttu-id="f835a-144">Sequenza di un determinato evento all'interno della richiesta.</span><span class="sxs-lookup"><span data-stu-id="f835a-144">Sequence of a given event within the request.</span></span>|<span data-ttu-id="f835a-145">51</span><span class="sxs-lookup"><span data-stu-id="f835a-145">51</span></span>|<span data-ttu-id="f835a-146">No</span><span class="sxs-lookup"><span data-stu-id="f835a-146">No</span></span>|  
|<span data-ttu-id="f835a-147">GroupID</span><span class="sxs-lookup"><span data-stu-id="f835a-147">GroupID</span></span>|`int`|<span data-ttu-id="f835a-148">ID del gruppo del carico di lavoro in cui viene generato l'evento di Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="f835a-148">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="f835a-149">66</span><span class="sxs-lookup"><span data-stu-id="f835a-149">66</span></span>|<span data-ttu-id="f835a-150">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-150">Yes</span></span>|  
|<span data-ttu-id="f835a-151">HostName</span><span class="sxs-lookup"><span data-stu-id="f835a-151">HostName</span></span>|`nvarchar`|<span data-ttu-id="f835a-152">Nome del computer in cui viene eseguito il client.</span><span class="sxs-lookup"><span data-stu-id="f835a-152">Name of the computer on which the client is running.</span></span> <span data-ttu-id="f835a-153">Questa colonna di dati viene popolata se il nome host viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="f835a-153">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="f835a-154">Per determinare il nome host, usare la funzione HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="f835a-154">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="f835a-155">8</span><span class="sxs-lookup"><span data-stu-id="f835a-155">8</span></span>|<span data-ttu-id="f835a-156">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-156">Yes</span></span>|  
|<span data-ttu-id="f835a-157">IntegerData</span><span class="sxs-lookup"><span data-stu-id="f835a-157">IntegerData</span></span>|`int`|<span data-ttu-id="f835a-158">Numero stimato di righe restituite.</span><span class="sxs-lookup"><span data-stu-id="f835a-158">Estimated number of rows returned.</span></span>|<span data-ttu-id="f835a-159">25</span><span class="sxs-lookup"><span data-stu-id="f835a-159">25</span></span>|<span data-ttu-id="f835a-160">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-160">Yes</span></span>|  
|<span data-ttu-id="f835a-161">IsSystem</span><span class="sxs-lookup"><span data-stu-id="f835a-161">IsSystem</span></span>|`int`|<span data-ttu-id="f835a-162">Indica se l'evento è stato generato per un processo di sistema o un processo utente.</span><span class="sxs-lookup"><span data-stu-id="f835a-162">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="f835a-163">1 = sistema, 0 = utente.</span><span class="sxs-lookup"><span data-stu-id="f835a-163">1 = system, 0 = user.</span></span>|<span data-ttu-id="f835a-164">60</span><span class="sxs-lookup"><span data-stu-id="f835a-164">60</span></span>|<span data-ttu-id="f835a-165">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-165">Yes</span></span>|  
|<span data-ttu-id="f835a-166">LineNumber</span><span class="sxs-lookup"><span data-stu-id="f835a-166">LineNumber</span></span>|`int`|<span data-ttu-id="f835a-167">Visualizza il numero della riga contenente l'errore.</span><span class="sxs-lookup"><span data-stu-id="f835a-167">Displays the number of the line containing the error.</span></span>|<span data-ttu-id="f835a-168">5</span><span class="sxs-lookup"><span data-stu-id="f835a-168">5</span></span>|<span data-ttu-id="f835a-169">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-169">Yes</span></span>|  
|<span data-ttu-id="f835a-170">LoginName</span><span class="sxs-lookup"><span data-stu-id="f835a-170">LoginName</span></span>|`nvarchar`|<span data-ttu-id="f835a-171">Nome dell'account di accesso dell'utente (account di accesso di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenziali di accesso di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows nel formato DOMINIO\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="f835a-171">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="f835a-172">11</span><span class="sxs-lookup"><span data-stu-id="f835a-172">11</span></span>|<span data-ttu-id="f835a-173">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-173">Yes</span></span>|  
|<span data-ttu-id="f835a-174">LoginSID</span><span class="sxs-lookup"><span data-stu-id="f835a-174">LoginSID</span></span>|`image`|<span data-ttu-id="f835a-175">ID di sicurezza (SID) dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="f835a-175">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="f835a-176">Queste informazioni sono disponibili nella vista del catalogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="f835a-176">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="f835a-177">Il SID è univoco per ogni account di accesso nel server.</span><span class="sxs-lookup"><span data-stu-id="f835a-177">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="f835a-178">41</span><span class="sxs-lookup"><span data-stu-id="f835a-178">41</span></span>|<span data-ttu-id="f835a-179">No</span><span class="sxs-lookup"><span data-stu-id="f835a-179">No</span></span>|  
|<span data-ttu-id="f835a-180">NestLevel</span><span class="sxs-lookup"><span data-stu-id="f835a-180">NestLevel</span></span>|`int`|<span data-ttu-id="f835a-181">Valore intero che rappresenta i dati restituiti da @@NESTLEVEL.</span><span class="sxs-lookup"><span data-stu-id="f835a-181">Integer representing the data returned by @@NESTLEVEL.</span></span>|<span data-ttu-id="f835a-182">29</span><span class="sxs-lookup"><span data-stu-id="f835a-182">29</span></span>|<span data-ttu-id="f835a-183">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-183">Yes</span></span>|  
|<span data-ttu-id="f835a-184">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="f835a-184">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="f835a-185">Dominio Windows di appartenenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f835a-185">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="f835a-186">7</span><span class="sxs-lookup"><span data-stu-id="f835a-186">7</span></span>|<span data-ttu-id="f835a-187">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-187">Yes</span></span>|  
|<span data-ttu-id="f835a-188">ObjectID</span><span class="sxs-lookup"><span data-stu-id="f835a-188">ObjectID</span></span>|`int`|<span data-ttu-id="f835a-189">ID dell'oggetto assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f835a-189">System-assigned ID of the object.</span></span>|<span data-ttu-id="f835a-190">22</span><span class="sxs-lookup"><span data-stu-id="f835a-190">22</span></span>|<span data-ttu-id="f835a-191">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-191">Yes</span></span>|  
|<span data-ttu-id="f835a-192">ObjectName</span><span class="sxs-lookup"><span data-stu-id="f835a-192">ObjectName</span></span>|`nvarchar`|<span data-ttu-id="f835a-193">Nome dell'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="f835a-193">Name of the object being referenced.</span></span>|<span data-ttu-id="f835a-194">34</span><span class="sxs-lookup"><span data-stu-id="f835a-194">34</span></span>|<span data-ttu-id="f835a-195">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-195">Yes</span></span>|  
|<span data-ttu-id="f835a-196">ObjectType</span><span class="sxs-lookup"><span data-stu-id="f835a-196">ObjectType</span></span>|`int`|<span data-ttu-id="f835a-197">Valore che rappresenta il tipo di oggetto coinvolto nell'evento.</span><span class="sxs-lookup"><span data-stu-id="f835a-197">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="f835a-198">Questo valore corrisponde alla colonna type nella tabella sys.objects.</span><span class="sxs-lookup"><span data-stu-id="f835a-198">This value corresponds to the type column in sys.objects.</span></span> <span data-ttu-id="f835a-199">Per i valori, vedere [Colonna ObjectType per gli eventi di traccia](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="f835a-199">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="f835a-200">28</span><span class="sxs-lookup"><span data-stu-id="f835a-200">28</span></span>|<span data-ttu-id="f835a-201">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-201">Yes</span></span>|  
|<span data-ttu-id="f835a-202">RequestID</span><span class="sxs-lookup"><span data-stu-id="f835a-202">RequestID</span></span>|`int`|<span data-ttu-id="f835a-203">ID della richiesta contenente l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f835a-203">ID of the request containing the statement.</span></span>|<span data-ttu-id="f835a-204">49</span><span class="sxs-lookup"><span data-stu-id="f835a-204">49</span></span>|<span data-ttu-id="f835a-205">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-205">Yes</span></span>|  
|<span data-ttu-id="f835a-206">ServerName</span><span class="sxs-lookup"><span data-stu-id="f835a-206">ServerName</span></span>|`nvarchar`|<span data-ttu-id="f835a-207">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracciata.</span><span class="sxs-lookup"><span data-stu-id="f835a-207">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="f835a-208">26</span><span class="sxs-lookup"><span data-stu-id="f835a-208">26</span></span>|<span data-ttu-id="f835a-209">No</span><span class="sxs-lookup"><span data-stu-id="f835a-209">No</span></span>|  
|<span data-ttu-id="f835a-210">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="f835a-210">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="f835a-211">Nome dell'account di accesso dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="f835a-211">Login name of the user who originated the session.</span></span> <span data-ttu-id="f835a-212">Se ad esempio si stabilisce la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'account di accesso Login1 e si esegue un'istruzione con l'account di accesso Login2, SessionLoginName indica Login1 e LoginName indica Login2.</span><span class="sxs-lookup"><span data-stu-id="f835a-212">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="f835a-213">In questa colonna sono visualizzati sia gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che quelli di Windows.</span><span class="sxs-lookup"><span data-stu-id="f835a-213">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="f835a-214">64</span><span class="sxs-lookup"><span data-stu-id="f835a-214">64</span></span>|<span data-ttu-id="f835a-215">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-215">Yes</span></span>|  
|<span data-ttu-id="f835a-216">SPID</span><span class="sxs-lookup"><span data-stu-id="f835a-216">SPID</span></span>|`int`|<span data-ttu-id="f835a-217">ID della sessione in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="f835a-217">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="f835a-218">12</span><span class="sxs-lookup"><span data-stu-id="f835a-218">12</span></span>|<span data-ttu-id="f835a-219">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-219">Yes</span></span>|  
|<span data-ttu-id="f835a-220">StartTime</span><span class="sxs-lookup"><span data-stu-id="f835a-220">StartTime</span></span>|`datetime`|<span data-ttu-id="f835a-221">Ora di inizio dell'evento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="f835a-221">Time at which the event started, if available.</span></span>|<span data-ttu-id="f835a-222">14</span><span class="sxs-lookup"><span data-stu-id="f835a-222">14</span></span>|<span data-ttu-id="f835a-223">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-223">Yes</span></span>|  
|<span data-ttu-id="f835a-224">TransactionID</span><span class="sxs-lookup"><span data-stu-id="f835a-224">TransactionID</span></span>|`bigint`|<span data-ttu-id="f835a-225">ID della transazione assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="f835a-225">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="f835a-226">4</span><span class="sxs-lookup"><span data-stu-id="f835a-226">4</span></span>|<span data-ttu-id="f835a-227">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-227">Yes</span></span>|  
|<span data-ttu-id="f835a-228">XactSequence</span><span class="sxs-lookup"><span data-stu-id="f835a-228">XactSequence</span></span>|`bigint`|<span data-ttu-id="f835a-229">Token usato per descrivere la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="f835a-229">Token used to describe the current transaction.</span></span>|<span data-ttu-id="f835a-230">50</span><span class="sxs-lookup"><span data-stu-id="f835a-230">50</span></span>|<span data-ttu-id="f835a-231">Sì</span><span class="sxs-lookup"><span data-stu-id="f835a-231">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f835a-232">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f835a-232">See Also</span></span>  
 <span data-ttu-id="f835a-233">[Eventi estesi](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="f835a-233">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="f835a-234">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f835a-234">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="f835a-235">[Guida di riferimento a operatori Showplan logici e fisici](../showplan-logical-and-physical-operators-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f835a-235">[Showplan Logical and Physical Operators Reference](../showplan-logical-and-physical-operators-reference.md) </span></span>  
 [<span data-ttu-id="f835a-236">Classe di evento Showplan XML Statistics Profile</span><span class="sxs-lookup"><span data-stu-id="f835a-236">Showplan XML Statistics Profile Event Class</span></span>](showplan-xml-statistics-profile-event-class.md)  
  
  