---
title: Disabilitare i vincoli di chiave esterna per la replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627671"
---
# <a name="disable-foreign-key-constraints-for-replication"></a>Disabilitare i vincoli di chiave esterna per la replica
  È possibile disabilitare vincoli di chiave esterna per la replica in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]. Questa operazione può essere utile se si pubblicano dati da una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
> [!NOTE]  
>  Se una tabella viene pubblicata usando la replica, i vincoli di chiave esterna vengono disabilitati automaticamente per le operazioni eseguite dagli agenti di replica. Quando un agente di replica esegue un accodamento, aggiornamento o una eliminazione a un sottoscrittore, il vincolo non viene controllato; se invece un utente esegue un accodamento, un aggiornamento o una eliminazione, il vincolo viene controllato. Il vincolo viene disabilitato per l'agente di replica in quanto esso è già stato controllato nel server di pubblicazione quando i dati sono stati inseriti, aggiornati o eliminati.  
  
 **Contenuto dell'articolo**  
  
-   **Prima di iniziare:**  
  
     [Sicurezza](#Security)  
  
-   **Per disabilitare un vincolo di chiave esterna per la replica usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Prima di iniziare  
  
###  <a name="security"></a><a name="Security"></a> Sicurezza  
  
####  <a name="permissions"></a><a name="Permissions"></a> Autorizzazioni  
 È necessario disporre dell'autorizzazione ALTER per la tabella.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Con SQL Server Management Studio  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a>Per disabilitare un vincolo di chiave esterna per la replica  
  
1.  In **Esplora oggetti**espandere la tabella contenente il vincolo di chiave esterna che si desidera modificare, quindi espandere la cartella **Chiavi** .  
  
2.  Fare clic con il pulsante destro del mouse sul vincolo di chiave esterna e selezionare **Modifica**.  
  
3.  Nella finestra di dialogo **Relazioni chiavi esterne** scegliere **No** per **Attiva per replica**.  
  
4.  Fare clic su **Close**.  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Con Transact-SQL  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a>Per disabilitare un vincolo di chiave esterna per la replica  
  
1.  Per eseguire questa attività in [!INCLUDE[tsql](../../includes/tsql-md.md)], rimuovere il vincolo della chiave esterna. Successivamente aggiungere un nuovo vincolo della chiave esterna e specificare l'opzione NOT FOR REPLICATION.  
  
 Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).  
  
###  <a name="TsqlExample"></a>  
