---
title: Metodo ReserveURL (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ReservedURL method
ms.assetid: b9008a62-3edd-4f8a-99f2-7598c2133899
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 95a58938ada19b4e49f094e3d8d01b241f1a4286
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722395"
---
# <a name="reserveurl-method-wmi-msreportserver_configurationsetting"></a>Metodo ReserveURL (MSReportServer_ConfigurationSetting WMI)
  Aggiunge una prenotazione URL per un'applicazione specifica.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Public Sub ReserveURL(Application as String, _  
    UrlString as String, Lcid as Int32, _   
    ByRef [Error] as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ReserveURL(string Application, string UrlString, int Lcid,   
    out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a>Parametri  
 *Applicazione*  
 Nome dell'applicazione per la quale riservare l'URL.  
  
 *URLString*  
 URL per la prenotazione.  
  
 *lcid*  
 Impostazioni locali da utilizzare per i messaggi di errore restituiti.  
  
 *Error (Errore) (Error (Errore)e)*  
 [out] Descrizione dell'errore che si è verificato.  
  
 *HRESULT*  
 [out] Valore che indica se la chiamata ha avuto esito positivo o negativo.  
  
## <a name="return-value"></a>Valore restituito  
 Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo. Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.  
  
## <a name="remarks"></a>Osservazioni  
 *UrlString* non include il nome della directory virtuale. A tal fine, viene fornito il metodo [SetVirtualDirectory](configurationsetting-method-setvirtualdirectory.md) .  
  
 Le prenotazioni URL vengono create per l'account del servizio Windows corrente. La modifica dell'account del servizio Windows richiede l'aggiornamento manuale di tutte le prenotazioni URL.  
  
 Questo metodo causa l'esecuzione dell'operazione di riciclo pesante da parte di tutti i domini applicazione. Una volta completata l'operazione, i domini applicazione vengono riavviati.  
  
## <a name="requirements"></a>Requisiti  
 **Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Membri di MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  
