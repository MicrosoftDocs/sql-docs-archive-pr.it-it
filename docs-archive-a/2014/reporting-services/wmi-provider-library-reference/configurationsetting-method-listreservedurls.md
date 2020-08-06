---
title: Metodo ListReservedURLs (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListReservedURLs method
ms.assetid: 32335af1-5eae-4420-a0ef-b1e8a3267166
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7639741adb0c756961c4c6b63a3bffb627c4a89c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627613"
---
# <a name="listreservedurls-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="4cc1f-102">Metodo ListReservedURLs (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="4cc1f-102">ListReservedURLs Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="4cc1f-103">Elenca gli URL riservati per tutte le applicazioni presenti nel server di report.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-103">Lists URLs reserved for all applications on the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc1f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cc1f-104">Syntax</span></span>  
  
```vb  
Public Sub ListReservedUrls(ByRef Application() as String, ByRef UrlString() as String, _  
    ByRef Account() as String, ByRef AccountSID() as String, _  
    ByRef length() as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListReservedUrls(out string[] Application, out string[] UrlString,  
        out string[] Account, out string[] AccountSID,  
        out int[] Length, out int[] HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cc1f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cc1f-105">Parameters</span></span>  
 <span data-ttu-id="4cc1f-106">*Application[]*</span><span class="sxs-lookup"><span data-stu-id="4cc1f-106">*Application[]*</span></span>  
 <span data-ttu-id="4cc1f-107">[out] Applicazioni che dispongono di prenotazioni URL.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-107">[out] The applications that have URL reservations.</span></span>  
  
 <span data-ttu-id="4cc1f-108">*UrlString[]*</span><span class="sxs-lookup"><span data-stu-id="4cc1f-108">*UrlString[]*</span></span>  
 <span data-ttu-id="4cc1f-109">[out] URL riservati.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-109">[out] The URLs that are reserved.</span></span>  
  
 <span data-ttu-id="4cc1f-110">*Account[]*</span><span class="sxs-lookup"><span data-stu-id="4cc1f-110">*Account[]*</span></span>  
 <span data-ttu-id="4cc1f-111">[out] Nomi account associati all'account per le prenotazioni URL.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-111">[out] The account names associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="4cc1f-112">*AccountSID[]*</span><span class="sxs-lookup"><span data-stu-id="4cc1f-112">*AccountSID[]*</span></span>  
 <span data-ttu-id="4cc1f-113">[out] SID di account associati all'account per le prenotazioni URL.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-113">[out] The account SIDs associated with the account for the URL reservations.</span></span>  
  
 <span data-ttu-id="4cc1f-114">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="4cc1f-114">*Length*</span></span>  
 <span data-ttu-id="4cc1f-115">[out] Lunghezza delle matrici restituite dal metodo.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-115">[out] The length of the arrays returned by the method.</span></span>  
  
 <span data-ttu-id="4cc1f-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="4cc1f-116">*HRESULT*</span></span>  
 <span data-ttu-id="4cc1f-117">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cc1f-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4cc1f-118">Return Value</span></span>  
 <span data-ttu-id="4cc1f-119">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="4cc1f-120">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="4cc1f-120">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cc1f-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4cc1f-121">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc1f-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cc1f-122">Requirements</span></span>  
 <span data-ttu-id="4cc1f-123">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cc1f-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc1f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cc1f-124">See Also</span></span>  
 [<span data-ttu-id="4cc1f-125">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="4cc1f-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  