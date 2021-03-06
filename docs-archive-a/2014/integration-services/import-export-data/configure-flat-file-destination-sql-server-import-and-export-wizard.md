---
title: Configurazione destinazione file flat (Importazione/Esportazione guidata SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.configureflatfiledest.f1
ms.assetid: 318e8da0-37d3-46cd-943a-fc5d66aad93a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2af8a1653d9a1aef0828aa112a25825ed23b8bf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635151"
---
# <a name="configure-flat-file-destination-sql-server-import-and-export-wizard"></a>Configurazione destinazione file flat (Importazione/Esportazione guidata SQL Server)
  Utilizzare la pagina **Configura destinazione file flat** per specificare le opzioni di formattazione per il file flat di destinazione e per visualizzare l'anteprima dei risultati prima di continuare.  
  
 Per ulteriori informazioni su questa procedura guidata, vedere [SQL Server importazione/esportazione guidata](import-and-export-data-with-the-sql-server-import-and-export-wizard.md). Per informazioni sulle opzioni di avvio della procedura guidata, nonché sulle autorizzazioni necessarie per eseguire la procedura guidata, vedere [eseguire l'importazione/esportazione guidata SQL Server](start-the-sql-server-import-and-export-wizard.md).  
  
 Lo scopo di Importazione/Esportazione guidata SQL Server è la copia di dati da un'origine a una destinazione. La procedura guidata può inoltre creare automaticamente un database di destinazione e le tabelle di destinazione. Se tuttavia è necessario copiare più database o tabelle, o altri tipi di oggetti di database, è preferibile utilizzare Copia guidata database. Per altre informazioni, vedere [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).  
  
## <a name="options"></a>Opzioni  
 **File flat di origine**  
 Nome del file di destinazione.  
  
 **Delimitatore di riga**  
 Consente di selezionare un delimitatore di riga nell'elenco.  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|**{CR}{LF}**|La riga è delimitata dalla combinazione di caratteri ritorno a capo/avanzamento riga.|  
|**{CR}**|La riga è delimitata da un ritorno a capo.|  
|**{LF}**|La riga è delimitata da un avanzamento riga.|  
|**Punto e virgola {;}**|La riga è delimitata da un punto e virgola.|  
|**Due punti {:}**|La riga è delimitata da due punti.|  
|**Virgola {,}**|La riga è delimitata da una virgola.|  
|**Tabulazione {t}**|La riga è delimitata da una tabulazione.|  
|**Barra verticale {&#124;}**|La riga è delimitata da una barra verticale.|  
  
 **Delimitatore di colonna**  
 Consente di selezionare un delimitatore di colonna nell'elenco.  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|**{CR}{LF}**|Le colonne sono delimitate dalla combinazione di caratteri ritorno a capo/avanzamento riga.|  
|**{CR}**|Le colonne sono delimitate da un ritorno a capo.|  
|**{LF}**|Le colonne sono delimitate da un avanzamento riga.|  
|**Punto e virgola {;}**|Le colonne sono delimitate da un punto e virgola.|  
|**Due punti {:}**|Le colonne sono delimitate da due punti.|  
|**Virgola {,}**|Le colonne sono delimitate da una virgola.|  
|**Tabulazione {t}**|Le colonne sono delimitate da una tabulazione.|  
|**Barra verticale {&#124;}**|Le colonne sono delimitate da una barra verticale.|  
  
 **Anteprima**  
 Visualizzazione nella finestra di dialogo **Anteprima dati** i risultati delle opzioni di formattazione selezionate per il file flat di destinazione.  
  
 **Modifica trasformazione**  
 Eliminare righe, accodare righe e configurare le colonne nel file di destinazione utilizzando la finestra di dialogo **Mapping colonne** .  
  
  
