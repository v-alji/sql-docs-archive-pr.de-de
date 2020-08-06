---
title: IPADRESSEN-Eigenschaft (ServerNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- IpAddresses Property (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- IpAddresses property
ms.assetid: e5d66f7e-9719-436e-b723-12d56f914a05
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b94c4c11327abc1f02bd1e99c414f806f75bc145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607572"
---
# <a name="ipaddresses-property-servernetworkprotocol-class"></a><span data-ttu-id="2ae09-102">IpAddresses-Eigenschaft (ServerNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="2ae09-102">IpAddresses Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="2ae09-103">Ruft die IP-Adressen ab, die dem Servernetzwerkprotokoll zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2ae09-103">Gets the IP addresses associated with the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ae09-104">Syntax</span></span>  
  
```  
  
object  
.IpAddresses [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="2ae09-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="2ae09-105">Parts</span></span>  
 <span data-ttu-id="2ae09-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2ae09-106">*object*</span></span>  
 <span data-ttu-id="2ae09-107">Ein- `ServerNetworkProtocol` Objekt, das das Netzwerkprotokoll darstellt, das von der-Instanz verwendet wird [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2ae09-107">A `ServerNetworkProtocol` object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2ae09-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ae09-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="2ae09-109">Ein Array von [ServerNetworkProtocolIPAdress-Klassenobjekten](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) , die die vom Server-Netzwerkprotokoll unterstützten IP-Adressen darstellen.</span><span class="sxs-lookup"><span data-stu-id="2ae09-109">An array of [ServerNetworkProtocolIPAdress Class](../servernetworkprotocolipaddress-class/servernetworkprotocolipaddress-class.md) objects that represent the IP addresses supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ae09-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2ae09-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae09-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ae09-111">See Also</span></span>  
 <span data-ttu-id="2ae09-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="2ae09-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
