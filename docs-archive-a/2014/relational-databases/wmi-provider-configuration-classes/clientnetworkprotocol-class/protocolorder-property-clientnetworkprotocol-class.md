---
title: ProtocolOrder-Eigenschaft (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolOrder Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolOrder property
ms.assetid: aa09b8ab-37db-4406-8973-acf503855fd2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8bccb7109972dea4697e9e289081cbf47d2f9492
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622495"
---
# <a name="protocolorder-property-clientnetworkprotocol-class"></a><span data-ttu-id="01885-102">ProtocolOrder-Eigenschaft (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="01885-102">ProtocolOrder Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="01885-103">Ruft die fortlaufende Nummer des Netzwerkprotokolls ab, auf das aktuell verwiesen wird. Dies erfolgt gemäß der [SetOrderValue-Methode (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="01885-103">Gets the order number of the currently referenced client network protocol as specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01885-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01885-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolOrder [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="01885-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="01885-105">Parts</span></span>  
 <span data-ttu-id="01885-106">*object*</span><span class="sxs-lookup"><span data-stu-id="01885-106">*object*</span></span>  
 <span data-ttu-id="01885-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="01885-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="01885-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="01885-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="01885-109">Ein `uint32`-Wert, der die fortlaufende Nummer des derzeitig referenzierten Clientnetzwerkprotokolls angibt, das durch die `OrderValue`-Methode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="01885-109">A `uint32` value that specifies the order number of the currently referenced client network protocol as set by the `OrderValue` method.</span></span> <span data-ttu-id="01885-110">Wenn das Clientnetzwerkprotokoll deaktiviert ist, ist dieser Wert Null.</span><span class="sxs-lookup"><span data-stu-id="01885-110">If the client network protocol is disabled, this value will be zero.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01885-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="01885-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01885-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01885-112">See Also</span></span>  
 <span data-ttu-id="01885-113">[Konfigurieren von Client Protokollen](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="01885-113">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="01885-114">Konfigurieren von Clientnetzwerkprotokollen und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="01885-114">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
