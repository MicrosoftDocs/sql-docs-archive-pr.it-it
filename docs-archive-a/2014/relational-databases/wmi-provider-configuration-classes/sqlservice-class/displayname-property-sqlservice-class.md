---
title: Proprietà DisplayName (classe SqlService) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- DisplayName Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- DisplayName property
ms.assetid: 49c408aa-6eb4-45cd-8d5c-60f065f24f5c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 147fc298d6d263caf1e4ad6852d4b02f86911572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722636"
---
# <a name="displayname-property-sqlservice-class"></a><span data-ttu-id="aee89-102">Proprietà DisplayName (classe SqlService)</span><span class="sxs-lookup"><span data-stu-id="aee89-102">DisplayName Property (SqlService Class)</span></span>
  <span data-ttu-id="aee89-103">Ottiene il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="aee89-103">Gets the display name of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aee89-104">Syntax</span></span>  
  
```  
  
object  
.DisplayName [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="aee89-105">Parti</span><span class="sxs-lookup"><span data-stu-id="aee89-105">Parts</span></span>  
 <span data-ttu-id="aee89-106">*object*</span><span class="sxs-lookup"><span data-stu-id="aee89-106">*object*</span></span>  
 <span data-ttu-id="aee89-107">Oggetto della [classe SqlService](sqlservice-class.md) che rappresenta il servizio.</span><span class="sxs-lookup"><span data-stu-id="aee89-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="aee89-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aee89-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="aee89-109">Valore string che specifica il nome visualizzato del servizio.</span><span class="sxs-lookup"><span data-stu-id="aee89-109">A string value that specifies the display name of the service.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aee89-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="aee89-110">Remarks</span></span>  
 <span data-ttu-id="aee89-111">La lunghezza massima della stringa è di 256 caratteri.</span><span class="sxs-lookup"><span data-stu-id="aee89-111">This string has a maximum length of 256 characters.</span></span> <span data-ttu-id="aee89-112">In Gestione configurazione [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene mantenuta la distinzione tra maiuscole e minuscole per il nome.</span><span class="sxs-lookup"><span data-stu-id="aee89-112">The name is case-preserved in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="aee89-113">Tuttavia, i nomi visualizzati vengono sempre confrontati senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="aee89-113">However, display name comparisons are always case-insensitive.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aee89-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="aee89-114">Example</span></span>  
  
```  
mysqlservice.DisplayName = "Atdisk"  
```  
  
## <a name="see-also"></a><span data-ttu-id="aee89-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aee89-115">See Also</span></span>  
 <span data-ttu-id="aee89-116">[Avvio e arresto di servizi](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="aee89-116">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
