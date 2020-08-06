---
title: Setdeaktiviert-Methode (ServerNetworkProtocol-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDisable Method (ServerNetworkProtocol Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDisable method
ms.assetid: 0ebbe0c5-07ad-4a76-a918-e379930adf71
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3176227aba4de1e5aca1be35ec1f071a15caa49e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615895"
---
# <a name="setdisable-method-servernetworkprotocol-class"></a><span data-ttu-id="ca890-102">SetDisable-Methode (ServerNetworkProtocol-Klasse)</span><span class="sxs-lookup"><span data-stu-id="ca890-102">SetDisable Method (ServerNetworkProtocol Class)</span></span>
  <span data-ttu-id="ca890-103">Deaktiviert das Server-Netzwerkprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ca890-103">Disables the server network protocol.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca890-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca890-104">Syntax</span></span>  
  
```  
  
object  
.SetDisable()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="ca890-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="ca890-105">Parts</span></span>  
 <span data-ttu-id="ca890-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ca890-106">*object*</span></span>  
 <span data-ttu-id="ca890-107">Ein [ServerNetworkProtocol-Klasse] ServerNetworkProtocol-Class.MD)-Objekt, das das Netzwerkprotokoll darstellt, das von der Instanz von verwendet wird [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ca890-107">A [ServerNetworkProtocol Class]servernetworkprotocol-class.md) object that represents the network protocol used by the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ca890-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca890-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ca890-109">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="ca890-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca890-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ca890-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca890-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca890-111">See Also</span></span>  
 <span data-ttu-id="ca890-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ca890-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
