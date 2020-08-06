---
title: Metodo ListIPAddresses (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ListIPAddresses method
ms.assetid: 7e7cf182-fba0-4604-a474-098461e23e9d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 845f7ba7db02a0b860f966184463580733af0faf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627616"
---
# <a name="listipaddresses-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="959b0-102">Metodo ListIPAddresses (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="959b0-102">ListIPAddresses Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="959b0-103">Elenca gli indirizzi IP per il computer del server di report.</span><span class="sxs-lookup"><span data-stu-id="959b0-103">Lists the IP addresses for the report server computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="959b0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="959b0-104">Syntax</span></span>  
  
```vb  
Public Sub ListIPAddresses (ByRef IPAddress() as String, _  
    ByRef IPVersion()as String, ByRef IsDhcpEnabled () as Boolean, _   
    ByRef Length as Int32, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void ListIPAddresses (out string[] IPAddress,   
    out string[] IPVersion, out bool[] isDhcpEnabled, out int length,   
    out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="959b0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="959b0-105">Parameters</span></span>  
 <span data-ttu-id="959b0-106">*IPAddress[]*</span><span class="sxs-lookup"><span data-stu-id="959b0-106">*IPAddress[]*</span></span>  
 <span data-ttu-id="959b0-107">[out] Elenco degli indirizzi IP per il computer.</span><span class="sxs-lookup"><span data-stu-id="959b0-107">[out] The list of IP address for the computer.</span></span>  
  
 <span data-ttu-id="959b0-108">*IPVersion[]*</span><span class="sxs-lookup"><span data-stu-id="959b0-108">*IPVersion[]*</span></span>  
 <span data-ttu-id="959b0-109">[out] Versione degli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="959b0-109">[out] The version for the IP addresses.</span></span>  
  
 <span data-ttu-id="959b0-110">*IsDhcpEnabled[]*</span><span class="sxs-lookup"><span data-stu-id="959b0-110">*IsDhcpEnabled[]*</span></span>  
 <span data-ttu-id="959b0-111">[out] Indica se gli indirizzi IP sono abilitati a DHCP.</span><span class="sxs-lookup"><span data-stu-id="959b0-111">[out] Indicates whether the IP addresses are DHCP enabled.</span></span>  
  
 <span data-ttu-id="959b0-112">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="959b0-112">*Length*</span></span>  
 <span data-ttu-id="959b0-113">[out] Lunghezza della matrice restituita dal metodo.</span><span class="sxs-lookup"><span data-stu-id="959b0-113">[out] The length of the array returned by the method.</span></span>  
  
 <span data-ttu-id="959b0-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="959b0-114">*HRESULT*</span></span>  
 <span data-ttu-id="959b0-115">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="959b0-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="959b0-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="959b0-116">Return Value</span></span>  
 <span data-ttu-id="959b0-117">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="959b0-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="959b0-118">Il valore 0 indica l'esito positivo della chiamata al metodo, mentre un codice di errore ne indica l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="959b0-118">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="959b0-119">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="959b0-119">Remarks</span></span>  
 <span data-ttu-id="959b0-120">Le stringhe*IPVersion* sono V4, V6.</span><span class="sxs-lookup"><span data-stu-id="959b0-120">*IPVersion* strings are V4, V6.</span></span>  
  
 <span data-ttu-id="959b0-121">Se *IsDhcpEnabled* è `True` , *IPAddress* è dinamico.</span><span class="sxs-lookup"><span data-stu-id="959b0-121">If *IsDhcpEnabled* is `True`, the *IPAddress* is dynamic.</span></span> <span data-ttu-id="959b0-122">Non deve essere utilizzato per le associazioni SSL.</span><span class="sxs-lookup"><span data-stu-id="959b0-122">It should not be used for SSL bindings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="959b0-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="959b0-123">Requirements</span></span>  
 <span data-ttu-id="959b0-124">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="959b0-124">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959b0-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="959b0-125">See Also</span></span>  
 [<span data-ttu-id="959b0-126">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="959b0-126">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  