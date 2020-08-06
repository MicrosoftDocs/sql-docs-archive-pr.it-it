---
title: Finestra di dialogo "Impostazioni server di pubblicazione" di replica di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publishersettings.f1
helpviewer_keywords:
- Publisher Settings dialog box
ms.assetid: 4fb70427-082d-4179-82a1-34b235accc43
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a9a5ca5b0d7bfae895287708af159f3316e4474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724491"
---
# <a name="sql-server-replication-publisher-settings-dialog-box"></a><span data-ttu-id="74bcc-102">Finestra di dialogo "Impostazioni server di pubblicazione" di replica di SQL Server</span><span class="sxs-lookup"><span data-stu-id="74bcc-102">SQL Server Replication 'Publisher Settings' dialog box</span></span>
  <span data-ttu-id="74bcc-103">La finestra di dialogo **Impostazioni server di pubblicazione** consente di modificare le impostazioni per i server di pubblicazione aggiunti al riquadro sinistro di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="74bcc-103">The **Publisher Settings** dialog box allows you to change settings for Publishers that have been added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74bcc-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="74bcc-104">Options</span></span>  
 <span data-ttu-id="74bcc-105">**Connessione server di pubblicazione**</span><span class="sxs-lookup"><span data-stu-id="74bcc-105">**Publisher Connection**</span></span>  
 <span data-ttu-id="74bcc-106">Fare clic su questo pulsante per aprire la finestra di dialogo **Connetti al server** , che consente di visualizzare e modificare le proprietà e le credenziali di connessione utilizzate da Monitoraggio replica per la connessione a un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="74bcc-106">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to a Publisher.</span></span>  
  
 <span data-ttu-id="74bcc-107">**Connessione server di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="74bcc-107">**Distributor Connection**</span></span>  
 <span data-ttu-id="74bcc-108">Questa opzione viene visualizzata solo se il server di pubblicazione utilizza un server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="74bcc-108">Displayed only if the Publisher uses a remote Distributor.</span></span> <span data-ttu-id="74bcc-109">Fare clic su questo pulsante per visualizzare la finestra di dialogo **Connetti al server** , che consente di visualizzare e modificare le proprietà e le credenziali di connessione utilizzate da Monitoraggio replica per la connessione al server di distribuzione remoto.</span><span class="sxs-lookup"><span data-stu-id="74bcc-109">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to the remote Distributor.</span></span>  
  
 <span data-ttu-id="74bcc-110">**Connetti automaticamente all'avvio di Monitoraggio replica**</span><span class="sxs-lookup"><span data-stu-id="74bcc-110">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="74bcc-111">Selezionare questa casella di controllo per consentire a Monitoraggio replica di connettersi automaticamente al server di distribuzione e di recuperare informazioni sullo stato del server di pubblicazione selezionato nella griglia posta nella parte superiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="74bcc-111">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="74bcc-112">Se questa casella di controllo è deselezionata è necessario connettersi manualmente dopo l'avvio di Monitoraggio replica. Fare clic con il pulsante destro del mouse sul server di pubblicazione visualizzato nel riquadro sinistro di Monitoraggio replica e scegliere **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="74bcc-112">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="74bcc-113">**Aggiorna automaticamente lo stato del server di pubblicazione e delle sue pubblicazioni**</span><span class="sxs-lookup"><span data-stu-id="74bcc-113">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="74bcc-114">Selezionare questa opzione per consentire a Monitoraggio replica di aggiornare automaticamente lo stato del server di pubblicazione selezionato nella griglia posta nella parte superiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="74bcc-114">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="74bcc-115">Se questa opzione è selezionata, Monitoraggio replica esegue il polling del server di distribuzione per ottenere informazioni sullo stato del server di pubblicazione e delle relative pubblicazioni.</span><span class="sxs-lookup"><span data-stu-id="74bcc-115">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="74bcc-116">L'intervallo di polling viene impostato dall'opzione **Frequenza di aggiornamento** .</span><span class="sxs-lookup"><span data-stu-id="74bcc-116">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="74bcc-117">Per altre informazioni sull'aggiornamento in Monitoraggio replica, vedere [Memorizzazione nella cache, aggiornamento e prestazioni di Monitoraggio replica](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="74bcc-117">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="74bcc-118">**Frequenza di aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="74bcc-118">**Refresh rate**</span></span>  
 <span data-ttu-id="74bcc-119">Immettere un valore, espresso in secondi, per specificare la frequenza di polling del server di distribuzione per ottenere informazioni sullo stato da parte di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="74bcc-119">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="74bcc-120">Valori inferiori indicano un polling più frequente, che influisce sulle prestazioni del server di distribuzione se il monitoraggio include un numero elevato di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="74bcc-120">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="74bcc-121">È consigliabile eseguire prove sul sistema per determinare un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="74bcc-121">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="74bcc-122">L'impostazione **Frequenza di aggiornamento** viene utilizzata anche se si seleziona **Aggiornamento automatico** in una delle finestre dei dettagli di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="74bcc-122">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="74bcc-123">**Mostra server di pubblicazione nel gruppo seguente**</span><span class="sxs-lookup"><span data-stu-id="74bcc-123">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="74bcc-124">Selezionare un gruppo di server di pubblicazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="74bcc-124">Select a Publisher group from the list.</span></span> <span data-ttu-id="74bcc-125">Il server di pubblicazione viene visualizzato in questo gruppo nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="74bcc-125">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="74bcc-126">I gruppi consentono di organizzare i server di pubblicazione e non influiscono sul funzionamento della replica.</span><span class="sxs-lookup"><span data-stu-id="74bcc-126">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span>  
  
 <span data-ttu-id="74bcc-127">**Nuovo gruppo**</span><span class="sxs-lookup"><span data-stu-id="74bcc-127">**New Group**</span></span>  
 <span data-ttu-id="74bcc-128">Fare clic su questa opzione per creare un nuovo gruppo di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="74bcc-128">Click to create a new Publisher group.</span></span> <span data-ttu-id="74bcc-129">Un gruppo di server di pubblicazione consente di organizzare facilmente i server di pubblicazione all'interno di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="74bcc-129">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="74bcc-130">I gruppi non influiscono sulla replica dei dati o sulla relazione tra i server in una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="74bcc-130">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74bcc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74bcc-131">See Also</span></span>  
 <span data-ttu-id="74bcc-132">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="74bcc-132">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="74bcc-133">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="74bcc-133">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  