---
title: SetStringValue-Methode (ClientNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ClientNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 88d67b22-0eea-48c9-ab73-e0b4907953df
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ba2350b798f1d7092a37a28ca35c17d6f4536a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724446"
---
# <a name="setstringvalue-method-clientnetworkprotocolproperty-class"></a><span data-ttu-id="e2d6b-102">SetStringValue-Methode (ClientNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="e2d6b-102">SetStringValue Method (ClientNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="e2d6b-103">Legt den Zeichenfolgenwert der aktuellen Eigenschaft fest, auf die durch den [PropertyIdx-Eigenschaftswert (ClientNetworkProtocolProperty-Klasse)](clientnetworkprotocolproperty-class.md) verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e2d6b-103">Sets the string value of the current property referenced by the [PropertyIdx Property (ClientNetworkProtocolProperty Class)](clientnetworkprotocolproperty-class.md) value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2d6b-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e2d6b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="e2d6b-105">Parts</span></span>  
 <span data-ttu-id="e2d6b-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e2d6b-106">*object*</span></span>  
 <span data-ttu-id="e2d6b-107">A [ClientNetworkProtocolProperty-Klassenobjekt](clientnetworkprotocolproperty-class.md) , das ein Attribut des vom [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendeten Netzwerkprotokolls darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2d6b-107">A [ClientNetworkProtocolProperty Class](clientnetworkprotocolproperty-class.md) object that represents an attribute of the network protocol used by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="e2d6b-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2d6b-108">Parameters</span></span>  
  
|<span data-ttu-id="e2d6b-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2d6b-109">Parameter</span></span>|<span data-ttu-id="e2d6b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e2d6b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2d6b-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="e2d6b-111">*StrValue*</span></span>|<span data-ttu-id="e2d6b-112">Ein Zeichenfolgenwert, der den neuen Wert der aktuellen Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="e2d6b-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e2d6b-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2d6b-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e2d6b-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="e2d6b-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2d6b-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e2d6b-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d6b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2d6b-116">See Also</span></span>  
 [<span data-ttu-id="e2d6b-117">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="e2d6b-117">Configure Client Protocols</span></span>](../../../database-engine/configure-windows/configure-client-protocols.md)  
  
  
