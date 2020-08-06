---
title: Classe di evento SP:StmtCompleted | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SP:StmtCompleted event class
ms.assetid: 9e8147a4-aeeb-49a6-80f8-df753d0f34cc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0d1b0daf439816b2a5ee9ba852b95f0628d2c863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637361"
---
# <a name="spstmtcompleted-event-class"></a><span data-ttu-id="539d4-102">SP:StmtCompleted - classe di evento</span><span class="sxs-lookup"><span data-stu-id="539d4-102">SP:StmtCompleted Event Class</span></span>
  <span data-ttu-id="539d4-103">La classe di evento SP:StmtCompleted indica che è stata completata un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] all'interno di una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="539d4-103">The SP:StmtCompleted event class indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>  
  
## <a name="spstmtcompleted-event-class-data-columns"></a><span data-ttu-id="539d4-104">Colonne di dati della classe di evento SP:StmtCompleted</span><span class="sxs-lookup"><span data-stu-id="539d4-104">SP:StmtCompleted Event Class Data Columns</span></span>  
  
|<span data-ttu-id="539d4-105">Nome colonna di dati</span><span class="sxs-lookup"><span data-stu-id="539d4-105">Data column name</span></span>|`Data type`|<span data-ttu-id="539d4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="539d4-106">Description</span></span>|<span data-ttu-id="539d4-107">ID colonna</span><span class="sxs-lookup"><span data-stu-id="539d4-107">Column ID</span></span>|<span data-ttu-id="539d4-108">Filtrabile</span><span class="sxs-lookup"><span data-stu-id="539d4-108">Filterable</span></span>|  
|----------------------|-------------------|-----------------|---------------|----------------|  
|<span data-ttu-id="539d4-109">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="539d4-109">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="539d4-110">Nome dell'applicazione client in cui è stata creata la connessione a un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="539d4-110">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="539d4-111">Questa colonna viene popolata con i valori passati dall'applicazione e non con il nome visualizzato del programma.</span><span class="sxs-lookup"><span data-stu-id="539d4-111">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="539d4-112">10</span><span class="sxs-lookup"><span data-stu-id="539d4-112">10</span></span>|<span data-ttu-id="539d4-113">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-113">Yes</span></span>|  
|<span data-ttu-id="539d4-114">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="539d4-114">ClientProcessID</span></span>|`int`|<span data-ttu-id="539d4-115">ID assegnato dal computer host al processo in cui è in esecuzione l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="539d4-115">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="539d4-116">Questa colonna di dati viene popolata se tramite il client viene indicato l'ID del processo client.</span><span class="sxs-lookup"><span data-stu-id="539d4-116">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="539d4-117">9</span><span class="sxs-lookup"><span data-stu-id="539d4-117">9</span></span>|<span data-ttu-id="539d4-118">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-118">Yes</span></span>|  
|<span data-ttu-id="539d4-119">CPU</span><span class="sxs-lookup"><span data-stu-id="539d4-119">CPU</span></span>|`int`|<span data-ttu-id="539d4-120">Tempo della CPU in millisecondi utilizzato dall'evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-120">Amount of CPU time (in milliseconds) used by the event.</span></span>|<span data-ttu-id="539d4-121">18</span><span class="sxs-lookup"><span data-stu-id="539d4-121">18</span></span>|<span data-ttu-id="539d4-122">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-122">Yes</span></span>|  
|<span data-ttu-id="539d4-123">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="539d4-123">DatabaseID</span></span>|`int`|<span data-ttu-id="539d4-124">ID del database nel quale viene eseguita la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="539d4-124">ID of the database in which the stored procedure is running.</span></span> <span data-ttu-id="539d4-125">Determinare il valore per un database utilizzando la funzione DB_ID.</span><span class="sxs-lookup"><span data-stu-id="539d4-125">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="539d4-126">3</span><span class="sxs-lookup"><span data-stu-id="539d4-126">3</span></span>|<span data-ttu-id="539d4-127">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-127">Yes</span></span>|  
|<span data-ttu-id="539d4-128">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="539d4-128">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="539d4-129">Nome del database nel quale viene eseguita la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="539d4-129">Name of the database in which the stored procedure is running.</span></span>|<span data-ttu-id="539d4-130">35</span><span class="sxs-lookup"><span data-stu-id="539d4-130">35</span></span>|<span data-ttu-id="539d4-131">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-131">Yes</span></span>|  
|<span data-ttu-id="539d4-132">Duration</span><span class="sxs-lookup"><span data-stu-id="539d4-132">Duration</span></span>|`bigint`|<span data-ttu-id="539d4-133">Durata dell'evento in microsecondi.</span><span class="sxs-lookup"><span data-stu-id="539d4-133">Amount of time (in microseconds) taken by the event.</span></span>|<span data-ttu-id="539d4-134">13</span><span class="sxs-lookup"><span data-stu-id="539d4-134">13</span></span>|<span data-ttu-id="539d4-135">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-135">Yes</span></span>|  
|<span data-ttu-id="539d4-136">EndTime</span><span class="sxs-lookup"><span data-stu-id="539d4-136">EndTime</span></span>|`datetime`|<span data-ttu-id="539d4-137">Ora di fine dell'evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-137">Time at which the event ended.</span></span> <span data-ttu-id="539d4-138">Questa colonna non viene popolata per le classi degli eventi di avvio, ad esempio SQL:BatchStarting o SP:Starting.</span><span class="sxs-lookup"><span data-stu-id="539d4-138">This column is not populated for starting event classes, such as SQL:BatchStarting or SP:Starting.</span></span>|<span data-ttu-id="539d4-139">15</span><span class="sxs-lookup"><span data-stu-id="539d4-139">15</span></span>|<span data-ttu-id="539d4-140">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-140">Yes</span></span>|  
|<span data-ttu-id="539d4-141">EventClass</span><span class="sxs-lookup"><span data-stu-id="539d4-141">EventClass</span></span>|`int`|<span data-ttu-id="539d4-142">Tipo di evento = 45.</span><span class="sxs-lookup"><span data-stu-id="539d4-142">Type of event = 45.</span></span>|<span data-ttu-id="539d4-143">27</span><span class="sxs-lookup"><span data-stu-id="539d4-143">27</span></span>|<span data-ttu-id="539d4-144">No</span><span class="sxs-lookup"><span data-stu-id="539d4-144">No</span></span>|  
|<span data-ttu-id="539d4-145">EventSequence</span><span class="sxs-lookup"><span data-stu-id="539d4-145">EventSequence</span></span>|`int`|<span data-ttu-id="539d4-146">Sequenza di un determinato evento all'interno della richiesta.</span><span class="sxs-lookup"><span data-stu-id="539d4-146">Sequence of a given event within the request.</span></span>|<span data-ttu-id="539d4-147">51</span><span class="sxs-lookup"><span data-stu-id="539d4-147">51</span></span>|<span data-ttu-id="539d4-148">No</span><span class="sxs-lookup"><span data-stu-id="539d4-148">No</span></span>|  
|<span data-ttu-id="539d4-149">GroupID</span><span class="sxs-lookup"><span data-stu-id="539d4-149">GroupID</span></span>|`int`|<span data-ttu-id="539d4-150">ID del gruppo del carico di lavoro in cui viene generato l'evento di Traccia SQL.</span><span class="sxs-lookup"><span data-stu-id="539d4-150">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="539d4-151">66</span><span class="sxs-lookup"><span data-stu-id="539d4-151">66</span></span>|<span data-ttu-id="539d4-152">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-152">Yes</span></span>|  
|<span data-ttu-id="539d4-153">HostName</span><span class="sxs-lookup"><span data-stu-id="539d4-153">HostName</span></span>|`nvarchar`|<span data-ttu-id="539d4-154">Nome del computer in cui viene eseguito il client.</span><span class="sxs-lookup"><span data-stu-id="539d4-154">Name of the computer on which the client is running.</span></span> <span data-ttu-id="539d4-155">Questa colonna di dati viene popolata se il client fornisce il nome host.</span><span class="sxs-lookup"><span data-stu-id="539d4-155">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="539d4-156">Per determinare il nome host, usare la funzione HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="539d4-156">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="539d4-157">8</span><span class="sxs-lookup"><span data-stu-id="539d4-157">8</span></span>|<span data-ttu-id="539d4-158">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-158">Yes</span></span>|  
|<span data-ttu-id="539d4-159">IntegerData</span><span class="sxs-lookup"><span data-stu-id="539d4-159">IntegerData</span></span>|`int`|<span data-ttu-id="539d4-160">Valore integer che dipende dalla classe di evento acquisita nella traccia.</span><span class="sxs-lookup"><span data-stu-id="539d4-160">Integer value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="539d4-161">25</span><span class="sxs-lookup"><span data-stu-id="539d4-161">25</span></span>|<span data-ttu-id="539d4-162">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-162">Yes</span></span>|  
|<span data-ttu-id="539d4-163">IntegerData2</span><span class="sxs-lookup"><span data-stu-id="539d4-163">IntegerData2</span></span>|`int`|<span data-ttu-id="539d4-164">Offset finale (in byte) dell'istruzione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="539d4-164">End offset (in bytes) of the statement that is being executed.</span></span>|<span data-ttu-id="539d4-165">55</span><span class="sxs-lookup"><span data-stu-id="539d4-165">55</span></span>|<span data-ttu-id="539d4-166">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-166">Yes</span></span>|  
|<span data-ttu-id="539d4-167">IsSystem</span><span class="sxs-lookup"><span data-stu-id="539d4-167">IsSystem</span></span>|`int`|<span data-ttu-id="539d4-168">Indica se l'evento è stato generato per un processo di sistema o un processo utente.</span><span class="sxs-lookup"><span data-stu-id="539d4-168">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="539d4-169">1 = sistema, 0 = utente.</span><span class="sxs-lookup"><span data-stu-id="539d4-169">1 = system, 0 = user.</span></span>|<span data-ttu-id="539d4-170">60</span><span class="sxs-lookup"><span data-stu-id="539d4-170">60</span></span>|<span data-ttu-id="539d4-171">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-171">Yes</span></span>|  
|<span data-ttu-id="539d4-172">LineNumber</span><span class="sxs-lookup"><span data-stu-id="539d4-172">LineNumber</span></span>|`int`|<span data-ttu-id="539d4-173">Numero di riga dell'istruzione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="539d4-173">Line number of the statement being executed.</span></span>|<span data-ttu-id="539d4-174">5</span><span class="sxs-lookup"><span data-stu-id="539d4-174">5</span></span>|<span data-ttu-id="539d4-175">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-175">Yes</span></span>|  
|<span data-ttu-id="539d4-176">LoginName</span><span class="sxs-lookup"><span data-stu-id="539d4-176">LoginName</span></span>|`nvarchar`|<span data-ttu-id="539d4-177">Nome dell'account di accesso dell'utente (account di accesso di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenziali di accesso di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows nel formato DOMINIO\nomeutente).</span><span class="sxs-lookup"><span data-stu-id="539d4-177">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="539d4-178">11</span><span class="sxs-lookup"><span data-stu-id="539d4-178">11</span></span>|<span data-ttu-id="539d4-179">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-179">Yes</span></span>|  
|<span data-ttu-id="539d4-180">LoginSid</span><span class="sxs-lookup"><span data-stu-id="539d4-180">LoginSid</span></span>|`image`|<span data-ttu-id="539d4-181">ID di sicurezza (SID) dell'utente connesso.</span><span class="sxs-lookup"><span data-stu-id="539d4-181">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="539d4-182">Queste informazioni sono disponibili nella vista del catalogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="539d4-182">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="539d4-183">Il SID è univoco per ogni account di accesso nel server.</span><span class="sxs-lookup"><span data-stu-id="539d4-183">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="539d4-184">41</span><span class="sxs-lookup"><span data-stu-id="539d4-184">41</span></span>|<span data-ttu-id="539d4-185">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-185">Yes</span></span>|  
|<span data-ttu-id="539d4-186">NestLevel</span><span class="sxs-lookup"><span data-stu-id="539d4-186">NestLevel</span></span>|`int`|<span data-ttu-id="539d4-187">Valore intero che rappresenta i dati restituiti da @@NESTLEVEL.</span><span class="sxs-lookup"><span data-stu-id="539d4-187">Integer representing the data returned by @@NESTLEVEL.</span></span>|<span data-ttu-id="539d4-188">29</span><span class="sxs-lookup"><span data-stu-id="539d4-188">29</span></span>|<span data-ttu-id="539d4-189">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-189">Yes</span></span>|  
|<span data-ttu-id="539d4-190">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="539d4-190">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="539d4-191">Dominio Windows di appartenenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="539d4-191">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="539d4-192">7</span><span class="sxs-lookup"><span data-stu-id="539d4-192">7</span></span>|<span data-ttu-id="539d4-193">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-193">Yes</span></span>|  
|<span data-ttu-id="539d4-194">NTUserName</span><span class="sxs-lookup"><span data-stu-id="539d4-194">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="539d4-195">Nome utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="539d4-195">Windows user name.</span></span>|<span data-ttu-id="539d4-196">6</span><span class="sxs-lookup"><span data-stu-id="539d4-196">6</span></span>|<span data-ttu-id="539d4-197">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-197">Yes</span></span>|  
|<span data-ttu-id="539d4-198">ObjectID</span><span class="sxs-lookup"><span data-stu-id="539d4-198">ObjectID</span></span>|`int`|<span data-ttu-id="539d4-199">ID dell'oggetto assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="539d4-199">System-assigned ID of the object.</span></span>|<span data-ttu-id="539d4-200">22</span><span class="sxs-lookup"><span data-stu-id="539d4-200">22</span></span>|<span data-ttu-id="539d4-201">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-201">Yes</span></span>|  
|<span data-ttu-id="539d4-202">ObjectName</span><span class="sxs-lookup"><span data-stu-id="539d4-202">ObjectName</span></span>|`nvarchar`|<span data-ttu-id="539d4-203">Nome dell'oggetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="539d4-203">Name of the object being referenced.</span></span>|<span data-ttu-id="539d4-204">34</span><span class="sxs-lookup"><span data-stu-id="539d4-204">34</span></span>|<span data-ttu-id="539d4-205">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-205">Yes</span></span>|  
|<span data-ttu-id="539d4-206">ObjectType</span><span class="sxs-lookup"><span data-stu-id="539d4-206">ObjectType</span></span>|`int`|<span data-ttu-id="539d4-207">Valore che rappresenta il tipo di oggetto coinvolto nell'evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-207">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="539d4-208">Questo valore corrisponde alla colonna type nella vista del catalogo sys.objects.</span><span class="sxs-lookup"><span data-stu-id="539d4-208">This value corresponds to the type column in the sys.objects catalog view.</span></span> <span data-ttu-id="539d4-209">Per i valori, vedere [Colonna ObjectType per gli eventi di traccia](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="539d4-209">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="539d4-210">28</span><span class="sxs-lookup"><span data-stu-id="539d4-210">28</span></span>|<span data-ttu-id="539d4-211">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-211">Yes</span></span>|  
|<span data-ttu-id="539d4-212">Offset</span><span class="sxs-lookup"><span data-stu-id="539d4-212">Offset</span></span>|`int`|<span data-ttu-id="539d4-213">Offset iniziale dell'istruzione nella stored procedure o nel batch.</span><span class="sxs-lookup"><span data-stu-id="539d4-213">Starting offset of the statement within the stored procedure or batch.</span></span>|<span data-ttu-id="539d4-214">61</span><span class="sxs-lookup"><span data-stu-id="539d4-214">61</span></span>|<span data-ttu-id="539d4-215">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-215">Yes</span></span>|  
|<span data-ttu-id="539d4-216">Letture</span><span class="sxs-lookup"><span data-stu-id="539d4-216">Reads</span></span>|`bigint`|<span data-ttu-id="539d4-217">Numero di letture logiche del disco eseguite dal server per conto dell'evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-217">Number of logical disk reads performed by the server on behalf of the event.</span></span>|<span data-ttu-id="539d4-218">16</span><span class="sxs-lookup"><span data-stu-id="539d4-218">16</span></span>|<span data-ttu-id="539d4-219">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-219">Yes</span></span>|  
|<span data-ttu-id="539d4-220">RequestID</span><span class="sxs-lookup"><span data-stu-id="539d4-220">RequestID</span></span>|`int`|<span data-ttu-id="539d4-221">ID della richiesta contenente l'istruzione.</span><span class="sxs-lookup"><span data-stu-id="539d4-221">ID of the request containing the statement.</span></span>|<span data-ttu-id="539d4-222">49</span><span class="sxs-lookup"><span data-stu-id="539d4-222">49</span></span>|<span data-ttu-id="539d4-223">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-223">Yes</span></span>|  
|<span data-ttu-id="539d4-224">RowCounts</span><span class="sxs-lookup"><span data-stu-id="539d4-224">RowCounts</span></span>|`bigint`|<span data-ttu-id="539d4-225">Numero di righe interessate da un evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-225">The number of rows affected by an event.</span></span>|<span data-ttu-id="539d4-226">48</span><span class="sxs-lookup"><span data-stu-id="539d4-226">48</span></span>|<span data-ttu-id="539d4-227">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-227">Yes</span></span>|  
|<span data-ttu-id="539d4-228">ServerName</span><span class="sxs-lookup"><span data-stu-id="539d4-228">ServerName</span></span>|`nvarchar`|<span data-ttu-id="539d4-229">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tracciata.</span><span class="sxs-lookup"><span data-stu-id="539d4-229">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="539d4-230">26</span><span class="sxs-lookup"><span data-stu-id="539d4-230">26</span></span>|<span data-ttu-id="539d4-231">No</span><span class="sxs-lookup"><span data-stu-id="539d4-231">No</span></span>|  
|<span data-ttu-id="539d4-232">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="539d4-232">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="539d4-233">Nome dell'account di accesso dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="539d4-233">Login name of the user who originated the session.</span></span> <span data-ttu-id="539d4-234">Se ad esempio si stabilisce la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'account di accesso Login1 e si esegue un'istruzione con l'account di accesso Login2, SessionLoginName indica Login1 e LoginName indica Login2.</span><span class="sxs-lookup"><span data-stu-id="539d4-234">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="539d4-235">In questa colonna sono visualizzati sia gli account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che quelli di Windows.</span><span class="sxs-lookup"><span data-stu-id="539d4-235">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="539d4-236">64</span><span class="sxs-lookup"><span data-stu-id="539d4-236">64</span></span>|<span data-ttu-id="539d4-237">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-237">Yes</span></span>|  
|<span data-ttu-id="539d4-238">SourceDatabaseID</span><span class="sxs-lookup"><span data-stu-id="539d4-238">SourceDatabaseID</span></span>|`int`|<span data-ttu-id="539d4-239">ID del database in cui esiste l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="539d4-239">The ID of the database the object exists in.</span></span>|<span data-ttu-id="539d4-240">62</span><span class="sxs-lookup"><span data-stu-id="539d4-240">62</span></span>|<span data-ttu-id="539d4-241">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-241">Yes</span></span>|  
|<span data-ttu-id="539d4-242">SPID</span><span class="sxs-lookup"><span data-stu-id="539d4-242">SPID</span></span>|`int`|<span data-ttu-id="539d4-243">ID della sessione in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-243">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="539d4-244">12</span><span class="sxs-lookup"><span data-stu-id="539d4-244">12</span></span>|<span data-ttu-id="539d4-245">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-245">Yes</span></span>|  
|<span data-ttu-id="539d4-246">StartTime</span><span class="sxs-lookup"><span data-stu-id="539d4-246">StartTime</span></span>|`datetime`|<span data-ttu-id="539d4-247">Ora di inizio dell'evento, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="539d4-247">Time at which the event started, if available.</span></span>|<span data-ttu-id="539d4-248">14</span><span class="sxs-lookup"><span data-stu-id="539d4-248">14</span></span>|<span data-ttu-id="539d4-249">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-249">Yes</span></span>|  
|<span data-ttu-id="539d4-250">TextData</span><span class="sxs-lookup"><span data-stu-id="539d4-250">TextData</span></span>|`ntext`|<span data-ttu-id="539d4-251">Valore di testo che dipende dalla classe di evento acquisita nella traccia.</span><span class="sxs-lookup"><span data-stu-id="539d4-251">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="539d4-252">1</span><span class="sxs-lookup"><span data-stu-id="539d4-252">1</span></span>|<span data-ttu-id="539d4-253">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-253">Yes</span></span>|  
|<span data-ttu-id="539d4-254">TransactionID</span><span class="sxs-lookup"><span data-stu-id="539d4-254">TransactionID</span></span>|`bigint`|<span data-ttu-id="539d4-255">ID della transazione assegnato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="539d4-255">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="539d4-256">4</span><span class="sxs-lookup"><span data-stu-id="539d4-256">4</span></span>|<span data-ttu-id="539d4-257">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-257">Yes</span></span>|  
|<span data-ttu-id="539d4-258">Scritture</span><span class="sxs-lookup"><span data-stu-id="539d4-258">Writes</span></span>|`bigint`|<span data-ttu-id="539d4-259">Numero di scritture fisiche su disco eseguite dal server per conto dell'evento.</span><span class="sxs-lookup"><span data-stu-id="539d4-259">Number of physical disk writes performed by the server on behalf of the event.</span></span>|<span data-ttu-id="539d4-260">17</span><span class="sxs-lookup"><span data-stu-id="539d4-260">17</span></span>|<span data-ttu-id="539d4-261">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-261">Yes</span></span>|  
|<span data-ttu-id="539d4-262">XactSequence</span><span class="sxs-lookup"><span data-stu-id="539d4-262">XactSequence</span></span>|`bigint`|<span data-ttu-id="539d4-263">Token utilizzato per descrivere la transazione corrente.</span><span class="sxs-lookup"><span data-stu-id="539d4-263">Token that describes the current transaction.</span></span>|<span data-ttu-id="539d4-264">50</span><span class="sxs-lookup"><span data-stu-id="539d4-264">50</span></span>|<span data-ttu-id="539d4-265">Sì</span><span class="sxs-lookup"><span data-stu-id="539d4-265">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="539d4-266">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="539d4-266">See Also</span></span>  
 <span data-ttu-id="539d4-267">[Eventi estesi](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="539d4-267">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="539d4-268">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="539d4-268">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  