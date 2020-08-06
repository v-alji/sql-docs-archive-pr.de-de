---
title: SetStringValue-Methode (ServerNetworkProtocolProperty-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStringValue Method (ServerNetworkProtocolProperty Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStringValue method
ms.assetid: 0911df30-55f7-4fca-a1fb-01d2c91c1467
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8eb4a27d700d801e3ca94362663c6d7feaa7dc86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696622"
---
# <a name="setstringvalue-method-servernetworkprotocolproperty-class"></a><span data-ttu-id="ba5c3-102">SetStringValue-Methode (ServerNetworkProtocolProperty-Klasse)</span><span class="sxs-lookup"><span data-stu-id="ba5c3-102">SetStringValue Method (ServerNetworkProtocolProperty Class)</span></span>
  <span data-ttu-id="ba5c3-103">Legt den Zeichenfolgenwert der Eigenschaft fest, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-103">Sets the string value of the referenced property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba5c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba5c3-104">Syntax</span></span>  
  
```  
  
object  
.SetStringValue(  
StrValue  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ba5c3-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="ba5c3-105">Parts</span></span>  
 <span data-ttu-id="ba5c3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ba5c3-106">*object*</span></span>  
 <span data-ttu-id="ba5c3-107">A [ServerNetworkProtocolProperty-Klassenobjekt](servernetworkprotocolproperty-class.md) , das ein Attribut des Netzwerkprotokolls in der Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-107">A [ServerNetworkProtocolProperty Class](servernetworkprotocolproperty-class.md) object that represents an attribute of the network protocol on the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="ba5c3-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba5c3-108">Parameters</span></span>  
  
|<span data-ttu-id="ba5c3-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba5c3-109">Parameter</span></span>|<span data-ttu-id="ba5c3-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ba5c3-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba5c3-111">*StrValue*</span><span class="sxs-lookup"><span data-stu-id="ba5c3-111">*StrValue*</span></span>|<span data-ttu-id="ba5c3-112">Ein Zeichenfolgenwert, der den neuen Wert der aktuellen Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-112">A string value that specifies the new value of the current property.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ba5c3-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba5c3-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="ba5c3-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba5c3-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ba5c3-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba5c3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba5c3-116">See Also</span></span>  
 <span data-ttu-id="ba5c3-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ba5c3-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
