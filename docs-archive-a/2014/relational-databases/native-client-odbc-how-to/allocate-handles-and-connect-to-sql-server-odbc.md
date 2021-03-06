---
title: Allocare handle e connettersi a SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725684"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a>Allocare handle e connettersi a SQL Server (ODBC)
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a>Per allocare handle e connettersi a SQL Server  
  
1.  Includere i file di intestazione ODBC Sql.h, Sqlext.h, Sqltypes.h.  
  
2.  Includere il file di intestazione specifico del driver [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Odbcss.h.  
  
3.  Chiamare [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un `HandleType` di SQL_HANDLE_ENV per inizializzare ODBC e allocare un handle di ambiente.  
  
4.  Chiamare [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) con `Attribute` impostato su SQL_ATTR_ODBC_VERSION e `ValuePtr` impostato su SQL_OV_ODBC3 per indicare che l'applicazione utilizzerà le chiamate di funzione ODBC 3. x format.  
  
5.  Facoltativamente, chiamare [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) per impostare altre opzioni di ambiente o chiamare [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) per ottenere le opzioni di ambiente.  
  
6.  Chiamare [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un `HandleType` di SQL_HANDLE_DBC per allocare un handle di connessione.  
  
7.  Facoltativamente, chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) per impostare le opzioni di connessione oppure chiamare [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) per ottenere le opzioni di connessione.  
  
8.  Chiamare SQLConnect per utilizzare un'origine dati esistente a cui connettersi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
     Oppure  
  
     Chiamare [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) per usare una stringa di connessione per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
     Il formato minimo di una stringa di connessione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] completa può essere uno dei seguenti:  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     Se la stringa di connessione non è completa, `SQLDriverConnect` può richiedere le informazioni necessarie. Questa operazione è controllata dal valore specificato per il parametro *DriverCompletion* .  
  
     \- - oppure -  
  
     Chiamare [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) più volte in modo iterativo per compilare la stringa di connessione e connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
9. Facoltativamente, chiamare [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) per ottenere gli attributi e il comportamento del driver per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] origine dati.  
  
10. Allocare e utilizzare le istruzioni.  
  
11. Chiamare Disconnect per disconnettersi da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e rendere disponibile l'handle di connessione per una nuova connessione.  
  
12. Chiamare [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) con un `HandleType` di SQL_HANDLE_DBC per liberare l'handle di connessione.  
  
13. Chiamare `SQLFreeHandle` con `HandleType` impostato su SQL_HANDLE_ENV per liberare l'handle di ambiente.  
  
> [!IMPORTANT]  
>  Se possibile, usare l'autenticazione di Windows. Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione. Evitare di archiviare le credenziali in un file. Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).  
  
## <a name="example"></a>Esempio  
 In questo esempio viene mostrata una chiamata a `SQLDriverConnect` per connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] senza richiedere un'origine dati ODBC esistente. Passando una stringa di connessione incompleta a `SQLDriverConnect`, fa in modo che il driver ODBC richieda all'utente di immettere le informazioni mancanti.  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
