---
title: Esecuzione e gestione dei pacchetti a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
ms.assetid: 1a08c75e-ce8c-45ee-81bd-32248bbdb2b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0b07b0b98674fa17891dbbcb01ec42934c2a72e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714519"
---
# <a name="running-and-managing-packages-programmatically"></a>Esecuzione e gestione dei pacchetti a livello di programmazione
  Se è necessario gestire ed eseguire pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] all'esterno dell'ambiente di sviluppo, è possibile modificare i pacchetti a livello di programmazione. Questo approccio rende disponibili diverse opzioni:  
  
-   Caricare ed eseguire un pacchetto esistente senza modifiche.  
  
-   Caricare un pacchetto esistente, riconfigurarlo, ad esempio per un'origine dati diversa, ed eseguirlo.  
  
-   Creare un nuovo pacchetto, aggiungere e configurare i componenti oggetto per oggetto e proprietà per proprietà, salvarlo ed eseguirlo.  
  
 È possibile caricare ed eseguire un pacchetto esistente da un'applicazione client scrivendo solo alcune righe di codice.  
  
 In questa sezione viene descritto e illustrato come eseguire un pacchetto esistente a livello di programmazione e come accedere all'output del flusso di dati da altre applicazioni. Come opzione di programmazione avanzata, è possibile creare a livello di programmazione un pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] riga per riga come descritto nell'argomento [Compilazione di pacchetti a livello di programmazione](../building-packages-programmatically/building-packages-programmatically.md).  
  
 In questa sezione vengono inoltre descritte altre attività amministrative che è possibile eseguire a livello di programmazione per gestire pacchetti archiviati, pacchetti in esecuzione e ruoli pacchetto.  
  
## <a name="running-packages-on-the-integration-services-server"></a>Esecuzione di pacchetti nel server Integration Services  
 Quando si distribuiscono pacchetti nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], è possibile eseguirli a livello di codice tramite lo spazio dei nomi <xref:Microsoft.SqlServer.Management.IntegrationServices>. L'assembly Microsoft.SqlServer.Management.IntegrationServices viene compilato con .NET Framework 3.5. Se si compila un'applicazione .NET Framework 4.0, potrebbe essere necessario aggiungere il riferimento all'assembly direttamente nel file di progetto in uso.  
  
 È inoltre possibile utilizzare lo spazio dei nomi per distribuire e gestire progetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nel server [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Per una panoramica dello spazio dei nomi e i frammenti di codice, vedere l'intervento sul blog relativo a [uno sguardo rapido del modello a oggetti gestito del catalogo SSIS](https://techcommunity.microsoft.com/t5/sql-server-integration-services/a-glimpse-of-the-ssis-catalog-managed-object-model/ba-p/387892), su blogs.msdn.com.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Differenze tra l'esecuzione locale e remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md)  
 Vengono descritte le differenze critiche tra l'esecuzione di un pacchetto in locale o nel server.  
  
 [Caricamento ed esecuzione di un pacchetto locale a livello di programmazione](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
 Viene descritto come eseguire un pacchetto esistente da un'applicazione client nel computer locale.  
  
 [Caricamento ed esecuzione di un pacchetto remoto a livello di programmazione](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
 Viene descritto come eseguire un pacchetto esistente da un'applicazione client e assicurarsi che venga eseguito nel server.  
  
 [Caricamento dell'output di un pacchetto locale](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
 Viene descritto come eseguire un pacchetto nel computer locale e caricare l'output del flusso di dati in un'applicazione client utilizzando la destinazione DataReader e lo spazio dei nomi DtsClient.  
  
 [Enumerazione dei pacchetti disponibili a livello di programmazione](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
 Viene descritto come individuare i pacchetti disponibili gestiti dal servizio [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].  
  
 [Gestione di pacchetti e cartelle a livello di programmazione](../run-manage-packages-programmatically/managing-packages-and-folders-programmatically.md)  
 Viene descritto come creare, rinominare ed eliminare pacchetti e cartelle.  
  
 [Gestione dei pacchetti in esecuzione a livello di programmazione](../run-manage-packages-programmatically/managing-running-packages-programmatically.md)  
 Viene descritto come elencare i pacchetti attualmente in esecuzione, esaminarne le proprietà e arrestare un pacchetto in esecuzione.  
  
 [Gestione dei ruoli pacchetto a livello di programmazione &#40;servizio SSIS&#41;](../run-manage-packages-programmatically/managing-package-roles-programmatically-ssis-service.md)  
 Viene descritto come ottenere o impostare informazioni sui ruoli assegnati a un pacchetto o a una cartella.  
  
## <a name="reference"></a>Riferimento  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../integration-services-error-and-message-reference.md)  
 Vengono elencati i codici di errore predefiniti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] con i relativi nomi simbolici e le descrizioni.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Estensione di pacchetti tramite scripting](../extending-packages-scripting/extending-packages-with-scripting.md)  
 Viene descritto come estendere il flusso di controllo utilizzando l'attività Script e come estendere il flusso di dati utilizzando il componente script.  
  
 [Estensione di pacchetti tramite oggetti personalizzati](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
 Viene descritto come creare e programmare attività personalizzate, componenti del flusso di dati e altri oggetti di pacchetto da utilizzare in più pacchetti.  
  
 [Compilazione di pacchetti a livello di programmazione](../building-packages-programmatically/building-packages-programmatically.md)  
 Viene descritto come creare, configurare e salvare pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a livello di programmazione.  
  
![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**<br /> Per i download, gli articoli, gli esempi e i video [!INCLUDE[msCoName](../../includes/msconame-md.md)] più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] su MSDN:<br /><br /> [Visitare la pagina relativa a Integration Services su MSDN](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.  
  
## <a name="see-also"></a>Vedere anche  
 [SQL Server Integration Services](../sql-server-integration-services.md)  
  
  
