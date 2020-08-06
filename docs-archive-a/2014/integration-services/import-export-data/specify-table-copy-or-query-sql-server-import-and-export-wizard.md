---
title: Impostazione copia tabella o query (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.specifytablecopyorquery.f1
ms.assetid: 08aa7158-40e6-4ef3-84d3-1265a8ba194c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a3d1eafb57475ed6a0f9fb20894fcc9718d1f0c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635126"
---
# <a name="specify-table-copy-or-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="7b4b3-102">Impostazione copia tabella o query (Importazione/Esportazione guidata SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7b4b3-102">Specify Table Copy or Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="7b4b3-103">Utilizzare la pagina **impostazione Copia tabella o query** per specificare la modalità di copia dei dati.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-103">Use the **Specify Table Copy or Query** page to specify how to copy data.</span></span> <span data-ttu-id="7b4b3-104">È possibile selezionare gli oggetti di database esistenti che si desidera copiare mediante l'interfaccia grafica oppure utilizzare Transact-SQL per creare una query più complessa.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-104">You can use a graphical interface to select the existing database objects you want to copy, or you can use Transact-SQL to create a more complex query.</span></span>  
  
 <span data-ttu-id="7b4b3-105">Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7b4b3-105">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="7b4b3-106">Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7b4b3-106">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="7b4b3-107">Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-107">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="7b4b3-108">La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-108">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="7b4b3-109">Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-109">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="7b4b3-110">Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7b4b3-110">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="7b4b3-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7b4b3-111">Options</span></span>  
 <span data-ttu-id="7b4b3-112">**Copia i dati da una o più tabelle o viste**</span><span class="sxs-lookup"><span data-stu-id="7b4b3-112">**Copy data from one or more tables or views**</span></span>  
 <span data-ttu-id="7b4b3-113">Consente di copiare i campi dalle tabelle e dalle viste di origine selezionate nella destinazione o nelle destinazioni specificate utilizzando la finestra di dialogo **Seleziona tabelle e viste di origine** .</span><span class="sxs-lookup"><span data-stu-id="7b4b3-113">Copy fields from selected source tables and views to the specified destination or destinations by using the **Select Source Tables and Views** dialog box.</span></span> <span data-ttu-id="7b4b3-114">Utilizzare questa opzione se si desidera copiare tutti i dati inclusi nell'origine senza filtrare o ordinare i record.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-114">Use this option if you want to copy all data in the source without filtering or ordering records.</span></span>  
  
 <span data-ttu-id="7b4b3-115">Quando si utilizza un [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provider di dati per connettersi all'origine dati, l'opzione **copia i dati da una o più tabelle o viste** potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-115">When you use a [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] data provider to connect to your data source, the **Copy data from one or more tables or views** option might not be available.</span></span> <span data-ttu-id="7b4b3-116">Questa opzione è disponibile solo per i provider per cui è presente una sezione ProviderDescription nel file ProviderDescriptors.xml.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-116">This option is available only for those providers that have a ProviderDescription section in the ProviderDescriptors.xml file.</span></span> <span data-ttu-id="7b4b3-117">Ogni sezione ProviderDescription contiene le informazioni necessarie per recuperare metadati dal provider corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-117">Each ProviderDescription section contains the information that is required to retrieve metadata from the corresponding provider.</span></span> <span data-ttu-id="7b4b3-118">Per impostazione predefinita, il file ProviderDescriptors.xml contiene una sezione ProviderDescription solo per i provider seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b4b3-118">By default, the ProviderDescriptors.xml file contains a ProviderDescription section for only the following providers:</span></span>  
  
-   <span data-ttu-id="7b4b3-119">System.Data.SqlClient</span><span class="sxs-lookup"><span data-stu-id="7b4b3-119">System.Data.SqlClient</span></span>  
  
-   <span data-ttu-id="7b4b3-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="7b4b3-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="7b4b3-121">System.Data.OleDb</span><span class="sxs-lookup"><span data-stu-id="7b4b3-121">System.Data.OleDb</span></span>  
  
-   <span data-ttu-id="7b4b3-122">System.Data.Odbc</span><span class="sxs-lookup"><span data-stu-id="7b4b3-122">System.Data.Odbc</span></span>  
  
 <span data-ttu-id="7b4b3-123">Per rendere disponibili la **copia dei dati da una o più tabelle o viste** per provider aggiuntivi, terze parti possono aggiungere le proprie sezioni ProviderDescriptor al file ProviderDescriptors.xml.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-123">To make the **Copy data from one or more tables or views** option available for additional providers, third parties can add their own ProviderDescriptor sections to the ProviderDescriptors.xml file.</span></span> <span data-ttu-id="7b4b3-124">Per impostazione predefinita, il file si trova in \<*drive*> : \Programmi\Microsoft SQL Server\100\DTS\ProviderDescriptors.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-124">By default, this file is in \<*drive*>:\Program Files\Microsoft SQL Server\100\DTS\ProviderDescriptors.</span></span> <span data-ttu-id="7b4b3-125">Per controllare i requisiti per la sezione ProviderDescriptor, vedere il file di schema ProviderDescriptors.xsd disponibile, per impostazione predefinita, nella stessa cartella del file ProviderDescriptors.xml.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-125">To review the requirements for the ProviderDescriptor section, see the ProviderDescriptors.xsd schema file that is, by default, in the same folder as the ProviderDescriptors.xml file.</span></span>  
  
 <span data-ttu-id="7b4b3-126">**Scrivi una query per specificare i dati da trasferire**</span><span class="sxs-lookup"><span data-stu-id="7b4b3-126">**Write a query to specify the data to transfer**</span></span>  
 <span data-ttu-id="7b4b3-127">Compilare istruzioni SQL per recuperare le righe utilizzando la finestra di dialogo **specificare una query di origine** .</span><span class="sxs-lookup"><span data-stu-id="7b4b3-127">Build SQL statements to retrieve rows by using the **Provide a Source Query** dialog box.</span></span> <span data-ttu-id="7b4b3-128">Utilizzare questa opzione se si desidera modificare o limitare i dati di origine durante l'operazione di copia.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-128">Use this option if you want to modify or restrict the source data during the copy operation.</span></span> <span data-ttu-id="7b4b3-129">È possibile copiare solo le righe che corrispondono ai criteri di selezione.</span><span class="sxs-lookup"><span data-stu-id="7b4b3-129">Only the rows matching the selection criteria are available for copying.</span></span>  
  
  