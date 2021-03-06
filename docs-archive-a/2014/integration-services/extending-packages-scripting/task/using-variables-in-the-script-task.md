---
title: Uso delle variabili nell'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727064"
---
# <a name="using-variables-in-the-script-task"></a>Utilizzo di variabili nell'attività Script
  Le variabili rendono possibile lo scambio di dati tra l'attività Script e altri oggetti del pacchetto. Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md).  
  
 L'attività Script utilizza la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> dell'oggetto `Dts` per leggere e scrivere negli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.Variable> del pacchetto.  
  
> [!NOTE]  
>  La proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> della classe <xref:Microsoft.SqlServer.Dts.Runtime.Variable> è di tipo `Object`. Poiché l'oggetto `Option Strict` dell'attività Script è abilitato, è necessario eseguire il cast della proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> nel tipo appropriato prima che sia possibile utilizzarla.  
  
 Aggiungere variabili esistenti agli elenchi <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> e <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> in **Editor attività Script** per renderle disponibili per lo script personalizzato. Tenere presente che per i nomi delle variabili viene applicata la distinzione tra maiuscole e minuscole. All'interno dello script le variabili di entrambi i tipi sono accessibili tramite la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> dell'oggetto `Dts`. Utilizzare la proprietà `Value` per leggere e scrivere in singole variabili. L'attività Script gestisce in modo trasparente il blocco mentre lo script legge e modifica i valori delle variabili.  
  
 È possibile utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Variables> restituita dalla proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> per verificare l'esistenza di una variabile prima di utilizzarla nel codice.  
  
 È anche possibile usare la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> (Dts.VariableDispenser) per usare variabili nell'attività Script. Quando si utilizza <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, è necessario gestire sia la semantica di blocco che il cast dei tipi di dati per i valori delle variabili nel codice personalizzato. Può essere necessario utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> anziché la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> se si desidera utilizzare una variabile non disponibile in fase di progettazione ma che viene creata a livello di programmazione in fase di esecuzione.  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a>Utilizzo dell'attività Script in un contenitore Ciclo Foreach  
 Quando un'attività Script viene eseguita ripetutamente in un contenitore Ciclo Foreach, lo script deve in genere gestire il contenuto dell'elemento corrente nell'enumeratore. Ad esempio, se si utilizza l'enumeratore Foreach File, lo script deve riconoscere il nome di file corrente. Se si utilizza l'enumeratore Foreach ADO, lo script deve conoscere il contenuto delle colonne nella riga di dati corrente.  
  
 Le variabili rendono possibile questa comunicazione tra il contenitore Ciclo Foreach e l'attività Script. Nella pagina **Mapping variabili** di **Editor ciclo Foreach** assegnare variabili a ogni elemento di dati restituito da un singolo elemento enumerato. Ad esempio, un enumeratore Foreach File restituisce solo un nome di file in corrispondenza dell'indice 0 e pertanto richiede solo un mapping di variabili, mentre un enumeratore che restituisce diverse colonne di dati in ogni riga richiede che venga eseguito il mapping di una variabile diversa a ogni colonna che si desidera utilizzare nell'attività Script.  
  
 Dopo aver eseguito il mapping degli elementi enumerati alle variabili, è necessario aggiungere le variabili mappate alla `ReadOnlyVariables` proprietà nella pagina **script** dell' **Editor attività script** per renderle disponibili per lo script. Per un esempio di un'attività Script all'interno di un contenitore Ciclo Foreach che elabora i file di immagine in una cartella, vedere [Uso di immagini con l'attività Script](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).  
  
## <a name="variables-example"></a>Esempio di variabili  
 Nell'esempio seguente viene illustrato come accedere e utilizzare le variabili in un'attività Script per determinare il percorso del flusso di lavoro del pacchetto. Nell'esempio si presuppone che siano state create variabili integer denominate e che siano state `CustomerCount` `MaxRecordCount` aggiunte alla `ReadOnlyVariables` raccolta in **Editor attività script**. La variabile `CustomerCount` contiene il numero di record di clienti da importare. Se il valore è maggiore del valore `MaxRecordCount`, l'attività Script riporta un errore. Quando si verifica un errore perché la soglia `MaxRecordCount` è stata superata, il percorso di errore del flusso di lavoro può implementare l'eventuale pulizia richiesta.  
  
 Per compilare correttamente l'esempio, è necessario aggiungere un riferimento all'assembly Microsoft.SqlServer.ScriptTask.  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
    {  
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**<br /> Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:<br /><br /> [Visitare la pagina relativa a Integration Services su MSDN](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.  
  
## <a name="see-also"></a>Vedere anche  
 [Variabili di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md)   
 [Usare variabili nei pacchetti](../../use-variables-in-packages.md)  
  
  
