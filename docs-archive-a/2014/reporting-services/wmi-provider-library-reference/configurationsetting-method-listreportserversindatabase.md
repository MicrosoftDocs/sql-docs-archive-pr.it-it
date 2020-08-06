---
title: Metodo ListReportServersInDatabase (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627615"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="5914f-102">Metodo ListReportServersInDatabase (MSReportServer_ConfigurationSetting WMI)</span><span class="sxs-lookup"><span data-stu-id="5914f-102">ListReportServersInDatabase Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="5914f-103">Restituisce l'elenco di installazioni del server di report presenti nel database del server di report, indipendentemente dal fatto che tali installazioni accedano a informazioni protette.</span><span class="sxs-lookup"><span data-stu-id="5914f-103">Returns the list of report server installations that are present in the report server database, regardless of whether they have access to secure information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5914f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5914f-104">Syntax</span></span>  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5914f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5914f-105">Parameters</span></span>  
 <span data-ttu-id="5914f-106">*MachineNames[]*</span><span class="sxs-lookup"><span data-stu-id="5914f-106">*MachineNames[]*</span></span>  
 <span data-ttu-id="5914f-107">[out] Matrice che contiene i nomi di computer per le installazioni del server di report nel database.</span><span class="sxs-lookup"><span data-stu-id="5914f-107">[out] An array containing the machine names for the report server installations in the database.</span></span>  
  
 <span data-ttu-id="5914f-108">*InstanceNames[]*</span><span class="sxs-lookup"><span data-stu-id="5914f-108">*InstanceNames[]*</span></span>  
 <span data-ttu-id="5914f-109">[out] Matrice che contiene i nomi delle istanze di ognuna delle installazioni del server di report nel database.</span><span class="sxs-lookup"><span data-stu-id="5914f-109">[out] An array containing the instance names of each of the report server installations in the database.</span></span>  
  
 <span data-ttu-id="5914f-110">*InstallationIDs[]*</span><span class="sxs-lookup"><span data-stu-id="5914f-110">*InstallationIDs[]*</span></span>  
 <span data-ttu-id="5914f-111">[out] Matrice che contiene gli ID di installazione di ogni installazione del server di report nel database.</span><span class="sxs-lookup"><span data-stu-id="5914f-111">[out] An array containing the installation IDs of each report server installation in the database.</span></span>  
  
 <span data-ttu-id="5914f-112">*IsInitialized[]*</span><span class="sxs-lookup"><span data-stu-id="5914f-112">*IsInitialized[]*</span></span>  
 <span data-ttu-id="5914f-113">[out] Matrice che contiene lo stato di inizializzazione di ogni installazione del server di report nel database.</span><span class="sxs-lookup"><span data-stu-id="5914f-113">[out] An array containing initialization status for each report server installation in the database.</span></span>  
  
 <span data-ttu-id="5914f-114">*Lunghezza*</span><span class="sxs-lookup"><span data-stu-id="5914f-114">*Length*</span></span>  
 <span data-ttu-id="5914f-115">[out] Lunghezza delle matrici restituite dal metodo.</span><span class="sxs-lookup"><span data-stu-id="5914f-115">[out] The length of the arrays returned by the method.</span></span> <span data-ttu-id="5914f-116">Tutte le matrici restituite hanno la stessa lunghezza.</span><span class="sxs-lookup"><span data-stu-id="5914f-116">All returned arrays have the same length.</span></span>  
  
 <span data-ttu-id="5914f-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="5914f-117">*HRESULT*</span></span>  
 <span data-ttu-id="5914f-118">[out] Valore che indica se la chiamata ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="5914f-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="5914f-119">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="5914f-119">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="5914f-120">[out] Matrice di stringhe che contiene errori aggiuntivi restituiti dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="5914f-120">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5914f-121">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5914f-121">Return Value</span></span>  
 <span data-ttu-id="5914f-122">Restituisce un *HRESULT* che indica l'esito positivo o negativo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="5914f-122">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="5914f-123">Un valore pari a 0 indica l'esito positivo della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="5914f-123">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="5914f-124">Un valore diverso da zero indica che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="5914f-124">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5914f-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5914f-125">Remarks</span></span>  
 <span data-ttu-id="5914f-126">ListReportServersInDatabase elenca le installazioni del server di report presenti nel database del server di report, indipendentemente dal fatto che tali installazioni accedano a informazioni protette e restituisce un set di matrici corrispondente in cui sono contenute le informazioni su ciascuna installazione.</span><span class="sxs-lookup"><span data-stu-id="5914f-126">ListReportServersInDatabase lists the report server installations that are present in the report server database, regardless of whether they have access to secure information, and returns a matched set of arrays containing information about each installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5914f-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5914f-127">Requirements</span></span>  
 <span data-ttu-id="5914f-128">**Spazio dei nomi:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5914f-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5914f-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5914f-129">See Also</span></span>  
 [<span data-ttu-id="5914f-130">Membri di MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="5914f-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  