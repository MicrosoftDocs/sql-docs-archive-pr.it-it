---
title: Tipo xs:QName | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xs:QName type
ms.assetid: 72c5bfde-b0b2-4372-bf36-97ba930dea06
author: rothja
ms.author: jroth
ms.openlocfilehash: 79aaf992243e665738f97c7ee1858528d6fb867c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719734"
---
# <a name="the-xsqname-type"></a>Xs:Tipo QName
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non supporta tipi derivati da **xs:QName** a causa dell'utilizzo di un elemento di restrizione di XML Schema. Attualmente, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non supporta tipi unione con **QName** come tipo di membro.  
  
## <a name="example"></a>Esempio  
 Le seguenti istruzioni `CREATE XML SCHEMA COLLECTION` non permettono di caricare l'elemento XML Schema, in quanto specificano il tipo `xs:QName` come tipo di membro dell'unione:  
  
```  
CREATE XML SCHEMA COLLECTION QNameLimitation1 AS N'  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="myUnion">  
        <xs:union memberTypes="xs:int xs:QName"/>  
    </xs:simpleType>  
</xs:schema>'  
GO  
  
CREATE XML SCHEMA COLLECTION QNameLimitation2 AS N'  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="myUnion">  
        <xs:union memberTypes="xs:integer">  
   <xs:simpleType>  
    <xs:list itemType="xs:QName"/>  
   </xs:simpleType>  
  </xs:union>  
    </xs:simpleType>  
</xs:schema>'  
GO  
```  
  
 Entrambe le istruzioni hanno esito negativo e generano un errore.  
  
## <a name="see-also"></a>Vedere anche  
 [Requisiti e limitazioni per le raccolte di XML Schema nel server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
