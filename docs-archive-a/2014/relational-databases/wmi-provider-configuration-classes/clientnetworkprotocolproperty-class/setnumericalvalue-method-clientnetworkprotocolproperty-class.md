---
title: SetNumericalValue-Methode (ClientNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: d4d6df52-9e68-4003-9e28-ece6716ba7f1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba963bb14e46aaa3f098ae74cd7aca92019256e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616957"
---
# <a name="setnumericalvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="94768-102">SetNumericalValue-Methode (ClientNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="94768-102">SetNumericalValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="94768-103">Legt den numerischen Wert der aktuellen Eigenschaft fest, auf die durch den [PropertyIdx-Eigenschaftswert (ClientNetworkProtocolProperty-Klasse)](clientnetworkprotocolproperty-class.md) verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="94768-103">Sets the numeric value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94768-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94768-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="94768-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="94768-105">Parts</span></span>  
 <span data-ttu-id="94768-106">*object*</span><span class="sxs-lookup"><span data-stu-id="94768-106">*object*</span></span>  
 <span data-ttu-id="94768-107">A [ClientNetworkProtocolProperty-Klassenobjekt](clientnetworkprotocolproperty-class.md) , das ein Attribut des vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendeten Netzwerkprotokolls darstellt.</span><span class="sxs-lookup"><span data-stu-id="94768-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="94768-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="94768-108">Parameters</span></span>  
  
|<span data-ttu-id="94768-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="94768-109">Parameter</span></span>|<span data-ttu-id="94768-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94768-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="94768-111">*value*</span><span class="sxs-lookup"><span data-stu-id="94768-111">*value*</span></span>|<span data-ttu-id="94768-112">Ein u`uint32`-Wert, der den numerischen Wert der Eigenschaft angibt, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="94768-112">A `uint32` value that specifies the numeric value of the referenced property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="94768-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="94768-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="94768-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="94768-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94768-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="94768-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94768-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94768-116">See Also</span></span>  
 [<span data-ttu-id="94768-117">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="94768-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
