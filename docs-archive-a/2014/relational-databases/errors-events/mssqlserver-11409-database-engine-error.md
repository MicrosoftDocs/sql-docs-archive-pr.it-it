---
title: MSSQLSERVER_11409 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 11409 (Database Engine error)
ms.assetid: 99b71a1c-a72d-4ca9-9d00-4230c9042ba5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e4249e13a3530f69978c78f2e2ca6e4583eed46a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624243"
---
# <a name="mssqlserver_11409"></a>MSSQLSERVER_11409
    
## <a name="details"></a>Dettagli  
  
|||  
|-|-|  
|Nome prodotto|SQL Server|  
|ID evento|11409|  
|Origine evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbolico|ALTERCOL_COLSET_DROP|  
|Testo del messaggio|Impossibile eliminare il set di colonne '%.*ls' nella tabella '%.\*ls' poiché la tabella contiene più di 1025 colonne.|  
  
## <a name="explanation"></a>Spiegazione  
 Le tabelle possono contenere un massimo di 1024 colonne non definite come colonne di tipo sparse o calcolate. Quando le colonne di tipo sparse provocano il superamento di 1024 colonne nella tabella, è necessario definire un set di colonne per la tabella. Nella tabella cui viene fatto riferimento sono contenute più di 1024 colonne ed è stato effettuato un tentativo di rimuovere il set di colonne.  
  
## <a name="user-action"></a>Azione dell'utente  
 È necessario mantenere il set di colonne con le colonne correnti nella tabella.  
  
 Per rimuovere il set di colonne, rimuovere innanzitutto le colonne dalla tabella fino a quando il relativo numero non supera 1024, quindi rimuovere il set di colonne.  
  
  
