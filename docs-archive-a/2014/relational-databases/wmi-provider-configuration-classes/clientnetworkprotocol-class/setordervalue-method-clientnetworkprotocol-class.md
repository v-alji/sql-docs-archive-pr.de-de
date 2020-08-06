---
title: Setup Value-Methode (ClientNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetOrderValue Method (ClientNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetOrderValue method
ms.assetid: 15f693fd-37f6-41d9-9dab-d2c93db19895
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6839e85b6131c54e233d980c84a8727eeda2202a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622494"
---
# <a name="setordervalue-method-clientnetworkprotocol-class"></a><span data-ttu-id="9b3e0-102">SetOrderValue-Methode (ClientNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="9b3e0-102">SetOrderValue Method (ClientNetworkProtocol Class)</span></span>
  <span data-ttu-id="9b3e0-103">Wählt das Protokoll mit dem angegebenen Reihenfolgenwert aus der Clientprotokollliste aus.</span><span class="sxs-lookup"><span data-stu-id="9b3e0-103">Selects the protocol with the specified order value from the client protocol list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b3e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b3e0-104">Syntax</span></span>  
  
```  
  
object  
.SetOrderValue(  
OrderValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="9b3e0-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="9b3e0-105">Parts</span></span>  
 <span data-ttu-id="9b3e0-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9b3e0-106">*object*</span></span>  
 <span data-ttu-id="9b3e0-107">A [ClientNetworkProtocol-Klassenobjekt](clientnetworkprotocol-class.md) , das das vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Client verwendete Netzwerkprotokoll darstellt.</span><span class="sxs-lookup"><span data-stu-id="9b3e0-107">A [ClientNetworkProtocol Class](clientnetworkprotocol-class.md) object that represents the network protocol used by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="9b3e0-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b3e0-108">Parameters</span></span>  
  
|<span data-ttu-id="9b3e0-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b3e0-109">Parameter</span></span>|<span data-ttu-id="9b3e0-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b3e0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b3e0-111">*OrderValue*</span><span class="sxs-lookup"><span data-stu-id="9b3e0-111">*OrderValue*</span></span>|<span data-ttu-id="9b3e0-112">Ein u`int32`-Wert, der den Reihenfolgenwert festlegt.</span><span class="sxs-lookup"><span data-stu-id="9b3e0-112">A u`int32` value that sets the order value.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9b3e0-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b3e0-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="9b3e0-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="9b3e0-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b3e0-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9b3e0-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3e0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b3e0-116">See Also</span></span>  
 [<span data-ttu-id="9b3e0-117">Eigenschaften der Clientprotokolle (Registerkarte Reihenfolge)</span><span class="sxs-lookup"><span data-stu-id="9b3e0-117">Client Protocols Properties (Order Tab)</span></span>](https://technet.microsoft.com/library/ms187884.aspx)  
  
  
