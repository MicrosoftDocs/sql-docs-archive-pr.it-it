---
title: Esecuzione di operazioni di copia bulk (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724607"
---
# <a name="performing-bulk-copy-operations-odbc"></a>Esecuzione di operazioni di copia bulk (ODBC)
  Lo standard ODBC non supporta direttamente le operazioni di copia bulk [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. In caso di connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versione 7.0 o successiva, il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client supporta le funzioni DB-Library che eseguono operazioni di copia bulk [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Questa estensione specifica del driver fornisce un percorso di aggiornamento semplice per le applicazioni DB-Library esistenti che utilizzano le funzioni di copia bulk. Il supporto specifico per la copia bulk è disponibile nei file seguenti:  
  
-   sqlncli.h  
  
     Include prototipi della funzione e definizioni costanti per le funzioni di copia bulk. sqlncli.h deve essere incluso nell'applicazione ODBC che esegue le operazioni di copia bulk e deve trovarsi nel percorso di inclusione dell'applicazione quando viene compilato.  
  
-   sqlncli11.lib  
  
     Deve trovarsi nel percorso della libreria del linker e deve essere specificato come un file da collegare. sqlncli11.lib è distribuito con il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.  
  
-   sqlncli11.dll  
  
     Deve essere presente in fase di esecuzione. sqlncli11.dll è distribuito con il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.  
  
> [!NOTE]  
>  La funzione ODBC **SQLBulkOperations** non ha alcuna relazione con le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funzioni di copia bulk. Per eseguire le operazioni di copia bulk è necessario che le applicazioni utilizzino le funzioni di copia bulk specifiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
## <a name="minimally-logging-bulk-copies"></a>Registrazione minima delle copie bulk  
 Con un modello di recupero con registrazione completa, tutte le operazioni di inserimento di righe eseguite durante il caricamento bulk vengono registrate in modo completo nel log delle transazioni. In caso di caricamenti di grandi quantità di dati, questo può causare un rapido esaurimento dello spazio disponibile nel log delle transazioni. In determinate condizioni la registrazione minima è consentita. Tale registrazione riduce la possibilità che un'operazione di caricamento bulk riempia lo spazio di log e risulta anche più efficiente della registrazione completa.  
  
 Per informazioni sull'utilizzo della registrazione minima, vedere [prerequisiti per la registrazione minima nell'importazione bulk](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).  
  
## <a name="remarks"></a>Osservazioni  
 Quando bcp.exe viene utilizzato in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versione successiva, potrebbero essere visualizzati errori nelle situazioni in cui non si presenta alcun errore nelle versioni precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]. Questo avviene perché nelle versioni successive bcp.exe non esegue più la conversione implicita dei tipi di dati. Nelle versioni precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] bcp.exe converte i dati numerici in un tipo di dati money, se la tabella di destinazione contiene tale tipo di dati. In tale situazione, tuttavia, bcp.exe tronca semplicemente i campi aggiuntivi. A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , se i tipi di dati non corrispondono tra il file e la tabella di destinazione, bcp.exe genererà un errore se sono presenti dati che dovrebbero essere troncati per adattarsi alla tabella di destinazione. Per risolvere questo errore, correggere i dati in modo che corrispondano al tipo di dati di destinazione. Se si desidera, è possibile utilizzare il file bcp.exe di una versione precedente a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
-   [Utilizzo di file di dati e file di formato](using-data-files-and-format-files.md)  
  
-   [Copia bulk da variabili di programma](bulk-copying-from-program-variables.md)  
  
-   [Gestione delle dimensioni dei batch di copia bulk](managing-bulk-copy-batch-sizes.md)  
  
-   [Copia bulk di dati di tipo text e image](bulk-copying-text-and-image-data.md)  
  
-   [Conversione della copia bulk da DB-Library a ODBC](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a>Vedere anche  
 [SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md)   
 [Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
