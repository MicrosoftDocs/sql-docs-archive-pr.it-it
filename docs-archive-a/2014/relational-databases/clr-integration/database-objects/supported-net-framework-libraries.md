---
title: Librerie di .NET Framework supportate | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623335"
---
# <a name="supported-net-framework-libraries"></a>Librerie .NET Framework supportate
  Grazie all'integrazione di CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è possibile creare stored procedure, trigger, funzioni definite dall'utente, tipi definiti dall'utente e aggregazioni definite dall'utente nel codice gestito. Con le librerie di classi .NET Framework è possibile accedere alle classi preesistenti che offrono funzionalità per manipolazione delle stringhe, operazioni matematiche avanzate, accesso ai file, crittografia e così via. A queste classi è possibile accedere da stored procedure gestite, tipi definiti dall'utente, trigger, funzioni definite dall'utente o funzioni di aggregazione definite dall'utente.  
  
> [!NOTE]  
>  Se si esegue il servizio o si aggiornano assembly non supportati nella Global Assembly Cache (GAC), il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . Se esiste un assembly in un' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] integrazione con CLR. Se si gestiscono o aggiornano assembly della GAC registrati anche nel database, inclusi gli assembly .NET Framework non supportati, assicurarsi di gestirne o aggiornarne anche la copia che si trova nei database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con l'istruzione `ALTER ASSEMBLY`. Per ulteriori informazioni, vedere l' [articolo della Knowledge Base 949080](https://support.microsoft.com/kb/949080).  
  
## <a name="supported-libraries"></a>Librerie supportate  
 A partire da [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] è disponibile un elenco di librerie di .NET Framework supportate, che sono state testate per garantire che soddisfino gli standard di affidabilità e sicurezza per l'interazione con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] li carica direttamente dalla Global Assembly Cache (GAC).  
  
 Le librerie e gli spazi dei nomi supportati dall'integrazione con CLR in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono:  
  
-   CustomMarshalers  
  
-   Microsoft.VisualBasic  
  
-   Microsoft.VisualC  
  
-   mscorlib  
  
-   System  
  
-   System.Configuration  
  
-   System.Data  
  
-   System.Data.OracleClient  
  
-   System.Data.SqlXml  
  
-   System.Deployment  
  
-   System.Security  
  
-   System.Transactions  
  
-   System.Web.Services  
  
-   System.Xml  
  
-   System.Core.dll  
  
-   System.Xml.Linq.dll  
  
## <a name="unsupported-libraries"></a>Librerie non supportate  
 Le librerie non supportate possono essere comunque chiamate da stored procedure gestite, trigger, funzioni definite dall'utente, tipi definiti dall'utente e funzioni di aggregazione definite dall'utente. La libreria non supportata deve essere prima registrata nel database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando l'istruzione `CREATE ASSEMBLY` prima che possa essere utilizzata nel codice. È necessario verificare e testare la sicurezza e l'affidabilità delle librerie non supportate registrate ed eseguite nel server.  
  
 Lo spazio dei nomi `System.DirectoryServices` non è ad esempio supportato. È necessario registrare l'assembly System.DirectoryServices.dll con le autorizzazioni `UNSAFE` prima che sia possibile chiamarlo dal codice. L'autorizzazione `UNSAFE` è necessaria perché le classi nello spazio dei nomi `System.DirectoryServices` non soddisfano i requisiti per `SAFE` o `EXTERNAL_ACCESS`. Per altre informazioni, vedere [restrizioni del modello di programmazione dell'integrazione CLR](clr-integration-programming-model-restrictions.md) e [sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di un assembly](../assemblies/creating-an-assembly.md)   
 [Sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md)   
 [Restrizioni relative al modello di programmazione dell'integrazione con CLR](clr-integration-programming-model-restrictions.md)  
  
  
