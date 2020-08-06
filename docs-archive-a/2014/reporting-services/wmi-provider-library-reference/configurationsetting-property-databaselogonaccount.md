---
title: Proprietà DatabaseLogonAccount (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722348"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a>Proprietà DatabaseLogonAccount (MSReportServer_ConfigurationSetting WMI)
  Specifica l'account di accesso utilizzato dal server di report al momento della connessione al database del server di report. Sola lettura.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a>Valori della proprietà  
 Oggetto `String` che rappresenta il nome dell'account di accesso.  
  
## <a name="example-code"></a>Codice di esempio  
 [Classe MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a>Osservazioni  
 I valori validi per questa proprietà varieranno a seconda del valore della proprietà [DatabaseLogonType](configurationsetting-property-databaselogontype.md) .  
  
 Questa proprietà viene ignorata se la proprietà [DatabaseLogonType](configurationsetting-property-databaselogontype.md) è impostata su `2 (Service)` .  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Membri di MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
