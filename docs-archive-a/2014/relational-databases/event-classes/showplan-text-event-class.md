---
title: Classe di evento Showplan Text | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Showplan Text event class
ms.assetid: f36c73b2-a1d1-4513-9594-78818f3fcb0d
author: stevestein
ms.author: sstein
ms.openlocfilehash: da0c24aa83c965c948365eddb9f8bd9820468579
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711980"
---
# <a name="showplan-text-event-class"></a><span data-ttu-id="afb11-102">Showplan Text - classe di evento</span><span class="sxs-lookup"><span data-stu-id="afb11-102">Showplan Text Event Class</span></span>
  <span data-ttu-id="afb11-103">La classe di evento Showplan Text viene generata quando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]esegue un'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="afb11-103">The Showplan Text event class occurs when [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executes an SQL statement.</span></span> <span data-ttu-id="afb11-104">Le informazioni incluse sono un subset delle informazioni disponibili nelle classi di evento Showplan All, Showplan XML Statistics Profile o Showplan XML.</span><span class="sxs-lookup"><span data-stu-id="afb11-104">The information included is a subset of the information available in Showplan All, Showplan XML Statistics Profile or Showplan XML event class.</span></span>  
  
 <span data-ttu-id="afb11-105">Se la classe di evento Showplan Text viene inclusa in una traccia, l'overhead ridurrà in modo significativo le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="afb11-105">When the Showplan Text event class is included in a trace, the amount of overhead will significantly impede performance.</span></span> <span data-ttu-id="afb11-106">Per ridurre al minimo tale rischio, limitare l'utilizzo di questa classe di evento alle tracce che consentono di monitorare problemi specifici per brevi periodi di tempo.</span><span class="sxs-lookup"><span data-stu-id="afb11-106">To minimize this, limit use of this event class to traces that monitor specific problems for brief periods of time.</span></span> <span data-ttu-id="afb11-107">La classe di evento Showplan Text non genererà lo stesso overhead di altre classi di eventi.</span><span class="sxs-lookup"><span data-stu-id="afb11-107">Showplan Text will not incur as much overhead as other Showplan event classes.</span></span>  
  
 <span data-ttu-id="afb11-108">Quando si include la classe di evento Showplan Text in una traccia, è necessario selezionare la colonna di dati BinaryData.</span><span class="sxs-lookup"><span data-stu-id="afb11-108">When the Showplan Text event class is included in a trace, the BinaryData data column must be selected.</span></span> <span data-ttu-id="afb11-109">In caso contrario, le informazioni relative a questa classe di evento non verranno visualizzate nella traccia.</span><span class="sxs-lookup"><span data-stu-id="afb11-109">If it is not, information for this event class will not be displayed in the trace.</span></span>  
  
## <a name="showplan-text-event-class-data-columns"></a><span data-ttu-id="afb11-110">Colonne di dati della classe di evento Showplan Text</span><span class="sxs-lookup"><span data-stu-id="afb11-110">Showplan Text Event Class Data Columns</span></span>  
  
|<span data-ttu-id="afb11-111">Nome colonna di dati</span><span class="sxs-lookup"><span data-stu-id="afb11-111">Data column name</span></span>|<span data-ttu-id="afb11-112">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="afb11-112">Data type</span></span>|<span data-ttu-id="afb11-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afb11-113">Description</span></span>|<span data-ttu-id="afb11-114">ID colonna</span><span class="sxs-lookup"><span data-stu-id="afb11-114">Column ID</span></span>|<span data-ttu-id="afb11-115">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="afb11-115">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="afb11-116">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="afb11-116">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="afb11-117">Nome dell'applicazione client in cui è stata creata la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afb11-117">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="afb11-118">Questa colonna viene popolata con i valori passati dall'applicazione e non con il nome visualizzato del programma.</span><span class="sxs-lookup"><span data-stu-id="afb11-118">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="afb11-119">10</span><span class="sxs-lookup"><span data-stu-id="afb11-119">10</span></span>|<span data-ttu-id="afb11-120">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-120">Yes</span></span>|  
|<span data-ttu-id="afb11-121">BinaryData</span><span class="sxs-lookup"><span data-stu-id="afb11-121">BinaryData</span></span>|`image`|<span data-ttu-id="afb11-122">Costo stimato del testo Showplan.</span><span class="sxs-lookup"><span data-stu-id="afb11-122">Estimated cost of the Showplan text.</span></span>|<span data-ttu-id="afb11-123">2</span><span class="sxs-lookup"><span data-stu-id="afb11-123">2</span></span>|<span data-ttu-id="afb11-124">No</span><span class="sxs-lookup"><span data-stu-id="afb11-124">No</span></span>|  
|<span data-ttu-id="afb11-125">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="afb11-125">ClientProcessID</span></span>|`int`|<span data-ttu-id="afb11-126">ID assegnato dal computer host al processo in cui è in esecuzione l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="afb11-126">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="afb11-127">Questa colonna di dati viene popolata se l'ID del processo client viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="afb11-127">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="afb11-128">9</span><span class="sxs-lookup"><span data-stu-id="afb11-128">9</span></span>|<span data-ttu-id="afb11-129">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-129">Yes</span></span>|  
|<span data-ttu-id="afb11-130">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="afb11-130">DatabaseID</span></span>|`int`|<span data-ttu-id="afb11-131">ID del database specificato nell'istruzione di *database* USE oppure il database predefinito se per un'istanza specifica l'istruzione di *database* USE non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="afb11-131">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="afb11-132">visualizza il nome del database se la colonna di dati ServerName è acquisita nella traccia e il server è disponibile.</span><span class="sxs-lookup"><span data-stu-id="afb11-132">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="afb11-133">Determinare il valore per un database utilizzando la funzione DB_ID.</span><span class="sxs-lookup"><span data-stu-id="afb11-133">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="afb11-134">3</span><span class="sxs-lookup"><span data-stu-id="afb11-134">3</span></span>|<span data-ttu-id="afb11-135">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-135">Yes</span></span>|  
|<span data-ttu-id="afb11-136">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="afb11-136">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="afb11-137">Nome del database nel quale viene eseguita l'istruzione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="afb11-137">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="afb11-138">35</span><span class="sxs-lookup"><span data-stu-id="afb11-138">35</span></span>|<span data-ttu-id="afb11-139">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-139">Yes</span></span>|  
|<span data-ttu-id="afb11-140">Event Class</span><span class="sxs-lookup"><span data-stu-id="afb11-140">Event Class</span></span>|`int`|<span data-ttu-id="afb11-141">Tipo di evento = 96.</span><span class="sxs-lookup"><span data-stu-id="afb11-141">Type of Event = 96.</span></span>|<span data-ttu-id="afb11-142">27</span><span class="sxs-lookup"><span data-stu-id="afb11-142">27</span></span>|<span data-ttu-id="afb11-143">No</span><span class="sxs-lookup"><span data-stu-id="afb11-143">No</span></span>|  
|<span data-ttu-id="afb11-144">EventSequence</span><span class="sxs-lookup"><span data-stu-id="afb11-144">EventSequence</span></span>|`int`|<span data-ttu-id="afb11-145">Sequenza di un determinato evento all'interno della richiesta.</span><span class="sxs-lookup"><span data-stu-id="afb11-145">Sequence of a given event within the request.</span></span>|<span data-ttu-id="afb11-146">51</span><span class="sxs-lookup"><span data-stu-id="afb11-146">51</span></span>|<span data-ttu-id="afb11-147">No</span><span class="sxs-lookup"><span data-stu-id="afb11-147">No</span></span>|  
|<span data-ttu-id="afb11-148">HostName</span><span class="sxs-lookup"><span data-stu-id="afb11-148">HostName</span></span>|`nvarchar`|<span data-ttu-id="afb11-149">Nome del computer in cui viene eseguito il client.</span><span class="sxs-lookup"><span data-stu-id="afb11-149">Name of the computer on which the client is running.</span></span> <span data-ttu-id="afb11-150">Questa colonna di dati viene popolata se il nome host viene fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="afb11-150">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="afb11-151">Per determinare il nome host, usare la funzione HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="afb11-151">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="afb11-152">8</span><span class="sxs-lookup"><span data-stu-id="afb11-152">8</span></span>|<span data-ttu-id="afb11-153">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-153">Yes</span></span>|  
|<span data-ttu-id="afb11-154">Integer Data</span><span class="sxs-lookup"><span data-stu-id="afb11-154">Integer Data</span></span>|`integer`|<span data-ttu-id="afb11-155">Numero stimato di righe restituite.</span><span class="sxs-lookup"><span data-stu-id="afb11-155">Estimated number of rows returned.</span></span>|<span data-ttu-id="afb11-156">25</span><span class="sxs-lookup"><span data-stu-id="afb11-156">25</span></span>|<span data-ttu-id="afb11-157">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-157">Yes</span></span>|  
|<span data-ttu-id="afb11-158">IsSystem</span><span class="sxs-lookup"><span data-stu-id="afb11-158">IsSystem</span></span>|`int`|<span data-ttu-id="afb11-159">Indica se l'evento è stato generato per un processo di sistema o un processo utente.</span><span class="sxs-lookup"><span data-stu-id="afb11-159">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="afb11-160">1 = sistema, 0 = utente.</span><span class="sxs-lookup"><span data-stu-id="afb11-160">1 = system, 0 = user.</span></span>|<span data-ttu-id="afb11-161">60</span><span class="sxs-lookup"><span data-stu-id="afb11-161">60</span></span>|<span data-ttu-id="afb11-162">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-162">Yes</span></span>|  
|<span data-ttu-id="afb11-163">LineNumber</span><span class="sxs-lookup"><span data-stu-id="afb11-163">LineNumber</span></span>|`int`|<span data-ttu-id="afb11-164">Visualizza il numero della riga contenente l'errore.</span><span class="sxs-lookup"><span data-stu-id="afb11-164">Displays the number of the line containing the error.</span></span>|<span data-ttu-id="afb11-165">5</span><span class="sxs-lookup"><span data-stu-id="afb11-165">5</span></span>|<span data-ttu-id="afb11-166">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-166">Yes</span></span>|  
|<span data-ttu-id="afb11-167">Login SID</span><span class="sxs-lookup"><span data-stu-id="afb11-167">Login SID</span></span>|`bitmap`|<span data-ttu-id="afb11-168">ID di sicurezza (SID) dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="afb11-168">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="afb11-169">Queste informazioni sono disponibili nella vista del catalogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="afb11-169">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="afb11-170">Il SID è univoco per ogni account di accesso nel server.</span><span class="sxs-lookup"><span data-stu-id="afb11-170">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="afb11-171">41</span><span class="sxs-lookup"><span data-stu-id="afb11-171">41</span></span>|<span data-ttu-id="afb11-172">No</span><span class="sxs-lookup"><span data-stu-id="afb11-172">No</span></span>|  
|<span data-ttu-id="afb11-173">LoginName</span><span class="sxs-lookup"><span data-stu-id="afb11-173">LoginName</span></span>|`nvarchar`|<span data-ttu-id="afb11-174">Nome dell'account di accesso dell'utente (account di accesso di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenziali di accesso di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows nel formato DOMINIO\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="afb11-174">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="afb11-175">11</span><span class="sxs-lookup"><span data-stu-id="afb11-175">11</span></span>|<span data-ttu-id="afb11-176">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-176">Yes</span></span>|  
|<span data-ttu-id="afb11-177">NestLevel</span><span class="sxs-lookup"><span data-stu-id="afb11-177">NestLevel</span></span>|`int`|<span data-ttu-id="afb11-178">Valore intero che rappresenta i dati restituiti da @@NESTLEVEL.</span><span class="sxs-lookup"><span data-stu-id="afb11-178">Integer representing the data returned by @@NESTLEVEL.</span></span>|<span data-ttu-id="afb11-179">29</span><span class="sxs-lookup"><span data-stu-id="afb11-179">29</span></span>|<span data-ttu-id="afb11-180">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-180">Yes</span></span>|  
|<span data-ttu-id="afb11-181">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="afb11-181">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="afb11-182">Dominio Windows di appartenenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="afb11-182">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="afb11-183">7</span><span class="sxs-lookup"><span data-stu-id="afb11-183">7</span></span>|<span data-ttu-id="afb11-184">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-184">Yes</span></span>|  
|<span data-ttu-id="afb11-185">ObjectID</span><span class="sxs-lookup"><span data-stu-id="afb11-185">ObjectID</span></span>|`int`|<span data-ttu-id="afb11-186">ID dell'oggetto assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="afb11-186">System-assigned ID of the object.</span></span>|<span data-ttu-id="afb11-187">22</span><span class="sxs-lookup"><span data-stu-id="afb11-187">22</span></span>|<span data-ttu-id="afb11-188">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-188">Yes</span></span>|  
|<span data-ttu-id="afb11-189">ObjectName</span><span class="sxs-lookup"><span data-stu-id="afb11-189">ObjectName</span></span>|`nvarchar`|<span data-ttu-id="afb11-190">Nome dell'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="afb11-190">Name of the object being referenced.</span></span>|<span data-ttu-id="afb11-191">34</span><span class="sxs-lookup"><span data-stu-id="afb11-191">34</span></span>|<span data-ttu-id="afb11-192">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-192">Yes</span></span>|  
|<span data-ttu-id="afb11-193">ObjectType</span><span class="sxs-lookup"><span data-stu-id="afb11-193">ObjectType</span></span>|`int`|<span data-ttu-id="afb11-194">Valore che rappresenta il tipo di oggetto coinvolto nell'evento.</span><span class="sxs-lookup"><span data-stu-id="afb11-194">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="afb11-195">Questo valore corrisponde alla colonna type nella tabella sys.objects.</span><span class="sxs-lookup"><span data-stu-id="afb11-195">This value corresponds to the type column in sys.objects.</span></span> <span data-ttu-id="afb11-196">Per i valori, vedere [Colonna ObjectType per gli eventi di traccia](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="afb11-196">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="afb11-197">28</span><span class="sxs-lookup"><span data-stu-id="afb11-197">28</span></span>|<span data-ttu-id="afb11-198">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-198">Yes</span></span>|  
|<span data-ttu-id="afb11-199">RequestID</span><span class="sxs-lookup"><span data-stu-id="afb11-199">RequestID</span></span>|`int`|<span data-ttu-id="afb11-200">Identificazione della richiesta che ha avviato la query full-text.</span><span class="sxs-lookup"><span data-stu-id="afb11-200">Request identification that initiated the full text query.</span></span>|<span data-ttu-id="afb11-201">49</span><span class="sxs-lookup"><span data-stu-id="afb11-201">49</span></span>|<span data-ttu-id="afb11-202">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-202">Yes</span></span>|  
|<span data-ttu-id="afb11-203">ServerName</span><span class="sxs-lookup"><span data-stu-id="afb11-203">ServerName</span></span>|`nvarchar`|<span data-ttu-id="afb11-204">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracciata.</span><span class="sxs-lookup"><span data-stu-id="afb11-204">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="afb11-205">26</span><span class="sxs-lookup"><span data-stu-id="afb11-205">26</span></span>|<span data-ttu-id="afb11-206">No</span><span class="sxs-lookup"><span data-stu-id="afb11-206">No</span></span>|  
|<span data-ttu-id="afb11-207">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="afb11-207">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="afb11-208">Nome dell'account di accesso dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="afb11-208">Login name of the user who originated the session.</span></span> <span data-ttu-id="afb11-209">Se ad esempio si stabilisce la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'account di accesso Login1 e si esegue un'istruzione con l'account di accesso Login2, SessionLoginName indica Login1 e LoginName indica Login2.</span><span class="sxs-lookup"><span data-stu-id="afb11-209">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="afb11-210">In questa colonna sono visualizzati sia gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che quelli di Windows.</span><span class="sxs-lookup"><span data-stu-id="afb11-210">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="afb11-211">64</span><span class="sxs-lookup"><span data-stu-id="afb11-211">64</span></span>|<span data-ttu-id="afb11-212">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-212">Yes</span></span>|  
|<span data-ttu-id="afb11-213">SPID</span><span class="sxs-lookup"><span data-stu-id="afb11-213">SPID</span></span>|`int`|<span data-ttu-id="afb11-214">ID della sessione in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="afb11-214">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="afb11-215">12</span><span class="sxs-lookup"><span data-stu-id="afb11-215">12</span></span>|<span data-ttu-id="afb11-216">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-216">Yes</span></span>|  
|<span data-ttu-id="afb11-217">StartTime</span><span class="sxs-lookup"><span data-stu-id="afb11-217">StartTime</span></span>|`datetime`|<span data-ttu-id="afb11-218">Ora di inizio dell'evento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="afb11-218">Time at which the event started, if available.</span></span>|<span data-ttu-id="afb11-219">14</span><span class="sxs-lookup"><span data-stu-id="afb11-219">14</span></span>|<span data-ttu-id="afb11-220">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-220">Yes</span></span>|  
|<span data-ttu-id="afb11-221">TransactionID</span><span class="sxs-lookup"><span data-stu-id="afb11-221">TransactionID</span></span>|`bigint`|<span data-ttu-id="afb11-222">ID della transazione assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="afb11-222">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="afb11-223">4</span><span class="sxs-lookup"><span data-stu-id="afb11-223">4</span></span>|<span data-ttu-id="afb11-224">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-224">Yes</span></span>|  
|<span data-ttu-id="afb11-225">XactSequence</span><span class="sxs-lookup"><span data-stu-id="afb11-225">XactSequence</span></span>|`bigint`|<span data-ttu-id="afb11-226">Token usato per descrivere la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="afb11-226">Token used to describe the current transaction.</span></span>|<span data-ttu-id="afb11-227">50</span><span class="sxs-lookup"><span data-stu-id="afb11-227">50</span></span>|<span data-ttu-id="afb11-228">Sì</span><span class="sxs-lookup"><span data-stu-id="afb11-228">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afb11-229">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afb11-229">See Also</span></span>  
 <span data-ttu-id="afb11-230">[Eventi estesi](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="afb11-230">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="afb11-231">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="afb11-231">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="afb11-232">[Guida di riferimento a operatori Showplan logici e fisici](../showplan-logical-and-physical-operators-reference.md) </span><span class="sxs-lookup"><span data-stu-id="afb11-232">[Showplan Logical and Physical Operators Reference](../showplan-logical-and-physical-operators-reference.md) </span></span>  
 <span data-ttu-id="afb11-233">[Showplan All-classe di evento](showplan-all-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="afb11-233">[Showplan All Event Class](showplan-all-event-class.md) </span></span>  
 <span data-ttu-id="afb11-234">[Showplan XML Statistics Profile-classe di evento](showplan-xml-statistics-profile-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="afb11-234">[Showplan XML Statistics Profile Event Class](showplan-xml-statistics-profile-event-class.md) </span></span>  
 [<span data-ttu-id="afb11-235">Classe di evento Showplan XML</span><span class="sxs-lookup"><span data-stu-id="afb11-235">Showplan XML Event Class</span></span>](showplan-xml-event-class.md)  
  
  