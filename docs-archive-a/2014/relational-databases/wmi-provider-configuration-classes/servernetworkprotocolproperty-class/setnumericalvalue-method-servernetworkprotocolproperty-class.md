---
title: SetNumericalValue-Methode (ServerNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetNumericalValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetNumericalValue method
ms.assetid: b3b4bce8-9d9e-4ccb-a223-0454281353b0
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: f5a4b8d6819dae11abe4cc097f0e423c23d909e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617854"
---
# <a name="setnumericalvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="7712a-102">SetNumericalValue-Methode (ServerNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="7712a-102">SetNumericalValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="7712a-103">Legt den numerischen Wert der Eigenschaft fest, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7712a-103">Sets the numeric value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7712a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7712a-104">Syntax</span></span>  
  
```  
  
object  
.SetNumericalValue(  
NumValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7712a-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7712a-105">Parts</span></span>  
 <span data-ttu-id="7712a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7712a-106">*object*</span></span>  
 <span data-ttu-id="7712a-107">Eine [ServerNetworkProtocolProperty-Klasse] ServerNetworkProtocolProperty-Class.MD)-Objekt, das ein Attribut des Netzwerk Protokolls in der Instanz von darstellt [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7712a-107">A [ServerNetworkProtocolProperty Class]servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="7712a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7712a-108">Parameters</span></span>  
  
|<span data-ttu-id="7712a-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="7712a-109">Parameter</span></span>|<span data-ttu-id="7712a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7712a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7712a-111">*NumValue*</span><span class="sxs-lookup"><span data-stu-id="7712a-111">*NumValue*</span></span>|<span data-ttu-id="7712a-112">Ein `uint32`-Wert, der den neuen Wert der aktuellen Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="7712a-112">A `uint32` value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7712a-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7712a-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="7712a-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="7712a-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7712a-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7712a-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7712a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7712a-116">See Also</span></span>  
 <span data-ttu-id="7712a-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7712a-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
