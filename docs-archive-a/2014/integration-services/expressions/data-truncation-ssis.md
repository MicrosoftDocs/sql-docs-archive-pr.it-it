---
title: Troncamento dei dati (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- truncating data
- data truncation [Integration Services]
- expressions [Integration Services], data truncation
- truncate options [Integration Services]
ms.assetid: 02461e15-49ca-445b-abb3-5c369c283ec2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e0c4280c9eacd22ebf84bf1570d485de51cab09b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637439"
---
# <a name="data-truncation-ssis"></a>Troncamento dei dati (SSIS)
  Un'espressione può causare il troncamento accidentale dei dati. Il troncamento può verificarsi nelle circostanze seguenti:  
  
-   Stringhe. Se ad esempio si convertono dati stringa con tipo di dati DT_WSTR in una stringa della stessa lunghezza in caratteri, ma con tipo di dati DT_STR e la stringa originale contiene caratteri DBCS (Double-Byte Character Set), si verificherà una perdita di dati.  
  
-   Cifre significative. Questo tipo di troncamento si verifica ad esempio quando si esegue il cast di un valore integer dal tipo di dati DT_I4 al tipo di dati DT_I2 oppure da un intero senza segno a un intero con segno.  
  
-   Cifre non significative. Questo tipo di troncamento si verifica ad esempio quando si esegue il cast di un numero reale dal tipo di dati DT_R8 al tipo di dati DT_R4 oppure di un valore integer dal tipo di dati DT_I4 al tipo di dati DT_R4.  
  
 L'analizzatore di espressioni identifica i cast espliciti che possono causare troncamenti e genera un avviso durante l'analisi dell'espressione. L'analizzatore di espressioni genera un avviso ad esempio quando viene eseguito il cast di una stringa di 30 caratteri in una stringa di 20 caratteri.  
  
> [!NOTE]  
>  In fase di esecuzione il troncamento non viene verificato e i dati vengono troncati senza generare avvisi. La maggior parte degli adattatori e delle trasformazioni supporta tuttavia output degli errori in grado di gestire la disposizione delle righe con errori. Per ulteriori informazioni sulla gestione del troncamento dei dati, vedere [gestione degli errori nei dati](../data-flow/error-handling-in-data.md).  
  
  
