---
title: Editor origine file flat (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.columns.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: b5af5f65-c087-44fd-b5ae-d0441245fef2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9b0249b2b17d50fdef4b5cf4aff70a1318614257
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624853"
---
# <a name="flat-file-source-editor-columns-page"></a>Editor origine file flat (pagina Colonne)
  Usare il nodo **Colonne** della finestra di dialogo **Editor origine file flat** per eseguire il mapping tra una colonna di output e ogni colonna esterna (di origine).  
  
> [!NOTE]  
>  La `FileNameColumnName` proprietà dell'origine file flat e la `FastParse` proprietà delle colonne di output non sono disponibili nell' **Editor origine file flat**, ma possono essere impostate tramite il **Editor avanzato**. Per ulteriori informazioni su queste proprietà, vedere la sezione relativa all'origine file flat in [Flat File Custom Properties](data-flow/flat-file-custom-properties.md).  
  
 Per ulteriori informazioni sull'origine file flat, vedere [Flat File Source](data-flow/flat-file-source.md).  
  
## <a name="options"></a>Opzioni  
 **Colonne esterne disponibili**  
 Consente di visualizzare l'elenco delle colonne esterne disponibili nell'origine dei dati. Non è possibile utilizzare questa tabella per l'aggiunta o l'eliminazione di colonne.  
  
 **Colonna esterna**  
 Consente di visualizzare le colonne esterne (origine) nell'ordine in cui verranno lette dall'attività. È possibile modificare l'ordine deselezionando innanzitutto le colonne della tabella selezionate e quindi selezionando dall'elenco le colonne esterne in un ordine diverso.  
  
 **Colonna di output**  
 Consente di specificare un nome univoco per ogni colonna di output. Per impostazione predefinita viene suggerito il nome della colonna esterna (di origine) selezionata. È comunque possibile scegliere qualsiasi nome descrittivo univoco. Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Editor origine file flat &#40;pagina Gestione connessione&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md)   
 [Editor origine file flat &#40;pagina output degli errori&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md)   
 [Gestione connessione file flat](connection-manager/file-connection-manager.md)  
  
  
