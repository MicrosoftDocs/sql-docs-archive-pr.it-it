---
title: Avvio di una connessione a un'origine dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [SQL Server Native Client]
- connections [SQL Server Native Client]
- SQL Server Native Client OLE DB provider, data source connections
- CoCreateInstance method
- OLE DB data sources [SQL Server Native Client]
ms.assetid: 7ebd1394-cc8d-4bcf-92f3-c374a26e7ba0
author: rothja
ms.author: jroth
ms.openlocfilehash: f88454339ee932c38655819cce475ab52d79975f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636045"
---
# <a name="establishing-a-connection-to-a-data-source"></a>Avvio di una connessione a un'origine dati
  Per accedere al [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client, il consumer deve prima creare un'istanza di un oggetto origine dati chiamando il metodo **CoCreateInstance** . Un identificatore univoco di classe (CLSID) identifica ogni provider OLE DB. Per il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, l'identificatore di classe è CLSID_SQLNCLI10. È inoltre possibile utilizzare il simbolo SQLNCLI_CLSID che verrà risolto nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client utilizzato nel sqlncli. h a cui si fa riferimento.  
  
 L'oggetto origine dati espone l'interfaccia **IDBProperties** usata dal consumer per fornire informazioni di base sull'autenticazione, ad esempio il nome del server, il nome del database, l'ID utente e la password. Per impostare queste proprietà, viene chiamato il metodo **IDBProperties::SetProperties**.  
  
 Se nel computer sono in esecuzione più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], il nome del server viene specificato come NomeServer\NomeIstanza.  
  
 L'oggetto origine dati espone anche l'interfaccia **IDBInitialize**. Dopo aver impostato le proprietà, la connessione all'origine dati viene stabilita chiamando il metodo **IDBInitialize::Initialize**. Ad esempio:  
  
```  
CoCreateInstance(CLSID_SQLNCLI10,   
                 NULL,   
                 CLSCTX_INPROC_SERVER,  
                 IID_IDBInitialize,   
                 (void **) &pIDBInitialize)  
```  
  
 Questa chiamata a **CoCreateInstance** crea un singolo oggetto della classe associata a CLSID_SQLNCLI10 (CSLID associato ai dati e al codice che verranno usati per creare l'oggetto). IID_IDBInitialize è un riferimento all'identificatore dell'interfaccia (**IDBInitialize**) da usare per comunicare con l'oggetto.  
  
 Di seguito è riportata una funzione di esempio che inizializza e stabilisce una connessione all'origine dati.  
  
```  
void InitializeAndEstablishConnection() {  
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQL Server Native Client OLE DB provider.  
   hr = CoCreateInstance(CLSID_SQLNCLI10,   
                         NULL,   
                         CLSCTX_INPROC_SERVER,  
                         IID_IDBInitialize,   
                         (void **) &pIDBInitialize);  
   // Initialize property values needed to establish connection.  
   for (i = 0 ; i < 4 ; i++)   
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   // See DBPROP structure for more information on InitProperties  
   InitProperties[0].dwPropertyID  = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt    = VT_BSTR;  
   InitProperties[0].vValue.bstrVal=   
                     SysAllocString(L"Server");  
   InitProperties[0].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid       = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt    = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"database");  
   InitProperties[1].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid       = DB_NULLID;  
  
   // Username (login).  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt    = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid       = DB_NULLID;  
   InitProperties[3].dwOptions    = DBPROPOPTIONS_REQUIRED;  
   InitProperties[3].colid       = DB_NULLID;  
  
   // Construct the DBPROPSET structure(rgInitPropSet). The   
   // DBPROPSET structure is used to pass an array of DBPROP   
   // structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties   = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hr = pIDBInitialize->QueryInterface(IID_IDBProperties,   
                           (void **)&pIDBProperties);  
   hr = pIDBProperties->SetProperties(1, rgInitPropSet);   
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   pIDBInitialize->Initialize();  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di un'applicazione del provider OLE DB di SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
