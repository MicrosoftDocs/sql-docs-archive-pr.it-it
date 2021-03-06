---
title: SQLGetStmtAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetStmtAttr function
ms.assetid: e64f4f94-eb73-4477-9745-080b6cbdc751
author: rothja
ms.author: jroth
ms.openlocfilehash: f1f9b6a0c0668540b566c9b3d7ede781c97a1dbf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629381"
---
# <a name="sqlgetstmtattr"></a>SQLGetStmtAttr
  Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client estende SQLGetStmtAttr per esporre gli attributi di istruzione specifici del driver.  
  
 [SQLSetStmtAttr](sqlsetstmtattr.md) elenca gli attributi di istruzione che sono sia di lettura che di scrittura. In questo argomento vengono elencati gli attributi dell'istruzione di sola lettura.  
  
## <a name="sql_sopt_ss_current_command"></a>SQL_SOPT_SS_CURRENT_COMMAND  
 L'attributo SQL_SOPT_SS_CURRENT_COMMAND espone il comando corrente di un batch di comandi. Il valore restituito è un numero intero che specifica il percorso del comando nel batch. Il valore *ValuePtr* è di tipo SQLLEN.  
  
## <a name="sql_sopt_ss_nocount_status"></a>SQL_SOPT_SS_NOCOUNT_STATUS  
 L'attributo SQL_SOPT_SS_NOCOUNT_STATUS indica l'impostazione corrente dell'opzione NOCOUNT, che controlla se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] segnala il numero di righe interessate da un'istruzione quando viene chiamato [SQLRowCount](sqlrowcount.md) . Il valore *ValuePtr* è di tipo SQLLEN.  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|SQL_NC_OFF|NOCOUNT è OFF. SQLRowCount restituisce il numero di righe interessate.|  
|SQL_NC_ON|NOCOUNT è ON. Il numero di righe interessate non viene restituito da SQLRowCount e il valore restituito è 0.|  
  
 Se SQLRowCount restituisce 0, l'applicazione deve testare SQL_SOPT_SS_NOCOUNT_STATUS. Se viene restituito SQL_NC_ON, il valore 0 di SQLRowCount indica solo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non ha restituito un conteggio di righe. Se viene restituito SQL_NC_OFF, NOCOUNT è disattivato e il valore 0 di SQLRowCount indica che l'istruzione non ha influito sulle righe.  
  
 Quando SQL_SOPT_SS_NOCOUNT_STATUS è SQL_NC_OFF, le applicazioni non dovrebbero visualizzare il valore di SQLRowCount. Le stored procedure o i batch di grandi dimensioni possono contenere più istruzioni SET NOCOUNT, pertanto non è possibile presupporre che SQL_SOPT_SS_NOCOUNT_STATUS rimanga costante. Questa opzione deve essere testata ogni volta che SQLRowCount restituisce 0.  
  
## <a name="sql_sopt_ss_querynotification_msgtext"></a>SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT  
 L'attributo SQL_SOPT_SS_QUERYNOTIFICATION_MSGTEXT restituisce il testo del messaggio per la richiesta di notifica di query.  
  
## <a name="sqlgetstmtattr-and-table-valued-parameters"></a>SQLGetStmtAttr e parametri con valori di tabella  
 È possibile chiamare SQLGetStmtAttr per ottenere il valore di SQL_SOPT_SS_PARAM_FOCUS nel descrittore del parametro dell'applicazione (APD) quando si utilizzano parametri con valori di tabella. Per ulteriori informazioni su SQL_SOPT_SS_PARAM_FOCUS, vedere [SQLSetStmtAttr](sqlsetstmtattr.md).  
  
 Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).  
  
## <a name="see-also"></a>Vedere anche  
 [SQLSetStmtAttr (funzione)](https://go.microsoft.com/fwlink/?LinkId=59370)   
 [Dettagli di implementazione dell'API ODBC](odbc-api-implementation-details.md)  
  
  
