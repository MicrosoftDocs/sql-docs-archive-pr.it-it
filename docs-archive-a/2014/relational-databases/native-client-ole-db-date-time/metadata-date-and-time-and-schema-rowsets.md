---
title: Set di righe dello schema e dei tipi Date e Time | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], schema rowsets
ms.assetid: 8c35e86f-0597-4ef4-b2b8-f643e53ed4c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 71a54cd1d40101b48a0e02fc4b6a6343b04fe185
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723800"
---
# <a name="date-and-time-and-schema-rowsets"></a>Data e ora e set di righe dello schema
  In questo argomento vengono fornite informazioni sui set di righe COLUMNS e PROCEDURE_PARAMETERS. Tali informazioni fanno riferimento ai miglioramenti apportati alla data e all'ora di OLE DB per [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].  
  
## <a name="columns-rowset"></a>Set di righe COLUMNS  
 Per i tipi di data/ora vengono restituiti i valori di colonna seguenti:  
  
|Tipo di colonna|DATA_TYPE|COLUMN_FLAGS, DBCOLUMFLAGS_SS_ISVARIABLESCALE|DATETIME_PRECISION|  
|-----------------|----------------|------------------------------------------------------|-------------------------|  
|date|DBTYPE_DBDATE|Cancella|0|  
|time|DBTYPE_DBTIME2|Set|0..7|  
|smalldatetime|DBTYPE_DBTIMESTAMP|Cancella|0|  
|Datetime|DBTYPE_DBTIMESTAMP|Cancella|3|  
|datetime2|DBTYPE_DBTIMESTAMP|Set|0..7|  
|datetimeoffset|DBTYPE_DBTIMESTAMPOFFSET|Set|0..7|  
  
 In COLUMN_FLAGS il valore di DBCOLUMNFLAGS_ISFIXEDLENGTH è sempre true per i tipi date/time e il valore dei flag seguenti è sempre false:  
  
-   DBCOLUMNFLAGS_CACHEDEFERRED  
  
-   DBCOLUMNFLAGS_ISBOOKMARK  
  
-   DBCOLUMNFLAGS_ISCHAPTER  
  
-   DBCOLUMNFLAGS_ISLONG  
  
-   DBCOLUMNFLAGS_ISROWID  
  
-   DBCOLUMNFLAGS_ISROWVER  
  
-   DBCOLUMNFLAGS_MAYDEFER  
  
 I flag restanti (DBCOLUMNFLAGS_ISNULLABLE, DBCOLUMNFLAGS_MAYBENULL, DBCOLUMNFLAGS_WRITE e DBCOLUMNFLAGS_WRITEUNKNOWN) possono essere impostati in base alla modalità di definizione della colonna.  
  
 In COLUMN_FLAGS è disponibile un nuovo flag DBCOLUMNFLAGS_SS_ISVARIABLESCALE che consente di determinare il tipo di server delle colonne nelle applicazioni, dove DATA_TYPE è DBTYPE_DBTIMESTAMP. Per identificare il tipo di server è necessario utilizzare anche DATETIME_PRECISION.  
  
 DBCOLUMNFLAGS_SS_ISVARIABLESCALE è valido solo quando si è connessi a un server [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (o versioni successive). DBCOLUMNFLAGS_SS_ISFIXEDSCALE non è definito quando si è connessi a server legacy.  
  
## <a name="procedure_parameters-rowset"></a>Set di righe PROCEDURE_PARAMETERS  
 DATA_TYPE contiene gli stessi valori del set di righe dello schema COLUMNS e TYPE_NAME contiene il tipo di server.  
  
 Una nuova colonna, SS_DATETIME_PRECISION, è stata aggiunta per restituire la precisione del tipo come nella colonna DATETIME_PRECISION, in modo analogo al set di righe COLUMNS.  
  
## <a name="provider_types-rowset"></a>Set di righe PROVIDER_TYPES  
 Per i tipi di data/ora vengono restituite le righe seguenti:  
  
|Tipo -><br /><br /> Colonna|Data|time|smalldatetime|Datetime|datetime2|datetimeoffset|  
|--------------------------|----------|----------|-------------------|--------------|---------------|--------------------|  
|TYPE_NAME|Data|time|smalldatetime|Datetime|datetime2|datetimeoffset|  
|DATA_TYPE|DBTYPE_DBDATE|DBTYPE_DBTIME2|DBTYPE_DBTIMESTAMP|DBTYPE_DBTIMESTAMP|DBTYPE_DBTIMESTAMP|DBTYPE_DBTIMESTAMPOFFSET|  
|COLUMN_SIZE|10|16|16|23|27|34|  
|LITERAL_PREFIX|'|'|'|'|'|'|  
|LITERAL_SUFFIX|'|'|'|'|'|'|  
|CREATE_PARAMS|NULL|scala|NULL|NULL|scala|scala|  
|IS_NULLABLE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|  
|CASE_SENSITIVE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|  
|RICERCABILE|DB_SEARCHABLE|DB_SEARCHABLE|DB_SEARCHABLE|DB_SEARCHABLE|DB_SEARCHABLE|DB_SEARCHABLE|  
|UNSIGNED_ATTRIBUTE|NULL|NULL|NULL|NULL|NULL|NULL|  
|FIXED_PREC_SCALE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|  
|AUTO_UNIQUE_VALUE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|  
|LOCAL_TYPE_NAME|Data|time|smalldatetime|Datetime|datetime2|datetimeoffset|  
|MINIMUM_SCALE|NULL|0|NULL|NULL|0|0|  
|MAXIMUM_SCALE|NULL|7|NULL|NULL|7|7|  
|GUID|NULL|NULL|NULL|NULL|NULL|NULL|  
|TYPELIB|NULL|NULL|NULL|NULL|NULL|NULL|  
|VERSION|NULL|NULL|NULL|NULL|NULL|NULL|  
|IS_LONG|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|VARIANT_FALSE|  
|BEST_MATCH|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE a meno che non si verifichi una delle condizioni seguenti:<br /><br /> -Il client è connesso a un server di livello inferiore.<br />-La proprietà di connessione per la compatibilità del tipo di dati specifica un livello di compatibilità pari a 80.|VARIANT_TRUE a meno che non si verifichi una delle condizioni seguenti:<br /><br /> -Il client è connesso a un server di livello inferiore.<br />-La proprietà di connessione per la compatibilità del tipo di dati specifica un livello di compatibilità pari a 80.|VARIANT_TRUE|  
|IS_FIXEDLENGTH|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|VARIANT_TRUE|  
  
 Poiché OLE DB definisce solo MINIMUM_SCALE e MAXIMUM_SCALE per i tipi numerici e decimali, l'utilizzo da parte di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client di queste colonne per time, datetime2 e datetimeoffset è di tipo non standard.  
  
## <a name="see-also"></a>Vedere anche  
 [Metadati &#40;OLE DB&#41;](../../database-engine/dev-guide/metadata-ole-db.md)  
  
  
