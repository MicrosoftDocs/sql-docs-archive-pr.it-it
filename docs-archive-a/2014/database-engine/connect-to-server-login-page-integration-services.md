---
title: Connetti al server (pagina Nome account di accesso) - Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 285518f4a1f3d9180d2c3c07a41bf75a00ea3593
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724139"
---
# <a name="connect-to-server-login-page-integration-services"></a>Connetti al server (pagina Nome account di accesso) - Integration Services
  Utilizzare questa scheda per visualizzare o specificare le opzioni seguenti per la connessione a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .  
  
## <a name="options"></a>Opzioni  
 **Tipo di server**  
 Per la registrazione di un server da Esplora oggetti, selezionare il tipo di server a cui connettersi, ovvero [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services. Nelle altre parti della finestra di dialogo vengono visualizzate solo le opzioni applicabili al tipo di server selezionato. Durante la registrazione di un server da Server registrati, la casella **Tipo server** è di sola lettura e corrisponde al tipo di server visualizzato nel componente Server registrati. Per registrare un tipo diverso di server, selezionare [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services nella barra degli strumenti Server registrati prima di avviare la registrazione di un nuovo server.  
  
 **Nome server**  
 Consente di selezionare il server a cui connettersi. Per impostazione predefinita verrà visualizzata l'ultima istanza del server a cui è stata effettuata la connessione.  
  
> [!NOTE]  
>  Non usare *\<servername>* \\ *\<instancename>* , perché non [!INCLUDE[ssIS](../includes/ssis-md.md)] supporta più istanze in un computer.  
  
 **autenticazione**  
 Solo l'autenticazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows è disponibile per [!INCLUDE[ssIS](../includes/ssis-md.md)]. Tale modalità consente di connettersi tramite un account utente di Windows.  
  
 **Nome utente**  
 Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.  
  
 **Password**  
 Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.  
  
 **Memorizza password**  
 Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.  
  
 **Connettere**  
 Consente di connettersi al server selezionato.  
  
 **Opzioni**  
 Fare clic su questo pulsante per modificare la finestra di dialogo e nascondere le opzioni aggiuntive per la connessione al server, ad esempio le opzioni per la memorizzazione della password.  
  
  
