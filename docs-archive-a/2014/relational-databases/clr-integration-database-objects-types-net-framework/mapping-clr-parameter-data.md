---
title: Mapping dei dati dei parametri CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlBinary data type
- SqlInt16 data type
- SqlMoney data type
- SqlString data type
- SqlSingle data type
- data types [CLR integration]
- SqlInt64 data type
- SqlDateTime data type
- SqlXml data type
- SqlBoolean data type
- SqlDecimal data type
- SqlBytes data type
- mapping data types [CLR integration]
- SqlChars data type
- SqlInt32 data type
ms.assetid: 89b43ee9-b9ad-4281-a4bf-c7c8d116daa2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7025c5180eac793534961af63df9ac701c95c03f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725959"
---
# <a name="mapping-clr-parameter-data"></a>Mapping dei dati dei parametri CLR
  Nella tabella seguente sono elencati i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipi di dati, gli equivalenti nella Common Language Runtime (CLR) per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nello `System.Data.SqlTypes` spazio dei nomi e i relativi equivalenti CLR nativi nell' [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.  
  
||||  
|-|-|-|  
|**Tipo di dati di SQL Server**|Tipo (in System.Data.SqlTypes o Microsoft.SqlServer.Types)|**Tipo di dati CLR (.NET Framework)**|  
|`bigint`|`SqlInt64`|**Int64, Nullable\<Int64>**|  
|`binary`|`SqlBytes, SqlBinary`|`Byte[]`|  
|`bit`|`SqlBoolean`|**Booleano, Nullable\<Boolean>**|  
|`char`|nessuno|nessuno|  
|`cursor`|nessuno|nessuno|  
|`date`|`SqlDateTime`|**DateTime, Nullable\<DateTime>**|  
|`datetime`|`SqlDateTime`|**DateTime, Nullable\<DateTime>**|  
|`datetime2`|Nessuno|**DateTime, Nullable\<DateTime>**|  
|`DATETIMEOFFSET`|`None`|**DateTimeOffset, Nullable\<DateTimeOffset>**|  
|`decimal`|`SqlDecimal`|**Decimale, Nullable\<Decimal>**|  
|`float`|`SqlDouble`|**Double, Nullable\<Double>**|  
|`geography`|`SqlGeography`<br /><br /> `SqlGeography`è definito in Microsoft.SqlServer.Types.dll, installato con SQL Server e può essere scaricato dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).|Nessuno|  
|`geometry`|`SqlGeometry`<br /><br /> `SqlGeometry`è definito in Microsoft.SqlServer.Types.dll, installato con SQL Server e può essere scaricato dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).|Nessuno|  
|`hierarchyid`|`SqlHierarchyId`<br /><br /> `SqlHierarchyId`è definito in Microsoft.SqlServer.Types.dll, installato con SQL Server e può essere scaricato dal [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164).|nessuno|  
|`image`|nessuno|nessuno|  
|`int`|`SqlInt32`|**Int32, Nullable\<Int32>**|  
|`money`|`SqlMoney`|**Decimale, Nullable\<Decimal>**|  
|`nchar`|`SqlChars, SqlString`|`String, Char[]`|  
|`ntext`|nessuno|nessuno|  
|`numeric`|`SqlDecimal`|**Decimale, Nullable\<Decimal>**|  
|`nvarchar`|`SqlChars, SqlString`<br /><br /> `SQLChars` rappresenta la soluzione migliore per il trasferimento dei dati e l'accesso ai dati, mentre `SQLString` è preferibile per l'esecuzione di operazioni di stringa.|`String, Char[]`|  
|`nvarchar(1), nchar(1)`|`SqlChars, SqlString`|**Char, String, Char [], Nullable\<char>**|  
|`real`|`SqlSingle` (la gamma di `SqlSingle`, tuttavia, è maggiore di `real`)|**Singolo, Nullable\<Single>**|  
|`rowversion`|Nessuno|`Byte[]`|  
|`smallint`|`SqlInt16`|**Int16, Nullable\<Int16>**|  
|`smallmoney`|`SqlMoney`|**Decimale, Nullable\<Decimal>**|  
|`sql_variant`|nessuno|`Object`|  
|`table`|nessuno|nessuno|  
|`text`|nessuno|nessuno|  
|`time`|nessuno|**TimeSpan, Nullable\<TimeSpan>**|  
|`timestamp`|nessuno|nessuno|  
|`tinyint`|`SqlByte`|**Byte, Nullable\<Byte>**|  
|`uniqueidentifier`|`SqlGuid`|**GUID, Nullable\<Guid>**|  
|`User-defined type(UDT)`|Nessuno|La stessa classe associata al tipo definito dall'utente (UDT) nello stesso assembly o un assembly dipendente.|  
|**varbinary**|`SqlBytes, SqlBinary`|`Byte[]`|  
|`varbinary(1), binary(1)`|`SqlBytes, SqlBinary`|**byte, byte [], Nullable\<byte>**|  
|`varchar`|nessuno|nessuno|  
|`xml`|`SqlXml`|nessuno|  
  
## <a name="automatic-data-type-conversion-with-out-parameters"></a>Conversione automatica dei tipi di dati con parametri Out  
 Un metodo CLR può restituire informazioni al codice o programma chiamante contrassegnando un parametro di input con il modificatore `out` (Microsoft Visual C#) o `<Out()> ByRef` (Microsoft Visual Basic). Se il parametro di input è un tipo di dati CLR nello spazio dei nomi `System.Data.SqlTypes` e il programma chiamante ne specifica il tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalente come parametro di input, una conversione dei tipi avviene automaticamente quando il metodo CLR restituisce il tipo di dati.  
  
 La stored procedure CLR seguente, ad esempio, include un parametro di input dei dati CLR `SqlInt32` contrassegnato da `out` (C#) o `<Out()> ByRef` (Visual Basic):  
  
```csharp  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void PriceSum(out SqlInt32 value)  
{ ... }  
```  
  
```vb  
<Microsoft.SqlServer.Server.SqlProcedure> _  
Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
...  
End Sub  
```  
  
 Dopo che l'assembly è stato compilato e creato nel database, la stored procedure viene creata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con l'istruzione Transact-SQL seguente che specifica un tipo dei dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di `int` come parametro OUTPUT:  
  
```  
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
```  
  
 Quando la stored procedure CLR viene chiamata, il tipo di dati `SqlInt32` viene convertito automaticamente in un tipo di dati `int` e restituito al programma chiamante.  
  
 Non tutti i tipi di dati CLR possono essere convertiti automaticamente nei tipi dei dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] equivalenti tramite un parametro out. Nella seguente tabella vengono descritte queste eccezioni.  
  
|||  
|-|-|  
|**Tipo di dati CLR (SQL Server)**|**Tipo di dati di SQL Server**|  
|`Decimal`|SMALLMONEY|  
|`SqlMoney`|SMALLMONEY|  
|`Decimal`|money|  
|`DateTime`|smalldatetime|  
|`SQLDateTime`|smalldatetime|  
  
## <a name="change-history"></a>Cronologia modifiche  
  
|Contenuto aggiornato|  
|---------------------|  
|Aggiunta dei tipi `SqlGeography`, `SqlGeometry` e `SqlHierarchyId` alla tabella di mapping.|  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi di dati di SQL Server in .NET Framework](sql-server-data-types-in-the-net-framework.md)  
  
  
