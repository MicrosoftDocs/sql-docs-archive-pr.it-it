---
title: Elaborare errori ODBC (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- errors [ODBC]
ms.assetid: 66ab0762-79fe-4a31-b655-27dd215a0af7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9f42223ffda8462ec740b94eb584565dfe286e0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722760"
---
# <a name="process-odbc-errors-odbc"></a><span data-ttu-id="7b9ea-102">Elaborare errori ODBC (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7b9ea-102">Process ODBC Errors (ODBC)</span></span>
  <span data-ttu-id="7b9ea-103">È possibile usare due chiamate di funzione ODBC per recuperare messaggi ODBC: [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) e [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md).</span><span class="sxs-lookup"><span data-stu-id="7b9ea-103">Two ODBC function calls can be used to retrieve ODBC messages: [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) and [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md).</span></span> <span data-ttu-id="7b9ea-104">Per ottenere informazioni correlate a ODBC nei campi di diagnostica **SQLState**, **pfNative** e **ErrorMessage**, chiamare [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) fino a quando no viene restituito SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-104">To obtain primary ODBC-related information in the **SQLState**, **pfNative**, and **ErrorMessage** diagnostic fields, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="7b9ea-105">Per ogni record di diagnostica, è possibile chiamare [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) per recuperare i singoli campi.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-105">For each diagnostic record, [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) can be called to retrieve individual fields.</span></span> <span data-ttu-id="7b9ea-106">Tutti i campi specifici del driver devono essere recuperati utilizzando `SQLGetDiagField`.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-106">All driver-specific fields must be retrieved using `SQLGetDiagField`.</span></span>  
  
 <span data-ttu-id="7b9ea-107">L'elaborazione di [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) e [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) viene eseguita da Gestione driver ODBC, non da un singolo driver.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-107">[SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) and [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) are processed by ODBC Driver Manager, not an individual driver.</span></span> <span data-ttu-id="7b9ea-108">Gestione driver ODBC memorizza nella cache i campi di diagnostica specifici del driver solo dopo che è stata stabilita una connessione.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-108">ODBC Driver Manager does not cache driver-specific diagnostic fields until a successful connection has been made.</span></span> <span data-ttu-id="7b9ea-109">È possibile chiamare [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) per i campi di diagnostica specifici del driver solo dopo che è stata stabilita una connessione.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-109">Calling [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) for driver-specific diagnostic fields is not possible before a successful connection.</span></span> <span data-ttu-id="7b9ea-110">Sono inclusi i comandi della connessione ODBC, anche se restituiscono SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-110">This includes the ODBC connection commands, even if they return SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="7b9ea-111">I campi di diagnostica specifici dei driver non saranno disponibili sino alla successiva chiamata alla funzione ODBC.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-111">Driver-specific diagnostic fields will not be available until the next ODBC function call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b9ea-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b9ea-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7b9ea-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b9ea-113">Description</span></span>  
 <span data-ttu-id="7b9ea-114">Questo esempio illustra un semplice gestore degli errori che chiama [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) per informazioni ODBC standard.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-114">This sample shows a simple error handler that calls [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) for the standard ODBC information.</span></span> <span data-ttu-id="7b9ea-115">Il gestore verifica quindi l'esistenza di una connessione valida e, se è presente, chiama `SQLGetDiagField` per ottenere i campi di diagnostica specifici del driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b9ea-115">It then tests for a valid connection, and if one exists, it calls `SQLGetDiagField` for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific diagnostic fields.</span></span> <span data-ttu-id="7b9ea-116">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="7b9ea-117">L'esempio è stato sviluppato per ODBC versione 3.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-117">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7b9ea-118">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-118">When possible, use Windows Authentication.</span></span> <span data-ttu-id="7b9ea-119">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-119">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="7b9ea-120">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-120">Avoid storing credentials in a file.</span></span> <span data-ttu-id="7b9ea-121">Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="7b9ea-121">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
 <span data-ttu-id="7b9ea-122">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-122">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="7b9ea-123">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="7b9ea-123">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="7b9ea-124">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-124">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="7b9ea-125">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-125">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="7b9ea-126">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-126">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="7b9ea-127">Per impostazione predefinita, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-127">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="7b9ea-128">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../includes/tsql-md.md)]) per creare la stored procedure utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-128">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the stored procedure used by this sample.</span></span>  
  
 <span data-ttu-id="7b9ea-129">Compilare il secondo listato di codice (C++) con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-129">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="7b9ea-130">Eseguire quindi il programma.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-130">Then, execute the program.</span></span>  
  
 <span data-ttu-id="7b9ea-131">Eseguire il terzo listato di codice ([!INCLUDE[tsql](../../includes/tsql-md.md)]) per eliminare la stored procedure utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="7b9ea-131">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the stored procedure used by this sample.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7b9ea-132">Codice</span><span class="sxs-lookup"><span data-stu-id="7b9ea-132">Code</span></span>  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BadOne')  
   DROP PROCEDURE BadOne  
  
Go  
  
CREATE PROCEDURE BadOne   
AS   
SELECT * FROM Purchasing.Vendor  
Go  
```  
  
### <a name="code"></a><span data-ttu-id="7b9ea-133">Codice</span><span class="sxs-lookup"><span data-stu-id="7b9ea-133">Code</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void ProcessLogMessages(SQLSMALLINT plm_handle_type, SQLHANDLE plm_handle, char *logstring, int ConnInd);  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) &&  
      (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         ProcessLogMessages(SQL_HANDLE_DBC, hdbc1, "SQLConnect() Failed\n\n", FALSE);  
         Cleanup();  
         return(9);  
   }  
   else {  
      ProcessLogMessages(SQL_HANDLE_DBC, hdbc1,  
         "\nConnect Successful\n\n", FALSE);  
   }  
  
   // Allocate statement handle, and then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      ProcessLogMessages(SQL_HANDLE_DBC, hdbc1, "SQLAllocHandle(hstmt1) Failed\n\n", TRUE);  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"exec BadOne", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         ProcessLogMessages(SQL_HANDLE_STMT, hstmt1, "SQLExecute() Failed\n\n", TRUE);  
         Cleanup();  
         return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA )  
      ;  
  
   // Clean up.   
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
void ProcessLogMessages(SQLSMALLINT plm_handle_type, SQLHANDLE plm_handle, char *logstring, int ConnInd) {  
   RETCODE plm_retcode = SQL_SUCCESS;  
   UCHAR plm_szSqlState[MAXBUFLEN] = "", plm_szErrorMsg[MAXBUFLEN] = "";  
   SDWORD plm_pfNativeError = 0L;  
   SWORD plm_pcbErrorMsg = 0;  
   SQLSMALLINT plm_cRecNmbr = 1;  
   SDWORD plm_SS_MsgState = 0, plm_SS_Severity = 0;  
   SQLINTEGER plm_Rownumber = 0;  
   USHORT plm_SS_Line;  
   SQLSMALLINT plm_cbSS_Procname, plm_cbSS_Srvname;  
   SQLCHAR plm_SS_Procname[MAXNAME], plm_SS_Srvname[MAXNAME];  
  
   if (logstring)  
      printf(logstring);  
  
   while (plm_retcode != SQL_NO_DATA_FOUND) {  
      plm_retcode = SQLGetDiagRec(plm_handle_type, plm_handle, plm_cRecNmbr,   
                                  plm_szSqlState, &plm_pfNativeError, plm_szErrorMsg,   
                                  MAXBUFLEN - 1, &plm_pcbErrorMsg);  
  
      // Note that if the application has not yet made a successful connection,   
      // the SQLGetDiagField information has not yet been cached by ODBC Driver Manager and   
      // these calls to SQLGetDiagField will fail.  
      if (plm_retcode != SQL_NO_DATA_FOUND) {  
         if (ConnInd) {   
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                                        SQL_DIAG_ROW_NUMBER, &plm_Rownumber,  
                                                        SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_LINE, &plm_SS_Line, SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,   
                                           SQL_DIAG_SS_MSGSTATE, &plm_SS_MsgState,  
                                           SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_SEVERITY, &plm_SS_Severity,  
                                           SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_PROCNAME, &plm_SS_Procname,  
                                           sizeof(plm_SS_Procname), &plm_cbSS_Procname);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_SRVNAME, &plm_SS_Srvname,   
                                           sizeof(plm_SS_Srvname), &plm_cbSS_Srvname);  
         }  
  
         printf("szSqlState = %s\n", plm_szSqlState);  
         printf("pfNativeError = %d\n", plm_pfNativeError);  
         printf("szErrorMsg = %s\n", plm_szErrorMsg);  
         printf("pcbErrorMsg = %d\n\n", plm_pcbErrorMsg);  
  
         if (ConnInd) {  
            printf("ODBCRowNumber = %d\n", plm_Rownumber);  
            printf("SSrvrLine = %d\n", plm_Rownumber);  
            printf("SSrvrMsgState = %d\n", plm_SS_MsgState);  
            printf("SSrvrSeverity = %d\n", plm_SS_Severity);  
            printf("SSrvrProcname = %s\n", plm_SS_Procname);  
            printf("SSrvrSrvname = %s\n\n", plm_SS_Srvname);  
         }  
      }  
  
      plm_cRecNmbr++;   // Increment to next diagnostic record.  
   }  
}  
```  
  
### <a name="code"></a><span data-ttu-id="7b9ea-134">Codice</span><span class="sxs-lookup"><span data-stu-id="7b9ea-134">Code</span></span>  
  
```  
use AdventureWorks  
DROP PROCEDURE BadOne  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b9ea-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b9ea-135">See Also</span></span>  
 [<span data-ttu-id="7b9ea-136">Procedure per l'utilizzo di ODBC</span><span class="sxs-lookup"><span data-stu-id="7b9ea-136">ODBC How-to Topics</span></span>](odbc-how-to-topics.md)  
  
  
