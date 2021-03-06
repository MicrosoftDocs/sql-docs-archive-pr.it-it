---
title: Uso di sinonimi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- synonyms [SMO]
ms.assetid: db0a9022-9549-43e5-b6b3-deb236f05fb8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5e8416dc3daea3b173fae92e5454a8a65c399e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637720"
---
# <a name="using-synonyms"></a>Utilizzo dei sinonimi
  Per sinonimo si intende un nome alternativo per un oggetto con ambito schema. In SMO i sinonimi sono rappresentati dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.Synonym>. L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Synonym> è un elemento figlio dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database>. Ciò significa che i sinonimi sono validi solo all'interno dell'ambito del database nel quale sono definiti. Il sinonimo può tuttavia fare riferimento a oggetti in un altro database o a un'istanza remota di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 L'oggetto a cui viene assegnato un nome alternativo è noto come oggetto di base. La proprietà name dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Synonym> è il nome alternativo assegnato all'oggetto di base.  
  
## <a name="example"></a>Esempio  
 Per l'esempio di codice seguente, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione. Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).  
  
## <a name="creating-a-synonym-in-visual-basic"></a>Creazione di un sinonimo in Visual Basic  
 Nell'esempio di codice viene illustrato come creare un sinonimo o un nome alternativo per un oggetto con ambito schema. Le applicazioni client possono utilizzare un singolo riferimento per l'oggetto di base mediante un sinonimo anziché utilizzare un nome costituito da più parti per fare riferimento all'oggetto di base.  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBSynonyms1](SMO How to#SMO_VBSynonyms1)]  -->  
  
## <a name="creating-a-synonym-in-visual-c"></a>Creazione di un sinonimo in Visual C#  
 Nell'esempio di codice viene illustrato come creare un sinonimo o un nome alternativo per un oggetto con ambito schema. Le applicazioni client possono utilizzare un singolo riferimento per l'oggetto di base mediante un sinonimo anziché utilizzare un nome costituito da più parti per fare riferimento all'oggetto di base.  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a Synonym object variable by supplying the   
            //parent database, name, and schema arguments in the constructor.   
            //The name is also a synonym of the name of the base object.   
            Synonym syn = new Synonym(db, "Shop", "Sales");  
  
            //Specify the base object, which is the object on which   
            //the synonym is based.   
            syn.BaseDatabase = "AdventureWorks2012";  
            syn.BaseSchema = "Sales";  
            syn.BaseObject = "Store";  
            syn.BaseServer = srv.Name;  
  
            //Create the synonym on the instance of SQL Server.   
            syn.Create();  
        }  
```  
  
## <a name="creating-a-synonym-in-powershell"></a>Creazione di un sinonimo in PowerShell  
 Nell'esempio di codice viene illustrato come creare un sinonimo o un nome alternativo per un oggetto con ambito schema. Le applicazioni client possono utilizzare un singolo riferimento per l'oggetto di base mediante un sinonimo anziché utilizzare un nome costituito da più parti per fare riferimento all'oggetto di base.  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#And the database object corresponding to Adventureworks  
$db = $srv.Databases["AdventureWorks2012"]  
  
$syn = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Synonym -ArgumentList $db, "Shop", "Sales"  
  
#Specify the base object, which is the object on which the synonym is based.  
$syn.BaseDatabase = "AdventureWorks2012"  
$syn.BaseSchema = "Sales"  
$syn.BaseObject = "Store"  
$syn.BaseServer = $srv.Name  
  
#Create the synonym on the instance of SQL Server.  
$syn.Create()  
```  
  
## <a name="see-also"></a>Vedere anche  
 [CREATE SYNONYM &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-synonym-transact-sql)  
