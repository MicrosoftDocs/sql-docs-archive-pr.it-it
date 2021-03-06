---
title: Utilizzo dei tipi di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625262"
---
# <a name="working-with-data-types"></a>Utilizzo dei tipi di dati
  I dati sono disponibili in diversi tipi e dimensioni, ad esempio una stringa con una lunghezza definita, un numero con una accuratezza specifica o un tipo di dati definito dall'utente che rappresenta un altro oggetto con un set di regole specifico. L' <xref:Microsoft.SqlServer.Management.Smo.DataType> oggetto classifica il tipo di dati in modo che possa essere gestito correttamente da [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . L'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType> è associato a oggetti che accettano dati. Gli oggetti [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) seguenti accettano dati che devono essere definiti da una proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType>:  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 La proprietà `DataType` per oggetti che accettano dati può essere impostata in diversi modi.  
  
-   Utilizzare il costruttore predefinito e specificare in modo esplicito le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType>  
  
-   Utilizzare un costruttore di overload e specificare le proprietà <xref:Microsoft.SqlServer.Management.Smo.DataType> come parametri.  
  
-   Specificare l'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType> inline nel costruttore di oggetti.  
  
-   Utilizzare uno dei membri statici della classe <xref:Microsoft.SqlServer.Management.Smo.DataType>, ad esempio `Int`. In questo modo verrà restituita un'istanza di un oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType>.  
  
 L'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType> include diverse proprietà che definiscono il tipo di dati. La proprietà <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> specifica, ad esempio, il tipo di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. I valori costanti che rappresentano i tipi di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono elencati nell'enumerazione <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>. Tale enumerazione si riferisce a tipi di dati quali `varchar`, `nchar`, `currency`, `integer`, `float` e `datetime`.  
  
 Quando viene stabilito il tipo di dati, è necessario impostare proprietà specifiche per i dati. Se, ad esempio, i dati sono di tipo `nchar`, è necessario impostare la lunghezza dei dati di stringa nella proprietà `Length`. La stessa operazione è richiesta anche nel caso dei valori numerici, per i quali è necessario specificare la precisione e la scala.  
  
 I tipi di dati <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> fanno riferimento agli oggetti contenenti la definizione de tipo di dati fornita dall'utente. <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> si basa sui tipi di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dell'enumerazione <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>. L'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> è basato sui [!INCLUDE[msCoName](../../../includes/msconame-md.md)] tipi di dati .NET. In genere, rappresentano dati di un tipo specifico riutilizzati di frequente dal database in base a regole business definite dall'organizzazione. Un tipo di dati che consente, ad esempio, di archiviare un importo e un denominatore di valuta risulterebbe utile in una società che gestisce più valute.  
  
 L'enumerazione <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> contiene un elenco di tutti i tipi di dati supportati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="examples"></a>Esempi  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a>Costruzione di un oggetto DataType con la specifica nel costruttore di Visual Basic  
 In questo esempio di codice viene illustrato come utilizzare il costruttore per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti.  
  
> [!NOTE]  
>  I tipi <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e XML richiedono tutti un nome per identificare l'oggetto.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a>Costruzione di un oggetto DataType con la specifica nel costruttore di Visual C#  
 In questo esempio di codice viene illustrato come utilizzare il costruttore per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti.  
  
> [!NOTE]  
>  I tipi <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e XML richiedono tutti un nome per identificare l'oggetto.  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a>Costruzione di un oggetto DataType mediante il costruttore predefinito di Visual Basic  
 In questo esempio di codice viene illustrato come utilizzare il costruttore predefinito per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti. Successivamente vengono utilizzate le proprietà per specificare il tipo di dati.  
  
 **Nota** I <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipi XML, e richiedono tutti un valore Name per identificare l'oggetto.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a>Costruzione di un oggetto DataType mediante il costruttore predefinito di Visual C#  
 In questo esempio di codice viene illustrato come utilizzare il costruttore predefinito per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti. Successivamente vengono utilizzate le proprietà per specificare il tipo di dati.  
  
 **Nota** I <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipi XML, e richiedono tutti un valore Name per identificare l'oggetto.  
  
```  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
