---
title: MultiIpConfigurationSupport-Eigenschaft (ServerNetworkProtocol-Klasse) | Microsoft-Dokumentation
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
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607571"
---
# <a name="multiipconfigurationsupport-property-servernetworkprotocol-class"></a><span data-ttu-id="adf98-102">MultiIpConfigurationSupport-Eigenschaft (ServerNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="adf98-102">MultiIpConfigurationSupport Property (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="adf98-103">Ruft die boolesche Eigenschaft ab, die angibt, ob mehrere IP-Adressen von einem Servernetzwerkprotokoll unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="adf98-103">Gets the Boolean property that specifies whether multiple IP addresses are supported by a server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adf98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="adf98-104">Syntax</span></span>  
  
```  
  
object  
.MultiIpConfigurationSupport [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="adf98-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="adf98-105">Parts</span></span>  
 <span data-ttu-id="adf98-106">*object*</span><span class="sxs-lookup"><span data-stu-id="adf98-106">*object*</span></span>  
 <span data-ttu-id="adf98-107">Ein [ProtocolName-Eingenschaftsobjekt (ServerNetworkProtocol-Klasse)](servernetworkprotocol-class.md) , das das Netzwerkprotokoll darstellt, das von der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="adf98-107">A [ProtocolName Property (ServerNetworkProtocol Class)](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="adf98-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="adf98-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="adf98-109">Ein boleescher Wert, der angibt, ob mehrere IP-Adressen vom Server-Netzwerkprotokoll unterstützt werden: `true`, wenn mehrere IP-Adressen vom Server-Netzwerkprotokoll unterstützt werden, bzw. `false`, wenn das Server-Netzwerkprotokoll nicht mehrere IP-Adressen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="adf98-109">A Boolean value that specifies whether multiple IP addresses are supported by the server network protocol: `true` if multiple IP addresses are supported by the server network protocol, or `false` if multiple IP addresses are not supported by the server network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adf98-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="adf98-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf98-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="adf98-111">See Also</span></span>  
 <span data-ttu-id="adf98-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="adf98-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
