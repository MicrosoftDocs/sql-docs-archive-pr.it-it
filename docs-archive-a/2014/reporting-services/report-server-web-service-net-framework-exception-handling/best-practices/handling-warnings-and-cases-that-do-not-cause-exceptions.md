---
title: Gestione di avvisi e casi che non causano eccezioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717381"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a>Gestione di avvisi e casi che non provocano eccezioni
  In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] non vengono generate eccezioni per gli avvisi e per determinati errori. Quando, ad esempio, si utilizza il metodo <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> per pubblicare un nuovo report in un server di report, gli avvisi vengono restituiti come matrice di oggetti <xref:ReportService2010.Warning>. Questi avvisi devono essere gestiti e visualizzati in modo che sia possibile eseguire l'azione appropriata.  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 Un altro modo per gestire gli errori consiste nel valutare i valori restituiti di determinati metodi. È ad esempio possibile utilizzare il metodo <xref:ReportService2010.ReportingService2010.FindItems%2A> per cercare elementi specifici nel database del server di report. Se non vengono trovati elementi corrispondenti ai criteri di ricerca, viene restituita una matrice Null di oggetti <xref:ReportService2010.CatalogItem>. È necessario valutare la matrice, verificare la presenza di `null` e comunicare all'utente se non sono stati trovati elementi.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:ReportService2010.CatalogItem>   
 [Introduzione alla gestione delle eccezioni in Reporting Services](../introducing-exception-handling-in-reporting-services.md)   
 [Classe SoapException di Reporting Services](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
