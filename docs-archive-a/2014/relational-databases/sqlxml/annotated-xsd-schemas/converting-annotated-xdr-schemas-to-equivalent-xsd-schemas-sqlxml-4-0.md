---
title: Conversione di schemi XDR con annotazioni in schemi XSD equivalenti (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XDR schemas, converting schemas
- annotated XSD schemas, converting schemas
- XDR to XSD Converter tool [SQLXML]
- XDR schemas [SQLXML], converting
- converting annotated schemas
- mapping schema [SQLXML], conversions
- XSD schemas [SQLXML], converting schemas
ms.assetid: 151c94a8-66d3-4c46-a5ff-a22df456940a
author: rothja
ms.author: jroth
ms.openlocfilehash: c36eb17aacb61a47fad0f389de9a3c216202827d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634938"
---
# <a name="converting-annotated-xdr-schemas-to-equivalent-xsd-schemas-sqlxml-40"></a>Conversione di schemi XDR con annotazioni in schemi XSD equivalenti (SQLXML 4.0)
  Il linguaggio XSD (XML Schema Definition) è il successore del linguaggio XDR (XML-Data Reduced). Con l'introduzione del supporto XSD in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, si presuppone che i nuovi schemi con annotazioni vengano creati utilizzando XSD. SQLXML 4.0 include un convertitore da XDR a XSD progettato per consentire la conversione di schemi XDR con annotazioni in schemi XSD equivalenti.  
  
> [!IMPORTANT]  
>  Dal momento che non si tratta di un convertitore da XDR a XSD universale, è possibile utilizzarlo solo quando si desidera convertire in XSD schemi XDR con annotazioni per l'utilizzo con SQLXML 4.0. Quando vengono utilizzati in altri ambienti, gli schemi XSD convertiti potrebbero non comportarsi come gli schemi XDR originali.  
  
 Se il file XDR di input specifica la codifica all'interno della dichiarazione XML, questa diventa la codifica del file XSD di output generato.  
  
 Il convertitore (Cvtschema.exe) viene installato nella cartella Programmi\SQLXML 4.0\bin ed eseguito nel prompt dei comandi.  
  
 La sintassi generale è la seguente:  
  
```  
cvtschema XDRFileName, [-y], [-w] [-?]  
```  
  
 Dove:  
  
 XDRFileName  
 È il nome del file XDR  da convertire in XSD. Lo strumento legge il file XDR di input e crea un file di output XSD nella directory di lavoro corrente. Se l'estensione del file di input è .xdr o .xml, il file XSD di output viene creato con lo stesso nome ma con estensione .xsd. Se l'estensione del file di input è diversa da .xml o .xdr (o se manca), il file di output viene creato con lo stesso nome del file di input al quale viene aggiunta l'estensione .xsd. Se ad esempio il nome del file XDR di input è SampleFile.abc, il file XSD risultante viene salvato come SampleFile.abc.xsd.  
  
 -y  
 (Facoltativo) Sovrascrive il file XSD esistente con il file XSD generato dal convertitore. Se non viene specificato il flag, il convertitore richiede di specificare se si desidera sovrascrivere il file XSD esistente e offre l'opportunità di modificare il nome del file di output.  
  
 -w  
 (Facoltativo) Restituisce avvisi non irreversibili generati nel processo di conversione dallo strumento. Per impostazione predefinita, lo strumento visualizza messaggi solo per gli errori irreversibili.  
  
 -?  
 Restituisce un elenco di opzioni che è possibile specificare con `cvtschema`, insieme a una spiegazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Mapping dei tipi di dati XSD ai tipi di dati XPath &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)   
 [Annotazioni XSD &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/xsd-annotations-sqlxml-4-0.md)  
  
  
