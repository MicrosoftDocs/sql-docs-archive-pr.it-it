---
title: Avvisi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent alerts, event types
- SQL Server Agent alerts, names
- alerts [SQL Server], performance conditions
- alerts [SQL Server], about alerts
- WMI event responses [SQL Server Agent alerts]
- events [WMI]
- performance condition alerts [SQL Server Agent]
- alerts [SQL Server], event types
- SQL Server Agent alerts, performance conditions
- SQL Server Agent alerts, about alerts
- alerts [SQL Server], names
ms.assetid: 3f57d0f0-4781-46ec-82cd-b751dc5affef
author: stevestein
ms.author: sstein
ms.openlocfilehash: 946bfd0c05e7739af4bfebf799980a0dc27de245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722215"
---
# <a name="alerts"></a>Avvisi
  Gli eventi vengono generati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e immessi nel registro applicazioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows. [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent legge il registro applicazioni ed esegue un confronto tra gli eventi e gli avvisi definiti. Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent rileva una corrispondenza, viene attivato un avviso, che rappresenta una risposta automatica a un evento. Oltre al controllo degli eventi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent può inoltre eseguire il monitoraggio delle condizioni delle prestazioni e degli eventi WMI (Windows Management Instrumentation).  
  
 Per definire un avviso, è necessario specificare gli elementi seguenti:  
  
-   Nome dell'avviso.  
  
-   Evento o condizione delle prestazioni che attiva l'avviso.  
  
-   Azione eseguita da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in risposta all'evento o alla condizione delle prestazioni.  
  
## <a name="naming-an-alert"></a>Denominazione di un avviso  
 Ogni avviso deve essere dotato di un nome. I nomi degli avvisi devono essere univoci nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non possono essere formati da più di **128** caratteri.  
  
## <a name="selecting-an-event-type"></a>Selezione di un tipo di evento  
 Un avviso rappresenta la risposta a un evento di tipo specifico. Gli avvisi rispondono ai tipi di evento seguenti:  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eventi  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] condizioni delle prestazioni  
  
-   Eventi WMI  
  
 Il tipo di evento determina i parametri utilizzati per specificare l'evento esatto.  
  
## <a name="specifying-a-sql-server-event"></a>Definizione di un evento di SQL Server  
 È possibile specificare la generazione di un avviso in risposta a uno o più eventi. Utilizzare i parametri seguenti per specificare gli eventi che comportano l'attivazione di un avviso:  
  
-   **Numero di errore**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent genera un avviso quando si verifica un errore specifico. È possibile, ad esempio, specificare il numero errore 2571 in risposta a tentativi non autorizzati di richiamare comandi DBCC (Database Console Commands).  
  
-   **Livello di gravità**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent genera un avviso quando si verifica un errore con il livello di gravità specificato. È possibile, ad esempio, specificare un livello di gravità 15 in risposta a errori di sintassi nelle istruzioni Transact-SQL.  
  
-   **Database**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent genera un avviso solo quando l'evento viene generato in un database specifico. Questa opzione si applica insieme al numero di errore o al livello di gravità. Se, ad esempio, un'istanza contiene un database utilizzato per la produzione e uno utilizzato per la segnalazione, è possibile definire un avviso in risposta a errori di sintassi solo nel database di produzione.  
  
-   **Testo dell'evento**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent genera un avviso quando l'evento indicato contiene una stringa di testo specifica nel messaggio dell'evento. È possibile, ad esempio, definire un avviso in risposta a messaggi contenenti il nome di una tabella o un vincolo specifico.  
  
## <a name="selecting-a-performance-condition"></a>Selezione di una condizione delle prestazioni  
 È possibile determinare la generazione di un avviso in risposta a una condizione delle prestazioni specifica. In questo caso, è necessario specificare il contatore delle prestazioni da monitorare, una soglia per l'avviso e il comportamento indicato dal contatore se viene generato l'avviso. Per impostare una condizione delle prestazioni, è necessario definire gli elementi indicati di seguito nella pagina [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Generale **della finestra di dialogo** Nuovo avviso **o** Proprietà avviso **di** Agent:  
  
-   **Object**  
  
     L'oggetto rappresenta l'area delle prestazioni da monitorare.  
  
-   **Contatore**  
  
     Un contatore è un attributo dell'area da monitorare.  
  
-   **Istanza**  
  
     L'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definisce l'istanza specifica, se disponibile, dell'attributo da monitorare.  
  
-   **Avvisa se il contatore** e **Valore**  
  
     La soglia per l'avviso e il comportamento prodotto dall'avviso. La soglia è rappresentata da un numero. Il comportamento può essere uno dei seguenti **: è minore di**, **diventa uguale a**o **è maggiore di un numero specificato per Valore**. L'opzione **Valore** rappresenta un numero che descrive il contatore della condizione delle prestazioni. Per impostare, ad esempio, un avviso per l'oggetto prestazione **SQLServer:Locks** quando il valore **Tempo di attesa blocchi (ms)** supera i 30 minuti, selezionare **è maggiore di** e **specificare 30 come valore**.  
  
     Sempre a titolo di esempio, è possibile specificare che un avviso venga generato per l'oggetto prestazione **SQLServer:Transactions** quando lo spazio disponibile in **tempdb** è minore di 1000 KB. Per procedere, scegliere il contatore **Spazio disponibile in tempdb (KB)**, **è minore di**e un **Valore** pari a **1000**.  
  
    > [!NOTE]  
    >  Viene eseguito un campionamento periodico dei dati relativi alle prestazioni, che può determinare un lieve ritardo (qualche secondo) tra il raggiungimento della soglia e la generazione dell'avviso.  
  
## <a name="selecting-a-wmi-event"></a>Selezione di un evento WMI  
 È possibile impostare la generazione di un avviso in risposta a un evento WMI specifico. Per selezionare un evento WMI, è necessario definire gli elementi indicati di seguito nella pagina [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Generale **della finestra di dialogo** Nuovo avviso **o** Proprietà avviso **di** Agent:  
  
-   **Spazio dei nomi**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent viene registrato come client WMI nello spazio dei nomi WMI indicato per le query per gli eventi.  
  
-   **Query**  
  
     [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent usa l'istruzione WQL (Windows Management Instrumentation Query Language) indicata per identificare l'evento specifico.  
  
 Di seguito vengono indicati alcuni collegamenti utili per l'esecuzione di operazioni comuni:  
  
 **Per creare un avviso in base a un numero di messaggio**  
  
-   [SQL Server Management Studio](create-an-alert-using-an-error-number.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 **Per creare un avviso in base ai livelli di gravità**  
  
-   [SQL Server Management Studio](create-an-alert-using-severity-level.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 **Per creare un avviso in base a un evento WMI**  
  
-   [SQL Server Management Studio](create-a-wmi-event-alert.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)  
  
 **Per definire la risposta a un avviso**  
  
-   [SQL Server Management Studio](../sql-server-management-studio-ssms.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
 **Per creare un messaggio di errore relativo a un evento definito dall'utente**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-addmessage-transact-sql)  
  
 **Per modificare un messaggio di errore relativo a un evento definito dall'utente**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
 **Per eliminare un messaggio di errore relativo a un evento definito dall'utente**  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-dropmessage-transact-sql)  
  
 **Per disabilitare o riattivare un avviso**  
  
-   [SQL Server Management Studio](disable-or-reactivate-an-alert.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-update-alert-transact-sql)  
  
## <a name="see-also"></a>Vedere anche  
 [Usare oggetti di SQL Server](../../relational-databases/performance-monitor/use-sql-server-objects.md)  
  
  
