---
title: Riferimento all'interfaccia utente della finestra di dialogo Esporta pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727079"
---
# <a name="export-package-dialog-box-ui-reference"></a>Riferimento all'interfaccia utente della finestra di dialogo Esporta pacchetto
  Usare la finestra di dialogo **Esporta pacchetto** disponibile in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]per esportare un pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in un percorso diverso ed eventualmente modificare il livello di protezione del pacchetto.  
  
## <a name="options"></a>Opzioni  
 **Posizione pacchetto**  
 Consente di selezionare il tipo di archiviazione in cui esportare il pacchetto. Sono disponibili le opzioni seguenti:  
  
 **SQL Server**  
  
 **File system**  
  
 **Archivio pacchetti SSIS**  
  
 **Server**  
 Consente di digitare il nome del server o di selezionarlo nell'elenco.  
  
 **autenticazione**  
 Consente di selezionare l'autenticazione di Windows o l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] . Questa opzione è disponibile solo se è stato selezionato il percorso di archiviazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
> [!IMPORTANT]  
>  Se possibile, è consigliabile utilizzare l'autenticazione di Windows.  
  
 **Tipo di autenticazione**  
 Consente di selezionare un tipo di autenticazione.  
  
 **Nome utente**  
 Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente.  
  
 **Password**  
 Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare una password.  
  
 **Percorso pacchetto**  
 Digitare il percorso del pacchetto oppure fare clic sul pulsante Sfoglia **(...)** e individuare la cartella in cui archiviare il pacchetto.  
  
 **Livello di protezione**  
 Fare clic sul pulsante Sfoglia **(...)** e aggiornare il livello di protezione nella finestra di dialogo **Livello di protezione pacchetto**. Per altre informazioni, vedere [Finestra di dialogo Livello di protezione pacchetto e Livello di protezione del progetto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Salva copia del pacchetto](../../2014/integration-services/save-copy-of-package.md)   
 [Riferimento all'interfaccia utente della finestra di dialogo Importa pacchetto](../../2014/integration-services/import-package-dialog-box-ui-reference.md)   
 [Salva pacchetti](save-packages.md)   
 [Importare ed esportare pacchetti &#40;servizio SSIS&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
