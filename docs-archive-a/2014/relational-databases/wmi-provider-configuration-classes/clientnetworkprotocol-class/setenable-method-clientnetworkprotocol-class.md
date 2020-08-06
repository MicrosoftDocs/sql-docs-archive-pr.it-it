---
title: Metodo seenable (classe ClientNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a66c756a-1311-4f4a-8088-818f8ed90056
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: dfba695506dd04ded82083b85bfbb751913fbcbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637108"
---
# <a name="setenable-method-clientnetworkprotocol-class"></a><span data-ttu-id="7a922-102">Metodo SetEnable (classe ClientNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="7a922-102">SetEnable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="7a922-103">Abilita il protocollo di rete del client specificato dalla [configurazione dei protocolli client](https://technet.microsoft.com/library/ms181035.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a922-103">Enables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a922-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a922-104">Syntax</span></span>  
  
```  
  
object  
.SetEnableMethod()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7a922-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7a922-105">Parts</span></span>  
 <span data-ttu-id="7a922-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7a922-106">*object*</span></span>  
 <span data-ttu-id="7a922-107">Oggetto della [classe ClientNetworkProtocol](clientnetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dal [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span><span class="sxs-lookup"><span data-stu-id="7a922-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7a922-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7a922-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="7a922-109">Valore `uint32` che è 0 se il servizio è stato modificato correttamente, 1 se la richiesta non è supportata e qualsiasi altro numero per indicare un errore.</span><span class="sxs-lookup"><span data-stu-id="7a922-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a922-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7a922-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a922-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a922-111">See Also</span></span>  
 [<span data-ttu-id="7a922-112">Configurazione di protocolli di rete client e di librerie di rete</span><span class="sxs-lookup"><span data-stu-id="7a922-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  