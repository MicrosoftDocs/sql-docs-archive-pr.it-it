---
title: Elemento &lt;xsd:redefine&gt; | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719733"
---
# <a name="the-ltxsdredefinegt-element"></a>Elemento &lt;xsd:redefine&gt;
  L'elemento **redefine** dello schema XSD W3C rende disponibile il supporto per la ridefinizione dei componenti di schema. Tuttavia, il supporto per questa direttiva è potenzialmente costoso per le prestazioni e richiede anche che vengano [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rivalide tutte le istanze del `xml` tipo di dati associate allo schema ridefinito. Di conseguenza, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non supporta questo elemento. Gli XML Schema che includono l'elemento **\<xsd:redefine>** vengono rifiutati dal server.  
  
 In alternativa, per aggiornare uno schema o i relativi componenti, è possibile eseguire le operazioni seguenti.  
  
1.  Creare una nuova raccolta XML Schema con i componenti di schema modificati.  
  
2.  Riscrivere tutti i tipi di dati `xml` (XML DT) che usano la raccolta XML Schema da ridefinire per usare in sostituzione la nuova raccolta XML Schema. A questo scopo, utilizzare l'opzione ALTER COLUMN del comando ALTER TABLE per riscrivere colonne o modificare i vincoli della raccolta XML Schema su variabili o parametri.  
  
3.  Eliminare la versione obsoleta della raccolta XML Schema.  
  
## <a name="see-also"></a>Vedere anche  
 [Requisiti e limitazioni per le raccolte di XML Schema nel server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
