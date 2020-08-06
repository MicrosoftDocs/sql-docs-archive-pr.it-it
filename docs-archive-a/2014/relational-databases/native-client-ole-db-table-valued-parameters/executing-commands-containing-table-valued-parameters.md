---
title: Esecuzione di comandi contenenti parametri con valori di tabella | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, executing commands containing
ms.assetid: 7ecba6f6-fe7a-462a-9aa3-d5115b6d4529
author: rothja
ms.author: jroth
ms.openlocfilehash: e3f616b2b9f95ae558e444bcbdae50eae123fa4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626076"
---
# <a name="executing-commands-containing-table-valued-parameters"></a><span data-ttu-id="e5378-102">Esecuzione di comandi contenenti parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="e5378-102">Executing Commands Containing Table-Valued Parameters</span></span>
  <span data-ttu-id="e5378-103">L'esecuzione di un comando contenente parametri con valori di tabella avviene in due fasi.</span><span class="sxs-lookup"><span data-stu-id="e5378-103">Executing a command that contains table-valued parameters requires two phases:</span></span>  
  
1.  <span data-ttu-id="e5378-104">Specifica dei tipi del parametro.</span><span class="sxs-lookup"><span data-stu-id="e5378-104">Specify the parameter types.</span></span>  
  
2.  <span data-ttu-id="e5378-105">Associazione dei dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="e5378-105">Bind the parameter data.</span></span>  
  
## <a name="table-valued-parameter-specification"></a><span data-ttu-id="e5378-106">Specifica del parametro con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="e5378-106">Table-Valued Parameter Specification</span></span>  
 <span data-ttu-id="e5378-107">Il tipo del parametro con valori di tabella può essere specificato dal consumer.</span><span class="sxs-lookup"><span data-stu-id="e5378-107">The consumer can specify the type of the table-valued parameter.</span></span> <span data-ttu-id="e5378-108">Le informazioni relative al tipo includono il nome del tipo</span><span class="sxs-lookup"><span data-stu-id="e5378-108">This information includes the table-valued parameter type name.</span></span> <span data-ttu-id="e5378-109">e il nome dello schema, se il tipo di tabella definito dall'utente per il parametro con valori di tabella non è presente nello schema predefinito corrente per la connessione.</span><span class="sxs-lookup"><span data-stu-id="e5378-109">It also includes the schema name, if the user-defined table type for the table-valued parameter is not in the current default schema for the connection.</span></span> <span data-ttu-id="e5378-110">In base al supporto server, il consumer può specificare anche informazioni facoltative sui metadati, ad esempio l'ordine delle colonne, e specificare che tutte le righe di determinate colonne includano i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e5378-110">Depending on server support, the consumer can also specify optional metadata information, such as ordering of columns, and can specify that all rows for particular columns have the default values.</span></span>  
  
 <span data-ttu-id="e5378-111">Per specificare un parametro con valori di tabella, il consumer chiama ISSCommandWithParameter::SetParameterInfo e, facoltativamente, chiama ISSCommandWithParameters::SetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="e5378-111">To specify a table-valued parameter, the consumer calls ISSCommandWithParameter::SetParameterInfo, and optionally calls ISSCommandWithParameters::SetParameterProperties.</span></span> <span data-ttu-id="e5378-112">Per un parametro con valori di tabella, il campo *pwszDataSourceType* nella struttura DBPARAMBINDINFO presenta un valore pari a DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="e5378-112">For a table-valued parameter, the *pwszDataSourceType* field in the DBPARAMBINDINFO structure has a value of DBTYPE_TABLE.</span></span> <span data-ttu-id="e5378-113">Il campo *ulParamSize* è impostato su ~0 per indicare che la lunghezza non è nota.</span><span class="sxs-lookup"><span data-stu-id="e5378-113">The *ulParamSize* field is set to ~0 to indicate that length is unknown.</span></span> <span data-ttu-id="e5378-114">Per impostare proprietà specifiche dei parametri con valori di tabella, ad esempio il nome dello schema, il nome del tipo, l'ordine delle colonne e le colonne predefinite, è possibile usare ISSCommandWithParameters::SetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="e5378-114">Particular properties for table-valued parameters, such as schema name, type name, column order, and default columns, can be set through ISSCommandWithParameters::SetParameterProperties.</span></span>  
  
## <a name="table-valued-parameter-binding"></a><span data-ttu-id="e5378-115">Associazione del parametro con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="e5378-115">Table-Valued Parameter Binding</span></span>  
 <span data-ttu-id="e5378-116">Un parametro con valori di tabella può essere qualsiasi oggetto set di righe.</span><span class="sxs-lookup"><span data-stu-id="e5378-116">A table-valued parameter can be any rowset object.</span></span> <span data-ttu-id="e5378-117">Il provider legge da questo oggetto mentre invia parametri con valori di tabella al server durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5378-117">The provider reads from this object while sending table-valued parameters to the server during execution.</span></span>  
  
 <span data-ttu-id="e5378-118">Per associare il parametro con valori di tabella, il consumer chiama IAccessor::CreateAccessor.</span><span class="sxs-lookup"><span data-stu-id="e5378-118">To bind the table-valued parameter, the consumer calls IAccessor::CreateAccessor.</span></span> <span data-ttu-id="e5378-119">Il campo *wType* della struttura DBBINDING per il parametro con valori di tabella è impostato su DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="e5378-119">The *wType* field of the DBBINDING structure for the table-valued parameter is set to DBTYPE_TABLE.</span></span> <span data-ttu-id="e5378-120">Il membro *pObject* della struttura DBBINDING è non NULL e il membro *iid* di *pObject* è impostato su IID_IRowset o su qualsiasi altra interfaccia dell'oggetto set di righe del parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="e5378-120">The *pObject* member of the DBBINDING structure is non-NULL, and the *pObject*'s *iid* member is set to IID_IRowset or any other table-valued parameter rowset object interfaces.</span></span> <span data-ttu-id="e5378-121">I campi restanti nella struttura DBBINDING devono essere impostati con la stessa modalità con cui sono impostati per i BLOB di flusso.</span><span class="sxs-lookup"><span data-stu-id="e5378-121">The remaining fields in the DBBINDING structure should be set the same way they are set for streamed BLOBs.</span></span>  
  
 <span data-ttu-id="e5378-122">Alle associazioni relative al parametro con valori di tabella e all'oggetto set di righe associato a un parametro con valori di tabella vengono applicate le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5378-122">In the bindings for the table-valued parameter and the rowset object associated with a table-valued parameter, the following restrictions apply:</span></span>  
  
-   <span data-ttu-id="e5378-123">Gli unici valori di stato consentiti per i dati di colonna dei set di righe di parametri con valori di tabella sono DBSTATUS_S_ISNULL e DBSTATUS_S_OK.</span><span class="sxs-lookup"><span data-stu-id="e5378-123">The only status values allowed for table-valued parameter rowset column data are DBSTATUS_S_ISNULL and DBSTATUS_S_OK.</span></span> <span data-ttu-id="e5378-124">DBSTATUS_S_DEFAULT genera un errore e il valore di stato associato viene impostato su DBSTATUS_E_BADSTATUS.</span><span class="sxs-lookup"><span data-stu-id="e5378-124">DBSTATUS_S_DEFAULT will result in a failure, and the bound status value will be set to DBSTATUS_E_BADSTATUS.</span></span>  
  
-   <span data-ttu-id="e5378-125">Un parametro con valori di tabella può essere contrassegnato dallo stato DBSTATUS_S_DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="e5378-125">A table-valued parameter can be marked with the status DBSTATUS_S_DEFAULT.</span></span> <span data-ttu-id="e5378-126">Gli unici valori validi sono DBSTATUS_S_DEFAULT e DBSTATUS_S_OK.</span><span class="sxs-lookup"><span data-stu-id="e5378-126">The only valid values are DBSTATUS_S_DEFAULT and DBSTATUS_S_OK.</span></span> <span data-ttu-id="e5378-127">Quando lo stato è impostato su DBSTATUS_S_DEFAULT, il valore del parametro con valori di tabella corrisponde a una tabella vuota.</span><span class="sxs-lookup"><span data-stu-id="e5378-127">When the status is set to DBSTATUS_S_DEFAULT, the value of the table-valued parameter corresponds to an empty table.</span></span>  
  
-   <span data-ttu-id="e5378-128">Le colonne di sola lettura nei parametri con valori di tabella (colonne Identity o calcolate) devono essere contrassegnate come predefinite tramite la proprietà SSPROP_PARAM_TABLE_DEFAULT_COLUMNS.</span><span class="sxs-lookup"><span data-stu-id="e5378-128">Read-only columns in table-valued parameters (identity or computed columns) must be marked as default by using the SSPROP_PARAM_TABLE_DEFAULT_COLUMNS property.</span></span> <span data-ttu-id="e5378-129">Anche le colonne che presentano un valore predefinito devono essere contrassegnate come predefinite tramite la proprietà SSPROP_PARAM_TABLE_DEFAULT_COLUMNS per far sì che il valore predefinito venga usato per i valori dei dati della colonna per un determinato parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="e5378-129">Columns that have a default value must also be marked as default through SSPROP_PARAM_TABLE_DEFAULT_COLUMNS property to allow the default value to be used for the column's data values for a particular table-valued parameter.</span></span> <span data-ttu-id="e5378-130">Il provider ignorerà i valori dei dati associati per le colonne contrassegnate come predefinite.</span><span class="sxs-lookup"><span data-stu-id="e5378-130">The provider will ignore the data values bound for the columns marked as default.</span></span>  
  
-   <span data-ttu-id="e5378-131">I dati saranno inviati al server per le colonne con DBPROP_COL_AUTOINCREMENT o SSPROP_COL_COMPUTED, a meno che non sia impostata anche la proprietà SSPROP_PARAM_TABLE_DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="e5378-131">Data will be sent to the server for columns with DBPROP_COL_AUTOINCREMENT or SSPROP_COL_COMPUTED, unless SSPROP_PARAM_TABLE_DEFAULT is also set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5378-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5378-132">See Also</span></span>  
 <span data-ttu-id="e5378-133">[Parametri con valori di tabella &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="e5378-133">[Table-Valued Parameters &#40;OLE DB&#41;](table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="e5378-134">Usare parametri con valori di tabella &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="e5378-134">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  