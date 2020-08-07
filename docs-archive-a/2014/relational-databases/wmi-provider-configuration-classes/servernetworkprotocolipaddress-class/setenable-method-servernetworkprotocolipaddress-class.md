---
title: Abrechenbare Methode (ServerNetworkProtocolIPAddress-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: baa86deb-95dd-416f-b2c7-cec1dfb91ab4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5be9c30acacaedba320fd68363e531b178918271
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619029"
---
# <a name="setenable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="abee0-102">SetEnable-Methode (ServerNetworkProtocolIPAddress-Klasse)</span><span class="sxs-lookup"><span data-stu-id="abee0-102">SetEnable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="abee0-103">Aktiviert die IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="abee0-103">Enables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abee0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="abee0-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="abee0-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="abee0-105">Parts</span></span>  
 <span data-ttu-id="abee0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="abee0-106">*object*</span></span>  
 <span data-ttu-id="abee0-107">A [ServerNetworkProtocolIPAdress-Klassenobjekt](servernetworkprotocolipaddress-class.md) , das eine IP-Adresse für das Netzwerkprotokoll in der Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="abee0-107">A [ServerNetworkProtocolIPAdress Class](servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="abee0-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="abee0-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="abee0-109">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="abee0-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abee0-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="abee0-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abee0-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abee0-111">See Also</span></span>  
 <span data-ttu-id="abee0-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="abee0-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
