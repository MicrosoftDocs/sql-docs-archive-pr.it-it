---
title: Proprietà delle origini dati (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 6e14fefc-4e0b-4847-a833-4cf0abe65d50
author: rothja
ms.author: jroth
ms.openlocfilehash: b3c3c2d34897b1e88894f67118fe51bd35a01089
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724556"
---
# <a name="data-source-properties-ole-db"></a>Proprietà delle origini dati (OLE DB)
  Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client implementa le proprietà dell'origine dati come indicato di seguito.  
  
|ID proprietà|Descrizione|  
|-----------------|-----------------|  
|DBPROP_CURRENTCATALOG|L/S: Lettura/scrittura Impostazione predefinita: Nessuna<br /><br /> Descrizione: il valore di DBPROP_CURRENTCATALOG segnala il database corrente per una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sessione del provider OLE DB di Native Client. Se si imposta il valore della proprietà, si ottiene lo stesso effetto che si ottiene impostando il database corrente utilizzando l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] USE *database*.<br /><br /> A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], se si chiama [sp_defaultdb](/sql/relational-databases/system-stored-procedures/sp-defaultdb-transact-sql) e si specifica il nome del database in caratteri minuscoli, anche se il database è stato creato usando sia maiuscole che minuscole, DBPROP_CURRENTCATALOG restituirà il nome in minuscolo. Con le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], DBPROP_CURRENTCATALOG restituisce invece la combinazione di maiuscole e minuscole prevista.|  
|DBPROP_MULTIPLECONNECTIONS|L/S: Lettura/scrittura Impostazione predefinita: VARIANT_FALSE<br /><br /> Descrizione: Se la connessione esegue un comando che non produce un set di righe o produce un set di righe che non è un cursore server e si esegue un altro comando, verrà creata una nuova connessione per eseguire il nuovo comando se DBPROP_MULTIPLECONNECTIONS è VARIANT_TRUE.<br /><br /> Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non creerà un'altra connessione se DBPROP_MULTIPLECONNECTION è VARIANT_FALSE o se una transazione è attiva nella connessione. Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce DB_E_OBJECTOPEN se DBPROP_MULTIPLECONNECTIONS è VARIANT_FALSE e restituisce E_FAIL se è presente una transazione attiva. Le transazioni e il blocco vengono gestiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per singola connessione. Se viene generata una seconda connessione, i comandi sulle connessioni separate non condividono blocchi. Per assicurarsi che un comando non blocchi un altro comando, mantenere attivi i blocchi sulle righe richieste da quest'ultimo. Ciò vale anche nel caso di creazione di più sessioni.<br /><br /> Ogni sessione ha una connessione separata.|  
  
 Nel set di proprietà specifico del provider DBPROPSET_SQLSERVERDATASOURCE, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client definisce le seguenti proprietà dell'origine dati aggiuntive.  
  
|ID proprietà|Descrizione|  
|-----------------|-----------------|  
|SSPROP_ENABLEFASTLOAD|L/S: Lettura/scrittura Impostazione predefinita: VARIANT_FALSE<br /><br /> Descrizione: Per abilitare la copia bulk dalla memoria, la proprietà SSPROP_ENABLEFASTLOAD deve essere impostata su VARIANT_TRUE. Se questa proprietà è impostata sull'origine dati, la sessione appena creata consente al consumer di accedere all'interfaccia [IRowsetFastLoad](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md).<br /><br /> Se la proprietà è impostata su VARIANT_TRUE, l'interfaccia **IRowsetFastLoad** è disponibile attraverso **IOpenRowset::OpenRowset** richiedendo l'interfaccia **IID_IRowsetFastLoad** o impostando **SSPROP_IRowsetFastLoad** su VARIANT_TRUE.|  
|SSPROP_ENABLEBULKCOPY|L/S: Lettura/scrittura Impostazione predefinita: VARIANT_FALSE<br /><br /> Descrizione: Per abilitare la copia bulk dai file, la proprietà SSPROP_ENABLEBULKCOPY deve essere impostata su VARIANT_TRUE. Se questa proprietà è impostata sull'origine dati, l'accesso del consumer all'interfaccia IBCPSession è disponibile allo stesso livello delle sessioni.<br /><br /> Anche SSPROP_IRowsetFastLoad deve essere impostato su VARIANT_TRUE.|  
  
## <a name="see-also"></a>Vedere anche  
 [Oggetti di origine dati &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
  
