---
title: Aggiungere un gruppo (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- groups [Master Data Services], adding
- adding groups [Master Data Services]
ms.assetid: c7a88381-3b2c-4af7-9cf7-3a930c1abdee
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f9da1d558ccb648af8fbc0dd3b802751bd5ae44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721552"
---
# <a name="add-a-group-master-data-services"></a>Aggiungere un gruppo (Master Data Services)
  Aggiungere un gruppo all'elenco **Gruppi** in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] per iniziare il processo di assegnazione dell'autorizzazione all'applicazione Web. Prima che un utente in un gruppo possa accedere a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], è necessario assegnare l'autorizzazione di gruppo a una o più aree funzionali e oggetti modello.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per eseguire questa procedura:  
  
-   È necessario disporre di autorizzazione per accedere all'area funzionale **Autorizzazioni utenti e gruppi** .  
  
### <a name="to-add-a-group"></a>Per aggiungere un gruppo  
  
1.  In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Autorizzazioni utenti e gruppi**.  
  
2.  Nella pagina **Utenti** scegliere **Gestisci gruppi**dalla barra dei menu.  
  
3.  Fare clic su **Aggiungi gruppi**.  
  
4.  Digitare il nome del gruppo preceduto dal nome di dominio di Active Directory o dal nome del computer server, come in *dominio\nome_gruppo* o *computer\nome_gruppo*.  
  
5.  Facoltativamente, fare clic su **Controlla nomi**.  
  
6.  Fare clic su **OK**.  
  
    > [!NOTE]  
    >  Quando l'utente accede per la prima volta a [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], il nome dell'utente viene aggiunto all'elenco di utenti di [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] .  
  
## <a name="next-steps"></a>Passaggi successivi  
  
-   [Assegnare autorizzazioni per aree funzionali &#40;Master Data Services&#41;](assign-functional-area-permissions-master-data-services.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Sicurezza &#40;Master Data Services&#41;](../../2014/master-data-services/security-master-data-services.md)  
  
  
