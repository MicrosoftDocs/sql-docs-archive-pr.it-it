---
title: Modello a oggetti SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711860"
---
# <a name="smo-object-model"></a>Modello a oggetti SMO
  Il modello a oggetti SMO è costituito da una gerarchia di oggetti. L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> rappresenta l'oggetto di livello principale e tutti gli oggetti classe di istanza si trovano all'interno dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.  
  
 La classe <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> è una classe di livello principale con una gerarchia di oggetti distinta. L' <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> oggetto rappresenta [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Servizi e impostazioni di rete disponibili tramite il provider WMI.  
  
 Oltre agli oggetti <xref:Microsoft.SqlServer.Management.Smo.Server> e <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, sono disponibili diverse classi di utilità che rappresentano attività e operazioni, ad esempio <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> o <xref:Microsoft.SqlServer.Management.Smo.Restore>  
  
 Il modello a oggetti SMO è costituito da diversi spazi dei nomi. Per altre informazioni, vedere [Spazio dei nomi SMO](smo-object-model-namespaces.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Diagramma del modello a oggetti SMO](smo-object-model-diagram.md)   
 [Spazi dei nomi SMO](smo-object-model-namespaces.md)   
 [Concetti relativi al provider WMI per Gestione configurazione](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
