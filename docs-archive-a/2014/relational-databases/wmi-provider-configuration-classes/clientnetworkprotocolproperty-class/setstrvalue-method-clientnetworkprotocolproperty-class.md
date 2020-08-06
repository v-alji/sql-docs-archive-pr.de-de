---
title: Setstrevalue-Methode (ClientNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStrValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStrValue method
ms.assetid: 4ff80124-6e2e-4d96-a692-57c17b53c55e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f3c23eebdbe948e1b77c47ef56a04691fa391938
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724442"
---
# <a name="setstrvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="d7dcb-102">SetStrValue-Methode (ClientNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="d7dcb-102">SetStrValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="d7dcb-103">Legt den Zeichenfolgenwert der aktuellen Eigenschaft fest, auf die durch den [PropertyIdx-Eigenschaftswert (ClientNetworkProtocolProperty-Klasse)](clientnetworkprotocolproperty-class.md) verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d7dcb-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7dcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7dcb-104">Syntax</span></span>  
  
```  
  
object  
.SetStrValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d7dcb-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="d7dcb-105">Parts</span></span>  
 <span data-ttu-id="d7dcb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d7dcb-106">*object*</span></span>  
 <span data-ttu-id="d7dcb-107">A [ClientNetworkProtocolProperty-Klassenobjekt](clientnetworkprotocolproperty-class.md) , das ein Attribut des vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendeten Netzwerkprotokolls darstellt.</span><span class="sxs-lookup"><span data-stu-id="d7dcb-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d7dcb-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7dcb-108">Parameters</span></span>  
  
|<span data-ttu-id="d7dcb-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7dcb-109">Parameter</span></span>|<span data-ttu-id="d7dcb-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d7dcb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d7dcb-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="d7dcb-111">*StrValue*</span></span>|<span data-ttu-id="d7dcb-112">Ein Zeichenfolgenwert, der den neuen Wert der aktuellen Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="d7dcb-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d7dcb-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7dcb-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d7dcb-114">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="d7dcb-114">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7dcb-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d7dcb-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dcb-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7dcb-116">See Also</span></span>  
 [<span data-ttu-id="d7dcb-117">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="d7dcb-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
