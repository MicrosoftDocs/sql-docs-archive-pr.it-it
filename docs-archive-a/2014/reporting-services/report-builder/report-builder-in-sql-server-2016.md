---
title: Generatore report SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10428"
helpviewer_keywords:
- overview of Report Builder
- getting started
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b2fb8994272eb24594239551d623021f7b87694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625194"
---
# <a name="report-builder-in-sql-server-2014"></a>Generatore report in SQL Server 2014
  Generatore report è un ambiente per la creazione di report destinato a utenti aziendali che preferiscono lavorare nell'ambiente [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office. Quando si progetta un report, si specifica dove ottenere i dati, quali dati ottenere e come visualizzarli. Quando si esegue il report, Elaborazione report utilizza tutte le informazioni specificate, recupera i dati e li combina con il layout per generare il report. È possibile visualizzare l'anteprima dei report in Generatore report oppure pubblicare un report in un server di report o in un server di report in modalità integrata SharePoint dove potrà essere eseguito da altri utenti.  
  
 Nel report riportato in questa illustrazione viene illustrata una matrice con gruppi di righe e colonne, grafici sparkline, indicatori e un grafico a torta riepilogativo nella cella d'angolo, accompagnata da una mappa con due set di dati geografici rappresentati da colore e dimensioni del cerchio.  
  
 ![rs_GettingStartedReport](../media/rs-gettingstartedreport.gif "rs_GettingStartedReport")  
  
##  <a name="jump-start-report-creation"></a><a name="JumpStartReptCreation"></a>Avvio della creazione del report  
  
-   **Avviare il report withreport le parti** create da un altro utente del team. Le parti di report sono elementi di report che sono stati pubblicati separatamente in un server di report o in un sito di SharePoint integrato con un server di report e possono essere riutilizzati in altri report. È possibile pubblicare elementi di report quali tabelle, matrici, grafici e immagini come parti di report.  
  
-   **Iniziare con un set di dati condiviso** creato da un altro utente del team. I set di dati condivisi sono query basate su un'origine dati condivisa che vengono salvate in un server di report o in un sito di SharePoint integrato con un server di report.  
  
-   **Iniziare con la Creazione guidata tabella, matrice o grafico**. Scegliere una connessione all'origine dati, trascinare campi per creare una query del set dei dati, selezionare un layout e uno stile e personalizzare il report.  
  
-   **Iniziare con la Creazione guidata mappa** per creare report che consentono di visualizzare dati aggregati su uno sfondo geografico o geometrico. I dati di una mappa possono essere dati spaziali di una query [!INCLUDE[tsql](../../includes/tsql-md.md)] o di un file di forma ESRI (Environmental Systems Research Institute, Inc.) . È inoltre possibile aggiungere un sfondo a tessera mappa di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Bing.  
  

  
##  <a name="design-your-report"></a><a name="DesignRept"></a>Progettare il report  
  
-   **Creare report con tabelle, matrici, grafici e layout in formato libero.** È possibile creare report tabella per i dati basati su colonne, report matrice (ad esempio report a campi incrociati o Tabella pivot) per i dati riepilogati, report grafico per i dati grafici e report in formato libero per qualsiasi altra esigenza. Nei report è possibile incorporare altri report e grafici, insieme a elenchi, grafica e controlli per applicazioni basate sul Web dinamiche.  
  
-   **Report da un'ampia gamma di origini dati.** Compilare report utilizzando dati da qualsiasi tipo di origine dati che disponga di un [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provider di dati gestito da, un provider OLE DB o un'origine dati ODBC. È possibile creare report che utilizzano dati relazionali e multidimensionali da database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], Oracle, Hyperion e così via. È inoltre possibile utilizzare un'estensione per l'elaborazione dei dati XML per recuperare dati da qualsiasi origine dei dati XML. Per progettare origini dati personalizzate, è possibile utilizzare funzioni con valori di tabella.  
  
-   **Modificare report esistenti.** Utilizzando Generatore report, è possibile personalizzare e aggiornare i report creati in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] Progettazione report.  
  
-   **Modificare i dati** filtrando, raggruppando e ordinando i dati oppure aggiungendo formule o espressioni.  
  
-   **Aggiungere grafici, misuratori, grafici sparkline e indicatori** per riepilogare i dati in un formato visivo e presentare in modo immediato volumi elevati di informazioni aggregate.  
  
-   **Aggiungere funzioni interattive** quali mappe documento, pulsanti Mostra/Nascondi e collegamenti drill-through a sottoreport e a report drill-through. Usare parametri e filtri per filtrare i dati per ottenere visualizzazioni personalizzate.  
  
-   **Incorporare o fare riferimento a immagini** e ad altre risorse, inclusi contenuti esterni.  
  

  
##  <a name="manage-your-report"></a><a name="ManageRpt"></a>Gestione del report  
  
-   **Salvare la definizione del report** nel computer in uso o nel server di report. Qui è possibile gestire la definizione e condividerla con altri utenti.  
  
-   **Scegliere un formato di presentazione** quando si apre il report o dopo averlo aperto. È possibile selezionare formati orientati al Web, di pagina o per applicazioni desktop. I formati disponibili includono HTML, MHTML, PDF, XML, CSV, TIFF, Word ed Excel.  
  
-   **Configurare sottoscrizioni.** Dopo aver pubblicato il report nel server di report o in un server di report in modalità integrata SharePoint, è possibile configurare il report in modo che venga eseguito a un'ora specifica, creare una cronologia del report e impostare sottoscrizioni per il recapito tramite posta elettronica.  
  
-   **Generare feed di dati** dal report tramite l'estensione per il rendering Atom di Reporting Services.  
  
> [!NOTE]  
>  I report pubblicati sono gestiti in un server di report o in server di report in modalità integrata SharePoint da un amministratore del server di report. Gli amministratori del server di report possono definire la sicurezza, impostare le proprietà e pianificare le operazioni, ad esempio la cronologia dei report e il recapito dei report tramite posta elettronica. Possono inoltre creare pianificazioni e origini dei dati condivise per renderle disponibili per l'utilizzo da parte di tutti gli utenti. Gli amministratori gestiscono inoltre tutte le cartelle del server di report. La capacità di eseguire le operazioni di gestione dipende dalle autorizzazioni dell'utente.  
  

  
##  <a name="in-this-section"></a><a name="InThisSection"></a> Contenuto della sezione  
 [Novità di Generatore report per SQL Server 2014](../what-s-new-in-report-builder-for-sql-server-2014.md)  
 Vengono illustrate le nuove caratteristiche disponibili in questa versione di Generatore report, incluse le mappe.  
  
 [Esercitazione: Creazione di un report grafico rapido offline](tutorial-create-a-quick-chart-report-offline-report-builder.md)  
 Vengono fornite informazioni preliminari su Generatore report e sulle procedure guidate disponibili per la creazione di report. Viene inoltre fornito un set di dati iniziale da utilizzare per evitare di connettersi a un'origine dati.  
  
 [Pianificazione di un report &#40;Generatore report&#41;](../report-design/planning-a-report-report-builder.md)  
 Vengono fornite informazioni sugli aspetti che è necessario considerare prima di iniziare a compilare il report.  
  
 [Concetti relativi alla creazione di report &#40;Generatore report e SSRS&#41;](../report-design/report-authoring-concepts-report-builder-and-ssrs.md)  
 Vengono definiti i concetti principali utilizzati in tutta la documentazione relativa a Generatore report.  
  
 [Visualizzazione di progettazione report &#40;Generatore report&#41;](report-design-view-report-builder.md)  
 Vengono illustrati i diversi riquadri e le diverse aree della visualizzazione di progettazione report.  
  
 [Visualizzazione di progettazione set di dati condivisi &#40;Generatore report&#41;](shared-dataset-design-view-report-builder.md)  
 Vengono illustrati i diversi riquadri e le diverse aree della visualizzazione di progettazione del set di dati condiviso.  
  
 [Tasti di scelta rapida &#40;Generatore report&#41;](keyboard-shortcuts-report-builder.md)  
 Vengono descritti i tasti di scelta rapida disponibili per la navigazione e la progettazione di report in Generatore report.  
  
 [Avvia Generatore report &#40;Generatore report&#41;](start-report-builder.md)  
 Viene illustrato come avviare le due diverse versioni di Generatore report, ovvero la versione autonoma e [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)].  
  
  
