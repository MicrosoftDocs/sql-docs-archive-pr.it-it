---
title: Concessione dell'accesso a un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636990"
---
# <a name="granting-access-to-a-database"></a>Concessione dell'accesso a un database
  L'utente Mary dispone ora dell'accesso all'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], ma non delle autorizzazioni necessarie per accedere ai database. L'utente non dispone inoltre dell'accesso al proprio database predefinito **TestData** a meno che non lo si autorizzi in qualità di utente del database.  
  
 Per concedere l'accesso all'utente Mary, passare al database **TestData** e quindi utilizzare l'istruzione CREATE USER per eseguire il mapping dell'account utente a un utente denominato Mary.  
  
### <a name="to-create-a-user-in-a-database"></a>Per creare un utente in un database  
  
1.  Digitare ed eseguire le istruzioni seguenti sostituendo `computer_name` con il nome del computer in uso per concedere all'utente `Mary` l'accesso al database `TestData` .  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     L'utente Mary dispone ora dell'accesso a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e al database `TestData` .  
  
## <a name="next-task-in-lesson"></a>Attività successiva della lezione  
 [Creazione di viste e stored procedure](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
