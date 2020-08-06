---
title: Metadati aggiuntivi dei parametri con valori di tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), catalog functions to retrieve metadata
- table-valued parameters (ODBC), metadata
ms.assetid: 6c193188-5185-4373-9a0d-76cfc150c828
author: rothja
ms.author: jroth
ms.openlocfilehash: 9907b6bdbabcea427e5feffd14369e8aa718094f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636073"
---
# <a name="additional-table-valued-parameter-metadata"></a><span data-ttu-id="3b26f-102">Metadati aggiuntivi dei parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="3b26f-102">Additional Table-Valued Parameter Metadata</span></span>
  <span data-ttu-id="3b26f-103">Per recuperare i metadati per un parametro con valori di tabella, un'applicazione chiama SQLProcedureColumns.</span><span class="sxs-lookup"><span data-stu-id="3b26f-103">To retrieve metadata for a table-valued parameter, an application calls SQLProcedureColumns.</span></span> <span data-ttu-id="3b26f-104">Per un parametro con valori di tabella, SQLProcedureColumns restituisce una singola riga.</span><span class="sxs-lookup"><span data-stu-id="3b26f-104">For a table-valued parameter, SQLProcedureColumns returns a single row.</span></span> <span data-ttu-id="3b26f-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Sono state aggiunte due colonne specifiche aggiuntive, SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMA_NAME, per fornire informazioni sullo schema e sul catalogo per i tipi di tabella associati ai parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="3b26f-105">Two additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific columns, SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMA_NAME, have been added to provide schema and catalog information for table types associated with table-valued parameters.</span></span> <span data-ttu-id="3b26f-106">In conformità con la specifica ODBC, SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMA_NAME vengono visualizzati prima di tutte le colonne specifiche del driver che sono state aggiunte nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e dopo tutte le colonne richieste da ODBC stesso.</span><span class="sxs-lookup"><span data-stu-id="3b26f-106">In conformance with the ODBC specification, SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMA_NAME appear before all driver-specific columns added in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and after all columns mandated by ODBC itself.</span></span>  
  
 <span data-ttu-id="3b26f-107">Nella tabella seguente sono elencate le colonne significative per i parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="3b26f-107">The following table lists columns that are significant for table-valued parameters.</span></span>  
  
|<span data-ttu-id="3b26f-108">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="3b26f-108">Column name</span></span>|<span data-ttu-id="3b26f-109">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="3b26f-109">Data type</span></span>|<span data-ttu-id="3b26f-110">Valore/commenti</span><span class="sxs-lookup"><span data-stu-id="3b26f-110">Value/comments</span></span>|  
|-----------------|---------------|---------------------|  
|<span data-ttu-id="3b26f-111">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3b26f-111">DATA_TYPE</span></span>|<span data-ttu-id="3b26f-112">Smallint non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-112">Smallint not NULL</span></span>|<span data-ttu-id="3b26f-113">SQL_SS_TABLE</span><span class="sxs-lookup"><span data-stu-id="3b26f-113">SQL_SS_TABLE</span></span>|  
|<span data-ttu-id="3b26f-114">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="3b26f-114">TYPE_NAME</span></span>|<span data-ttu-id="3b26f-115">WVarchar(128) non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-115">WVarchar(128) not NULL</span></span>|<span data-ttu-id="3b26f-116">Nome del tipo del parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="3b26f-116">The type name of the table-valued parameter.</span></span>|  
|<span data-ttu-id="3b26f-117">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="3b26f-117">COLUMN_SIZE</span></span>|<span data-ttu-id="3b26f-118">Integer</span><span class="sxs-lookup"><span data-stu-id="3b26f-118">Integer</span></span>|<span data-ttu-id="3b26f-119">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-119">NULL</span></span>|  
|<span data-ttu-id="3b26f-120">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3b26f-120">BUFFER_LENGTH</span></span>|<span data-ttu-id="3b26f-121">Integer</span><span class="sxs-lookup"><span data-stu-id="3b26f-121">Integer</span></span>|<span data-ttu-id="3b26f-122">0</span><span class="sxs-lookup"><span data-stu-id="3b26f-122">0</span></span>|  
|<span data-ttu-id="3b26f-123">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="3b26f-123">DECIMAL_DIGITS</span></span>|<span data-ttu-id="3b26f-124">Smallint</span><span class="sxs-lookup"><span data-stu-id="3b26f-124">Smallint</span></span>|<span data-ttu-id="3b26f-125">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-125">NULL</span></span>|  
|<span data-ttu-id="3b26f-126">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="3b26f-126">NUM_PREC_RADIX</span></span>|<span data-ttu-id="3b26f-127">Smallint</span><span class="sxs-lookup"><span data-stu-id="3b26f-127">Smallint</span></span>|<span data-ttu-id="3b26f-128">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-128">NULL</span></span>|  
|<span data-ttu-id="3b26f-129">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3b26f-129">NULLABLE</span></span>|<span data-ttu-id="3b26f-130">Smallint non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-130">Smallint not NULL</span></span>|<span data-ttu-id="3b26f-131">SQL_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3b26f-131">SQL_NULLABLE</span></span>|  
|<span data-ttu-id="3b26f-132">REMARKS</span><span class="sxs-lookup"><span data-stu-id="3b26f-132">REMARKS</span></span>|<span data-ttu-id="3b26f-133">Varchar</span><span class="sxs-lookup"><span data-stu-id="3b26f-133">Varchar</span></span>|<span data-ttu-id="3b26f-134">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-134">NULL</span></span>|  
|<span data-ttu-id="3b26f-135">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="3b26f-135">COLUMN_DEF</span></span>|<span data-ttu-id="3b26f-136">WVarchar(4000)</span><span class="sxs-lookup"><span data-stu-id="3b26f-136">WVarchar(4000)</span></span>|<span data-ttu-id="3b26f-137">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-137">NULL</span></span>|  
|<span data-ttu-id="3b26f-138">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="3b26f-138">SQL_DATA_TYPE</span></span>|<span data-ttu-id="3b26f-139">Smallint non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-139">Smallint not NULL</span></span>|<span data-ttu-id="3b26f-140">SQL_SS_TABLE</span><span class="sxs-lookup"><span data-stu-id="3b26f-140">SQL_SS_TABLE</span></span>|  
|<span data-ttu-id="3b26f-141">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="3b26f-141">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="3b26f-142">Smallint</span><span class="sxs-lookup"><span data-stu-id="3b26f-142">Smallint</span></span>|<span data-ttu-id="3b26f-143">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-143">NULL</span></span>|  
|<span data-ttu-id="3b26f-144">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="3b26f-144">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="3b26f-145">Integer</span><span class="sxs-lookup"><span data-stu-id="3b26f-145">Integer</span></span>|<span data-ttu-id="3b26f-146">NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-146">NULL</span></span>|  
|<span data-ttu-id="3b26f-147">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="3b26f-147">ORDINAL_POSITION</span></span>|<span data-ttu-id="3b26f-148">Integer non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-148">Integer not NULL</span></span>|<span data-ttu-id="3b26f-149">Posizione ordinale del parametro.</span><span class="sxs-lookup"><span data-stu-id="3b26f-149">The ordinal position of the parameter.</span></span>|  
|<span data-ttu-id="3b26f-150">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="3b26f-150">IS_NULLABLE</span></span>|<span data-ttu-id="3b26f-151">Varchar</span><span class="sxs-lookup"><span data-stu-id="3b26f-151">Varchar</span></span>|<span data-ttu-id="3b26f-152">"YES"</span><span class="sxs-lookup"><span data-stu-id="3b26f-152">"YES"</span></span>|  
|<span data-ttu-id="3b26f-153">SS_TYPE_CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="3b26f-153">SS_TYPE_CATALOG_NAME</span></span>|<span data-ttu-id="3b26f-154">WVarchar(128) non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-154">WVarchar(128) not NULL</span></span>|<span data-ttu-id="3b26f-155">Catalogo contenente la definizione di tipo per il tipo di tabella del parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="3b26f-155">The catalog that contains the type definition for the table type of the table-valued parameter.</span></span>|  
|<span data-ttu-id="3b26f-156">SS_TYPE_SCHEMA_NAME</span><span class="sxs-lookup"><span data-stu-id="3b26f-156">SS_TYPE_SCHEMA_NAME</span></span>|<span data-ttu-id="3b26f-157">WVarchar(128) non NULL</span><span class="sxs-lookup"><span data-stu-id="3b26f-157">WVarchar(128) not NULL</span></span>|<span data-ttu-id="3b26f-158">Schema contenente la definizione di tipo per il tipo di tabella del parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="3b26f-158">The schema that contains the type definition for the table type of the table-valued parameter.</span></span>|  
  
 <span data-ttu-id="3b26f-159">Le colonne WVarchar sono definite come Varchar nella specifica di ODBC ma, di fatto, vengono restituite come WVarchar in tutti i driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recenti.</span><span class="sxs-lookup"><span data-stu-id="3b26f-159">The WVarchar columns are defined as Varchar in the ODBC specification, but are actually returned as WVarchar in all recent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC drivers.</span></span> <span data-ttu-id="3b26f-160">Questa modifica è stata apportata quando il supporto Unicode è stato aggiunto alla specifica di ODBC 3.5 ma non è stato esplicitamente menzionato.</span><span class="sxs-lookup"><span data-stu-id="3b26f-160">This change was made when Unicide support was added to the ODBC 3.5 specification, but not called out explicitly.</span></span>  
  
 <span data-ttu-id="3b26f-161">Per ottenere metadati aggiuntivi per i parametri con valori di tabella, un'applicazione utilizza le funzioni di catalogo SQLColumns e SQLPrimaryKeys.</span><span class="sxs-lookup"><span data-stu-id="3b26f-161">To obtain additional metadata for table-valued parameters, an application uses the catalog functions SQLColumns and SQLPrimaryKeys.</span></span> <span data-ttu-id="3b26f-162">Prima che queste funzioni vengano chiamate per i parametri con valori di tabella, è necessario che l'attributo dell'istruzione SQL_SOPT_SS_NAME_SCOPE venga impostato su SQL_SS_NAME_SCOPE_TABLE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="3b26f-162">Before these functions are called for table-valued parameters, the application must set the statement attribute SQL_SOPT_SS_NAME_SCOPE to SQL_SS_NAME_SCOPE_TABLE_TYPE.</span></span> <span data-ttu-id="3b26f-163">Questo valore indica che l'applicazione richiede metadati per un tipo di tabella piuttosto che una tabella effettiva.</span><span class="sxs-lookup"><span data-stu-id="3b26f-163">This value indicates that the application requires metadata for a table type rather than an actual table.</span></span> <span data-ttu-id="3b26f-164">L'applicazione passa quindi il TYPE_NAME del parametro con valori di tabella come parametro *TableName* .</span><span class="sxs-lookup"><span data-stu-id="3b26f-164">The application then passes the TYPE_NAME of the table-valued parameter as the *TableName* parameter.</span></span> <span data-ttu-id="3b26f-165">Per identificare il catalogo e lo schema per il parametro con valori di tabella, SS_TYPE_CATALOG_NAME e SS_TYPE_SCHEMA_NAME vengono utilizzati rispettivamente con i parametri *CatalogName* e *SchemaName* .</span><span class="sxs-lookup"><span data-stu-id="3b26f-165">SS_TYPE_CATALOG_NAME and SS_TYPE_SCHEMA_NAME are used with the *CatalogName* and *SchemaName* parameters, respectively, to identify the catalog and schema for the table-valued parameter.</span></span> <span data-ttu-id="3b26f-166">Quando un'applicazione ha completato il recupero dei metadati per i parametri con valori di tabella, deve impostare nuovamente SQL_SOPT_SS_NAME_SCOPE sul valore predefinito di SQL_SS_NAME_SCOPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="3b26f-166">When an application has finished retrieving metadata for table-valued parameters, it must set SQL_SOPT_SS_NAME_SCOPE back to its default value of SQL_SS_NAME_SCOPE_TABLE.</span></span>  
  
 <span data-ttu-id="3b26f-167">Quando SQL_SOPT_SS_NAME_SCOPE è impostato su SQL_SS_NAME_SCOPE_TABLE, le query ai server collegati non riescono.</span><span class="sxs-lookup"><span data-stu-id="3b26f-167">When SQL_SOPT_SS_NAME_SCOPE is set to SQL_SS_NAME_SCOPE_TABLE, queries to linked servers fail.</span></span> <span data-ttu-id="3b26f-168">Le chiamate a SQLColumns o SQLPrimaryKeys con un catalogo contenente un componente server avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3b26f-168">Calls to SQLColumns or SQLPrimaryKeys with a catalog that contains a server component will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b26f-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b26f-169">See Also</span></span>  
 [<span data-ttu-id="3b26f-170">Parametri con valori di tabella &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3b26f-170">Table-Valued Parameters &#40;ODBC&#41;</span></span>](table-valued-parameters-odbc.md)  
  
  