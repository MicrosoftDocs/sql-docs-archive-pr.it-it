---
title: Database crittografati con Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624953"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a>Database crittografati con gruppi di disponibilità AlwaysOn (SQL Server)
  In questo argomento sono contenute informazioni su come utilizzare correttamente database crittografati o recentemente decrittografati con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].  
  
 **Contenuto dell'argomento**  
  
-   [Limitazioni e restrizioni](#Restrictions)  
  
-   [Attività correlate](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> Limitazioni e restrizioni  
  
-   Se un database viene crittografato o contiene una chiave di crittografia del database (DEK), non è possibile usare [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] o [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] per aggiungere il database a un gruppo di disponibilità. Anche se è stato decrittografato un database crittografato, i backup del log potrebbero contenere dati crittografati. In questo caso, la sincronizzazione dei dati iniziale completa potrebbe non riuscire sul database. Questo avviene perché l'operazione di ripristino del log potrebbe richiedere il certificato usato dalle chiavi di crittografia del database e tale certificato potrebbe non essere disponibile.  
  
     Affinché un database decrittografato sia idoneo a essere aggiunto a un gruppo di disponibilità usando la procedura guidata:  
  
    1.  Creare un backup del log del database primario.  
  
    2.  Creare un backup del log completo del database primario.  
  
    3.  Ripristinare il backup del database nell'istanza del server in cui è ospitata la replica secondaria.  
  
    4.  Creare un nuovo backup del log dal database primario.  
  
    5.  Ripristinare questo backup del log sul database secondario.  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> Attività correlate  
  
-   [Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md)   
 [Transparent Data Encryption &#40;TDE&#41;](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
