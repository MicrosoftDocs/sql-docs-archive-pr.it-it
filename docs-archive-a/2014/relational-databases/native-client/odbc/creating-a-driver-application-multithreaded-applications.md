---
title: Applicazioni multithread | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
author: rothja
ms.author: jroth
ms.openlocfilehash: b680086f76e0c1a1e8c8cfc2f4ef82099957b3fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635512"
---
# <a name="multithreaded-applications"></a>Applicazioni a thread multipli
  Il driver ODBC di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client è un driver a thread multipli. La scrittura di un'applicazione a thread multipli costituisce un'alternativa all'utilizzo di chiamate asincrone per elaborare più chiamate ODBC. Un thread può effettuare una chiamata ODBC asincrona e altri thread possono eseguire l'elaborazione mentre il primo thread è bloccato in attesa della risposta alla chiamata. Questo modello è più efficiente dell'esecuzione di chiamate asincrone, in quanto elimina l'overhead quale il traffico di rete e l'esecuzione di test di chiamate a funzioni ODBC ripetute per SQL_STILL_EXECUTING.  
  
 La modalità asincrona non rappresenta ancora un metodo efficace per l'elaborazione. I miglioramenti nelle prestazioni di un modello a thread multipli non sono sufficienti a giustificare la riscrittura delle applicazioni asincrone. Se gli utenti convertono applicazioni DB-Library che utilizzano il modello asincrono DB-Library, sarà più semplice convertirle nel modello asincrono ODBC.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di un'applicazione driver ODBC di SQL Server Native Client](creating-a-driver-application.md)  
  
  
