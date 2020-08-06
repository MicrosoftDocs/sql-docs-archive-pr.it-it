---
title: SQL Server 2014 Express local DB | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- user instances
- LocalDB, described
- local database runtime
- file database
- LocalDB
ms.assetid: 5a641a46-7cfb-4d7b-a90d-6e4625719d74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: af60935af0d183ab7ed6d1c10f84229b7ead3730
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638089"
---
# <a name="sql-server-2014-express-localdb"></a><span data-ttu-id="bd30c-102">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="bd30c-102">SQL Server 2014 Express LocalDB</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="bd30c-103">[!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] `LocalDB` è una modalità di esecuzione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] destinata agli sviluppatori del programma.</span><span class="sxs-lookup"><span data-stu-id="bd30c-103">[!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] `LocalDB` is an execution mode of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] targeted to program developers.</span></span> <span data-ttu-id="bd30c-104">`LocalDB`l'installazione di copia un set minimo di file necessari per avviare [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd30c-104">`LocalDB` installation copies a minimal set of files necessary to start the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="bd30c-105">Una volta `LocalDB` installato, gli sviluppatori avviano una connessione utilizzando una stringa di connessione speciale.</span><span class="sxs-lookup"><span data-stu-id="bd30c-105">Once `LocalDB` is installed, developers initiate a connection by using a special connection string.</span></span> <span data-ttu-id="bd30c-106">Durante la connessione, l'infrastruttura [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] necessaria viene creata automaticamente e avviata, consentendo all'applicazione di usare il database senza attività di configurazione complesse o lunghe.</span><span class="sxs-lookup"><span data-stu-id="bd30c-106">When connecting, the necessary [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] infrastructure is automatically created and started, enabling the application to use the database without complex or time consuming configuration tasks.</span></span> <span data-ttu-id="bd30c-107">Con Developer Tools gli sviluppatori dispongono di un [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] che consente di scrivere e verificare il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] senza dover gestire un'istanza del server completa di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd30c-107">Developer Tools can provide developers with a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that lets them write and test [!INCLUDE[tsql](../../includes/tsql-md.md)] code without having to manage a full server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bd30c-108">Un'istanza di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] `LocalDB` viene gestita tramite l' `SqlLocalDB.exe` utilità.</span><span class="sxs-lookup"><span data-stu-id="bd30c-108">An instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]`LocalDB` is managed by using the `SqlLocalDB.exe` utility.</span></span> [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]<span data-ttu-id="bd30c-109">`LocalDB`deve essere utilizzato al posto della [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] funzionalità dell'istanza utente deprecata.</span><span class="sxs-lookup"><span data-stu-id="bd30c-109">`LocalDB` should be used in place of the [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] user instance feature which is deprecated.</span></span>  
  
## <a name="installing-localdb"></a><span data-ttu-id="bd30c-110">Installazione di LocalDB</span><span class="sxs-lookup"><span data-stu-id="bd30c-110">Installing LocalDB</span></span>  
 <span data-ttu-id="bd30c-111">Il metodo principale di installazione di `LocalDB` consiste nell'utilizzare il programma SqlLocalDB.msi.</span><span class="sxs-lookup"><span data-stu-id="bd30c-111">The primary method of installing `LocalDB` is by using the SqlLocalDB.msi program.</span></span> <span data-ttu-id="bd30c-112">`LocalDB`è un'opzione per l'installazione di qualsiasi SKU di [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd30c-112">`LocalDB` is an option when installing any SKU of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)].</span></span> <span data-ttu-id="bd30c-113">Selezionare `LocalDB` nella pagina **Selezione funzionalità** durante l'installazione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd30c-113">Select `LocalDB` on the **Feature Selection** page during installation of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="bd30c-114">Può essere presente una sola installazione dei `LocalDB` file binari per ogni versione principale [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd30c-114">There can be only one installation of the `LocalDB` binary files for each major [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] version.</span></span> <span data-ttu-id="bd30c-115">È possibile avviare più processi del [!INCLUDE[ssDE](../../includes/ssde-md.md)] e in tutti verranno usati gli stessi file binari.</span><span class="sxs-lookup"><span data-stu-id="bd30c-115">Multiple [!INCLUDE[ssDE](../../includes/ssde-md.md)] processes can be started and will all use the same binaries.</span></span> <span data-ttu-id="bd30c-116">Un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] è stata avviata perché `LocalDB` presenta le stesse limitazioni di[!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd30c-116">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] started as the `LocalDB` has the same limitations as [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)]</span></span>  
  
## <a name="description"></a><span data-ttu-id="bd30c-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd30c-117">Description</span></span>  
 <span data-ttu-id="bd30c-118">Il `LocalDB` programma di installazione utilizza il programma SqlLocalDB.msi per installare i file necessari nel computer.</span><span class="sxs-lookup"><span data-stu-id="bd30c-118">The `LocalDB` setup program uses the SqlLocalDB.msi program to install the necessary files on the computer.</span></span> <span data-ttu-id="bd30c-119">Una volta installato, `LocalDB` è un'istanza di in [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] grado di creare e aprire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database di.</span><span class="sxs-lookup"><span data-stu-id="bd30c-119">Once installed, `LocalDB` is an instance of [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] that can create and open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="bd30c-120">I file del database di sistema per il database sono archiviati nel percorso locale AppData degli utenti che generalmente è nascosto.</span><span class="sxs-lookup"><span data-stu-id="bd30c-120">The system database files for the database are stored in the users' local AppData path which is normally hidden.</span></span> <span data-ttu-id="bd30c-121">Ad esempio **C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server Local DB\Instances\LocalDBApp1\\**.</span><span class="sxs-lookup"><span data-stu-id="bd30c-121">For example **C:\Users\\<user\>\AppData\Local\Microsoft\Microsoft SQL Server Local DB\Instances\LocalDBApp1\\**.</span></span> <span data-ttu-id="bd30c-122">I file del database utente sono archiviati nel percorso indicato dall'utente, in genere nella cartella **C:\Users\\<user\>\Documents\\**.</span><span class="sxs-lookup"><span data-stu-id="bd30c-122">User database files are stored where the user designates, typically somewhere in the **C:\Users\\<user\>\Documents\\** folder.</span></span>  
  
 <span data-ttu-id="bd30c-123">Per ulteriori informazioni sull'inclusione `LocalDB` in un'applicazione, vedere [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] la [documentazione Cenni preliminari sui dati locali](https://msdn.microsoft.com/library/ms233817\(VS.110\).aspx), [procedura dettagliata: creazione di un database SQL Server database](https://msdn.microsoft.com/library/ms233763\(VS.110\).aspx)locale e [procedura dettagliata: connessione ai dati in un database di SQL Server database locale (Windows Forms)](https://msdn.microsoft.com/library/ms171890\(VS.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="bd30c-123">For more information about including `LocalDB` in an application, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] documentation [Local Data Overview](https://msdn.microsoft.com/library/ms233817\(VS.110\).aspx), [Walkthrough: Creating a SQL Server LocalDB Database](https://msdn.microsoft.com/library/ms233763\(VS.110\).aspx), and [Walkthrough: Connecting to Data in a SQL Server LocalDB Database (Windows Forms)](https://msdn.microsoft.com/library/ms171890\(VS.110\).aspx).</span></span>  
  
 <span data-ttu-id="bd30c-124">Per ulteriori informazioni sull' `LocalDB` API, vedere [SQL Server Express riferimento all'API dell'istanza del database locale](https://msdn.microsoft.com/library/hh234692\(SQL.110\).aspx) e [funzione LocalDBStartInstance](https://msdn.microsoft.com/library/hh217143\(SQL.110\).aspx).</span><span class="sxs-lookup"><span data-stu-id="bd30c-124">For more information about the `LocalDB` API, see [SQL Server Express LocalDB Instance API Reference](https://msdn.microsoft.com/library/hh234692\(SQL.110\).aspx) and [LocalDBStartInstance Function](https://msdn.microsoft.com/library/hh217143\(SQL.110\).aspx).</span></span>  
  
 <span data-ttu-id="bd30c-125">L'utilità SqlLocalDb consente di creare nuove istanze di `LocalDB` , avviare e arrestare un'istanza di `LocalDB` e include opzioni che consentono di gestire `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-125">The SqlLocalDb utility can create new instances of `LocalDB`, start and stop an instance of `LocalDB`, and includes options to help you manage `LocalDB`.</span></span>  <span data-ttu-id="bd30c-126">Per altre informazioni sull'utilità SqlLocalDb, vedere [Utilità SqlLocalDB](../../tools/sqllocaldb-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bd30c-126">For more information about the SqlLocalDb utility, see [SqlLocalDB Utility](../../tools/sqllocaldb-utility.md).</span></span>  
  
 <span data-ttu-id="bd30c-127">Le regole di confronto dell'istanza per `LocalDB` sono impostate su SQL_Latin1_General_CP1_CI_AS e non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="bd30c-127">The instance collation for `LocalDB` is set to SQL_Latin1_General_CP1_CI_AS and cannot be changed.</span></span> <span data-ttu-id="bd30c-128">Le regole di confronto a livello di database, di colonna e di espressione sono supportate normalmente.</span><span class="sxs-lookup"><span data-stu-id="bd30c-128">Database-level, column-level, and expression-level collations are supported normally.</span></span> <span data-ttu-id="bd30c-129">Ai database indipendenti vengono applicate le regole di confronto dei metadati e di tempdb definite da [Contained Database Collations](../../relational-databases/databases/contained-database-collations.md).</span><span class="sxs-lookup"><span data-stu-id="bd30c-129">Contained databases follow the metadata and tempdb collations rules defined by [Contained Database Collations](../../relational-databases/databases/contained-database-collations.md).</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="bd30c-130">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="bd30c-130">Restrictions</span></span>  
 <span data-ttu-id="bd30c-131">`LocalDB`Impossibile essere un sottoscrittore della replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="bd30c-131">`LocalDB` cannot be a merge replication subscriber.</span></span>  
  
 <span data-ttu-id="bd30c-132">`LocalDB`non supporta FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="bd30c-132">`LocalDB` does not support FILESTREAM.</span></span>  
  
 <span data-ttu-id="bd30c-133">`LocalDB`consente solo code locali per Service Broker.</span><span class="sxs-lookup"><span data-stu-id="bd30c-133">`LocalDB` only allows local queues for Service Broker.</span></span>  
  
 <span data-ttu-id="bd30c-134">Un'istanza di di `LocalDB` proprietà degli account predefiniti, ad esempio NT AUTHORITY\SYSTEM, può avere problemi di gestibilità a causa del reindirizzamento di windows file System; Usare invece un account di Windows normale come proprietario.</span><span class="sxs-lookup"><span data-stu-id="bd30c-134">An instance of `LocalDB` owned by the built-in accounts such as NT AUTHORITY\SYSTEM can have manageability issues due to windows file system redirection; Instead use a normal windows account as the owner.</span></span>  
  
### <a name="automatic-and-named-instances"></a><span data-ttu-id="bd30c-135">Istanze denominate e automatiche</span><span class="sxs-lookup"><span data-stu-id="bd30c-135">Automatic and Named Instances</span></span>  
 <span data-ttu-id="bd30c-136">`LocalDB`supporta due tipi di istanze: istanze automatiche e istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="bd30c-136">`LocalDB` supports two kinds of instances: Automatic instances and named instances.</span></span>  
  
-   <span data-ttu-id="bd30c-137">Le istanze automatiche di `LocalDB` sono pubbliche.</span><span class="sxs-lookup"><span data-stu-id="bd30c-137">Automatic instances of `LocalDB` are public.</span></span> <span data-ttu-id="bd30c-138">Vengono create e gestite automaticamente per l'utente e possono essere usate da qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="bd30c-138">They are created and managed automatically for the user and can be used by any application.</span></span> <span data-ttu-id="bd30c-139">Un'istanza automatica di `LocalDB` è disponibile per ogni versione di `LocalDB` installata nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bd30c-139">One automatic instance of `LocalDB` exists for every version of `LocalDB` installed on the user's computer.</span></span> <span data-ttu-id="bd30c-140">Le istanze automatiche di `LocalDB` forniscono una gestione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="bd30c-140">Automatic instances of `LocalDB` provide seamless instance management.</span></span> <span data-ttu-id="bd30c-141">Non c'è necessità di creare l'istanza in quanto già funziona.</span><span class="sxs-lookup"><span data-stu-id="bd30c-141">There is no need to create the instance; it just works.</span></span> <span data-ttu-id="bd30c-142">In tal modo è possibile migrare e installare e l'applicazione con facilità in un computer diverso.</span><span class="sxs-lookup"><span data-stu-id="bd30c-142">This allows for easy application installation and migration to a different computer.</span></span> <span data-ttu-id="bd30c-143">Se nel computer di destinazione è installata la versione specificata di `LocalDB`, l'istanza automatica di `LocalDB` per quella versione è disponibile anche sul computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bd30c-143">If the target machine has the specified version of `LocalDB` installed, the automatic instance of `LocalDB` for that version is available on the target machine as well.</span></span> <span data-ttu-id="bd30c-144">Le istanze automatiche di `LocalDB` hanno un modello speciale per il nome dell'istanza che appartiene a uno spazio dei nomi riservato.</span><span class="sxs-lookup"><span data-stu-id="bd30c-144">Automatic instances of `LocalDB` have a special pattern for the instance name that belongs to a reserved namespace.</span></span> <span data-ttu-id="bd30c-145">In questo modo si evitano conflitti di nomi con istanze denominate di `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-145">This prevents name conflicts with named instances of `LocalDB`.</span></span> <span data-ttu-id="bd30c-146">Il nome per l'istanza automatica è **MSSQLLocalDB**.</span><span class="sxs-lookup"><span data-stu-id="bd30c-146">The name for the automatic instance is **MSSQLLocalDB**.</span></span>  
  
-   <span data-ttu-id="bd30c-147">Le istanze denominate di `LocalDB` sono private.</span><span class="sxs-lookup"><span data-stu-id="bd30c-147">Named instances of `LocalDB` are private.</span></span> <span data-ttu-id="bd30c-148">Sono di proprietà di una sola applicazione, responsabile della creazione e della gestione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="bd30c-148">They are owned by a single application that is responsible for creating and managing the instance.</span></span> <span data-ttu-id="bd30c-149">Le istanze denominate forniscono l'isolamento dalle altre istanze e possono migliorare le prestazioni riducendo la contesa di risorse con altri utenti del database.</span><span class="sxs-lookup"><span data-stu-id="bd30c-149">Named instances provide isolation from other instances and can improve performance by reducing resource contention with other database users.</span></span> <span data-ttu-id="bd30c-150">Le istanze denominate devono essere create in modo esplicito dall'utente tramite l' `LocalDB` API di gestione o in modo implicito tramite il file di app.config per un'applicazione gestita (sebbene l'applicazione gestita possa usare anche l'API, se necessario).</span><span class="sxs-lookup"><span data-stu-id="bd30c-150">Named instances must be created explicitly by the user through the `LocalDB` management API or implicitly via the app.config file for a managed application (although managed application may also use the API, if desired).</span></span> <span data-ttu-id="bd30c-151">A ogni istanza denominata di `LocalDB` è associata una `LocalDB` versione che punta al rispettivo set di `LocalDB` file binari.</span><span class="sxs-lookup"><span data-stu-id="bd30c-151">Each named instance of `LocalDB` has an associated `LocalDB` version that points to the respective set of `LocalDB` binaries.</span></span> <span data-ttu-id="bd30c-152">Il nome dell'istanza di `LocalDB` è un `sysname` tipo di dati che può contenere fino a 128 caratteri.</span><span class="sxs-lookup"><span data-stu-id="bd30c-152">The instance name of a `LocalDB` is `sysname` data type and can have up to 128 characters.</span></span> <span data-ttu-id="bd30c-153">Questo comportamento è diverso rispetto alle istanze denominate normali di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , che limitano i nomi a nomi NetBIOS normali di 16 caratteri ASCII. Il nome di un'istanza di `LocalDB` può contenere qualsiasi carattere Unicode che sia valido all'interno di un nome file.</span><span class="sxs-lookup"><span data-stu-id="bd30c-153">(This differs from regular named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], which limits names to regular NetBIOS names of 16 ASCII chars.) The name of an instance of `LocalDB` can contain any Unicode characters that are legal within a filename.</span></span>  <span data-ttu-id="bd30c-154">Un'istanza denominata che utilizza un nome dell'istanza automatica diventa un'istanza automatica.</span><span class="sxs-lookup"><span data-stu-id="bd30c-154">A named instance that uses an automatic instance name becomes an automatic instance.</span></span>  
  
 <span data-ttu-id="bd30c-155">I diversi utenti di un computer possono avere istanze con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="bd30c-155">Different users of a computer can have instances with the same name.</span></span> <span data-ttu-id="bd30c-156">Ogni istanza è un processo diverso in esecuzione come utente diverso.</span><span class="sxs-lookup"><span data-stu-id="bd30c-156">Each instance is a different processes running as a different user.</span></span>  
  
## <a name="shared-instances-of-localdb"></a><span data-ttu-id="bd30c-157">Istanze condivise di LocalDB</span><span class="sxs-lookup"><span data-stu-id="bd30c-157">Shared Instances of LocalDB</span></span>  
 <span data-ttu-id="bd30c-158">Per supportare scenari in cui più utenti del computer devono connettersi a una singola istanza di `LocalDB` , `LocalDB` supporta la condivisione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="bd30c-158">To support scenarios where multiple users of the computer need to connect to a single instance of `LocalDB`, `LocalDB` supports instance sharing.</span></span> <span data-ttu-id="bd30c-159">Il proprietario di un'istanza può decidere di consentire agli altri utenti del computer di connettersi all'istanza.</span><span class="sxs-lookup"><span data-stu-id="bd30c-159">An instance owner can choose to allow the other users on the computer to connect to his instance.</span></span> <span data-ttu-id="bd30c-160">Le istanze automatiche e denominate di `LocalDB` possono essere condivise.</span><span class="sxs-lookup"><span data-stu-id="bd30c-160">Both automatic and named instances of `LocalDB` can be shared.</span></span> <span data-ttu-id="bd30c-161">Per condividere un'istanza di `LocalDB`, un utente ne seleziona un nome condiviso (alias).</span><span class="sxs-lookup"><span data-stu-id="bd30c-161">To share an instance of `LocalDB` a user selects a shared name (alias) for it.</span></span> <span data-ttu-id="bd30c-162">Poiché il nome condiviso è visibile a tutti gli utenti del computer, questo nome condiviso deve essere univoco nel computer.</span><span class="sxs-lookup"><span data-stu-id="bd30c-162">Because the shared name is visible to all users of the computer, this shared name must be unique on the computer.</span></span> <span data-ttu-id="bd30c-163">Il nome condiviso di un'istanza di `LocalDB` ha lo stesso formato dell'istanza denominata di `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-163">The shared name for an instance of `LocalDB` has the same format as the named instance of `LocalDB`.</span></span>  
  
 <span data-ttu-id="bd30c-164">Solo un amministratore del computer può creare un'istanza condivisa di `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-164">Only an administrator on the computer can create a shared instance of `LocalDB`.</span></span> <span data-ttu-id="bd30c-165">È possibile annullare la condivisione di un'istanza condivisa di `LocalDB` da un amministratore o dal proprietario dell'istanza condivisa di `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-165">A shared instance of `LocalDB` can be unshared by an administrator or by the owner of the shared instance of `LocalDB`.</span></span> <span data-ttu-id="bd30c-166">Per condividere e annullare la condivisione di un'istanza di `LocalDB` , utilizzare `LocalDBShareInstance` i `LocalDBUnShareInstance` metodi e dell' `LocalDB` API oppure le opzioni Condividi e non condivise dell'utilità SqlLocalDB.</span><span class="sxs-lookup"><span data-stu-id="bd30c-166">To share and unshared an instance of `LocalDB`, use the `LocalDBShareInstance` and `LocalDBUnShareInstance` methods of the `LocalDB` API, or the share and unshared options of the SqlLocalDb utility.</span></span>  
  
## <a name="starting-localdb-and-connecting-to-localdb"></a><span data-ttu-id="bd30c-167">Avvio e connessione a LocalDB</span><span class="sxs-lookup"><span data-stu-id="bd30c-167">Starting LocalDB and Connecting to LocalDB</span></span>  
  
### <a name="connecting-to-the-automatic-instance"></a><span data-ttu-id="bd30c-168">Connessione all'istanza automatica</span><span class="sxs-lookup"><span data-stu-id="bd30c-168">Connecting to the Automatic Instance</span></span>  
 <span data-ttu-id="bd30c-169">Il modo più semplice per usare `LocalDB` consiste nel connettersi all'istanza automatica di proprietà dell'utente corrente usando la stringa di connessione **"Server = (local DB) \MSSQLLocalDB; Integrated Security = true"**.</span><span class="sxs-lookup"><span data-stu-id="bd30c-169">The easiest way to use `LocalDB` is to connect to the automatic instance owned by the current user by using the connection string **"Server=(localdb)\MSSQLLocalDB;Integrated Security=true"**.</span></span> <span data-ttu-id="bd30c-170">Per connettersi a un database specifico usando il nome del file, usare una stringa di connessione simile a **"Server=(LocalDB)\MSSQLLocalDB; Integrated Security=true ;AttachDbFileName=D:\Data\MyDB1.mdf"**.</span><span class="sxs-lookup"><span data-stu-id="bd30c-170">To connect to a specific database by using the file name, connect using a connection string similar to **"Server=(LocalDB)\MSSQLLocalDB; Integrated Security=true ;AttachDbFileName=D:\Data\MyDB1.mdf"**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd30c-171">La prima volta che un utente in un computer tenta di connettersi a `LocalDB` , l'istanza automatica deve essere creata e avviata.</span><span class="sxs-lookup"><span data-stu-id="bd30c-171">The first time a user on a computer tries to connect to `LocalDB`, the automatic instance must be both created and started.</span></span> <span data-ttu-id="bd30c-172">Il tempo aggiuntivo necessario per la creazione dell'istanza può determinare un errore di tentativo di connessione generando un messaggio di timeout.</span><span class="sxs-lookup"><span data-stu-id="bd30c-172">The extra time for the instance to be created can cause the connection attempt to fail with a timeout message.</span></span> <span data-ttu-id="bd30c-173">In una situazione simile, attendere pochi secondi per consentire il completamento del processo di creazione, quindi riconnettersi.</span><span class="sxs-lookup"><span data-stu-id="bd30c-173">When this happens, wait a few seconds to let the creation process complete, and then connect again.</span></span>  
  
### <a name="creating-and-connecting-to-a-named-instances"></a><span data-ttu-id="bd30c-174">Creazione e connessione alle istanze denominate</span><span class="sxs-lookup"><span data-stu-id="bd30c-174">Creating and Connecting to a Named Instances</span></span>  
 <span data-ttu-id="bd30c-175">Oltre all'istanza automatica, `LocalDB` supporta anche le istanze denominate.</span><span class="sxs-lookup"><span data-stu-id="bd30c-175">In addition to the automatic instance, `LocalDB` also supports named instances.</span></span> <span data-ttu-id="bd30c-176">Utilizzare il programma SqlLocalDB.exe per creare, avviare e arrestare un'istanza denominata di `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-176">Use the SqlLocalDB.exe program to create, start, and stop an named instance of `LocalDB`.</span></span> <span data-ttu-id="bd30c-177">Per altre informazioni su SqlLocalDB.exe, vedere [Utilità SqlLocalDB](../../tools/sqllocaldb-utility.md).</span><span class="sxs-lookup"><span data-stu-id="bd30c-177">For more information about SqlLocalDB.exe, see [SqlLocalDB Utility](../../tools/sqllocaldb-utility.md).</span></span>  
  
```ms-dos  
REM Create an instance of LocalDB  
"C:\Program Files\Microsoft SQL Server\120\Tools\Binn\SqlLocalDB.exe" create LocalDBApp1  
REM Start the instance of LocalDB  
"C:\Program Files\Microsoft SQL Server\120\Tools\Binn\SqlLocalDB.exe" start LocalDBApp1  
REM Gather information about the instance of LocalDB  
"C:\Program Files\Microsoft SQL Server\120\Tools\Binn\SqlLocalDB.exe" info LocalDBApp1  
```  
  
 <span data-ttu-id="bd30c-178">Nell'ultima riga sopra indicata vengono restituite informazioni simili alle seguenti.</span><span class="sxs-lookup"><span data-stu-id="bd30c-178">The last line above, returns information similar to the following.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd30c-179">Nome</span><span class="sxs-lookup"><span data-stu-id="bd30c-179">Name</span></span>|<span data-ttu-id="bd30c-180">"LocalDBApp1"</span><span class="sxs-lookup"><span data-stu-id="bd30c-180">"LocalDBApp1"</span></span>|  
|<span data-ttu-id="bd30c-181">Versione</span><span class="sxs-lookup"><span data-stu-id="bd30c-181">Version</span></span>|\<Current Version>|  
|<span data-ttu-id="bd30c-182">Nome condiviso</span><span class="sxs-lookup"><span data-stu-id="bd30c-182">Shared name</span></span>|<span data-ttu-id="bd30c-183">""</span><span class="sxs-lookup"><span data-stu-id="bd30c-183">""</span></span>|  
|<span data-ttu-id="bd30c-184">Proprietario</span><span class="sxs-lookup"><span data-stu-id="bd30c-184">Owner</span></span>|<span data-ttu-id="bd30c-185">"\<Your Windows User>"</span><span class="sxs-lookup"><span data-stu-id="bd30c-185">"\<Your Windows User>"</span></span>|  
|<span data-ttu-id="bd30c-186">Creazione automatica</span><span class="sxs-lookup"><span data-stu-id="bd30c-186">Auto create</span></span>|<span data-ttu-id="bd30c-187">No</span><span class="sxs-lookup"><span data-stu-id="bd30c-187">No</span></span>|  
|<span data-ttu-id="bd30c-188">State</span><span class="sxs-lookup"><span data-stu-id="bd30c-188">State</span></span>|<span data-ttu-id="bd30c-189">in esecuzione</span><span class="sxs-lookup"><span data-stu-id="bd30c-189">running</span></span>|  
|<span data-ttu-id="bd30c-190">Ultima ora inizio</span><span class="sxs-lookup"><span data-stu-id="bd30c-190">Last start time</span></span>|\<Date and Time>|  
|<span data-ttu-id="bd30c-191">Nome pipe dell'istanza</span><span class="sxs-lookup"><span data-stu-id="bd30c-191">Instance pipe name</span></span>|<span data-ttu-id="bd30c-192">np:\\\\.\pipe\LOCALDB#F365A78E\tsql\query</span><span class="sxs-lookup"><span data-stu-id="bd30c-192">np:\\\\.\pipe\LOCALDB#F365A78E\tsql\query</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="bd30c-193">Se l'applicazione usa una versione di .NET prima di 4.0.2, è necessario connettersi direttamente al named pipe di `LocalDB` .</span><span class="sxs-lookup"><span data-stu-id="bd30c-193">If your application uses a version of .NET before 4.0.2 you must connect directly to the named pipe of the `LocalDB`.</span></span> <span data-ttu-id="bd30c-194">Il valore del nome della pipe dell'istanza è il named pipe `LocalDB` su cui è in ascolto l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="bd30c-194">The Instance pipe name value is the named pipe that the instance of `LocalDB` is listening on.</span></span> <span data-ttu-id="bd30c-195">La parte del nome della pipe dell'istanza dopo il database locale # verrà modificata ogni volta che `LocalDB` viene avviata l'istanza di.</span><span class="sxs-lookup"><span data-stu-id="bd30c-195">The portion of the Instance pipe name after LOCALDB# will change each time the instance of `LocalDB` is started.</span></span> <span data-ttu-id="bd30c-196">Per connettersi all'istanza di utilizzando `LocalDB` [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , digitare il nome pipe dell'istanza nella casella **nome server** della finestra di dialogo \*\*Connetti a [!INCLUDE[ssDE](../../includes/ssde-md.md)] \*\* .</span><span class="sxs-lookup"><span data-stu-id="bd30c-196">To connect to the instance of `LocalDB` by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], type the Instance pipe name in the **Server name** box of the **Connect to [!INCLUDE[ssDE](../../includes/ssde-md.md)]** dialog box.</span></span> <span data-ttu-id="bd30c-197">Dal programma personalizzato è possibile stabilire una connessione all'istanza di `LocalDB` utilizzando una stringa di connessione simile a`SqlConnection conn = new SqlConnection(@"Server=np:\\.\pipe\LOCALDB#F365A78E\tsql\query");`</span><span class="sxs-lookup"><span data-stu-id="bd30c-197">From your custom program you can establish connection to the instance of `LocalDB` using a connection string similar to `SqlConnection conn = new SqlConnection(@"Server=np:\\.\pipe\LOCALDB#F365A78E\tsql\query");`</span></span>  
  
### <a name="connecting-to-a-shared-instance-of-localdb"></a><span data-ttu-id="bd30c-198">Connessione a un'istanza condivisa di LocalDB</span><span class="sxs-lookup"><span data-stu-id="bd30c-198">Connecting to a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="bd30c-199">Per connettersi a un'istanza condivisa di `LocalDB` Add \*\*. \\ \*\* (punto + barra rovesciata) alla stringa di connessione per fare riferimento allo spazio dei nomi riservato per le istanze condivise.</span><span class="sxs-lookup"><span data-stu-id="bd30c-199">To connect to a shared instance of `LocalDB` add **.\\** (dot + backslash) to the connection string to reference the namespace reserved for shared instances.</span></span> <span data-ttu-id="bd30c-200">Ad esempio, per connettersi a un'istanza condivisa di `LocalDB` denominata, `AppData` utilizzare una stringa di connessione, ad esempio `(localdb)\.\AppData` come parte della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="bd30c-200">For example, to connect to a shared instance of `LocalDB` named `AppData` use a connection string such as `(localdb)\.\AppData` as part of the connection string.</span></span> <span data-ttu-id="bd30c-201">Un utente che si connette a un'istanza condivisa di di `LocalDB` cui non è proprietario deve disporre di un account di accesso con autenticazione di Windows o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticazione di.</span><span class="sxs-lookup"><span data-stu-id="bd30c-201">A user connecting to a shared instance of `LocalDB` that they do not own must have a Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication login.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bd30c-202">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="bd30c-202">Troubleshooting</span></span>  
 <span data-ttu-id="bd30c-203">Per informazioni sulla risoluzione dei problemi `LocalDB` , vedere [risoluzione dei problemi SQL Server 2012 Express](https://social.technet.microsoft.com/wiki/contents/articles/4609.aspx)local DB.</span><span class="sxs-lookup"><span data-stu-id="bd30c-203">For information about troubleshooting `LocalDB`, see [Troubleshooting SQL Server 2012 Express LocalDB](https://social.technet.microsoft.com/wiki/contents/articles/4609.aspx).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="bd30c-204">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bd30c-204">Permissions</span></span>  
 <span data-ttu-id="bd30c-205">Un'istanza di [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] `LocalDB` è un'istanza creata da un utente per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="bd30c-205">An instance of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)]`LocalDB` is an instance created by a user for their use.</span></span> <span data-ttu-id="bd30c-206">Qualsiasi utente del computer può creare un database utilizzando un'istanza di `LocalDB` , archiviando i file nel proprio profilo utente ed eseguendo il processo con le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="bd30c-206">Any user on the computer can create a database using an instance of `LocalDB`, storing files under their user profile and running the process under their credentials.</span></span> <span data-ttu-id="bd30c-207">Per impostazione predefinita, l'accesso all'istanza di `LocalDB` è limitato al relativo proprietario.</span><span class="sxs-lookup"><span data-stu-id="bd30c-207">By default, access to the instance of `LocalDB` is limited to its owner.</span></span> <span data-ttu-id="bd30c-208">I dati contenuti in `LocalDB` sono protetti da file System accesso ai file di database.</span><span class="sxs-lookup"><span data-stu-id="bd30c-208">The data contained in the `LocalDB` is protected by file system access to the database files.</span></span> <span data-ttu-id="bd30c-209">Se i file di database dell'utente vengono archiviati in un percorso condiviso, il database può essere aperto da chiunque disponga di file system accesso a tale percorso utilizzando un'istanza di di `LocalDB` cui è proprietario.</span><span class="sxs-lookup"><span data-stu-id="bd30c-209">If user database files are stored in a shared location, the database can be opened by anyone with file system access to that location by using an instance of `LocalDB` that they own.</span></span> <span data-ttu-id="bd30c-210">Se i file di database si trovano in un percorso protetto, ad esempio la cartella dati utente, solo quell'utente e gli amministratori con accesso a quella cartella, possono aprire il database.</span><span class="sxs-lookup"><span data-stu-id="bd30c-210">If the database files are in a protected location, such as the users data folder, only that user, and any administrators with access to that folder, can open the database.</span></span> <span data-ttu-id="bd30c-211">I `LocalDB` file possono essere aperti solo da un'istanza di `LocalDB` alla volta.</span><span class="sxs-lookup"><span data-stu-id="bd30c-211">The `LocalDB` files can only be opened by one instance of `LocalDB` at a time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd30c-212">`LocalDB`viene sempre eseguito nel contesto di sicurezza degli utenti. ovvero `LocalDB` non viene mai eseguito con le credenziali del gruppo dell'amministratore locale.</span><span class="sxs-lookup"><span data-stu-id="bd30c-212">`LocalDB` always runs under the users security context; that is, `LocalDB` never runs with credentials from the local Administrator's group.</span></span> <span data-ttu-id="bd30c-213">Ciò significa che tutti i file di database utilizzati da un' `LocalDB` istanza devono essere accessibili utilizzando l'account di Windows dell'utente proprietario, senza considerare l'appartenenza al gruppo Administrators locale.</span><span class="sxs-lookup"><span data-stu-id="bd30c-213">This means that all database files used by a `LocalDB` instance must be accessible using the owning user's Windows account, without considering membership in the local Administrators group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd30c-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd30c-214">See Also</span></span>  
 [<span data-ttu-id="bd30c-215">Utilità SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="bd30c-215">SqlLocalDB Utility</span></span>](../../tools/sqllocaldb-utility.md)  
  
  