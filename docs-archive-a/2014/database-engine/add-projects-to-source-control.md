---
title: Aggiungere progetti al controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- adding projects
- projects [SQL Server Management Studio], adding
ms.assetid: fd4616b2-a564-4a66-ac53-d1f5cba213c2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0afef4ef91e4d80db7e956d03a95a2ecffe1dc4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625549"
---
# <a name="add-projects-to-source-control"></a>Aggiungere progetti al controllo del codice sorgente
  Nelle soluzioni di [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] possono essere ospitati più progetti. L'inclusione o meno della soluzione alla quale appartiene un progetto nel controllo del codice sorgente determina il modo in cui il progetto stesso viene aggiunto al controllo. Se si archivia una soluzione inclusa nel controllo del codice sorgente, il progetto verrà aggiunto automaticamente al controllo. Per ulteriori informazioni sull'archiviazione di soluzioni, vedere [archiviare i file](../../2014/database-engine/check-in-files.md).  
  
 Se la soluzione alla quale appartiene il progetto non è inclusa nel controllo del codice sorgente, è possibile aggiungere tale soluzione al controllo in modo che tutti i progetti della soluzione vengano aggiunti automaticamente. Per ulteriori informazioni sull'aggiunta di soluzioni al controllo del codice sorgente, vedere [aggiungere soluzioni al controllo del codice sorgente](../../2014/database-engine/add-solutions-to-source-control.md).  
  
 Se non si desidera aggiungere la soluzione al controllo del codice sorgente, è possibile utilizzare il comando **Aggiungi selezione al controllo del codice sorgente** per aggiungere manualmente il progetto.  
  
 Gli oggetti di database non vengono protetti direttamente dal provider del controllo del codice sorgente. È tuttavia possibile creare script relativi agli oggetti di database e salvarli includendoli nel controllo del codice sorgente.  
  
### <a name="to-add-a-project-to-source-control"></a>Per aggiungere un progetto al controllo del codice sorgente  
  
1.  In Esplora soluzioni selezionare il progetto desiderato.  
  
2.  Scegliere **controllo del codice sorgente**dal menu **file** , quindi fare clic su **Aggiungi progetti selezionati al controllo del codice sorgente**.  
  
    > [!NOTE]  
    >  Se si utilizza il comando **Aggiungi progetti selezionati al controllo del codice sorgente** per aggiungere un progetto che appartiene a una soluzione controllata dal codice sorgente, viene richiesto se si desidera aggiungere il progetto come sottocartella della soluzione controllata dal codice sorgente o aggiungere il progetto come cartella separata.  
  
3.  Se richiesto, eseguire l'accesso al provider del controllo del codice sorgente.  
  
4.  Verrà visualizzata la finestra **di dialogo Aggiungi a progetto SourceSafe** . Il nome del progetto viene visualizzato nella casella **progetto** .  
  
5.  Nell'elenco **cartelle** aprire la cartella in cui si vuole inserire il progetto. In alternativa, è possibile fare clic su **Crea** per creare una cartella con il nome visualizzato nella casella **progetto** .  
  
## <a name="see-also"></a>Vedere anche  
 [Aggiungere soluzioni e progetti al controllo del codice sorgente](../../2014/database-engine/add-solutions-and-projects-to-source-control.md)  
  
  
