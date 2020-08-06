---
title: Proprietà MultiIpConfigurationSupport (classe ServerNetworkProtocol) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- MultiIpConfigurationSupport property
ms.assetid: 442c6133-4038-42db-a67d-2631285ac76b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 80401a607c9155451a869082162affcca401ebca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623075"
---
# <a name="multiipconfigurationsupport-property-servernetworkprotocol-class"></a><span data-ttu-id="7b561-102">Proprietà MultiIpConfigurationSupport (classe ServerNetworkProtocol)</span><span class="sxs-lookup"><span data-stu-id="7b561-102">MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="7b561-103">Ottiene la proprietà booleana che specifica se più indirizzi IP sono supportati da un protocollo di rete del server.</span><span class="sxs-lookup"><span data-stu-id="7b561-103">Gets the Boolean property that specifies whether multiple IP addresses are supported by a server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b561-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b561-104">Syntax</span></span>  
  
```  
  
object  
.MultiIpConfigurationSupport [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="7b561-105">Parti</span><span class="sxs-lookup"><span data-stu-id="7b561-105">Parts</span></span>  
 <span data-ttu-id="7b561-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7b561-106">*object*</span></span>  
 <span data-ttu-id="7b561-107">Oggetto della [Proprietà ProtocolName (classe ServerNetworkProtocol)](servernetworkprotocol-class.md) che rappresenta il protocollo di rete utilizzato dall'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b561-107">A [ProtocolName Property (ServerNetworkProtocol Class)](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7b561-108">Valore proprietà/Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b561-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="7b561-109">Valore booleano che specifica se più indirizzi IP sono supportati dal protocollo di rete del server. `true` se più indirizzi IP sono supportati dal protocollo di rete del server; `false` se più indirizzi IP non sono supportati dal protocollo di rete del server.</span><span class="sxs-lookup"><span data-stu-id="7b561-109">A Boolean value that specifies whether multiple IP addresses are supported by the server network protocol: `true` if multiple IP addresses are supported by the server network protocol, or `false` if multiple IP addresses are not supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b561-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7b561-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b561-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b561-111">See Also</span></span>  
 <span data-ttu-id="7b561-112">[Configurazione di protocolli di rete server e di librerie di rete](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7b561-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
