---
title: Proprietà SqlServiceType (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SqlServiceType Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SqlServiceType property
ms.assetid: dbff2968-3011-41d6-a141-52d814af0213
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 18e0fc741d19eefbb93dbcb7fb6fd4a221ce86d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717622"
---
# <a name="sqlservicetype-property-sqlservice-class"></a>Proprietà SqlServiceType (classe SqlService)
  Ottiene il tipo del servizio gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
object  
.SqlServiceType [= value]  
```  
  
## <a name="parts"></a>Parti  
 *object*  
 Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 Valore uint32 che specifica il tipo di servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .  
  
## <a name="remarks"></a>Osservazioni  
 I possibili valori restituiti sono i seguenti:  
  
|Type|Definizione|  
|----------|----------------|  
|*1*|MSSQLSERVER è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .|  
|*2*|SQLSERVERAGENT è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent.|  
|*3*|MSFTESQL è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del motore di ricerca full-text.|  
|*4*|MsDtsServer è il servizio [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .|  
|*5*|MSSQLServerOLAPService è il servizio [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .|  
|*6*|ReportServer è il servizio [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .|  
|*7*|SQLBrowser è il servizio [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Browser.|  
  
## <a name="see-also"></a>Vedere anche  
 [Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
