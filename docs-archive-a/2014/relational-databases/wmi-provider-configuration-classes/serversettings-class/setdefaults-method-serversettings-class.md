---
title: Metodo sedefaults (classe ServerSettings) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 76e4cfab-4b15-4da4-bb2f-8aac6f927f79
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 93dd2eee5a395d4d7463ebf9b85530fcf82d1888
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715112"
---
# <a name="setdefaults-method-serversettings-class"></a>Metodo SetDefaults (classe ServerSettings)
  Imposta tutti i valori predefiniti per l'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con l'opzione per sovrascrivere i dati esistenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a>Parti  
 *object*  
 Oggetto della [classe ServerSettings](serversettings-class.md) che rappresenta un' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] istanza del client.  
  
#### <a name="parameters"></a>Parametri  
  
|Parametro|Descrizione|  
|---------------|-----------------|  
|*OverwriteAll*|Valore booleano che specifica se sovrascrivere i valori esistenti nell'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. `true` per sovrascrivere i dati esistenti; `false` se i dati esistenti non devono essere sovrascritti.|  
  
## <a name="property-valuereturn-value"></a>Valore proprietà/Valore restituito  
 Valore u`int32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="see-also"></a>Vedere anche  
 [Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)  
  
  
