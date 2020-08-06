---
title: Aggiornamento di un'applicazione da SQL Server 2005 Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, updating applications
ms.assetid: 1e1e570c-7f14-4e16-beab-c328e3fbdaa8
author: rothja
ms.author: jroth
ms.openlocfilehash: 6db02837b854d237607eba7583d204a4860906b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722720"
---
# <a name="updating-an-application-from-sql-server-2005-native-client"></a>Aggiornamento di un'applicazione da SQL Server 2005 Native Client
  In questo argomento vengono descritte le modifiche di rilievo introdotte in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client rispetto a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].  
  
 Quando si esegue l'aggiornamento da Microsoft Data Access Components (MDAC) a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, si potrebbero anche notare alcune differenze di comportamento. Per ulteriori informazioni, vedere [aggiornamento di un'applicazione a SQL Server Native Client da MDAC](updating-an-application-to-sql-server-native-client-from-mdac.md).  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 9.0 fornito con [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 fornito con [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.5 fornito con [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)]. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 11.0 fornito con [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] e [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].  
  
|Differenze di comportamento in SQL Server Native Client nelle versione successive a [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]|Descrizione|  
|------------------------------------------------------------------------------------|-----------------|  
|In OLE DB viene applicato il riempimento solo in base alla scala definita.|Per le conversioni in cui i dati convertiti vengono inviati al server, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (a partire da [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]) vengono inseriti zeri finali nei dati solo fino alla lunghezza massima dei valori `datetime`. In SQL Server Native Client 9.0 viene applicato un riempimento fino a un massimo di 9 cifre.|  
|Convalida di DBTYPE_DBTIMESTAMP per ICommandWithParameter::SetParameterInfo.|[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]Native Client (a partire da [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ) implementa il requisito OLE DB per *BScale* in ICommandWithParameter:: separameterinfo da impostare sulla precisione frazionaria dei secondi per DBTYPE_DBTIMESTAMP.|  
|Il `sp_columns` stored procedure restituisce ora **"No"** invece di **"No"** per la colonna IS_NULLABLE.|A partire da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0 ( [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] ), `sp_columns` stored procedure restituisce ora **"No"** invece di **"No"** per una colonna IS_NULLABLE.|  
|SQLSetDescRec, SQLBindParameter e SQLBindCol eseguono ora la verifica della coerenza.|Prima di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, l'impostazione SQL_DESC_DATA_PTR non ha provocato una verifica di coerenza per qualsiasi tipo di descrittore in SQLSetDescRec, SQLBindParameter o SQLBindCol.|  
|SQLCopyDesc ora esegue la verifica della coerenza del descrittore.|Prima di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, SQLCopyDesc non esegue una verifica di coerenza quando il campo SQL_DESC_DATA_PTR è stato impostato su un record specifico.|  
|SQLGetDescRec non esegue più una verifica di coerenza del descrittore.|Prima di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, SQLGetDescRec esegue una verifica di coerenza del descrittore quando è stato impostato il campo SQL_DESC_DATA_PTR. Tale controllo non è richiesto dalla specifica ODBC e in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 ([!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]) e versioni successive non viene più eseguito.|  
|Quando la data non è inclusa nell'intervallo consentito viene restituito un errore differente.|Per il tipo `datetime`, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (a partire da [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]) viene restituito un numero di errore diverso rispetto a quello restituito nelle versioni precedenti per una data non compresa nell'intervallo.<br /><br /> In particolare, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 9.0 restituisce il numero 22007 per tutti i valori di anno non compresi nell'intervallo consentito nelle conversioni di stringa a `datetime`, mentre [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client a partire dalla versione 10.0 ([!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]) restituisce il numero 22008 quando la data è compresa nell'intervallo supportato da `datetime2` ma esterna all'intervallo supportato da `datetime` o `smalldatetime`.|  
|Il valore `datetime` tronca i secondi frazionari e non viene arrotondato se tale arrotondamento comporta la modifica del giorno.|Nelle versioni precedenti a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, il client arrotonda i valori `datetime` inviati al server al valore 1/300 di un secondo più vicino. A partire da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, in questo scenario si verifica il troncamento dei secondi frazionari se l'arrotondamento comporta la modifica del giorno.|  
|Possibile troncamento di secondi per il valore `datetime`.|In un'applicazione compilata con [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] Native Client (o versioni successive) che si connette a un server [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 2005 vengono troncati i secondi e i secondi frazionari per la porzione di tempo dei dati inviati al server se si esegue l'associazione a una colonna datetime con un identificatore di tipo DBTYPE_DBTIMESTAMP (OLE DB) o SQL_TIMESTAMP (ODBC) e una scala di 0.<br /><br /> Ad esempio:<br /><br /> Dati di input: 1994-08-21 21:21:36.000<br /><br /> Dati inseriti: 1994-08-21 21:21:00.000|  
|La conversione dei dati OLE DB da DBTYPE_DBTIME a DBTYPE_DATE non può più causare la modifica del giorno.|Nelle versioni precedenti a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, se la parte relativa all'ora di un tipo DBTYPE_DATE è entro mezzo secondo dalla mezzanotte, il codice di conversione OLE DB causa la modifica del giorno. A partire da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0, il giorno non viene modificato (i secondi frazionari vengono troncati ma non vengono arrotondati).|  
|Modifiche della conversione IBCPSession::BCColFmt.|A partire da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10,0, quando si usa IBCPSession:: BCOColFmt per convertire SqlDateTime o SqlDateTime in un tipo stringa, viene esportato un valore frazionario. Quando ad esempio si converte il tipo SQLDATETIME nel tipo SQLNVARCHARMAX, le versioni precedenti di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client restituiscono<br /><br /> 1989-02-01 00:00:00. [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 e versioni successive restituiscono 1989-02-01 00:00:00.0000000.|  
|Le dimensioni dei dati inviati devono corrispondere alla lunghezza specificata in SQL_LEN_DATA_AT_EXEC.|Quando si utilizza SQL_LEN_DATA_AT_EXEC, le dimensioni dei dati devono corrispondere alla lunghezza specificata con SQL_LEN_DATA_AT_EXEC. È possibile utilizzare SQL_DATA_AT_EXEC ma l'utilizzo di SQL_LEN_DATA_AT_EXEC comporta vantaggi potenziali in termini di prestazioni.|  
|Le applicazioni personalizzate che utilizzano l'API BCP ora possono visualizzare un avviso.|L'API BCP genererà un messaggio di avviso se la lunghezza dei dati di tutti i tipi è superiore a quella specificata per un campo. In precedenza, questo avviso veniva visualizzato solo per i dati di tipo carattere e non per tutti i tipi.|  
|Se si inserisce una stringa vuota in un oggetto `sql_variant` associato come tipo data/ora viene generato un errore.|In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 9.0 l'inserimento di una stringa vuota in un oggetto `sql_variant` associato come tipo data/ora non genera alcun errore. In questa situazione in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client 10.0 e versioni successive viene correttamente generato un errore.|  
|Convalida dei parametri SQL_C_TYPE _TIMESTAMP e DBTYPE_DBTIMESTAMP più restrittiva.|Prima di [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] native client, `datetime` i valori venivano arrotondati per adattarsi alla scala delle `datetime` `smalldatetime` colonne e in base a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] Native Client (e versioni successive) applica le regole di convalida più restrittive definite nella specifica ODBC per i secondi frazionari. Se non è possibile convertire il valore di un parametro nel tipo SQL utilizzando la scala specificata o implicita dell'associazione client senza causare il troncamento delle cifre finali, viene restituito un errore.|  
|Quando è in esecuzione un trigger, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] potrebbe restituire risultati diversi.|A causa delle modifiche introdotte in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], un'istruzione che ha causato l'esecuzione di un trigger con `NOCOUNT OFF` attivo potrebbe restituire risultati diversi a un'applicazione. In una situazione di questo tipo l'applicazione potrebbe generare un errore. Per correggere l'errore, impostare `NOCOUNT ON` nel trigger o chiamare SQLMoreResults per passare al risultato successivo.|  
  
## <a name="see-also"></a>Vedere anche  
 [Programmazione in SQL Server Native Client](../sql-server-native-client-programming.md)  
  
  