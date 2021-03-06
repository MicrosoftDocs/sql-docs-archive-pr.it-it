---
title: Finestra di comando
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Command Window [Transact-SQL]
ms.assetid: e567ebf9-0793-451b-92c7-26193a02d9da
author: rothja
ms.author: jroth
ms.openlocfilehash: c766ed5408de96b6a2305ce377f9031947618a7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636663"
---
# <a name="command-window"></a>Finestra di comando
  Usare la funzionalità **Finestra di comando** per eseguire comandi, ad esempio i comandi debug o di modifica, sul codice incluso nella finestra dell'editor di query del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] di cui è in corso il debug. Per usare la funzionalità **Finestra di comando**, è necessario usare la modalità di debug. Il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] supporta molti dei comandi supportati anche nella finestra **Comando** di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Per altre informazioni, vedere [Visual Studio Command Window](https://go.microsoft.com/fwlink/?LinkId=112007)(Finestra di comando di Visual Studio).  
  
## <a name="task-list"></a>Elenco attività  
 **Per accedere alla funzionalità Finestra di comando**  
  
-   Scegliere **Avvia debug** dal menu **Debug**.  
  
 **Per stampare il valore di una variabile**  
  
-   In **finestra**digitare **debug. Print \<VariableName> **, quindi premere INVIO.  
  
 **Per elencare le informazioni sul thread corrente**  
  
-   In **finestra**Digitare `Debug.ListThread` e quindi premere INVIO.  
  
 **Per aggiungere una variabile alla finestra Controllo immediato**  
  
-   In **finestra**digitare **debug. controllo immediato \<VariableName> **, quindi premere INVIO.  
  
## <a name="see-also"></a>Vedere anche  
 [Debugger Transact-SQL](transact-sql-debugger.md)  
