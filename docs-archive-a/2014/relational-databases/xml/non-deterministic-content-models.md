---
title: Modelli di contenuto non deterministici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712831"
---
# <a name="non-deterministic-content-models"></a>modelli di contenuto non deterministici
  Prima di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), gli elementi XML Schema che contenevano modelli di contenuto non deterministici venivano rifiutati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, i modelli di contenuto non deterministici vengono accettati se i vincoli di occorrenza sono 0, 1 o senza vincoli.  
  
## <a name="example-non-deterministic-content-model-rejected"></a>Esempio: modello di contenuto non deterministico rifiutato  
 Nello schema dell'esempio viene illustrato il tentativo di creare un elemento XML Schema con un modello di contenuto non deterministico. Il codice ha esito negativo poiché non è possibile determinare se l'elemento `<root>` debba avere una sequenza di due elementi `<a>` oppure se l'elemento `<root>` debba averne due, ognuna con un elemento `<a>` .  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 È possibile correggere lo schema spostando il vincolo di occorrenza in una posizione univoca, ad esempio, il vincolo può essere spostato nella particella contenente la sequenza:  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 In alternativa, il vincolo può essere spostato sull'elemento contenuto:  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a>Esempio: modello di contenuto non deterministico accettato  
 Lo schema seguente verrebbe rifiutato nelle versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Requisiti e limitazioni per le raccolte di XML Schema nel server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
