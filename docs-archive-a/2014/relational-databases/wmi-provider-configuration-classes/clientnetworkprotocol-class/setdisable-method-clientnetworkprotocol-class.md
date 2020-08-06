---
title: Setdeaktiviert-Methode (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: bce69ab9-ea5b-43fd-8114-08b1b5890755
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2bad312f1f7c7e9540acdaf3dd46df78b953d4ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630558"
---
# <a name="setdisable-method-clientnetworkprotocol-class"></a><span data-ttu-id="46f6d-102">SetDisable-Methode (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="46f6d-102">SetDisable Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="46f6d-103">Deaktiviert das Clientnetzwerkprotokoll, das in [Konfigurieren von Clientprotokollen](https://technet.microsoft.com/library/ms181035.aspx)angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="46f6d-103">Disables the client network protocol that is specified by the [Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46f6d-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="46f6d-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="46f6d-105">Parts</span></span>  
 <span data-ttu-id="46f6d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="46f6d-106">*object*</span></span>  
 <span data-ttu-id="46f6d-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="46f6d-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="46f6d-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="46f6d-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="46f6d-109">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="46f6d-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46f6d-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46f6d-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f6d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46f6d-111">See Also</span></span>  
 [<span data-ttu-id="46f6d-112">Konfigurieren von Clientnetzwerkprotokollen und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="46f6d-112">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
