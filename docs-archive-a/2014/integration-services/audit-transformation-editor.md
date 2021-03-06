---
title: Editor trasformazione controllo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724056"
---
# <a name="audit-transformation-editor"></a>Editor trasformazione Controllo
  La trasformazione Controllo consente di includere nel flusso di dati di un pacchetto informazioni sull'ambiente in cui viene eseguito il pacchetto. Ad esempio, il nome del pacchetto, del computer e dell'operatore può essere aggiunto al flusso di dati. [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] include variabili di sistema che forniscono queste informazioni.  
  
 Per ulteriori informazioni sulla trasformazione Controllo, vedere [Audit Transformation](data-flow/transformations/audit-transformation.md).  
  
## <a name="options"></a>Opzioni  
 **Nome colonna di output**  
 Consente di specificare il nome di una nuova colonna di output che conterrà le informazioni di controllo.  
  
 **Tipo di controllo**  
 Consente di selezionare una variabile di sistema disponibile per visualizzare le informazioni di controllo.  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|**GUID istanza esecuzione**|Consente di specificare il GUID che identifica in modo univoco l'istanza di esecuzione del pacchetto.|  
|**ID pacchetto**|Consente di specificare il GUID che identifica in modo univoco il pacchetto.|  
|**Nome pacchetto**|Consente di specificare il nome del pacchetto.|  
|**ID versione**|Consente di specificare il GUID che identifica in modo univoco la versione del pacchetto.|  
|**Ora di inizio esecuzione**|Consente di specificare l'ora di inizio dell'esecuzione del pacchetto.|  
|**Nome computer**|Consente di specificare il nome del computer sul quale è stato avviato il pacchetto.|  
|**Nome utente**|Consente di specificare il nome dell'account di accesso dell'utente che ha avviato il pacchetto.|  
|**Nome attività**|Consente di specificare il nome dell'attività Flusso di dati a cui è associata la trasformazione Controllo.|  
|**ID attività**|Consente di specificare il GUID che identifica in modo univoco l'attività Flusso di dati a cui è associata la trasformazione Controllo.|  
  
## <a name="see-also"></a>Vedere anche  
 [Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
