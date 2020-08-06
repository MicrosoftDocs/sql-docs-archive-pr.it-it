---
title: Trasformazione Multicast | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multicasttrans.f1
helpviewer_keywords:
- multiple outputs
- Multicast transformation
- datasets [Integration Services], multiple outputs
- multiple transformations
ms.assetid: 32194784-1684-40cd-9f91-1aba4d8360d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7b5c0a38c966c89f426a213f302b45c390b77cfe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727107"
---
# <a name="multicast-transformation"></a>Multicast - trasformazione
  La trasformazione Multicast distribuisce il proprio input a uno o più output. Questa trasformazione è simile alla trasformazione Suddivisione condizionale. Entrambe le trasformazioni dirigono uno stesso input verso più output, ma la trasformazione Multicast dirige tutte le righe verso tutti gli output, mentre la trasformazione Suddivisione condizionale dirige una riga a un singolo output. Per altre informazioni, vedere [Trasformazione Suddivisione condizionale](conditional-split-transformation.md).  
  
 Per configurare la trasformazione Multicast, è necessario aggiungere gli output.  
  
 Tramite la trasformazione Multicast un pacchetto può creare copie logiche dei dati. Questa funzionalità è utile quando il pacchetto deve applicare più set di trasformazioni agli stessi dati. È ad esempio possibile aggregare una copia dei dati e caricare nella relativa destinazione solo le informazioni di riepilogo, mentre un'altra copia dei dati viene estesa con valori di ricerca e colonne derivate prima di caricarla nella relativa destinazione.  
  
 Questa trasformazione include un input e più output. Non supporta un output degli errori.  
  
## <a name="configuration-of-the-multicast-transformation"></a>Configurazione della trasformazione Multicast  
 È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.  
  
 Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Multicast** , vedere [Editor trasformazione Multicast](../../multicast-transformation-editor.md).  
  
 Per informazioni sulle proprietà che è possibile impostare a livello di codice, vedere [Proprietà comuni](../../common-properties.md).  
  
## <a name="related-tasks"></a>Attività correlate  
 Per informazioni su come impostare le proprietà del componente, vedere [Impostazione delle proprietà di un componente del flusso di dati](../set-the-properties-of-a-data-flow-component.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Flusso di dati](../data-flow.md)   
 [Trasformazioni di Integration Services](integration-services-transformations.md)  
  
  
