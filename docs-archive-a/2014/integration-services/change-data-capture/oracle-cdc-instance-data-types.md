---
title: Tipi di dati dell'istanza di Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712275"
---
# <a name="oracle-cdc-instance-data-types"></a>Tipi di dati dell'istanza di Oracle CDC
  L'istanza di Oracle CDC supporta la maggior parte dei tipi di dati Oracle. Nelle sezioni seguenti vengono descritti i tipi di dati supportati e non.  
  
## <a name="supported-data-types"></a>Tipi di dati supportati  
 Nella tabella seguente vengono descritti i tipi di dati Oracle che è possibile acquisire e il relativo mapping predefinito a tipi di dati SQL Server nelle tabelle delle modifiche. Quando si aggiunge un'istanza di acquisizione per una tabella Oracle di origine, è possibile eseguire l'override di alcuni mapping.  
  
|Tipo di dati del database Oracle|Tipo di dati di SQL Server|  
|-------------------------------|--------------------------|  
|BINARY_FLOAT|real|  
|BINARY_DOUBLE|FLOAT|  
|CHAR|NVARCHAR|  
|DATE|DATETIME|  
|FLOAT|FLOAT|  
|INT|NUMERIC (38)|  
|INTERVAL|DATETIME|  
|NCHAR|NVARCHAR|  
|NUMBER|FLOAT|  
|NVARCHAR2|NVARCHAR|  
|RAW|VARBINARY|  
|real|FLOAT|  
|timestamp|DATETIME2|  
|TIMESTAMP WITH TIME ZONE|VARCHAR (37)|  
|TIMESTAMP WITH LOCAL TIME ZONE|VARCHAR (37)|  
|VARCHAR2|VARCHAR|  
|XMLTYPE|NVARCHAR (MAX)|  
  
## <a name="non-supported-data-types"></a>Tipi di dati non supportati  
 Non è possibile acquisire le tabelle Oracle di origine con colonne dei tipi di dati Oracle seguenti. Le colonne acquisite con questi tipi di dati risulteranno Null; tuttavia, una modifica del loro valore viene indicata nella maschera di modifica delle tabelle acquisite.  
  
-   LONG  
  
-   XMLTYPE  
  
-   BLOB  
  
-   CLOB  
  
 Non è possibile acquisire le tabelle Oracle di origine con colonne dei tipi di dati Oracle seguenti.  
  
-   BFILE  
  
-   ROWID  
  
-   REF  
  
-   UROWID  
  
-   Tabella nidificata  
  
 Se in una tabella sono presenti i tipi di dati seguenti, non sarà possibile ottenere dati per alcuna colonna della tabella tramite LogMinder:  
  
-   Tipi di dati definiti dall'utente  
  
-   VARRAY  
  
## <a name="see-also"></a>Vedere anche  
 [Progettazione Change Data Capture per Oracle di Attunity](change-data-capture-designer-for-oracle-by-attunity.md)   
 [Istanza di Oracle CDC](the-oracle-cdc-instance.md)  
  
  
