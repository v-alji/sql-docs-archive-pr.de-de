---
title: Properties-Eigenschaft (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Properties Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Properties property
ms.assetid: 7e0a4e38-4555-4750-8fd3-4425b29e6aa1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 09836db1f510ac77635924c51e5341686627d54d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630561"
---
# <a name="properties-property-clientnetworkprotocol-class"></a><span data-ttu-id="713c3-102">Properties-Eigenschaft (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="713c3-102">Properties Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="713c3-103">Ruft die Eigenschaften ab, die dem aktuellen Clientnetzwerkprotokoll zugeordnet sind, das in [Konfigurieren von Clientprotokollen](https://technet.microsoft.com/library/ms181035.aspx)angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="713c3-103">Gets the properties associated with the current client network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="713c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="713c3-104">Syntax</span></span>  
  
```  
  
object  
.Properties [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="713c3-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="713c3-105">Parts</span></span>  
 <span data-ttu-id="713c3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="713c3-106">*object*</span></span>  
 <span data-ttu-id="713c3-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="713c3-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="713c3-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="713c3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="713c3-109">Ein Array von [ClientNetworkProtocolProperty-Klassen](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) Objekten, die die Eigenschaften darstellen, die vom aktuellen Client Netzwerkprotokoll unterstützt werden, auf das von der-Eigenschaft verwiesen wird `OrderValue` .</span><span class="sxs-lookup"><span data-stu-id="713c3-109">An array of [ClientNetworkProtocolProperty Class](../clientnetworkprotocolproperty-class/clientnetworkprotocolproperty-class.md) objects that represent the properties supported by the current client network protocol that is referenced by the `OrderValue` property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="713c3-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="713c3-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="713c3-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="713c3-111">See Also</span></span>  
 [<span data-ttu-id="713c3-112">Konfigurieren von Clientnetzwerkprotokollen und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="713c3-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
