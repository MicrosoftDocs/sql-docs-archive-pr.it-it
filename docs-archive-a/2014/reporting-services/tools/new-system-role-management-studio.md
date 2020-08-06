---
title: Nuovo ruolo a livello di sistema (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.newsystemrole.f1
ms.assetid: 7b4a0b98-975b-478a-8359-7db39ccbb347
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a744fc78bdd5ae6ef3a37f96ff5ae8cd10f71a80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716016"
---
# <a name="new-system-role-management-studio"></a>Nuovo ruolo a livello di sistema (Management Studio)
  Utilizzare questa pagina per creare una definizione di ruolo a livello di sistema. Tramite una definizione di ruolo a livello di sistema è possibile specificare un set di attività a livello di sistema consentite per un server di report nel suo complesso.  
  
> [!NOTE]  
>  Le definizioni di ruolo vengono utilizzate solo in un server di report in esecuzione in modalità nativa. Se il server di report è configurato per l'integrazione con SharePoint, questa pagina non è disponibile.  
  
## <a name="options"></a>Opzioni  
 **Nome**  
 Consente di digitare la definizione del ruolo. I nomi di definizione di ruolo devono essere univoci nell'ambito dello spazio dei nomi del server di report. Il nome deve includere almeno un carattere alfanumerico. È inoltre possibile utilizzare spazi e alcuni simboli. Il nome non può contenere i caratteri seguenti:  
  
 ; ? : \@ & = +, $/*\< >  
  
 " /  
  
 **Descrizione**  
 Consente di digitare una descrizione per illustrare le modalità di utilizzo del ruolo ed elencare le azioni supportate.  
  
 **Attività**  
 Consente di selezionare le attività a livello di sistema che possono essere eseguite tramite questo ruolo. Non è possibile creare nuove attività o modificare attività esistenti supportate da [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Non è possibile selezionare attività a livello di elemento per una definizione di ruolo a livello di sistema.  
  
 **Descrizione dell'attività**  
 Visualizza una descrizione dell'attività, che include le operazioni o autorizzazioni supportate.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida sensibile al contesto del server di report in Management Studio](report-server-in-management-studio-f1-help.md)   
 [Definizioni di ruolo](../security/role-definitions.md)  
  
  
