---
title: Sicurezza agente di lettura coda | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.security.QRA.f1
helpviewer_keywords:
- Queue Reader Agent Security dialog box
ms.assetid: 77938da0-2afd-4455-8826-f4a6a9440cb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 22a5e5751184b626ab1af86f01782a42028b5ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636684"
---
# <a name="queue-reader-agent-security"></a>Sicurezza agente di lettura coda
  La finestra di dialogo **Sicurezza agente di lettura coda** consente di specificare l'account di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con cui viene eseguito l'agente di lettura coda e vengono stabilite le connessioni locali al server di distribuzione. L'agente si connette al server di pubblicazione utilizzando l'account specificato nella finestra di dialogo **Proprietà server di pubblicazione** , alla quale è possibile accedere dalla finestra di dialogo **Proprietà server di distribuzione** . L'agente si connette al Sottoscrittore utilizzando lo stesso contesto dell'agente di distribuzione per la sottoscrizione. Per altre informazioni, vedere [View and Modify Replication Security Settings](security/view-and-modify-replication-security-settings.md).  
  
 L'account deve essere valido è deve essere stata specificata la password corretta. Gli account e le password vengono convalidati solo dopo l'avvio dell'esecuzione di un agente.  
  
## <a name="options"></a>Opzioni  
 **Account processo**  
 Consente di immettere l'account di Windows con cui viene eseguito l'agente di lettura coda nel server di distribuzione. L'account di Windows specificato deve essere almeno membro del ruolo predefinito del database **db_owner** nel server di distribuzione.  
  
 **Password** e **Conferma password**  
 Immettere la password per l'account di Windows.  
  
## <a name="see-also"></a>Vedere anche  
 [Gestire gli account di accesso e le password nella replica](security/identity-and-access-control-replication.md#manage-logins-and-passwords-in-replication)   
 [Modello di sicurezza dell'agente di replica](security/replication-agent-security-model.md)   
 [Panoramica degli agenti di replica](agents/replication-agents-overview.md)   
 [Procedure consigliate per la sicurezza della replica](security/replication-security-best-practices.md)  
  
  
