---
title: Informazioni nelle interfacce di errore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636054"
---
# <a name="information-in-error-interfaces"></a>Informazioni nelle interfacce di errore
  Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client segnala alcune informazioni sugli errori e sullo stato nelle interfacce di errore definite dall'OLE DB **IErrorInfo**, **IErrorRecords**e **ISQLErrorInfo**.  
  
 Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta le funzioni membro **IErrorInfo** come indicato di seguito.  
  
|Funzione membro|Descrizione|  
|---------------------|-----------------|  
|**GetDescription**|Stringa descrittiva del messaggio di errore.|  
|**GetGUID**|GUID dell'interfaccia che ha definito l'errore.|  
|**GetHelpContext**|Non supportato. Restituisce sempre zero.|  
|**GetHelpFile**|Non supportato. Viene restituito sempre NULL.|  
|**GetSource**|Stringa "Microsoft SQL Server Native Client".|  
  
 Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta le funzioni membro **IErrorRecords** disponibili per il consumer come indicato di seguito.  
  
|Funzione membro|Descrizione|  
|---------------------|-----------------|  
|**GetBasicErrorInfo**|Inserisce in una struttura ERRORINFO le informazioni di base su un errore. Una struttura ERRORINFO contiene membri che identificano il valore restituito HRESULT per l'errore nonché il provider e l'interfaccia alle quali si applica l'errore.|  
|**GetCustomErrorObject**|Restituisce un riferimento nelle interfacce **ISQLErrorInfo** e [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).|  
|**GetErrorInfo**|Restituisce un riferimento in un'interfaccia **IErrorInfo**.|  
|**GetErrorParameters**|Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non restituisce parametri al consumer tramite **GetErrorParameters**.|  
|**GetRecordCount**|Conteggio dei record di errore disponibili.|  
  
 Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta i parametri **ISQLErrorInfo:: GetSQLInfo** come indicato di seguito.  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|*pbstrSQLState*|Restituisce un valore SQLSTATE per l'errore. I valori SQLSTATE vengono definiti nelle specifiche API, SQL-92, ODBC e ISO SQL. Né [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] né [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native client OLE DB provider definiscono valori SQLSTATE specifici dell'implementazione.|  
|*plNativeError*|Restituisce il numero di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da **master.dbo.sysmessages**, quando disponibile. Gli errori nativi sono disponibili dopo un tentativo riuscito di inizializzare un' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] origine dati del provider OLE DB di Native Client. Prima del tentativo, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce sempre zero.|  
  
## <a name="see-also"></a>Vedere anche  
 [Errori](errors.md)  
  
  
