---
title: Campi di descrizione per le colonne costitutive dei parametri con valori di tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), descriptor fields for constituent columns
ms.assetid: 944b3968-fd47-4847-98d6-b87e8ef2acdc
author: rothja
ms.author: jroth
ms.openlocfilehash: 7474a4a80309f6ce9754fefabfd0080c89f803b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636070"
---
# <a name="descriptor-fields-for-table-valued-parameter-constituent-columns"></a>Campi di descrizione per le colonne che costituiscono parametri con valori di tabella
  I campi di descrizione dei parametri con valori di tabella descritti in questa sezione vengono modificati usando [SQLSetDescField](../native-client-odbc-api/sqlsetdescfield.md) e [SQLSetDescField](../native-client-odbc-api/sqlsetdescfield.md) con l'handle per il descrittore del parametro di implementazione (dpi).  
  
## <a name="remarks"></a>Osservazioni  
 SQL_DESC_AUTO_UNIQUE_VALUE viene utilizzato per parametri con valori di tabella e altre caratteristiche.  
  
|Nome attributo|Type|Descrizione|  
|--------------------|----------|-----------------|  
|SQL_DESC_AUTO_UNIQUE_VALUE|SQLINTEGER|SQL_TRUE indica che la colonna è una colonna Identity.<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]può utilizzare queste informazioni per ottimizzare le prestazioni, ma le applicazioni non devono impostarle per le colonne Identity.|  
  
 Gli attributi seguenti vengono aggiunti a tutti i tipi di parametro nel campo di descrizione del parametro dell'applicazione (APD, Application Parameter Descriptor) e nel campo di descrizione del parametro di implementazione (IPD, Implementation Parameter Descriptor):  
  
|Nome attributo|Type|Descrizione|  
|--------------------|----------|-----------------|  
|SQL_CA_SS_COLUMN_COMPUTED|SQLSMALLINT|SQL_TRUE indica che la colonna è calcolata.<br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]può utilizzare queste informazioni per ottimizzare le prestazioni, ma le applicazioni non devono impostarle per le colonne calcolate.<br /><br /> Questo attributo viene ignorato per le associazioni che non sono colonne di parametri con valori di tabella.|  
|SQL_CA_SS_COLUMN_IN_UNIQUE_KEY|SQLSMALLINT|SQL_TRUE indica che una colonna di parametri con valori di tabella viene utilizzata in una chiave univoca. Questa impostazione può migliorare le prestazioni di esecuzione delle query. Questo attributo viene ignorato per le associazioni che non sono colonne di parametri con valori di tabella.|  
|SQL_CA_SS_COLUMN_SORT_ORDER|SQLSMALLINT|Indica l'ordinamento di una colonna di parametri con valori di tabella. Questa impostazione può migliorare le prestazioni di esecuzione delle query. Questo attributo viene ignorato per le associazioni che non sono colonne di parametri con valori di tabella. Di seguito sono indicati i valori possibili:<br /><br /> -SQL_SS_ASCENDING_ORDER<br />-SQL_SS_DESCENDING_ORDER<br />-SQL_SS_ORDER_UNSPECIFIED<br /><br /> I valori diversi da SQL_SS_ASCENDING_ORDER e SQL_SS_DESCENDING_ORDER generano un errore con SQLSTATE HY024 e il messaggio 'Valore di attributo non valido' e vengono considerati SQL_SS_ORDER_UNSPECIFIED, ovvero il valore predefinito per l'attributo.|  
|SQL_CA_SS_COLUMN_SORT_ORDINAL|SQLSMALLINT|Indica l'ordinale di una colonna di parametri con valori di tabella nel set di colonne che definiscono l'ordinamento complessivo per un parametro con valori di tabella. Questa impostazione può migliorare le prestazioni di esecuzione delle query. Questo attributo viene ignorato per le associazioni che non sono colonne di parametri con valori di tabella. Gli ordinali per l'ordinamento iniziano da 1. Il valore 0, che rappresenta il valore predefinito, indica che una colonna di parametri con valori di tabella non specifica l'ordinamento delle colonne.|  
|SQL_CA_SS_COLUMN_HAS_DEFAULT_VALUE|SQLSMALLINT|Indica se assegnare a tutte le righe nel parametro con valori di tabella il valore predefinito per la colonna. Per i parametri con valori di tabella, non è possibile selezionare il valore predefinito riga per riga. Il valore SQL_FALSE indica che alle righe saranno assegnati valori non predefiniti. Questa è l'impostazione predefinita. Il valore SQL_TRUE indica che la colonna specificherà valori predefiniti per tutte le righe.<br /><br /> Se l'attributo è impostato su SQL_TRUE, non verranno inviati dati al server.<br /><br /> Questo campo può essere utilizzato anche con colonne Identity o calcolate se i valori di colonna non sono necessari per l'elaborazione server.|  
  
 Questi attributi sono validi solo per le colonne di parametri con valori di tabella e vengono ignorati per gli altri parametri.  
  
 Se SQL_CA_SS_COL_HAS_DEFAULT_VALUE è impostato per una colonna di parametri con valori di tabella, SQL_DESC_DATA_PTR per la colonna deve essere un puntatore null. In caso contrario, SQLExecute o SQLExecDirect restituirà SQL_ERROR. Verrà generato un record di diagnostica con SQLSTATE = 07S01 e il messaggio "utilizzo non valido del parametro predefinito per il parametro \<p> , colonna \<c> ", dove \<p> è l'ordinale del parametro e \<c> è l'ordinale di colonna.  
  
## <a name="see-also"></a>Vedere anche  
 [Parametri con valori di tabella &#40;&#41;ODBC](table-valued-parameters-odbc.md)  
  
  
