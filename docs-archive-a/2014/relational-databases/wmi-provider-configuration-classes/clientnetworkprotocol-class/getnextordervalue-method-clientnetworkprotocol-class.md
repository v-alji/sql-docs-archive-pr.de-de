---
title: GetNextOrderValue-Methode (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetNextOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetNextOrderValue method
ms.assetid: d741dc5c-c225-43d9-a730-7ad664ac525f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bdc3eecd9e151d7da32a5fd65a90552c0743b3d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630563"
---
# <a name="getnextordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="4ca04-102">GetNextOrderValue-Methode (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="4ca04-102">GetNextOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="4ca04-103">Wählt das Protokoll aus, das sich in der Protokollliste an der nächsten Position befindet.</span><span class="sxs-lookup"><span data-stu-id="4ca04-103">Selects the protocol that is in the next position in the list of protocols.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ca04-104">Syntax</span></span>  
  
```  
  
object  
.GetNextOrderValue()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="4ca04-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="4ca04-105">Parts</span></span>  
 <span data-ttu-id="4ca04-106">*object*</span><span class="sxs-lookup"><span data-stu-id="4ca04-106">*object*</span></span>  
 <span data-ttu-id="4ca04-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="4ca04-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4ca04-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4ca04-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="4ca04-109">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="4ca04-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ca04-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4ca04-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca04-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ca04-111">See Also</span></span>  
 <span data-ttu-id="4ca04-112">[Konfigurieren von Client Protokollen](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="4ca04-112">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="4ca04-113">Konfigurieren von Clientnetzwerkprotokollen und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="4ca04-113">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
