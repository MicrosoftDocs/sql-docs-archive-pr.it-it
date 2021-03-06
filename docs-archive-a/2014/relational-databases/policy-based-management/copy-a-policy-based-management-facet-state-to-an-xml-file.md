---
title: Copiare lo stato di un facet della gestione basata su criteri in un file XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715199"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a>Copiare lo stato di un facet della gestione basata su criteri in un file XML
  In questo argomento verrà descritto come copiare lo stato di un facet della gestione basata su criteri in un file XML in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
 **Contenuto dell'articolo**  
  
-   **Prima di iniziare:**  
  
     [Sicurezza](#Security)  
  
-   **Per copiare lo stato di un facet in un file XML tramite:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Prima di iniziare  
  
###  <a name="security"></a><a name="Security"></a> Sicurezza  
  
####  <a name="permissions"></a><a name="Permissions"></a> Autorizzazioni  
 Le procedure descritte in questo argomento richiedono l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Utilizzo di SQL Server Management Studio  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a>Per copiare lo stato di un facet in un file XML  
  
1.  In Esplora oggetti fare clic con il pulsante destro del mouse su un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], su un oggetto istanza, su un database o su un oggetto di database, quindi scegliere **Facet**.  
  
2.  Nella finestra di dialogo **Visualizza facet -**_nome_oggetto_ fare clic su **Esporta stato corrente come criteri**.  
  
3.  Nella finestra di dialogo **Esporta come criterio** digitare il percorso e il nome del file oppure usare il pulsante Sfoglia (**...**) per trovare il file, quindi digitare il nome del file XML. Per ulteriori informazioni sulle opzioni disponibili in questa finestra di dialogo, vedere [Export As Policy Dialog Box](export-as-policy-dialog-box.md).  
  
4.  Al termine, fare clic su **OK**.  
  
  
