---
title: Modificare le connessioni che utilizzano i protocolli di rete Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk o NWLink IPX SPX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], modifying connections
- SPP [SQL Server]
- NWLink IPX/SPX [SQL Server]
- connections [SQL Server]
- AppleTalk [SQL Server]
- Sequenced Packet Protocol [SQL Server]
- Multiprotocol Net-Library [SQL Server]
- Banyan VINES Sequenced Package Protocol [SQL Server]
- IPX/SPX [SQL Server]
- protocols [SQL Server], modifying connections
- RPC [SQL Server]
ms.assetid: 5c5ae453-cc5b-4898-95c7-ad34157b1f60
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 750b9c0b76ab6c3b43908ecb8454f31ac1a25b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724375"
---
# <a name="modify-connections-that-use-banyan-vines-sequenced-packet-protocol-spp-multiprotocol-appletalk-or-nwlink-ipx-spx-network-protocols"></a><span data-ttu-id="e0886-102">Modificare le connessioni che usano i protocolli di rete Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk o NWLink IPX/SPX</span><span class="sxs-lookup"><span data-stu-id="e0886-102">Modify connections that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX SPX network protocols</span></span>
  <span data-ttu-id="e0886-103">Sono stati rilevati protocolli di connettività client/server non supportati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0886-103">The Upgrade Advisor has detected client server connectivity protocols that are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e0886-104">Le applicazioni client che utilizzano i protocolli di rete Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk o NWLink IPX/SPX devono effettuare la connessione utilizzando un protocollo supportato.</span><span class="sxs-lookup"><span data-stu-id="e0886-104">Client applications that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk, or NWLink IPX/SPX network protocols must connect using a supported protocol.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e0886-105">Componente</span><span class="sxs-lookup"><span data-stu-id="e0886-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="e0886-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0886-106">Description</span></span>  
 <span data-ttu-id="e0886-107">I protocolli di rete Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk e NWLink IPX/SPX non sono supportati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0886-107">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support the Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX/SPX network protocols.</span></span> <span data-ttu-id="e0886-108">Per i client che in precedenza utilizzavano questi protocolli è necessario selezionare un protocollo diverso.</span><span class="sxs-lookup"><span data-stu-id="e0886-108">Clients previously connecting with these protocols must select a different protocol.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="e0886-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="e0886-109">Corrective Action</span></span>  
 <span data-ttu-id="e0886-110">Modificare le applicazioni client in modo che utilizzino un protocollo supportato per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="e0886-110">Change the client applications to use a supported protocol when connecting to the server.</span></span> <span data-ttu-id="e0886-111">Se è stato installato un alias che utilizza uno dei protocolli non supportati, tale alias deve essere modificato in modo da utilizzare uno dei protocolli supportati.</span><span class="sxs-lookup"><span data-stu-id="e0886-111">If you have an alias setup that uses one of the unsupported protocols then the alias must be modified to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="e0886-112">Se la stringa di connessione dell'applicazione USA o carica in modo specifico uno di questi protocolli, specificando NETWORK = DBMSRPCN per RPC, NETWORK = DBMSADSN per AppleTalk o NETWORK = DBMSVINN per la proprietà Banyan VINES oppure usando un prefisso esplicito, ad esempio "SPX:*Server\Istanza*" per SPX, "BV:*Server*" per Banyan VINES, "ADSP:*server*" per AppleTalk o "RPC:*Server*" per il multiprotocollo, è necessario modificare l'applicazione per usare uno dei protocolli supportati.</span><span class="sxs-lookup"><span data-stu-id="e0886-112">If your application connection string specifically uses or loads one of these protocols, by either specifying NETWORK=DBMSRPCN for RPC, NETWORK=DBMSADSN for Appletalk, or NETWORK=DBMSVINN for Banyan VINES property, or by using an explicit prefix such as "spx:*server\instance*" for SPX, "bv:*server*" for Banyan VINES, "adsp:*server*" for AppleTalk, or "rpc:*server*" for multiprotocol, then you must modify your application to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="e0886-113">Per ulteriori informazioni, vedere "Scelta di un Protocollo di rete" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e0886-113">For more information, see "Choosing a Network Protocol" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0886-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0886-114">See Also</span></span>  
 <span data-ttu-id="e0886-115">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e0886-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e0886-116">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="e0886-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  