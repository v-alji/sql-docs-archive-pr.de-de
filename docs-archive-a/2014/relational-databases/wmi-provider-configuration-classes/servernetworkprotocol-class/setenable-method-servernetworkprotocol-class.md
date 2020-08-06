---
title: Server able-Methode (ServerNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetEnable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEnable method
ms.assetid: a287950b-086f-4b6d-a2d8-4d3973bd1b21
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8f77b7a92fe226e349a03ffba03cfe8d67c280e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615893"
---
# <a name="setenable-method-servernetworkprotocol-class"></a><span data-ttu-id="f1e6f-102">SetEnable-Methode (ServerNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="f1e6f-102">SetEnable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="f1e6f-103">Aktiviert das Server-Netzwerkprotokoll.</span><span class="sxs-lookup"><span data-stu-id="f1e6f-103">Enables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1e6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1e6f-104">Syntax</span></span>  
  
```  
  
object  
.SetEnable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f1e6f-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="f1e6f-105">Parts</span></span>  
 <span data-ttu-id="f1e6f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f1e6f-106">*object*</span></span>  
 <span data-ttu-id="f1e6f-107">A [ServerNetworkProtocol-Klassenobjekt](servernetworkprotocol-class.md) , das das Netzwerkprotokoll darstellt, das von der Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f1e6f-107">A [ServerNetworkProtocol Class](servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f1e6f-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f1e6f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f1e6f-109">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="f1e6f-109">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1e6f-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f1e6f-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e6f-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1e6f-111">See Also</span></span>  
 <span data-ttu-id="f1e6f-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f1e6f-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
