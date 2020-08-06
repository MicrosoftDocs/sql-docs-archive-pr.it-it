---
title: Connettersi a un file di Microsoft Excel (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connexcelfile.f1
ms.assetid: 126f7d6b-d270-40e7-b23e-8d114f87065b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 79bb3d57470be8acbbb990dde71cf21b62b3cb2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625726"
---
# <a name="connect-to-a-microsoft-excel-file-ssas"></a>Connessione a un file di Microsoft Excel (SSAS)
  Questa pagina dell' **Importazione guidata tabella** consente di connettersi a un file di Microsoft Excel archiviato nel computer locale. Per accedere alla procedura guidata da [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dal menu **Modello** selezionare **Importa da origine dati**.  
  
 Per connettersi a un file di Microsoft Excel, è necessario che nel computer sia installato il provider ACE appropriato. Per altre informazioni, vedere [Origini dati supportate &#40;SSAS tabulare&#41;](tabular-models/data-sources-supported-ssas-tabular.md).  
  
> [!NOTE]  
>  Le credenziali dell'utente corrente vengono utilizzate in caso di selezione di un file in questa pagina. Tuttavia, l'importazione non verrà completata se l'utente specificato nella pagina Impostazioni di rappresentazione non dispone di privilegi sufficienti per leggere dal file selezionato.  
  
## <a name="ui-element-list"></a>Elenco di elementi dell'interfaccia utente  
 **Nome descrittivo connessione**  
 Digitare un nome univoco per questa connessione all'origine dati. Questo campo è obbligatorio.  
  
 **Percorso file di Excel**  
 Specificare il percorso completo del file di Excel.  
  
 **Sfoglia**  
 Passare al percorso in cui è disponibile un file di Excel.  
  
 **Funzionalità avanzate**  
 Impostare altre proprietà relative alla connessione tramite la finestra di dialogo **Impostazione delle proprietà avanzate** .  
  
 **Utilizza la prima riga per le intestazioni di colonna**  
 Specificare se utilizzare la prima riga di dati per le intestazioni di colonna della tabella di destinazione.  
  
 **Test connessione**  
 Provare a stabilire una connessione all'origine dati utilizzando le impostazioni correnti. Viene visualizzato un messaggio che indica se la connessione è stata stabilita.  
  
  
