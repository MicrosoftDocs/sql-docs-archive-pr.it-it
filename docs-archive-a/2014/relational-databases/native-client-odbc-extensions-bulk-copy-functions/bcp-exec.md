---
title: bcp_exec | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623236"
---
# <a name="bcp_exec"></a>bcp_exec
  Esegue una copia bulk completa di dati tra una tabella di database e un file utente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a>Argomenti  
 *hdbc*  
 Handle di connessione ODBC abilitato per la copia bulk.  
  
 *pnRowsProcessed*  
 Puntatore a DBINT. La funzione **bcp_exec** compila questo DBINT con il numero di righe copiate correttamente. Se *pnRowsProcessed* è null, viene ignorato da **bcp_exec**.  
  
## <a name="returns"></a>Restituisce  
 SUCCEED, SUCCEED_ASYNC o FAIL. La funzione **bcp_exec** restituisce esito positivo se vengono copiate tutte le righe. **bcp_exec** restituisce SUCCEED_ASYNC se un'operazione di copia bulk asincrona è ancora in attesa. **bcp_exec** restituisce esito negativo se si verifica un errore completo o se il numero di righe che generano errori raggiunge il valore specificato per BCPMAXERRS utilizzando [bcp_control](bcp-control.md). Il valore predefinito BCPMAXERRS è 10. L'opzione BCPMAXERRS influisce solo sugli errori di sintassi rilevati dal provider durante la lettura delle righe dal file di dati, ma non delle righe inviate al server. Il server interrompe il batch quando rileva un errore con una riga. Controllare il parametro *pnRowsProcessed* per il numero di righe copiate correttamente.  
  
## <a name="remarks"></a>Osservazioni  
 Questa funzione copia i dati da un file utente a una tabella di database o viceversa, a seconda del valore del parametro *eDirection* in [bcp_init](bcp-init.md).  
  
 Prima di chiamare **bcp_exec**, chiamare **bcp_init** con un nome di file utente valido. In caso contrario, viene generato un errore.  
  
 **bcp_exec** è l'unica funzione di copia bulk che probabilmente sarà in attesa per un periodo di tempo. è anche l'unica funzione di copia bulk che supporta la modalità asincrona. Per impostare la modalità asincrona, utilizzare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) per impostare SQL_ATTR_ASYNC_ENABLE su SQL_ASYNC_ENABLE_ON prima di chiamare **bcp_exec**. Per verificare il completamento, chiamare **bcp_exec** con gli stessi parametri. Se la copia bulk non è stata ancora completata, **bcp_exec** restituisce SUCCEED_ASYNC. Restituisce anche in *pnRowsProcessed* un conteggio dello stato del numero di righe inviate al server. Il commit delle righe inviate al server non viene eseguito fino a quando non viene raggiunta la fine di un batch.  
  
 Per informazioni sulle modifiche di rilievo apportate alla copia bulk a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , vedere [esecuzione di operazioni di copia bulk &#40;&#41;ODBC ](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come utilizzare **bcp_exec**:  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di copia bulk](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
