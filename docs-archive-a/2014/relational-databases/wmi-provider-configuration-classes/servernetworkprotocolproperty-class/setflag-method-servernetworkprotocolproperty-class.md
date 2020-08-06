---
title: SetFlag-Methode (ServerNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetFlag Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetFlag method
ms.assetid: 95288931-8eb1-4477-ad80-619cf7073e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a90b4fca194f20cc0a2d70c947577594155f051
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697633"
---
# <a name="setflag-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="1ab0d-102">SetFlag-Methode (ServerNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="1ab0d-102">SetFlag Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="1ab0d-103">Legt das Flag der Eigenschaft fest, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1ab0d-103">Sets the flag of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ab0d-104">Syntax</span></span>  
  
```  
  
object  
.SetFlag(  
BoolValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1ab0d-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1ab0d-105">Parts</span></span>  
 <span data-ttu-id="1ab0d-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1ab0d-106">*object*</span></span>  
 <span data-ttu-id="1ab0d-107">Eine [ServerNetworkProtocolProperty-Klasse] ServerNetworkProtocolProperty-Class.MD)-Objekt, das ein Attribut des Netzwerk Protokolls in der Instanz von darstellt [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ab0d-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="1ab0d-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ab0d-108">Parameters</span></span>  
  
|<span data-ttu-id="1ab0d-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ab0d-109">Parameter</span></span>|<span data-ttu-id="1ab0d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ab0d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ab0d-111">*Booleer Wert*</span><span class="sxs-lookup"><span data-stu-id="1ab0d-111">*BoolValue*</span></span>|<span data-ttu-id="1ab0d-112">Ein boleescher Wert, der den neuen Wert des Flags angibt.</span><span class="sxs-lookup"><span data-stu-id="1ab0d-112">A Boolean value that specifies the new value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1ab0d-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1ab0d-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="1ab0d-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="1ab0d-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab0d-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ab0d-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab0d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ab0d-116">See Also</span></span>  
 <span data-ttu-id="1ab0d-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1ab0d-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
