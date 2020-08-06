---
title: Guida di riferimento a PowerShell per il motore di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3c379a43-c497-47dd-8e7d-2b015c068bb7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2d72f9fcedee02e475369c32a7c263578c9ff156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629589"
---
# <a name="database-engine-powershell-reference"></a>Guida di riferimento a PowerShell per il motore di database
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] include un set di cmdlet di Windows PowerShell 2.0 cmdlet per l'esecuzione di azioni comuni in [!INCLUDE[ssDE](../includes/ssde-md.md)]. È possibile inoltre convertire espressioni di query e Uniform Resource Name (URN) nei percorsi di SQL Server PowerShell o utilizzarli per specificare uno o più oggetti in [!INCLUDE[ssDE](../includes/ssde-md.md)].  
  
## <a name="database-engine-cmdlets"></a>Cmdlet del motore di database  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] include un numero relativamente basso di cmdlet per il [!INCLUDE[ssDE](../includes/ssde-md.md)]. La maggior parte degli script di PowerShell che funzionano con [!INCLUDE[ssDE](../includes/ssde-md.md)] utilizzano il provider di PowerShell per SQL Server e i modelli a oggetti di facilità di gestione di SQL Server. Per altre informazioni, vedere [Provider PowerShell per SQL Server](../powershell/sql-server-powershell-provider.md).  
  
 Per informazioni sulla Guida dei cmdlet di SQL Server in un ambiente Windows PowerShell, vedere [Visualizzazione della Guida di SQL Server PowerShell](../powershell/sql-server-powershell.md).  
  
### <a name="in-this-section"></a>Contenuto della sezione  
 In questa sezione sono incluse informazioni sui cmdlet indicati.  
  
|Descrizione|Cmdlet|  
|-----------------|------------|  
|Esegue script Transact-SQL e XQuery, ad esempio script che possono essere eseguiti tramite l'utilità `sqlcmd`.|[Cmdlet Invoke-Sqlcmd](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|Valuta se un oggetto Motore di database è conforme alla gestione basata su criteri.|[cmdlet Invoke-PolicyEvaluation](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
  
### <a name="information-about-other-cmdlets"></a>Informazioni su altri cmdlet  
 I cmdlet `Encode-Sqlname` e `Decode-Sqlname` consentono di specificare identificatori SQL Server che contengono caratteri non supportati nei percorsi di Windows PowerShell. Per altre informazioni, vedere [Identificatori di SQL Server in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).  
  
 Utilizzare il cmdlet `Convert-UrnToPath` per convertire un Unique Resource Name per un oggetto [!INCLUDE[ssDE](../includes/ssde-md.md)] in un percorso del provider PowerShell per SQL Server. Per altre informazioni, vedere [Conversione di URN in percorsi di provider di SQL Server](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).  
  
## <a name="query-expressions-and-unique-resource-names"></a>Espressioni di query e Unique Resource Name  
 Le espressioni di query sono stringhe che utilizzano una sintassi analoga a XPath per specificare un set di criteri utilizzato per enumerare uno o più oggetti in una gerarchia del modello a oggetti. L'URN (Unique Resource Name) è un tipo specifico di stringa di espressione di query che identifica un singolo oggetto in modo univoco. Per altre informazioni, vedere [Espressioni di query e Uniform Resource Name](../powershell/query-expressions-and-uniform-resource-names.md).  
  
## <a name="see-also"></a>Vedere anche  
 [SQL Server PowerShell](../powershell/sql-server-powershell.md)  
  
  
