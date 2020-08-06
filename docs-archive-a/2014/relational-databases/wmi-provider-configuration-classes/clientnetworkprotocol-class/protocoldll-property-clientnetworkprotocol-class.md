---
title: ProtocolDLL-Eigenschaft (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ProtocolDLL Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ProtocolDLL property
ms.assetid: fe8650d5-7b9d-46f8-bf74-baf1d9d2a06a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cb008003b05b00e342795d51afee2b4491a71260
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617857"
---
# <a name="protocoldll-property-clientnetworkprotocol-class"></a><span data-ttu-id="c04fd-102">ProtocolDLL-Eigenschaft (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="c04fd-102">ProtocolDLL Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="c04fd-103">Ruft den Namen der DLL-Datei ab, die von dem in [Konfigurieren von Clientprotokollen](https://technet.microsoft.com/library/ms181035.aspx)angegebenen Netzwerkprotokoll benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c04fd-103">Gets the name of the .dll file required by the network protocol specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c04fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c04fd-104">Syntax</span></span>  
  
```  
  
object  
.ProtocolDLL [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="c04fd-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="c04fd-105">Parts</span></span>  
 <span data-ttu-id="c04fd-106">*object*</span><span class="sxs-lookup"><span data-stu-id="c04fd-106">*object*</span></span>  
 <span data-ttu-id="c04fd-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="c04fd-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c04fd-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c04fd-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="c04fd-109">Ein Zeichenfolgewert, der den Namen der -dll-Datei angibt, die vom Clientnetzwerkprotokoll benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c04fd-109">A string value that specifies the protocol .dll file required by the client network protocol.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c04fd-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c04fd-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04fd-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c04fd-111">See Also</span></span>  
 [<span data-ttu-id="c04fd-112">Konfigurieren von Clientnetzwerkprotokollen und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="c04fd-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
