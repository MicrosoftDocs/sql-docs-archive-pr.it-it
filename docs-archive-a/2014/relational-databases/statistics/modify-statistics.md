---
title: Modificare statistiche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- statistics [SQL Server], modifying
- modifying statistics
ms.assetid: b06299ca-ed52-411a-b245-45eac4628c99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6dd44da6d1a80050f37f08e49773f95af0e5a339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636624"
---
# <a name="modify-statistics"></a>Modificare statistiche
  È possibile modificare statistiche esistenti in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
 **Contenuto dell'articolo**  
  
-   **Prima di iniziare:**  
  
     [Sicurezza](#Security)  
  
-   **Modificare statistiche tramite:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Prima di iniziare  
  
###  <a name="security"></a><a name="Security"></a> Sicurezza  
  
####  <a name="permissions"></a><a name="Permissions"></a> Autorizzazioni  
 Sono necessarie le autorizzazioni seguenti:  
  
-   L'utente deve disporre dell'autorizzazione ALTER per la tabella o la vista.  
  
-   L'utente deve essere il proprietario della tabella o della vista indicizzata o un membro di uno dei seguenti ruoli: ruolo predefinito del server **sysadmin** , ruolo predefinito del database **db_owner** o ruolo predefinito del database **db_ddladmin** .  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Utilizzo di SQL Server Management Studio  
  
#### <a name="to-modify-statistics"></a>Per modificare le statistiche  
  
1.  In **Esplora oggetti**fare clic sul segno più per espandere il database in cui si desidera modificare una statistica.  
  
2.  Fare clic sul segno più per espandere la cartella **Tabelle** .  
  
3.  Fare clic sul segno più per espandere la tabella in cui si desidera modificare una statistica.  
  
4.  Fare clic sul segno più per espandere la cartella **Statistiche** .  
  
5.  Fare clic con il pulsante destro del mouse sull'oggetto statistiche che si vuole modificare e scegliere **Proprietà**.  
  
6.  Nella pagina **Generali** della finestra di dialogo **Proprietà statistiche -** *nome_statistiche* fare clic su **Aggiungi**, **Rimuovi**, **Sposta su** o **Sposta giù**, o su qualsiasi combinazione, per modificare le proprietà delle statistiche. Si noti che la posizione di una colonna nella griglia **Colonne statistiche** può avere un impatto significativo sull'utilità delle statistiche.  
  
7.  Fare clic su **OK**.  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Uso di Transact-SQL  
 **Per modificare le statistiche**  
  
 Non è possibile eseguire questa attività utilizzando istruzioni Transact-SQL. Per modificare statistiche tramite Transact-SQL, è innanzitutto necessario eliminare la statistica esistente e quindi ricrearla con i nuovi attributi.  
  
 Per altre informazioni, vedere [DROP STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-statistics-transact-sql) e [CREATE STATISTICS &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-statistics-transact-sql).  
  
  
