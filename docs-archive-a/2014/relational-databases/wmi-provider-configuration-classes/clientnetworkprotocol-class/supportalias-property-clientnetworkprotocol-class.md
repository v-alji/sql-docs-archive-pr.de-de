---
title: SupportAlias-Eigenschaft (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SupportAlias Property (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SupportAlias property
ms.assetid: 1e7a2e87-c356-40a6-a6d9-e492467629f9
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6fd06ad0921dbb113a89af77e46733a28c2226c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622488"
---
# <a name="supportalias-property-clientnetworkprotocol-class"></a><span data-ttu-id="a1578-102">SupportAlias-Eigenschaft (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="a1578-102">SupportAlias Property (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="a1578-103">Ruft die boolesche Eigenschaft ab, die angibt, ob das durch die [SetOrderValue-Methode (ClientNetworkProtocol-Klasse)](clientnetworkprotocol-class.md) angegebene aktuelle Netzwerkprotokoll Aliase unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1578-103">Gets the Boolean property that specifies whether the current network protocol specified by the [SetOrderValue Method (ClientNetworkProtocol Class)](clientnetworkprotocol-class.md) support aliases.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1578-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1578-104">Syntax</span></span>  
  
```  
  
object  
.SupportAlias [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="a1578-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="a1578-105">Parts</span></span>  
 <span data-ttu-id="a1578-106">*object*</span><span class="sxs-lookup"><span data-stu-id="a1578-106">*object*</span></span>  
 <span data-ttu-id="a1578-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="a1578-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a1578-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a1578-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a1578-109">Ein boolescher Wert, der angibt, ob das Clientnetzwerkprotokoll Aliase unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a1578-109">A Boolean value that specifies whether the client network protocol supports aliases.</span></span>  
  
 <span data-ttu-id="a1578-110">Wenn der Wert "True" lautet, unterstützt das Clientnetzwerkprotokoll Aliase.</span><span class="sxs-lookup"><span data-stu-id="a1578-110">If True, the client network protocol supports aliases.</span></span>  
  
 <span data-ttu-id="a1578-111">Wenn der Wert "False" lautet, unterstützt das Clientnetzwerkprotokoll keine Aliase.</span><span class="sxs-lookup"><span data-stu-id="a1578-111">If False, the client network protocol does not support aliases.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1578-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a1578-112">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1578-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1578-113">See Also</span></span>  
 [<span data-ttu-id="a1578-114">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="a1578-114">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
