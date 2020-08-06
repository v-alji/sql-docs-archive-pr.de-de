---
title: Setdeaktiviert-Methode (ServerNetworkProtocolIPAddress-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocolIPAddress Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 7a7cc8cc-9fb8-4bf5-b483-2150d633ee10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9fbe928de1144c3065ddabb07bfd48606fdcea51
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696630"
---
# <a name="setdisable-method-servernetworkprotocolipaddress-class"></a><span data-ttu-id="ec592-102">SetDisable-Methode (ServerNetworkProtocolIPAddress-Klasse)</span><span class="sxs-lookup"><span data-stu-id="ec592-102">SetDisable Method (ServerNetworkProtocolIPAddress Class)</span></span>
  <span data-ttu-id="ec592-103">Deaktiviert die IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ec592-103">Disables the IP address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec592-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec592-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ec592-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="ec592-105">Parts</span></span>  
 <span data-ttu-id="ec592-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ec592-106">*object*</span></span>  
 <span data-ttu-id="ec592-107">Eine [ServerNetworkProtocolIPAddress-Klasse] ServerNetworkProtocolIPAddress-Class.MD)-Objekt, das eine IP-Adresse für das Netzwerkprotokoll in einer Instanz von darstellt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ec592-107">A [ServerNetworkProtocolIPAdress Class]servernetworkprotocolipaddress-class.md) object that represents an IP address for the network protocol on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ec592-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec592-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ec592-109">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="ec592-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec592-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ec592-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec592-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec592-111">See Also</span></span>  
 <span data-ttu-id="ec592-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ec592-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
