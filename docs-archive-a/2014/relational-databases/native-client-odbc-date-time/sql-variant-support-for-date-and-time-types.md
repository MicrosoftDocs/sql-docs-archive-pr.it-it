---
title: Supporto sql_variant per i tipi di data e ora | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- sql_variant data type
ms.assetid: 12ff1ea6-e2cc-40e6-910c-3126974a90b3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0818f0ccee72264ea7cab69b90e18418179031ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722784"
---
# <a name="sql_variant-support-for-date-and-time-types"></a>Supporto sql_variant per i tipi di data e ora
  In questo argomento viene illustrato come il tipo di dati `sql_variant` supporta la funzionalità avanzata di data e ora.  
  
 L'attributo della colonna SQL_CA_SS_VARIANT_TYPE è utilizzato per restituire il tipo C di una colonna dei risultati variant. [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] introduce un attributo aggiuntivo, SQL_CA_SS_VARIANT_SQL_TYPE che imposta il tipo SQL di una colonna dei risultati variant nel IRD (descrittore delle righe di implementazione). SQL_CA_SS_VARIANT_SQL_TYPE può essere utilizzato anche nel descrittore del parametro di implementazione (IPD, Implementation Parameter Descriptor ) per specificare il tipo SQL di un parametro SQL_SS_TIME2 o SQL_SS_TIMESTAMPOFFSET nel quale il tipo SQL_C_BINARY C è associato al tipo SQL_SS_VARIANT.  
  
 I nuovi tipi SQL_SS_TIME2 e SQL_SS_TIMESTAMPOFFSET possono essere impostati da SQLColAttribute. SQL_CA_SS_VARIANT_SQL_TYPE possono essere restituiti da SQLGetDescField.  
  
 Per le colonne dei risultati, il driver convertirà i tipi da variant a date/time. Per ulteriori informazioni, vedere [conversioni da SQL a C](datetime-data-type-conversions-from-sql-to-c.md). Quando si esegue il binding a SQL_C_BINARY, la lunghezza del buffer deve essere sufficientemente grande da ricevere lo struct che corrisponde al tipo SQL.  
  
 Per i parametri SQL_SS_TIME2 e SQL_SS_TIMESTAMPOFFSET, il driver convertirà i valori C in valori `sql_variant`, come descritto nella tabella seguente. Se un parametro viene associato come SQL_C_BINARY e il tipo di server è SQL_SS_VARIANT, verrà trattato come valore binario, a meno che l'applicazione non abbia impostato SQL_CA_SS_VARIANT_SQL_TYPE su un tipo SQL diverso. In questo caso SQL_CA_SS_VARIANT_SQL_TYPE ha la precedenza, ovvero se è impostato SQL_CA_SS_VARIANT_SQL_TYPE, viene ignorato il comportamento predefinito che consiste nel dedurre il tipo SQL variant dal tipo C.  
  
|Tipo C|Tipo di server|Commenti|  
|------------|-----------------|--------------|  
|SQL_C_CHAR|varchar|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_WCHAR|nvarcar|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_TINYINT|smallint|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_STINYINT|smallint|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_SHORT|smallint|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_SSHORT|smallint|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_USHORT|int|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_LONG|int|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_SLONG|int|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_ULONG|bigint|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_SBIGINT|bigint|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_FLOAT|real|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_DOUBLE|float|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_BIT|bit|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_UTINYINT|TINYINT|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_BINARY|varbinary|SQL_CA_SS_VARIANT_SQL_TYPE non è impostato.|  
|SQL_C_BINARY|time|SQL_CA_SS_VARIANT_SQL_TYPE = SQL_SS_TIME2<br /><br /> Scale è impostato su SQL_DESC_PRECISION (il parametro *DecimalDigits* di `SQLBindParameter` ).|  
|SQL_C_BINARY|datetimeoffset|SQL_CA_SS_VARIANT_SQL_TYPE = SQL_SS_TIMESTAMPOFFSET<br /><br /> Scale è impostato su SQL_DESC_PRECISION (il parametro *DecimalDigits* di `SQLBindParameter` ).|  
|SQL_C_TYPE_DATE|date|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_TYPE_TIME|time(0)|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato.|  
|SQL_C_TYPE_TIMESTAMP|datetime2|Scale è impostato su SQL_DESC_PRECISION (il parametro *DecimalDigits* di `SQLBindParameter` ).|  
|SQL_C_NUMERIC|decimal|La precisione è impostata su SQL_DESC_PRECISION (il parametro *ColumnSize* di `SQLBindParameter` ).<br /><br /> Set di scalabilità da SQL_DESC_SCALE (il parametro *DecimalDigits* di SQLBindParameter).|  
|SQL_C_SS_TIME2|time|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato|  
|SQL_C_SS_TIMESTAMPOFFSET|datetimeoffset|SQL_CA_SS_VARIANT_SQL_TYPE viene ignorato|  
  
## <a name="see-also"></a>Vedere anche  
 [Miglioramenti di data e ora &#40;ODBC&#41;](date-and-time-improvements-odbc.md)  
  
  
