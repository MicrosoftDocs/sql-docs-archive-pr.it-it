---
title: Percorso di archiviazione del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], storage location
ms.assetid: cf88c62e-581e-42f2-846f-a9bf1d7c3292
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab370889396f40f52a348523e7f268892f549192
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714647"
---
# <a name="database-storage-location"></a>Percorso di archiviazione dei database
  Spesso, un amministratore del database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] desidera che un determinato database risieda al di fuori della cartella di dati del server. Queste situazioni sono il più delle volte determinate da esigenze aziendali, ad esempio il miglioramento delle prestazioni o l'ampliamento dello spazio di archiviazione. In questi casi, la `DbStorageLocation` proprietà di database consente all' [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] amministratore di database di specificare il percorso del database in un disco locale o in un dispositivo di rete.  
  
## <a name="dbstoragelocation-database-property"></a>Proprietà di database DbStorageLocation  
 La proprietà di database `DbStorageLocation` specifica la cartella in cui vengono creati e gestiti tutti i file di dati e di metadati dei database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Tutti i file di metadati vengono archiviati nella cartella `DbStorageLocation`, ad eccezione del file di metadati del database, che viene archiviato nella cartella di dati del server. Per l'impostazione del valore della proprietà di database `DbStorageLocation`, è necessario considerare due fattori importanti:  
  
-   La proprietà di database `DbStorageLocation` deve essere impostata su un percorso di cartella in formato UNC esistente o su una stringa vuota. Una stringa vuota è il valore predefinito per la cartella di dati del server. Se la cartella non esiste, quando si esegue un comando `Create`, `Attach` o `Alter` verrà generato un errore.  
  
-   La proprietà di database `DbStorageLocation` non può essere impostata in modo che punti a una cartella di dati del server o a una delle relative sottocartelle. Se il percorso punta alla cartella di dati del server o a una delle relative sottocartelle, quando si esegue un comando `Create`, `Attach` o `Alter` verrà generato un errore.  
  
> [!IMPORTANT]  
>  È consigliabile impostare il percorso UNC per l'utilizzo di una rete SAN (Storage Area Network) basata su iSCSI o di un disco collegato localmente. Qualsiasi percorso UNC di una condivisione di rete o qualsiasi soluzione di archiviazione remota a latenza elevata produce un'installazione non supportata.  
  
### <a name="dbstoragelocation-compared-to-storagelocation"></a>Confronto tra DbStorageLocation e StorageLocation  
 `DbStorageLocation` specifica la cartella in cui risiedono tutti i file di dati e di metadati del database, mentre `StorageLocation` specifica la cartella in cui risiedono una o più partizioni di un cubo. `StorageLocation` può essere impostata in modo indipendente da `DbStorageLocation`. Si tratta di una decisione dell'amministratore di database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in base ai risultati previsti. Spesso le due proprietà vengono usate in modo sovrapposto.  
  
## <a name="dbstoragelocation-usage"></a>Utilizzo di DbStorageLocation  
 La `DbStorageLocation` Proprietà database viene utilizzata come parte di un `Create` comando di database in una sequenza di comandi di database `Detach` / `Attach` , in una `Backup` / `Restore` sequenza di comandi di database o in un `Synchronize` comando di database. La modifica della proprietà di database `DbStorageLocation` è considerata una modifica strutturale nell'oggetto di database, ovvero è necessario ricreare tutti i metadati e rielaborare tutti i dati.  
  
> [!IMPORTANT]  
>  Non è consigliabile modificare il percorso di archiviazione dei database tramite un comando `Alter`. È invece consigliabile usare una sequenza di `Detach` / `Attach` comandi di database. vedere [spostare un database di Analysis Services](move-an-analysis-services-database.md), [connettersi e scollegare Analysis Services database](attach-and-detach-analysis-services-databases.md)).  
  
## <a name="see-also"></a>Vedere anche  
 [Microsoft. AnalysisServices. database. DbStorageLocation *](/dotnet/api/microsoft.analysisservices.core.database.dbstoragelocation)   
 [Collegamento e scollegamento di Analysis Services database](attach-and-detach-analysis-services-databases.md)   
 [Spostare un database di Analysis Services](move-an-analysis-services-database.md)   
 [Elemento DbStorageLocation](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)   
 [Create element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)   
 [Connetti elemento](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element)   
 [Elemento Synchronize &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/synchronize-element-xmla)  
  
  
