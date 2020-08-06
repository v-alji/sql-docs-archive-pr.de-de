---
title: SetFlag-Methode (ClientNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 0407520f-2f84-4f68-b2b7-429697286c1b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1c83a1d647b62f0e5c5acf0659d54bf787bf0c96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722654"
---
# <a name="setflag-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="6b83d-102">SetFlag-Methode (ClientNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="6b83d-102">SetFlag Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="6b83d-103">Legt das Flag der aktuellen Eigenschaft fest, auf die durch den [PropertyIdx-Eigenschaftswert (ClientNetworkProtocolProperty-Klasse)](clientnetworkprotocolproperty-class.md) verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6b83d-103">Sets the flag of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b83d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b83d-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
) [=]  
```  
  
## <a name="parts"></a><span data-ttu-id="6b83d-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="6b83d-105">Parts</span></span>  
 <span data-ttu-id="6b83d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="6b83d-106">*object*</span></span>  
 <span data-ttu-id="6b83d-107">A [ClientNetworkProtocolProperty-Klassenobjekt](clientnetworkprotocolproperty-class.md) , das ein Attribut des vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendeten Netzwerkprotokolls darstellt.</span><span class="sxs-lookup"><span data-stu-id="6b83d-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="6b83d-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b83d-108">Parameters</span></span>  
  
|<span data-ttu-id="6b83d-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b83d-109">Parameter</span></span>|<span data-ttu-id="6b83d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6b83d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b83d-111">*Booleer Wert*</span><span class="sxs-lookup"><span data-stu-id="6b83d-111">*BoolValue*</span></span>|<span data-ttu-id="6b83d-112">Ein boleescher Wert, der den neuen Wert des Flags angibt.</span><span class="sxs-lookup"><span data-stu-id="6b83d-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6b83d-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b83d-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="6b83d-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="6b83d-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b83d-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6b83d-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b83d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b83d-116">See Also</span></span>  
 [<span data-ttu-id="6b83d-117">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="6b83d-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
