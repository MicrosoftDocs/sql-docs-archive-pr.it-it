---
title: Attività di download di BLOB di Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713395"
---
# <a name="azure-blob-download-task"></a>Attività di download di BLOB di Azure
  L'attività di download di BLOB di Azure consente a un pacchetto di SSIS di scaricare file da un archivio BLOB di Azure.   
Per aggiungere un' **attività di download di BLOB di Azure**, trascinare l'attività in Progettazione SSIS e farvi doppio clic oppure clic con il pulsante destro del mouse, quindi scegliere **Modifica** per visualizzare la finestra di dialogo seguente relativa all' **editor dell'attività di download di BLOB di Azure** .  
  
 La tabella seguente fornisce una descrizione dei campi della finestra di dialogo.  
  
|||  
|-|-|  
|**Campo**|**Descrizione**|  
|AzureStorageConnection|Consente di specificare un'istanza esistente di Gestione connessioni dell'archiviazione di Azure o di creare una nuova istanza che fa riferimento a un account di archiviazione di Azure che indica la posizione in cui sono ospitati i file BLOB.|  
|BlobContainer|Consente di specificare il nome del contenitore BLOB che include i file BLOB da scaricare.|  
|BlobDirectory|Consente di specificare il nome della directory BLOB che include i file BLOB da scaricare. La directory BLOB è una struttura gerarchica virtuale.|  
|LocalDirectory|Consente di specificare la directory locale in cui verranno archiviati i file BLOB.|  
|FileName|Specifica un filtro per i nomi per la selezione di file con il modello di nomi specificato. ad esempio MySheet*.xls\* include file quali MySheet001.xls e MySheetABC.xlsx.|  
|TimeRangeFrom/TimeRangeTo|Specifica un filtro basato su un intervallo di tempo. Saranno inclusi i file modificati dopo **TimeRangeFrom** e prima di **TimeRangeTo** .|  
  
  
