---
title: Modifiche al comportamento della lunghezza della stringa e della sottostringa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 2119b7ba-2e52-44bf-ac57-82c2d46a48ff
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 1188823a877b4c5dc9cef13431492dfe3b303e23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628221"
---
# <a name="changes-to-behavior-of-string-length-and-substring"></a>Modifiche al comportamento di sottostringa e lunghezza stringa
  La [funzione String-length &#40;&#41;XQuery](/sql/xquery/functions-on-string-values-string-length) e la [funzione SUBSTRING &#40;le funzioni&#41;XQuery](/sql/xquery/functions-on-string-values-substring) possono restituire risultati diversi se utilizzate con database XML che contengono caratteri surrogati.  
  
## <a name="description"></a>Descrizione  
 Quando un database è impostato per essere compatibile con [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , il comportamento della [funzione di lunghezza stringa &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-string-length) e la [funzione substring &#40;XQuery&#41;](/sql/xquery/functions-on-string-values-substring) funzioni cambiano quando si gestiscono caratteri supplementari Unicode. Ogni carattere supplementare Unicode, definito mediante un punto di codice maggiore di U+FFFF, viene contato come un carattere anziché due da queste funzioni, come nelle versioni precedenti.  
  
 Per ulteriori informazioni sui caratteri surrogati, vedere [surrogati e caratteri supplementari](https://go.microsoft.com/fwlink/?LinkId=178317).  
  
## <a name="see-also"></a>Vedere anche  
 [Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md)   
 [SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;](https://docs.microsoft.com/sql/sql-server/install/sql-server-2014-upgrade-advisor)  
  
  
