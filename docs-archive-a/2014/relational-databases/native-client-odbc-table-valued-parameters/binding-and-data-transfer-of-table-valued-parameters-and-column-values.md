---
title: Associazione e Trasferimento dati di valori di colonna e parametri con valori di tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), binding and data transfer
ms.assetid: 0a2ea462-d613-42b6-870f-c7fa086a6b42
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e9e30e22a69b2d500990cc1481506b4edbda99b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636071"
---
# <a name="binding-and-data-transfer-of-table-valued-parameters-and-column-values"></a><span data-ttu-id="c4f4a-102">Associazione e trasferimento dati di valori di colonna e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c4f4a-102">Binding and Data Transfer of Table-Valued Parameters and Column Values</span></span>
  <span data-ttu-id="c4f4a-103">Analogamente agli altri parametri, i parametri con valori di tabella devono essere associati prima di poter essere passati al server.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-103">Table-valued parameters, like other parameters, must be bound before they are passed to the server.</span></span> <span data-ttu-id="c4f4a-104">L'applicazione associa i parametri con valori di tabella nello stesso modo in cui associa altri parametri: usando SQLBindParameter o chiamate equivalenti a SQLSetDescField o SQLSetDescRec.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-104">The application binds table-valued parameters the same way it binds other parameters: by using SQLBindParameter or equivalent calls to SQLSetDescField or SQLSetDescRec.</span></span> <span data-ttu-id="c4f4a-105">Il tipo di dati del server per un parametro con valori di tabella è SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-105">The server data type for a table-valued parameter is SQL_SS_TABLE.</span></span> <span data-ttu-id="c4f4a-106">Il tipo C può essere specificato come SQL_C_DEFAULT o SQL_C_BINARY.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-106">The C type can be specified either as SQL_C_DEFAULT or SQL_C_BINARY.</span></span>  
  
 <span data-ttu-id="c4f4a-107">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o versioni successive, sono supportati solo parametri con valori di tabella di input.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-107">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later, only input table-valued parameters are supported.</span></span> <span data-ttu-id="c4f4a-108">Qualsiasi tentativo di impostare SQL_DESC_PARAMETER_TYPE su un valore diverso da SQL_PARAM_INPUT restituirà, pertanto, SQL_ERROR con SQLSTATE = HY105 e il messaggio "Tipo di parametro non valido".</span><span class="sxs-lookup"><span data-stu-id="c4f4a-108">Therefore, any attempt to set SQL_DESC_PARAMETER_TYPE to a value other than SQL_PARAM_INPUT will return SQL_ERROR with SQLSTATE = HY105 and the message "Invalid parameter type".</span></span>  
  
 <span data-ttu-id="c4f4a-109">È possibile assegnare valori predefiniti a intere colonne dei parametri con valori di tabella utilizzando l'attributo SQL_CA_SS_COL_HAS_DEFAULT_VALUE.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-109">Entire table-valued parameter columns can be assigned default values by using the attribute SQL_CA_SS_COL_HAS_DEFAULT_VALUE.</span></span> <span data-ttu-id="c4f4a-110">Ai singoli valori della colonna di parametri con valori di tabella, tuttavia, non è possibile assegnare valori predefiniti utilizzando SQL_DEFAULT_PARAM in *StrLen_or_IndPtr* con SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-110">Individual table-valued parameter column values, however, cannot be assigned default values by using SQL_DEFAULT_PARAM in *StrLen_or_IndPtr* with SQLBindParameter.</span></span> <span data-ttu-id="c4f4a-111">I parametri con valori di tabella nel suo complesso non possono essere impostati su un valore predefinito usando SQL_DEFAULT_PARAM in *StrLen_or_IndPtr* con SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-111">Table-valued parameters as a whole cannot be set to a default value by using SQL_DEFAULT_PARAM in *StrLen_or_IndPtr* with SQLBindParameter.</span></span> <span data-ttu-id="c4f4a-112">Se queste regole non sono seguite, SQLExecute o SQLExecDirect restituirà SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-112">If these rules are not followed, SQLExecute or SQLExecDirect will return SQL_ERROR.</span></span> <span data-ttu-id="c4f4a-113">Verrà generato un record di diagnostica con SQLSTATE = 07S01 e il messaggio "utilizzo non valido del parametro predefinito per il parametro \<p> ", dove \<p> è il numero ordinale di TVP nell'istruzione di query.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-113">A diagnostic record will be generated with SQLSTATE=07S01 and the message "Invalid use of default parameter for parameter \<p>", where \<p> is the ordinal of the TVP in the query statement.</span></span>  
  
 <span data-ttu-id="c4f4a-114">Dopo avere associato il parametro con valori di tabella, dovrà essere associata anche ogni colonna del parametro.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-114">After binding the table-valued parameter, the application must then bind each table-valued parameter column.</span></span> <span data-ttu-id="c4f4a-115">A tale scopo, l'applicazione chiama prima SQLSetStmtAttr per impostare SQL_SOPT_SS_PARAM_FOCUS sull'ordinale di un parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-115">To do this, the application first calls SQLSetStmtAttr to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of a table-valued parameter.</span></span> <span data-ttu-id="c4f4a-116">Quindi, l'applicazione associa le colonne del parametro con valori di tabella tramite chiamate alle routine seguenti: SQLBindParameter, SQLSetDescRec e SQLSetDescField.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-116">Then the application binds the columns of the table-valued parameter by calls to the following routines: SQLBindParameter, SQLSetDescRec, and SQLSetDescField.</span></span> <span data-ttu-id="c4f4a-117">Impostando SQL_SOPT_SS_PARAM_FOCUS su 0, viene ripristinato l'effetto consueto di SQLBindParameter, SQLSetDescRec e SQLSetDescField in operando sui parametri di primo livello normali.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-117">Setting SQL_SOPT_SS_PARAM_FOCUS to 0 restores the usual effect of SQLBindParameter, SQLSetDescRec, and SQLSetDescField in operating on regular top-level parameters.</span></span>  
  
 <span data-ttu-id="c4f4a-118">La ricezione e l'invio di dati effettivi non riguardano il parametro con valori di tabella stesso ma ognuna delle colonne che lo costituiscono.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-118">No actual data is sent or received for the table-valued parameter itself, but data is sent and received for each of its constituent columns.</span></span> <span data-ttu-id="c4f4a-119">Poiché il parametro con valori di tabella è una pseudo colonna, i parametri per SQLBindParameter vengono usati per fare riferimento a attributi diversi rispetto ad altri tipi di dati, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c4f4a-119">Because the table-valued parameter is a pseudo column, the parameters for SQLBindParameter are used to refer to different attributes than other data types, as follows:</span></span>  
  
|<span data-ttu-id="c4f4a-120">Parametro</span><span class="sxs-lookup"><span data-stu-id="c4f4a-120">Parameter</span></span>|<span data-ttu-id="c4f4a-121">Attributo correlato per i tipi di parametro non con valori di tabella, incluse le colonne</span><span class="sxs-lookup"><span data-stu-id="c4f4a-121">Related attribute for non-table-valued parameter types, including columns</span></span>|<span data-ttu-id="c4f4a-122">Attributo correlato per i parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c4f4a-122">Related attribute for table-valued parameters</span></span>|  
|---------------|--------------------------------------------------------------------------------|----------------------------------------------------|  
|<span data-ttu-id="c4f4a-123">*InputOutputType*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-123">*InputOutputType*</span></span>|<span data-ttu-id="c4f4a-124">SQL_DESC_PARAMETER_TYPE in IPD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-124">SQL_DESC_PARAMETER_TYPE in IPD.</span></span><br /><br /> <span data-ttu-id="c4f4a-125">Per le colonne dei parametri con valori di tabella, deve corrispondere all'impostazione per il parametro con valori di tabella stesso.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-125">For table-valued parameter columns, this must be the same as the setting for the table-valued parameter itself.</span></span>|<span data-ttu-id="c4f4a-126">SQL_DESC_PARAMETER_TYPE in IPD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-126">SQL_DESC_PARAMETER_TYPE in IPD.</span></span><br /><br /> <span data-ttu-id="c4f4a-127">Deve essere SQL_PARAM_INPUT.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-127">This must be SQL_PARAM_INPUT.</span></span>|  
|<span data-ttu-id="c4f4a-128">*ValueType*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-128">*ValueType*</span></span>|<span data-ttu-id="c4f4a-129">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in APD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-129">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in APD.</span></span>|<span data-ttu-id="c4f4a-130">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in APD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-130">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in APD.</span></span><br /><br /> <span data-ttu-id="c4f4a-131">Deve essere SQL_C_DEFAULT o SQL_C_BINARY.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-131">This must be SQL_C_DEFAULT or SQL_C_BINARY.</span></span>|  
|<span data-ttu-id="c4f4a-132">*ParameterType*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-132">*ParameterType*</span></span>|<span data-ttu-id="c4f4a-133">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in IPD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-133">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in IPD.</span></span>|<span data-ttu-id="c4f4a-134">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in IPD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-134">SQL_DESC_TYPE, SQL_DESC_CONCISE_TYPE in IPD.</span></span><br /><br /> <span data-ttu-id="c4f4a-135">Deve essere SQL_SS_TABLE.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-135">This must be SQL_SS_TABLE.</span></span>|  
|<span data-ttu-id="c4f4a-136">*ColumnSize*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-136">*ColumnSize*</span></span>|<span data-ttu-id="c4f4a-137">SQL_DESC_LENGTH o SQL_DESC_PRECISION in IPD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-137">SQL_DESC_LENGTH or SQL_DESC_PRECISION in IPD.</span></span><br /><br /> <span data-ttu-id="c4f4a-138">Dipende dal valore di *ParameterType*.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-138">This depends on the value of *ParameterType*.</span></span>|<span data-ttu-id="c4f4a-139">SQL_DESC_ARRAY_SIZE</span><span class="sxs-lookup"><span data-stu-id="c4f4a-139">SQL_DESC_ARRAY_SIZE</span></span><br /><br /> <span data-ttu-id="c4f4a-140">Può essere impostato anche utilizzando SQL_ATTR_PARAM_SET_SIZE quando lo stato attivo del parametro è impostato sul parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-140">Can also be set using SQL_ATTR_PARAM_SET_SIZE when the parameter focus is set to the table-valued parameter.</span></span><br /><br /> <span data-ttu-id="c4f4a-141">Per un parametro con valori di tabella, è il numero di righe nei buffer delle colonne dei parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-141">For a table-valued parameter, this is the number of rows in the table-valued parameter column buffers.</span></span>|  
|<span data-ttu-id="c4f4a-142">*DecimalDigits*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-142">*DecimalDigits*</span></span>|<span data-ttu-id="c4f4a-143">SQL_DESC_PRECISION o SQL_DESC_SCALE in IPD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-143">SQL_DESC_PRECISION or SQL_DESC_SCALE in IPD.</span></span>|<span data-ttu-id="c4f4a-144">Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-144">Unused.</span></span> <span data-ttu-id="c4f4a-145">Deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-145">This must be 0.</span></span><br /><br /> <span data-ttu-id="c4f4a-146">Se questo parametro non è 0, SQLBindParameter restituirà SQL_ERROR e verrà generato un record di diagnostica con SQLSTATE = HY104 e il messaggio "precisione o scala non valida".</span><span class="sxs-lookup"><span data-stu-id="c4f4a-146">If this parameter is not 0, SQLBindParameter will return SQL_ERROR, and a diagnostic record will be generated with SQLSTATE= HY104 and the message "Invalid precision or scale".</span></span>|  
|<span data-ttu-id="c4f4a-147">*ParameterValuePtr*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-147">*ParameterValuePtr*</span></span>|<span data-ttu-id="c4f4a-148">SQL_DESC_DATA_PTR in APD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-148">SQL_DESC_DATA_PTR in APD.</span></span>|<span data-ttu-id="c4f4a-149">SQL_CA_SS_TYPE_NAME.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-149">SQL_CA_SS_TYPE_NAME.</span></span><br /><br /> <span data-ttu-id="c4f4a-150">Questo parametro è facoltativo per le chiamate di stored procedure ed è possibile specificare NULL se non è richiesto.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-150">This is optional for stored procedure calls, and NULL can be specified if it is not required.</span></span> <span data-ttu-id="c4f4a-151">Deve essere specificato per le istruzioni SQL che non sono chiamate di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-151">It must be specified for SQL statements that are not procedure calls.</span></span><br /><br /> <span data-ttu-id="c4f4a-152">Questo parametro serve anche come valore univoco utilizzabile dall'applicazione per identificare il parametro con valori di tabella quando viene utilizzata l'associazione variabile di righe.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-152">This parameter also serves as a unique value that the application can use to identify this table-valued parameter when variable row binding is used.</span></span> <span data-ttu-id="c4f4a-153">Per ulteriori informazioni, vedere la sezione "Associazione variabile di righe di parametri con valori di tabella" più avanti n questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-153">For more information, see the "Variable Table-Valued Parameter Row Binding" section, later in this topic.</span></span><br /><br /> <span data-ttu-id="c4f4a-154">Quando si specifica un nome di tipo di parametro con valori di tabella in una chiamata a SQLBindParameter, è necessario specificarlo come valore Unicode, anche nelle applicazioni compilate come applicazioni ANSI.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-154">When a table-valued parameter type name is specified on a call to SQLBindParameter, it must be specified as a Unicode value, even in applications that are built as ANSI applications.</span></span> <span data-ttu-id="c4f4a-155">Il valore utilizzato per il parametro *StrLen_or_IndPtr* deve essere SQL_NTS o la lunghezza della stringa del nome moltiplicato per sizeof (WCHAR).</span><span class="sxs-lookup"><span data-stu-id="c4f4a-155">The value used for the parameter *StrLen_or_IndPtr* should be either SQL_NTS or the string length of the name multiplied by sizeof(WCHAR).</span></span>|  
|<span data-ttu-id="c4f4a-156">*BufferLength*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-156">*BufferLength*</span></span>|<span data-ttu-id="c4f4a-157">SQL_DESC_OCTET_LENGTH in APD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-157">SQL_DESC_OCTET_LENGTH in APD.</span></span>|<span data-ttu-id="c4f4a-158">Lunghezza del nome del tipo di parametro con valori di tabella espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-158">The length of the table-valued parameter type name in bytes.</span></span><br /><br /> <span data-ttu-id="c4f4a-159">Può essere SQL_NTS, se il nome del tipo è con terminazione Null oppure 0 se il nome del tipo di parametro con valori di tabella non è richiesto.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-159">This can be SQL_NTS if the type name is null terminated, or 0 if the table-valued parameter type name is not required.</span></span>|  
|<span data-ttu-id="c4f4a-160">*StrLen_or_IndPtr*</span><span class="sxs-lookup"><span data-stu-id="c4f4a-160">*StrLen_or_IndPtr*</span></span>|<span data-ttu-id="c4f4a-161">SQL_DESC_OCTET_LENGTH_PTR in APD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-161">SQL_DESC_OCTET_LENGTH_PTR in APD.</span></span>|<span data-ttu-id="c4f4a-162">SQL_DESC_OCTET_LENGTH_PTR in APD.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-162">SQL_DESC_OCTET_LENGTH_PTR in APD.</span></span><br /><br /> <span data-ttu-id="c4f4a-163">Per i parametri con valori di tabella è un conteggio di righe anziché una lunghezza di dati.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-163">For table-valued parameters, this is a row count rather than a data length.</span></span>|  
  
 <span data-ttu-id="c4f4a-164">Sono supportate due modalità di trasferimento dati per i parametri con valori di tabella: associazione di righe fissa e variabile.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-164">Two data transfer modes are supported for table-valued parameters: fixed row binding and variable row binding.</span></span>  
  
## <a name="fixed-table-valued-parameter-row-binding"></a><span data-ttu-id="c4f4a-165">Associazione fissa di righe di parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c4f4a-165">Fixed Table-Valued Parameter Row Binding</span></span>  
 <span data-ttu-id="c4f4a-166">Per l'associazione fissa di righe, un'applicazione alloca i buffer (o le matrici di buffer) di dimensioni sufficienti a contenere tutti i possibili valori delle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-166">For fixed row binding, an application allocates buffers (or buffer arrays) large enough for all possible input column values.</span></span> <span data-ttu-id="c4f4a-167">L'applicazione effettua quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c4f4a-167">The application does the following:</span></span>  
  
1.  <span data-ttu-id="c4f4a-168">Associa tutti i parametri usando le chiamate SQLBindParameter, SQLSetDescRec o SQLSetDescField.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-168">Binds all parameters by using SQLBindParameter, SQLSetDescRec, or SQLSetDescField calls.</span></span>  
  
    1.  <span data-ttu-id="c4f4a-169">Imposta SQL_DESC_ARRAY_SIZE sul numero massimo di righe che possono essere trasferite per ogni parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-169">Sets SQL_DESC_ARRAY_SIZE to the maximum number of rows that can be transferred for each table-valued parameter.</span></span> <span data-ttu-id="c4f4a-170">Questa operazione può essere eseguita nella chiamata SQLBindParameter.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-170">This can be done in the SQLBindParameter call.</span></span>  
  
2.  <span data-ttu-id="c4f4a-171">Chiama SQLSetStmtAttr per impostare SQL_SOPT_SS_PARAM_FOCUS sull'ordinale di ogni parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-171">Calls SQLSetStmtAttr to set SQL_SOPT_SS_PARAM_FOCUS to the ordinal of each table-valued parameter.</span></span>  
  
    1.  <span data-ttu-id="c4f4a-172">Per ogni parametro con valori di tabella, associa le colonne di parametri con valori di tabella tramite chiamate SQLBindParameter, SQLSetDescRec o SQLSetDescField.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-172">For each table-valued parameter, binds table-valued parameter columns by using SQLBindParameter, SQLSetDescRec, or SQLSetDescField calls.</span></span>  
  
    2.  <span data-ttu-id="c4f4a-173">Per ogni colonna di parametri con valori di tabella con valori predefiniti, chiama SQLSetDescField per impostare SQL_CA_SS_COL_HAS_DEFAULT_VALUE su 1.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-173">For each table-valued parameter column that is to have default values, calls SQLSetDescField to set SQL_CA_SS_COL_HAS_DEFAULT_VALUE to 1.</span></span>  
  
3.  <span data-ttu-id="c4f4a-174">Chiama SQLSetStmtAttr per impostare SQL_SOPT_SS_PARAM_FOCUS su 0.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-174">Calls SQLSetStmtAttr to set SQL_SOPT_SS_PARAM_FOCUS to 0.</span></span> <span data-ttu-id="c4f4a-175">Questa operazione deve essere eseguita prima della chiamata a SQLExecute o SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-175">This must be done before SQLExecute or SQLExecDirect is called.</span></span> <span data-ttu-id="c4f4a-176">In caso contrario, viene restituito SQL_ERROR e vengono generati un record di dati diagnostici con SQLSTATE=HY024 e il messaggio "Valore attributo non valido, SQL_SOPT_SS_PARAM_FOCUS (deve essere zero in fase di esecuzione)."</span><span class="sxs-lookup"><span data-stu-id="c4f4a-176">Otherwise, SQL_ERROR is be returned and a diagnostic record is generated with SQLSTATE=HY024 and the message "Invalid attribute value, SQL_SOPT_SS_PARAM_FOCUS (must be zero at execution time)".</span></span>  
  
4.  <span data-ttu-id="c4f4a-177">Imposta *StrLen_or_IndPtr* o SQL_DESC_OCTET_LENGTH_PTR su SQL_DEFAULT_PARAM per un parametro con valori di tabella senza righe o il numero di righe da trasferire alla chiamata successiva di SQLExecute o SQLExecDirect se il parametro con valori di tabella contiene righe.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-177">Sets *StrLen_or_IndPtr* or SQL_DESC_OCTET_LENGTH_PTR to SQL_DEFAULT_PARAM for a table-valued parameter with no rows, or the number of rows to be transferred on the next call of SQLExecute or SQLExecDirect if the table-valued parameter has rows.</span></span> <span data-ttu-id="c4f4a-178">Impossibile impostare *StrLen_or_IndPtr* o SQL_DESC_OCTET_LENGTH_PTR su SQL_NULL_DATA per un parametro con valori di tabella perché i parametri con valori di tabella non ammettono i valori null (sebbene le colonne costituenti dei parametri con valori di tabella possano essere nullable).</span><span class="sxs-lookup"><span data-stu-id="c4f4a-178">*StrLen_or_IndPtr* or SQL_DESC_OCTET_LENGTH_PTR cannot be set to SQL_NULL_DATA for a table-valued parameter as table-valued parameters are not nullable (though table-valued parameter constituent columns may be nullable).</span></span> <span data-ttu-id="c4f4a-179">Se questa proprietà è impostata su un valore non valido, SQLExecute o SQLExecDirect restituisce SQL_ERROR e viene generato un record di diagnostica con SQLSTATE = HY090 e il messaggio "lunghezza di stringa o di buffer non valida per il parametro \<p> ", dove p è il numero di parametro.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-179">If this is set to an invalid value, SQLExecute or SQLExecDirect returns SQL_ERROR, and a diagnostic record is generated with SQLSTATE=HY090 and the message "Invalid string or buffer length for parameter \<p>", where p is the parameter number.</span></span>  
  
5.  <span data-ttu-id="c4f4a-180">Chiama SQLExecute o SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-180">Calls SQLExecute or SQLExecDirect.</span></span>  
  
 <span data-ttu-id="c4f4a-181">I valori della colonna di parametri con valori di tabella di input possono essere passati in parti se *StrLen_or_IndPtr* è impostato su SQL_LEN_DATA_AT_EXEC (*length*) o SQL_DATA_AT_EXEC per la colonna.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-181">Input table-valued parameter column values can be passed in pieces if *StrLen_or_IndPtr* is set to SQL_LEN_DATA_AT_EXEC(*length*) or SQL_DATA_AT_EXEC for the column.</span></span> <span data-ttu-id="c4f4a-182">Si tratta di una procedura analoga a quella utilizzata per passare i valori in parti quando vengono utilizzate matrici di parametri.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-182">This is similar to passing values in pieces when arrays of parameters are used.</span></span> <span data-ttu-id="c4f4a-183">Come per tutti i parametri data-at-execution, SQLParamData non indica la riga della matrice per cui il driver richiede i dati; l'applicazione deve occuparsi di questo.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-183">As with all data-at-execution parameters, SQLParamData does not indicate which row of the array the driver is requesting data for; the application must take care of this.</span></span> <span data-ttu-id="c4f4a-184">L'applicazione non può prevedere l'ordine con il quale il driver richiederà i valori.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-184">The application cannot make any assumptions about the order in which the driver will request values.</span></span>  
  
## <a name="variable-table-valued-parameter-row-binding"></a><span data-ttu-id="c4f4a-185">Associazione variabile di righe di parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="c4f4a-185">Variable Table-Valued Parameter Row Binding</span></span>  
 <span data-ttu-id="c4f4a-186">Per l'associazione variabile di righe, le righe vengono trasferite in batch in fase di esecuzione e l'applicazione passa le righe al driver su richiesta.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-186">For variable row binding, rows are transferred in batches at execution time and the application passes rows to the driver on demand.</span></span> <span data-ttu-id="c4f4a-187">Si tratta di una procedura simile al data-at-execution per i valori di parametri singoli.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-187">This is similar to data-at-execution for individual parameter values.</span></span> <span data-ttu-id="c4f4a-188">Per l'associazione variabile di righe, l'applicazione effettua quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c4f4a-188">For variable row binding, the application does the following:</span></span>  
  
1.  <span data-ttu-id="c4f4a-189">Associa i parametri e le colonne di parametri con valori di tabella come descritto nei passaggi da 1 a 3 della sezione precedente, "Associazione fissa di righe di parametri con valori di tabella".</span><span class="sxs-lookup"><span data-stu-id="c4f4a-189">Binds parameters and table-valued parameter columns as described in steps 1 to 3 of the previous section, "Fixed Table-Valued Parameter Row Binding".</span></span>  
  
2.  <span data-ttu-id="c4f4a-190">Imposta *StrLen_or_IndPtr* o SQL_DESC_OCTET_LENGTH_PTR per tutti i parametri con valori di tabella che devono essere passati in fase di esecuzione al SQL_DATA_AT_EXEC.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-190">Sets *StrLen_or_IndPtr* or SQL_DESC_OCTET_LENGTH_PTR for any table-valued parameters that are to be passed at execution time to SQL_DATA_AT_EXEC.</span></span> <span data-ttu-id="c4f4a-191">Se non sono impostati valori, il parametro verrà elaborato come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-191">If neither is set, the parameter will be processed as described in the previous section.</span></span>  
  
3.  <span data-ttu-id="c4f4a-192">Chiama SQLExecute o SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-192">Calls SQLExecute or SQLExecDirect.</span></span> <span data-ttu-id="c4f4a-193">Verrà restituito SQL_NEED_DATA se sono presenti parametri SQL_PARAM_INPUT o SQL_PARAM_INPUT_OUTPUT da gestire come parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-193">This will return SQL_NEED_DATA if there are any SQL_PARAM_INPUT or SQL_PARAM_INPUT_OUTPUT parameters to be handled as data-at-execution parameters.</span></span> <span data-ttu-id="c4f4a-194">In questo caso, l'applicazione effettua quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c4f4a-194">In this case, the application does the following:</span></span>  
  
    -   <span data-ttu-id="c4f4a-195">Chiama SQLParamData.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-195">Calls SQLParamData.</span></span> <span data-ttu-id="c4f4a-196">Viene restituito il valore *ParameterValuePtr* per un parametro data-at-execution e un codice restituito di SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-196">This returns the *ParameterValuePtr* value for a data-at-execution parameter and a return code of SQL_NEED_DATA.</span></span> <span data-ttu-id="c4f4a-197">Quando tutti i dati dei parametri sono stati passati al driver, SQLParamData restituisce SQL_SUCCESS, SQL_SUCCESS_WITH_INFO o SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-197">When all parameter data has been passed to the driver, SQLParamData returns SQL_SUCCESS, SQL_SUCCESS_WITH_INFO, or SQL_ERROR.</span></span> <span data-ttu-id="c4f4a-198">Per i parametri data-at-execution, *ParameterValuePtr*, che corrisponde al campo del descrittore SQL_DESC_DATA_PTR, può essere considerato come un token per identificare in modo univoco un parametro per il quale è richiesto un valore.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-198">For data-at-execution parameters, *ParameterValuePtr*, which is the same as the descriptor field SQL_DESC_DATA_PTR, can be regarded as a token to uniquely identify a parameter for which a value is required.</span></span> <span data-ttu-id="c4f4a-199">Tale "token" viene passato dall'applicazione al driver in fase di associazione, quindi viene passato nuovamente all'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-199">This "token" is passed from the application to the driver at bind time, then passed back to the application at execution time.</span></span>  
  
4.  <span data-ttu-id="c4f4a-200">Per inviare i dati delle righe di parametri con valori di tabella per i parametri con valori di tabella null, se il parametro con valori di tabella non contiene righe, un'applicazione chiama SQLPutData con *StrLen_Or_Ind* impostato su SQL_DEFAULT_PARAM.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-200">To send table-valued parameter row data for null table-valued parameters, if the table-valued parameter has no rows, an application calls SQLPutData with *StrLen_or_Ind* set to SQL_DEFAULT_PARAM.</span></span>  
  
     <span data-ttu-id="c4f4a-201">Per i TVP non Null, un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="c4f4a-201">For non-NULL TVPs, an application:</span></span>  
  
    -   <span data-ttu-id="c4f4a-202">Imposta *Str_Len_or_Ind* per tutte le colonne di parametri con valori di tabella sui valori appropriati e popola i buffer dei dati per le colonne di parametri con valori di tabella che non devono essere parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-202">Sets *Str_Len_or_Ind* for all the table-valued parameter columns to appropriate values, and populates data buffers for table-valued parameter columns that are not to be data-at-execution parameters.</span></span> <span data-ttu-id="c4f4a-203">È possibile utilizzare la funzionalità data-at-execution per le colonne di parametri con valori di tabella seguendo procedure analoghe a quelle necessarie per passare in parti i parametri ordinari al driver.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-203">You can use data-at-execution for table-valued parameter columns in a similar way to that in which ordinary parameters can be passed to the driver in pieces.</span></span>  
  
    -   <span data-ttu-id="c4f4a-204">Chiama SQLPutData con *Str_Len_or_Ind* impostato sul numero di righe da inviare al server.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-204">Calls SQLPutData with *Str_Len_or_Ind* set to the number of rows to be sent to the server.</span></span> <span data-ttu-id="c4f4a-205">I valori esterni all'intervallo compreso tra 0 e SQL_DESC_ARRAY_SIZE o SQL_DEFAULT_PARAM sono un errore e restituiranno SQLSTATE HY090, con il messaggio "Lunghezza di stringa o di buffer non valida".</span><span class="sxs-lookup"><span data-stu-id="c4f4a-205">Any value outside the range 0 to SQL_DESC_ARRAY_SIZE or SQL_DEFAULT_PARAM is an error, and will return SQLSTATE HY090, with the message "Invalid string or buffer length".</span></span> <span data-ttu-id="c4f4a-206">0 indica che tutte le righe sono state inviate e non sono più disponibili dati per un parametro con valori di tabella (come indicato nel secondo punto elenco).</span><span class="sxs-lookup"><span data-stu-id="c4f4a-206">0 indicates that all rows have been sent and there is no more data for a table-valued parameter (as noted in the second bullet item in this list).</span></span> <span data-ttu-id="c4f4a-207">SQL_DEFAULT_PARAM può essere utilizzato solo la prima volta che il driver richiede dati per un parametro con valori di tabella (come descritto nel primo punto elenco).</span><span class="sxs-lookup"><span data-stu-id="c4f4a-207">SQL_DEFAULT_PARAM can only be used the first time the driver requests data for a table-valued parameter (as described in the first bullet item in this list).</span></span>  
  
5.  <span data-ttu-id="c4f4a-208">Quando tutte le righe sono state inviate, chiama SQLPutData per il parametro con valori di tabella con un valore *Str_Len_or_Ind* pari a 0, quindi procede con il passaggio 3a precedente.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-208">When all rows have been sent, calls SQLPutData for the table-valued parameter with a *Str_Len_or_Ind* value of 0, then proceeds to step 3a above.</span></span>  
  
6.  <span data-ttu-id="c4f4a-209">Chiama di nuovo SQLParamData.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-209">Calls SQLParamData again.</span></span> <span data-ttu-id="c4f4a-210">Se sono presenti parametri data-at-execution tra le colonne di parametri con valori di tabella, questi verranno identificati dal valore *ValuePtrPtr* restituito da SQLParamData.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-210">If there are any data-at-execution parameters among the table-valued parameter columns, these will be identified by the value *ValuePtrPtr* returned by SQLParamData.</span></span> <span data-ttu-id="c4f4a-211">Quando sono disponibili tutti i valori di colonna, SQLParamData restituirà nuovamente il valore *ParameterValuePtr* per il parametro con valori di tabella e l'applicazione verrà riavviata.</span><span class="sxs-lookup"><span data-stu-id="c4f4a-211">When all column values are available, SQLParamData will again return the *ParameterValuePtr* value for the table-valued parameter, and the application begins again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f4a-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4f4a-212">See Also</span></span>  
 [<span data-ttu-id="c4f4a-213">Parametri con valori di tabella &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="c4f4a-213">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  