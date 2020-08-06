---
title: RemoveCertificate-Methode (ServerSettings-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (ServerSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 9ffdbc39-93f5-48fb-859a-86a3ad545827
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 00731fab5c4bdec61848df93829dd5013a7454f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696597"
---
# <a name="removecertificate-method-serversettings-class"></a><span data-ttu-id="e7d79-102">RemoveCertificate-Methode (ServerSettings-Klasse)</span><span class="sxs-lookup"><span data-stu-id="e7d79-102">RemoveCertificate Method (ServerSettings Class)</span></span>
  <span data-ttu-id="e7d79-103">Entfernt das aktuelle Sicherheitszertifikat aus der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7d79-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7d79-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="e7d79-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="e7d79-105">Parts</span></span>  
 <span data-ttu-id="e7d79-106">*object*</span><span class="sxs-lookup"><span data-stu-id="e7d79-106">*object*</span></span>  
 <span data-ttu-id="e7d79-107">Ein [ServerSettings-Klassenobjekt](serversettings-class.md) , das die Servereinstellungen in einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7d79-107">A [ServerSettings Class](serversettings-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e7d79-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7d79-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="e7d79-109">Ein u`int32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="e7d79-109">A u`int32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7d79-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e7d79-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7d79-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7d79-111">See Also</span></span>  
 <span data-ttu-id="e7d79-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="e7d79-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
