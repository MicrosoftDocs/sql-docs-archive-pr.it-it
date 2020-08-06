---
title: Proprietà SQL Server Agent (pagina Cronologia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.agent.history.f1
ms.assetid: dc73734c-b3c3-407f-bbd1-8714b4fa47b0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d67ff3da97e11292abcac03958fe1e423b35d7d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636517"
---
# <a name="sql-server-agent-properties-history-page"></a>Proprietà SQL Server Agent (pagina Cronologia)
  Utilizzare questa pagina per visualizzare e modificare le impostazioni per la gestione del [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log della cronologia del servizio Agent.  
  
## <a name="options"></a>Opzioni  
 **Limita dimensioni log cronologia processo**  
 Consente di impostare limiti sulla quantità di informazioni sulla cronologia processo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene nel log.  
  
 **Dimensioni massime log cronologia processo (righe)**  
 Consente di impostare il numero massimo di righe che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene nel log. Quando il log raggiunge dimensioni tali da contenere questo numero di righe, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent rimuove le righe meno recenti per consentire l'inserimento delle nuove.  
  
 **Numero massimo di righe di cronologia per processo**  
 Consente di impostare il numero massimo di righe che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent mantiene per ogni processo. Quando la cronologia di un determinato processo si estende fino a contenere questo numero di righe, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consente di rimuovere le righe meno recenti per consentire l'inserimento delle nuove.  
  
 **Rimuovi cronologia dell'agente**  
 Viene indicato che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent consentirà di rimuovere le voci presenti nel log da più tempo rispetto a quanto specificato. Si tratta di un'esecuzione singola che consente di rimuovere la cronologia. Se è necessario un processo ricorrente, creare e pianificare un piano di manutenzione con un processo di pulizia.  
  
 **Più vecchia di**  
 Consente di impostare il periodo di tempo per cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent manterrà le voci.  
  
## <a name="see-also"></a>Vedere anche  
 [Log degli errori di SQL Server Agent](sql-server-agent-error-log.md)  
  
  
