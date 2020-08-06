---
title: SetProtocolsOrder-Methode (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetProtocolsOrder Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetProtocolsOrder method
ms.assetid: b86d98b9-aae4-4e74-b4da-1ec984d5c8b4
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: aaa1d43c8a2f7f210f61761b28313a93ac6c7a90
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622490"
---
# <a name="setprotocolsorder-method-clientnetworkprotocol-class"></a><span data-ttu-id="85a3c-102">SetProtocolsOrder-Methode (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="85a3c-102">SetProtocolsOrder Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="85a3c-103">Ändert die Reihenfolge der Protokollliste.</span><span class="sxs-lookup"><span data-stu-id="85a3c-103">Changes the order of the protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85a3c-104">Syntax</span></span>  
  
```  
  
object  
.SetProtocolsOrder(  
ProtocolOrderList  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="85a3c-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="85a3c-105">Parts</span></span>  
 <span data-ttu-id="85a3c-106">*object*</span><span class="sxs-lookup"><span data-stu-id="85a3c-106">*object*</span></span>  
 <span data-ttu-id="85a3c-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="85a3c-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="85a3c-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="85a3c-108">Parameters</span></span>  
  
|<span data-ttu-id="85a3c-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="85a3c-109">Parameter</span></span>|<span data-ttu-id="85a3c-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="85a3c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85a3c-111">*Protocolorderlist*</span><span class="sxs-lookup"><span data-stu-id="85a3c-111">*ProtocolOrderList*</span></span>|<span data-ttu-id="85a3c-112">Eine Zeichenfolgenarray, das die Clientnetzwerkprotokolle in der neuen Reihenfolge auflistet.</span><span class="sxs-lookup"><span data-stu-id="85a3c-112">A string[] array that lists the client network protocols in the new order.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="85a3c-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="85a3c-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="85a3c-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="85a3c-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85a3c-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="85a3c-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a3c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85a3c-116">See Also</span></span>  
 <span data-ttu-id="85a3c-117">[Konfigurieren von Client Protokollen](https://technet.microsoft.com/library/ms181035.aspx) </span><span class="sxs-lookup"><span data-stu-id="85a3c-117">[Configure Client Protocols](https://technet.microsoft.com/library/ms181035.aspx) </span></span>  
 [<span data-ttu-id="85a3c-118">Konfigurieren von Clientnetzwerkprotokollen und Netzwerkbibliotheken</span><span class="sxs-lookup"><span data-stu-id="85a3c-118">Configuring Client Network Protocols and Net-Libraries</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
