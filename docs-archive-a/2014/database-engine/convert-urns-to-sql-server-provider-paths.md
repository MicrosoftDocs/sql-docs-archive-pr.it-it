---
title: Convertire URN in percorsi di provider di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628972"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a>Conversione di URN in percorsi di provider di SQL Server
  Il modello SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Objects) consente di compilare URN (Uniform Resource Name) per gli oggetti. Ogni URN identifica in modo univoco un oggetto SMO e può essere convertito in un percorso di provider di SQL Server PowerShell tramite il cmdlet `Convert-UrnToPath`.  
  
## <a name="converting-urns-to-paths"></a>Conversione di URN in percorsi  
 Ciascun URN dispone delle stesse informazioni di un percorso dell'oggetto, ma in formato diverso. Ad esempio, di seguito è riportato il percorso di una tabella:  
  
 SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address  
  
 Di seguito è riportato l'URN dello stesso oggetto:  
  
 Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']  
  
 Se è stato creato un oggetto SMO in uno script di PowerShell, è possibile fare riferimento alla proprietà `Urn` per ottenere l'URN dell'oggetto e quindi utilizzare il cmdlet `Convert-UrnToPath` per convertire la stringa URN SMO in un percorso di Windows PowerShell. È quindi possibile utilizzare il provider per passare a posizioni diverse nel percorso.  
  
 Se i nomi di nodo contengono caratteri estesi non supportati nei nomi di percorso di Windows PowerShell, `Convert-UrnToPath` li codifica nella rappresentazione esadecimale. Ad esempio, "My:Table" viene restituito come "My%3ATable".  
  
 Per esempi dell'utilizzo del cmdlet, in Windows PowerShell eseguire:  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Espressioni di query e nomi di risorse uniformi](../powershell/query-expressions-and-uniform-resource-names.md)   
 [Provider di SQL Server PowerShell](../powershell/sql-server-powershell-provider.md)   
 [SQL Server PowerShell](../powershell/sql-server-powershell.md)  
