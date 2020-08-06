---
title: Metodo SetStrValue (classe SqlServiceAdvancedProperty) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (SqlServiceAdvancedProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 1fededc3-81ba-4b08-83f9-189b96140799
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d977eb9845c820c4128d1d60337151eeb3893eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717568"
---
# <a name="setstrvalue-method-sqlserviceadvancedproperty-class"></a><span data-ttu-id="c8d5b-102">Metodo SetStrValue (classe SqlServiceAdvancedProperty)</span><span class="sxs-lookup"><span data-stu-id="c8d5b-102">SetStrValue Method (SqlServiceAdvancedProperty Class)</span></span>
  <span data-ttu-id="c8d5b-103">Imposta il valore string di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-103">Sets the string value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8d5b-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="c8d5b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c8d5b-105">Parts</span></span>  
 <span data-ttu-id="c8d5b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c8d5b-106">*object*</span></span>  
 <span data-ttu-id="c8d5b-107">Oggetto della [classe SqlServiceAdvancedProperty](sqlserviceadvancedproperty-class.md) che rappresenta una proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-107">A [SqlServiceAdvancedProperty Class](sqlserviceadvancedproperty-class.md) object that represents an advanced property.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c8d5b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8d5b-108">Parameters</span></span>  
  
|<span data-ttu-id="c8d5b-109">Parametro</span><span class="sxs-lookup"><span data-stu-id="c8d5b-109">Parameter</span></span>|<span data-ttu-id="c8d5b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8d5b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8d5b-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="c8d5b-111">*StrValue*</span></span>|<span data-ttu-id="c8d5b-112">Valore string che specifica il valore della proprietà avanzata.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-112">A string value that specifies the value of the advanced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c8d5b-113">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8d5b-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="c8d5b-114">Valore uint32 che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8d5b-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c8d5b-115">Remarks</span></span>  
 <span data-ttu-id="c8d5b-116">Il tipo di valore della proprietà deve essere *string* per impostare la proprietà su un valore string.</span><span class="sxs-lookup"><span data-stu-id="c8d5b-116">The property value type must be *string* to set the property to a string value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d5b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d5b-117">See Also</span></span>  
 <span data-ttu-id="c8d5b-118">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c8d5b-118">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
