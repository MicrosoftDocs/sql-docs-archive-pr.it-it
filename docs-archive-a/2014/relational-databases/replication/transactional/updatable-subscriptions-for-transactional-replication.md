---
title: Sottoscrizioni aggiornabili per la replica transazionale | Microsoft Docs
ms.custom: ''
ms.date: 03/31/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, updatable subscriptions
- updatable subscriptions, about updatable subscriptions
- queued updating subscriptions [SQL Server replication]
- immediate updating subscriptions
- subscriptions [SQL Server replication], updatable
- updatable subscriptions
ms.assetid: 8eec95cb-3a11-436e-bcee-bdcd05aa5c5a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e0b739ffe34a14519ff5290c406805ff7715edce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637746"
---
# <a name="updatable-subscriptions-for-transactional-replication"></a><span data-ttu-id="fcd2e-102">Updatable Subscriptions for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="fcd2e-102">Updatable Subscriptions for Transactional Replication</span></span>

<span data-ttu-id="fcd2e-103">**Si applica a:** SQL Server 2008 (e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="fcd2e-103">**Applies to:** SQL Server 2008 (and later)</span></span>

    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)]  
  
<span data-ttu-id="fcd2e-104">In SQL Server 2014, la replica transazionale supporta gli aggiornamenti nei Sottoscrittori tramite sottoscrizioni aggiornabili e la replica peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-104">In SQL Server 2014, transactional replication supports updates at Subscribers through updatable subscriptions and peer-to-peer replication.</span></span> <span data-ttu-id="fcd2e-105">Di seguito sono indicati i due tipi di sottoscrizioni aggiornabili:</span><span class="sxs-lookup"><span data-stu-id="fcd2e-105">The following are the two types of updatable subscriptions:</span></span>  
  
-   <span data-ttu-id="fcd2e-106">Aggiornamento immediato.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-106">Immediate updating.</span></span> <span data-ttu-id="fcd2e-107">Per l'aggiornamento dei dati nel Sottoscrittore è necessario che il server di pubblicazione e il Sottoscrittore siano connessi.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-107">The Publisher and Subscriber must be connected to update data at the Subscriber.</span></span>  
  
-   <span data-ttu-id="fcd2e-108">Aggiornamento in coda. Per l'aggiornamento dei dati nel Sottoscrittore non è necessario che il server di pubblicazione e il Sottoscrittore siano connessi.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-108">Queued updating The Publisher and Subscriber do not have to be connected to update data at the Subscriber.</span></span> <span data-ttu-id="fcd2e-109">È possibile eseguire gli aggiornamenti mentre il Sottoscrittore o il server di pubblicazione è offline.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-109">Updates can be made while the Subscriber or Publisher is offline.</span></span>  
  
 <span data-ttu-id="fcd2e-110">Quando si aggiornano i dati in un Sottoscrittore, questi vengono innanzitutto propagati al server di pubblicazione e quindi agli altri Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-110">When data is updated at a Subscriber, it is first propagated to the Publisher and then propagated to other Subscribers.</span></span> <span data-ttu-id="fcd2e-111">Se si utilizza l'aggiornamento immediato, le modifiche vengono propagate immediatamente tramite il protocollo di commit in due fasi.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-111">If immediate updating is used, the changes are propagated immediately using the two-phase commit protocol.</span></span> <span data-ttu-id="fcd2e-112">Se si utilizza l'aggiornamento in coda, le modifiche vengono archiviate in una coda. Le transazioni in coda vengono quindi applicate in modo asincrono nel server di pubblicazione ogni volta che è disponibile la connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-112">If queued updating is used, the changes are stored in a queue; the queued transactions are then applied asynchronously at the Publisher whenever network connectivity is available.</span></span> <span data-ttu-id="fcd2e-113">Poiché gli aggiornamenti vengono propagati in modo asincrono al server di pubblicazione, gli stessi dati potrebbero essere stati aggiornati dal server di pubblicazione o da un altro Sottoscrittore e potrebbero verificarsi conflitti in fase di applicazione degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-113">Because the updates are propagated asynchronously to the Publisher, the same data may have been updated by the Publisher or by another Subscriber and conflicts can occur when applying the updates.</span></span> <span data-ttu-id="fcd2e-114">I conflitti vengono rilevati e risolti in base a criteri di risoluzione dei conflitti impostati durante la creazione della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-114">Conflicts are detected and resolved according to a conflict resolution policy that is set when creating the publication.</span></span>  
  
 <span data-ttu-id="fcd2e-115">Se si crea una pubblicazione transazionale con sottoscrizioni aggiornabili tramite la Creazione guidata nuova pubblicazione, verranno abilitati sia l'aggiornamento immediato che l'aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-115">If you create a transactional publication with updatable subscriptions in the New Publication Wizard, both immediate updating and queued updating are enabled.</span></span> <span data-ttu-id="fcd2e-116">Se si crea una pubblicazione con stored procedure, è possibile abilitare una o entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-116">If you create a publication with stored procedures, you can enable one or both options.</span></span> <span data-ttu-id="fcd2e-117">Quando si crea una sottoscrizione della pubblicazione, è necessario specificare la modalità di aggiornamento da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-117">When you create a subscription to the publication, you specify which update mode to use.</span></span> <span data-ttu-id="fcd2e-118">Se necessario, sarà quindi possibile passare da una modalità di aggiornamento all'altra.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-118">You can then switch between update modes if necessary.</span></span> <span data-ttu-id="fcd2e-119">Per ulteriori informazioni, vedere la sezione seguente "Passaggio da una modalità di aggiornamento all'altra".</span><span class="sxs-lookup"><span data-stu-id="fcd2e-119">For more information, see the following section "Switching between Update Modes".</span></span>  
  
 <span data-ttu-id="fcd2e-120">Per abilitare le sottoscrizioni aggiornabili per le pubblicazioni transazionali, [Enable Updating Subscriptions for Transactional Publications](../publish/enable-updating-subscriptions-for-transactional-publications.md)</span><span class="sxs-lookup"><span data-stu-id="fcd2e-120">To enable updatable subscriptions for transactional publications, [Enable Updating Subscriptions for Transactional Publications](../publish/enable-updating-subscriptions-for-transactional-publications.md)</span></span>  
  
 <span data-ttu-id="fcd2e-121">Per creare sottoscrizioni aggiornabili per le pubblicazioni transazionali, vedere [Create an Updatable Subscription to a Transactional Publication](../publish/create-an-updatable-subscription-to-a-transactional-publication.md)</span><span class="sxs-lookup"><span data-stu-id="fcd2e-121">To create updatable subscriptions for transactional publications, see [Create an Updatable Subscription to a Transactional Publication](../publish/create-an-updatable-subscription-to-a-transactional-publication.md)</span></span>  
  
## <a name="switching-between-update-modes"></a><span data-ttu-id="fcd2e-122">Passaggio da una modalità di aggiornamento all'altra</span><span class="sxs-lookup"><span data-stu-id="fcd2e-122">Switching Between Update Modes</span></span>  
 <span data-ttu-id="fcd2e-123">Quando si utilizzano le sottoscrizioni aggiornabili, è possibile specificare che per una sottoscrizione venga utilizzata una modalità di aggiornamento e quindi si passi all'altra se l'applicazione lo richiede.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-123">When using updatable subscriptions you can specify that a subscription should use one update mode and then switch to the other if the application requires it.</span></span> <span data-ttu-id="fcd2e-124">È possibile, ad esempio, specificare che per una sottoscrizione venga utilizzato l'aggiornamento immediato, ma si passi all'aggiornamento in coda se un errore di sistema provoca la perdita della connettività di rete.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-124">For example, you can specify that a subscription should use immediate updating, but switch to queued updating if a system failure results in the loss of network connectivity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fcd2e-125">La replica non passa automaticamente da una modalità di aggiornamento all'altra.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-125">Replication does not switch automatically between update modes.</span></span> <span data-ttu-id="fcd2e-126">Per passare da una modalità all'altra, è necessario impostare la modalità di aggiornamento tramite SQL Server Management Studio oppure l'applicazione deve chiamare [sp_setreplfailovermode &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fcd2e-126">You must set the update mode through SQL Server Management Studio or your application must call [sp_setreplfailovermode &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-setreplfailovermode-transact-sql) to switch between modes.</span></span>  
  
 <span data-ttu-id="fcd2e-127">Se si passa dall'aggiornamento immediato all'aggiornamento in coda, non sarà possibile tornare all'aggiornamento immediato fino a quando il Sottoscrittore e il server di pubblicazione non sono connessi e tramite l'agente di lettura coda non sono stati applicati al server di pubblicazione tutti i messaggi in sospeso nella coda.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-127">If you switch from immediate updating to queued updating, you cannot switch back to immediate updating until the Subscriber and Publisher are connected and the Queue Reader Agent has applied all pending messages in the queue to the Publisher.</span></span>  
  
 <span data-ttu-id="fcd2e-128">**Per passare da una modalità di aggiornamento all'altra**</span><span class="sxs-lookup"><span data-stu-id="fcd2e-128">**To switch between update modes**</span></span>  
  
 <span data-ttu-id="fcd2e-129">Per passare da una modalità di aggiornamento all'altra, è necessario abilitare la pubblicazione e la sottoscrizione per entrambe le modalità e quindi passare da una all'altra, se necessario.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-129">To switch between updating modes, you must enable the publication and subscription for both update modes, and then switch between them if necessary.</span></span> <span data-ttu-id="fcd2e-130">Per ulteriori informazioni, vedere</span><span class="sxs-lookup"><span data-stu-id="fcd2e-130">For more information, see</span></span>  
<span data-ttu-id="fcd2e-131">[Passare da una modalità di aggiornamento all'altra per una sottoscrizione transazionale aggiornabile](../administration/switch-between-update-modes-for-an-updatable-transactional-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="fcd2e-131">[Switch Between Update Modes for an Updatable Transactional Subscription](../administration/switch-between-update-modes-for-an-updatable-transactional-subscription.md).</span></span>  
  
### <a name="considerations-for-using-updatable-subscriptions"></a><span data-ttu-id="fcd2e-132">Considerazioni per l'utilizzo di sottoscrizioni aggiornabili</span><span class="sxs-lookup"><span data-stu-id="fcd2e-132">Considerations for Using Updatable Subscriptions</span></span>  
  
-   <span data-ttu-id="fcd2e-133">Dopo avere abilitato una pubblicazione per le sottoscrizioni aggiornabili o per le sottoscrizioni ad aggiornamento in coda, non sarà possibile disabilitare l'opzione per la pubblicazione, anche nel caso in cui non sia necessaria per le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-133">After a publication is enabled for updating subscriptions or queued updating subscriptions, the option cannot be disabled for the publication (although subscriptions do not need to use it).</span></span> <span data-ttu-id="fcd2e-134">Per disabilitare l'opzione, è necessario eliminare la pubblicazione e crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-134">To disable the option, the publication must be deleted and a new one created.</span></span>  
  
-   <span data-ttu-id="fcd2e-135">La ripubblicazione dei dati non è supportata.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-135">Republishing data is not supported.</span></span>  
  
-   <span data-ttu-id="fcd2e-136">La replica aggiunge la colonna **msrepl_tran_version** alle tabelle pubblicate per consentire il rilevamento.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-136">Replication adds the **msrepl_tran_version** column to published tables for tracking purposes.</span></span> <span data-ttu-id="fcd2e-137">A causa di questa colonna aggiuntiva, tutte le istruzioni `INSERT` devono includere un elenco di colonne.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-137">Because of this additional column, all `INSERT` statements should include a column list.</span></span>  
  
-   <span data-ttu-id="fcd2e-138">Per apportare modifiche allo schema in una tabella di una pubblicazione che supporta le sottoscrizioni aggiornabili, è necessario arrestare tutte le attività nella tabella nel server di pubblicazione e nei Sottoscrittori e propagare a tutti i nodi le modifiche ai dati in sospeso prima di apportare modifiche allo schema.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-138">To make schema changes on a table in a publication that supports updating subscriptions, all activity on the table must be stopped at the Publisher and Subscribers, and pending data changes must be propagated to all nodes before making any schema changes.</span></span> <span data-ttu-id="fcd2e-139">In questo modo le transazioni in sospeso non entrano in conflitto con le modifiche allo schema in sospeso.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-139">This ensures that outstanding transactions do not conflict with the pending schema change.</span></span> <span data-ttu-id="fcd2e-140">Dopo avere propagato a tutti i nodi le modifiche dello schema, è possibile riprendere le attività nelle tabelle pubblicate.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-140">After the schema changes have propagated to all nodes, activity can resume on the published tables.</span></span> <span data-ttu-id="fcd2e-141">Per altre informazioni, vedere [Come mettere una topologia di replica in stato di inattività &#40;programmazione Transact-SQL della replica&#41;](../administration/quiesce-a-replication-topology-replication-transact-sql-programming.md).</span><span class="sxs-lookup"><span data-stu-id="fcd2e-141">For more information, see [Quiesce a Replication Topology &#40;Replication Transact-SQL Programming&#41;](../administration/quiesce-a-replication-topology-replication-transact-sql-programming.md).</span></span>  
  
-   <span data-ttu-id="fcd2e-142">Se si prevede di passare da una modalità di aggiornamento all'altra, è necessario eseguire l'agente di lettura coda almeno una volta dopo l'inizializzazione della sottoscrizione. Per impostazione predefinita, l'agente di lettura coda viene eseguito continuamente.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-142">If you plan to switch between update modes, the Queue Reader Agent must run at least once after the subscription has been initialized (by default, the Queue Reader Agent runs continuously).</span></span>  
  
-   <span data-ttu-id="fcd2e-143">Se il database del Sottoscrittore è partizionato orizzontalmente e nella partizione vi sono righe presenti nel Sottoscrittore ma non nel server di pubblicazione, il Sottoscrittore non potrà aggiornare tali righe.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-143">If the Subscriber database is partitioned horizontally and there are rows in the partition that exist at the Subscriber, but not at the Publisher, the Subscriber cannot update the preexisting rows.</span></span> <span data-ttu-id="fcd2e-144">I tentativi di aggiornamento di queste righe generano un errore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-144">Attempting to update these rows returns an error.</span></span> <span data-ttu-id="fcd2e-145">In questi casi è necessario eliminare le righe dalla tabella e quindi aggiungerle nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-145">The rows should be deleted from the table and then added at the Publisher.</span></span>  
  
### <a name="updates-at-the-subscriber"></a><span data-ttu-id="fcd2e-146">Aggiornamenti nel Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="fcd2e-146">Updates at the Subscriber</span></span>  
  
-   <span data-ttu-id="fcd2e-147">Gli aggiornamenti nel Sottoscrittore vengono propagati al server di pubblicazione, anche se una sottoscrizione è scaduta o inattiva.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-147">Updates at the Subscriber are propagated to the Publisher even if a subscription is expired or is inactive.</span></span> <span data-ttu-id="fcd2e-148">Verificare che tali sottoscrizioni vengano eliminate o reinizializzate.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-148">Ensure that any such subscriptions are either dropped or reinitialized.</span></span>  
  
-   <span data-ttu-id="fcd2e-149">Se le colonne `TIMESTAMP` o `IDENTITY` vengono usate e replicate come tipi di dati di base, i valori contenuti non devono essere aggiornati nel sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-149">If `TIMESTAMP` or `IDENTITY` columns are used, and they are replicated as their base data types, values in these columns should not be updated at the Subscriber.</span></span>  
  
-   <span data-ttu-id="fcd2e-150">I sottoscrittori non possono aggiornare o inserire valori `text`, `ntext` o `image` perché non è possibile leggere dalle tabelle inserite o eliminate all'interno dei trigger di rilevamento modifiche della replica.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-150">Subscribers cannot update or insert `text`, `ntext` or `image` values because it is not possible to read from the inserted or deleted tables inside the replication change-tracking triggers.</span></span> <span data-ttu-id="fcd2e-151">In modo analogo, i sottoscrittori non possono aggiornare o inserire valori `text` o `image` tramite `WRITETEXT` o `UPDATETEXT` perché i dati vengono sovrascritti dal server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-151">Similarly, Subscribers cannot update or insert `text` or `image` values using `WRITETEXT` or `UPDATETEXT` because the data is overwritten by the Publisher.</span></span> <span data-ttu-id="fcd2e-152">È invece possibile partizionare le colonne `text` e `image` in una tabella distinta e modificare le due tabelle all'interno di una transazione.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-152">Instead, you could partition the `text` and `image` columns into a separate table and modify the two tables within a transaction.</span></span>  
  
     <span data-ttu-id="fcd2e-153">Per aggiornare gli oggetti di grandi dimensioni in un sottoscrittore, usare i tipi di dati `varchar(max)`, `nvarchar(max)`, `varbinary(max)` anziché, rispettivamente, `text`, `ntext`, e `image`.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-153">To update large objects at a Subscriber, use the data types `varchar(max)`, `nvarchar(max)`, `varbinary(max)` instead of `text`, `ntext`, and `image` data types, respectively.</span></span>  
  
-   <span data-ttu-id="fcd2e-154">Gli aggiornamenti delle chiavi univoche, incluse le chiavi primarie, che generano duplicati, ad esempio, un aggiornamento del form `UPDATE <column> SET <column> =<column>+1` , non sono consentiti e vengono rifiutati in quanto violazioni dell'univocità.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-154">Updates to unique keys (including primary keys) that generate duplicates (for example, an update of the form `UPDATE <column> SET <column> =<column>+1` are not allowed and will be rejected because of a uniqueness violation.</span></span> <span data-ttu-id="fcd2e-155">Questo avviene perché gli aggiornamenti dei set eseguiti nel sottoscrittore vengono propagati tramite replica come singole istruzioni `UPDATE` per tutte le righe interessate.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-155">This is because set updates made at the Subscriber are propagated by replication as individual `UPDATE` statements for each row affected.</span></span>  
  
-   <span data-ttu-id="fcd2e-156">Se il database del Sottoscrittore è partizionato orizzontalmente e nella partizione vi sono righe presenti nel Sottoscrittore ma non nel server di pubblicazione, il Sottoscrittore non potrà aggiornare tali righe.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-156">If the Subscriber database is partitioned horizontally and there are rows in the partition that exist at the Subscriber but not at the Publisher, the Subscriber cannot update the pre-existing rows.</span></span> <span data-ttu-id="fcd2e-157">I tentativi di aggiornamento di queste righe generano un errore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-157">Attempting to update these rows returns an error.</span></span> <span data-ttu-id="fcd2e-158">In questi casi è necessario eliminare le righe dalla tabella e inserirle di nuovo.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-158">The rows should be deleted from the table and inserted again.</span></span>  
  
### <a name="user-defined-triggers"></a><span data-ttu-id="fcd2e-159">Trigger definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="fcd2e-159">User-defined Triggers</span></span>  
  
-   <span data-ttu-id="fcd2e-160">Se per l'applicazione sono necessari trigger nel sottoscrittore, i trigger devono essere definiti con l'opzione `NOT FOR REPLICATION` nel server di pubblicazione e nel sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-160">If the application requires triggers at the Subscriber, the triggers should be defined with the `NOT FOR REPLICATION` option at the Publisher and Subscriber.</span></span> <span data-ttu-id="fcd2e-161">In questo modo, i trigger vengono attivati solo per modifiche ai dati originali, ma non quando le modifiche vengono replicate.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-161">This ensures that triggers fire only for the original data change, but not when that change is replicated.</span></span>  
  
     <span data-ttu-id="fcd2e-162">Verificare che il trigger definito dall'utente non venga attivato quando il trigger di replica aggiorna la tabella.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-162">Ensure that the user-defined trigger does not fire when the replication trigger updates the table.</span></span> <span data-ttu-id="fcd2e-163">A tale scopo, chiamare la procedura `sp_check_for_sync_trigger` nel corpo del trigger definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-163">This is accomplished by calling the procedure `sp_check_for_sync_trigger` in the body of the user-defined trigger.</span></span> <span data-ttu-id="fcd2e-164">Per altre informazioni, vedere [sp_addlinkedserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-check-for-sync-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fcd2e-164">For more information, see [sp_check_for_sync_trigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-check-for-sync-trigger-transact-sql).</span></span>  
  
### <a name="immediate-updating"></a><span data-ttu-id="fcd2e-165">Aggiornamento immediato</span><span class="sxs-lookup"><span data-stu-id="fcd2e-165">Immediate Updating</span></span>  
  
-   <span data-ttu-id="fcd2e-166">Per le sottoscrizioni ad aggiornamento immediato, le modifiche nel Sottoscrittore vengono propagate al server di pubblicazione e applicate tramite Microsoft Distributed Transaction Coordinator (MS DTC).</span><span class="sxs-lookup"><span data-stu-id="fcd2e-166">For immediate updating subscriptions, changes at the Subscriber are propagated to the Publisher and applied using Microsoft Distributed Transaction Coordinator (MS DTC).</span></span> <span data-ttu-id="fcd2e-167">Verificare che MS DTC sia installato e configurato nel server di pubblicazione e nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-167">Ensure that MS DTC is installed and configured at the Publisher and Subscriber.</span></span> <span data-ttu-id="fcd2e-168">Per ulteriori informazioni, vedere la documentazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-168">For more information, see the Windows documentation.</span></span>  
  
-   <span data-ttu-id="fcd2e-169">Per i trigger utilizzati dalle sottoscrizioni ad aggiornamento immediato, per replicare le modifiche è necessaria una connessione al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-169">The triggers used by immediate updating subscriptions require a connection to the Publisher to replicate changes.</span></span>  
  
-   <span data-ttu-id="fcd2e-170">Se la pubblicazione consente le sottoscrizioni ad aggiornamento immediato e un articolo nella pubblicazione contiene un filtro colonne, non è possibile escludere tramite il filtro le colonne che non ammettono valori Null senza valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-170">If the publication allows immediate updating subscriptions and an article in the publication has a column filter, you cannot filter out non-nullable columns without defaults.</span></span>  
  
### <a name="queued-updating"></a><span data-ttu-id="fcd2e-171">Aggiornamento in coda</span><span class="sxs-lookup"><span data-stu-id="fcd2e-171">Queued Updating</span></span>  
  
-   <span data-ttu-id="fcd2e-172">Le tabelle incluse in una pubblicazione di tipo merge non possono essere pubblicate anche come parte di una pubblicazione transazionale che consente le sottoscrizioni ad aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-172">Tables included in a merge publication cannot also be published as part of a transactional publication that allows queued updating subscriptions.</span></span>  
  
-   <span data-ttu-id="fcd2e-173">La chiave primaria viene utilizzata come indicatore di posizione dei record per tutte le query, pertanto non è consigliabile apportare aggiornamenti a colonne chiave primaria quando si utilizza l'aggiornamento in coda.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-173">Updates made to primary key columns are not recommended when using queued updating because the primary key is used as a record locator for all queries.</span></span> <span data-ttu-id="fcd2e-174">Quando i criteri di risoluzione dei conflitti sono impostati su Prevale il Sottoscrittore, è necessario prestare attenzione durante l'aggiornamento delle chiavi primarie.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-174">When the conflict resolution policy is set to Subscriber Wins, updates to primary keys should be made with caution.</span></span> <span data-ttu-id="fcd2e-175">Se gli aggiornamenti alla chiave primaria vengono eseguiti sia nel Sottoscrittore che nel server di pubblicazione, si ottengono due righe con chiavi primarie diverse.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-175">If updates to the primary key are made at both the Publisher and at the Subscriber, the result will be two rows with different primary keys.</span></span>  
  
-   <span data-ttu-id="fcd2e-176">Per le colonne del tipo di dati `SQL_VARIANT`:, quando i dati vengono inseriti o aggiornati nel sottoscrittore, ne viene eseguito il mapping dall'agente di lettura coda quando vengono copiati dal sottoscrittore alla coda nel modo illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fcd2e-176">For columns of data type `SQL_VARIANT`: when data is inserted or updated at the Subscriber, it is mapped in the following way by the Queue Reader Agent when it is copied from the Subscriber to the queue:</span></span>  
  
    -   <span data-ttu-id="fcd2e-177">Viene eseguito il mapping di `BIGINT`, `DECIMAL`, `NUMERIC`, `MONEY` e `SMALLMONEY` a `NUMERIC`.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-177">`BIGINT`, `DECIMAL`, `NUMERIC`, `MONEY`, and `SMALLMONEY` are mapped to `NUMERIC`.</span></span>  
  
    -   <span data-ttu-id="fcd2e-178">Viene eseguito il mapping di `BINARY` e `VARBINARY` ai dati `VARBINARY`.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-178">`BINARY` and `VARBINARY` are mapped to `VARBINARY` data.</span></span>  
  
### <a name="conflict-detection-and-resolution"></a><span data-ttu-id="fcd2e-179">Rilevamento e risoluzione di conflitti</span><span class="sxs-lookup"><span data-stu-id="fcd2e-179">Conflict Detection and Resolution</span></span>  
  
-   <span data-ttu-id="fcd2e-180">Per i criteri di risoluzione dei conflitti Prevale il Sottoscrittore: la risoluzione dei conflitti non è supportata per gli aggiornamenti alle colonne chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-180">For the Subscriber Wins conflict policy: conflict resolution is not supported for updates to primary key columns.</span></span>  
  
-   <span data-ttu-id="fcd2e-181">I conflitti provocati dagli errori relativi ai vincoli di chiave esterna non vengono risolti dalla replica:</span><span class="sxs-lookup"><span data-stu-id="fcd2e-181">Conflicts due to foreign key constraint failures are not resolved by replication:</span></span>  
  
    -   <span data-ttu-id="fcd2e-182">Se non si prevedono conflitti e i dati sono partizionati correttamente, ovvero se i Sottoscrittori non aggiornano le stesse righe, è possibile utilizzare vincoli di chiave esterna nel server di pubblicazione e nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-182">If conflicts are not expected and data is well partitioned (Subscribers do not update the same rows), you can use foreign key constraints on the Publisher and Subscribers.</span></span>  
  
    -   <span data-ttu-id="fcd2e-183">Se si prevedono conflitti, quando si utilizza l'opzione di risoluzione dei conflitti "Prevale il Sottoscrittore", è consigliabile non utilizzare vincoli di chiave esterna nel server di pubblicazione e nel Sottoscrittore, mentre, quando si utilizza l'opzione di risoluzione dei conflitti "Prevale il server di pubblicazione", è consigliabile non utilizzare vincoli di chiave esterna nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="fcd2e-183">If conflicts are expected: you should not use foreign key constraints at the Publisher or Subscriber if you use "Subscriber wins" conflict resolution; you should not use foreign key constraints at the Subscriber if you use "Publisher wins" conflict resolution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd2e-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcd2e-184">See Also</span></span>  
 <span data-ttu-id="fcd2e-185">[Peer-to-Peer Transactional Replication](peer-to-peer-transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fcd2e-185">[Peer-to-Peer Transactional Replication](peer-to-peer-transactional-replication.md) </span></span>  
 <span data-ttu-id="fcd2e-186">[Replica transazionale](transactional-replication.md) </span><span class="sxs-lookup"><span data-stu-id="fcd2e-186">[Transactional Replication](transactional-replication.md) </span></span>  
 <span data-ttu-id="fcd2e-187">[Pubblicare dati e oggetti di database](../publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fcd2e-187">[Publish Data and Database Objects](../publish/publish-data-and-database-objects.md) </span></span>  
 [<span data-ttu-id="fcd2e-188">Sottoscrizione delle pubblicazioni</span><span class="sxs-lookup"><span data-stu-id="fcd2e-188">Subscribe to Publications</span></span>](../subscribe-to-publications.md)  
  
  