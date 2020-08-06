---
title: PropertyValType-Eigenschaft (ServerNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PropertyValType Property (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PropertyValType property
ms.assetid: fbd42e8e-0642-4a19-b3c8-6ce88345145f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: be6c42fbaa36080ec8144d95abb045a3b4328057
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723634"
---
# <a name="propertyvaltype-property-servernetworkprotocolproperty-class"></a><span data-ttu-id="e2e24-102">PropertyValType-Eigenschaft (ServerNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="e2e24-102">PropertyValType Property (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="e2e24-103">Ruft den Datentyp des Werts ab, der in der referenzierten Eigenschaft enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e2e24-103">Gets the data type of the value stored in the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e24-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2e24-104">Syntax</span></span>  
  
```  
  
object  
.PropertyValType [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="e2e24-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="e2e24-105">Parts</span></span>  
 <span data-ttu-id="e2e24-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e2e24-106">*object*</span></span>  
 <span data-ttu-id="e2e24-107">A [ServerNetworkProtocolProperty-Klassenobjekt](servernetworkprotocolproperty-class.md) , das ein Attribut des Netzwerkprotokolls in der Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2e24-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e2e24-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e2e24-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="e2e24-109">Ein `uint32`-Wert, der den Datentyp des Eigenschaftswerts angibt.</span><span class="sxs-lookup"><span data-stu-id="e2e24-109">A `uint32` value that specifies the data type of the property value.</span></span> <span data-ttu-id="e2e24-110">Bei einem Zeichenfolgenwert wird 0 und bei einem numerischen Typ 1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e2e24-110">It returns 0 for a string value and 1 for a numerical type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2e24-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e2e24-111">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e24-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2e24-112">See Also</span></span>  
 <span data-ttu-id="e2e24-113">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e2e24-113">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
