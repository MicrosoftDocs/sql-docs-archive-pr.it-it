---
title: 'Esercitazione: Preparazione del server per la replica | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: ce30a095-2975-4387-9377-94a461ac78ee
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1f036ff2a111ee6b5f97655b9bebaf34391a436
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637742"
---
# <a name="tutorial-preparing-the-server-for-replication"></a>Esercitazione: Preparazione del server per la replica
  È importante pianificare la sicurezza prima di configurare la topologia di replica. In questa esercitazione viene illustrato come proteggere la topologia di replica e come configurare la distribuzione, ovvero il primo passaggio nella replica dei dati. È necessario completare questa esercitazione prima delle altre esercitazioni sulla replica.  
  
> [!NOTE]  
>  Per eseguire in modo protetto la replica dei dati tra server, è consigliabile seguire le indicazioni riportate in [Procedure consigliate per la sicurezza della replica](security/replication-security-best-practices.md).  
  
## <a name="what-you-will-learn"></a>Lezioni dell'esercitazione  
 In questa esercitazione verranno descritte le procedure per preparare i server in modo che la replica possa essere eseguita in modo protetto con privilegi minimi. Nella prima lezione viene illustrato come creare gli account di servizio Windows utilizzati per l'esecuzione degli agenti di replica. Nella seconda lezione viene illustrato come configurare la cartella utilizzata per creare e archiviare gli snapshot di pubblicazione. Nella terza lezione viene illustrato come configurare la distribuzione e impostare le autorizzazioni.  
  
## <a name="requirements"></a>Requisiti  
 Questa esercitazione è destinata agli utenti esperti nelle operazioni di database fondamentali ma con una limitata conoscenza della replica.  
  
 Per utilizzare l'esercitazione è necessario che nel sistema siano installati i componenti seguenti:  
  
-   [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] con il database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] . Per una maggiore sicurezza, i database di esempio non vengono installati per impostazione predefinita.  
  
 **Tempo stimato per il completamento di questa esercitazione: 30 minuti.**  
  
## <a name="lessons-in-this-tutorial"></a>Lezioni dell'esercitazione  
  
-   [Lezione 1: Creazione di account di Windows per la replica](lesson-1-creating-windows-accounts-for-replication.md)  
  
-   [Lezione 2: Preparazione della cartella snapshot](lesson-2-preparing-the-snapshot-folder.md)  
  
-   [Lezione 3: Configurazione della distribuzione](lesson-3-configuring-distribution.md)  
  
 [Avviare l'esercitazione](lesson-1-creating-windows-accounts-for-replication.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Configura distribuzione](configure-distribution.md)   
 [Sicurezza replica di SQL Server](security/view-and-modify-replication-security-settings.md)  
  
  
