---
title: RemoveCertificate-Methode (SInstance-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- RemoveCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveCertificate method
ms.assetid: 7e5dbafa-a634-4617-9622-510514fce0ce
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4b876cd75778d1da9c9a46f65f39b915ebee0552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696593"
---
# <a name="removecertificate-method-sinstance-class"></a><span data-ttu-id="7a6d3-102">RemoveCertificate-Methode (SInstance-Klasse)</span><span class="sxs-lookup"><span data-stu-id="7a6d3-102">RemoveCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="7a6d3-103">Entfernt das aktuelle Sicherheitszertifikat aus der Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a6d3-103">Removes the current security certificate from the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a6d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a6d3-104">Syntax</span></span>  
  
```  
  
object  
.RemoveCertificate()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7a6d3-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7a6d3-105">Parts</span></span>  
 <span data-ttu-id="7a6d3-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7a6d3-106">*object*</span></span>  
 <span data-ttu-id="7a6d3-107">Ein [SInstance-Klassenobjekt](sinstance-class.md) , das die Servereinstellungen in einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="7a6d3-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7a6d3-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a6d3-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="7a6d3-109">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="7a6d3-109">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a6d3-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7a6d3-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a6d3-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a6d3-111">See Also</span></span>  
 <span data-ttu-id="7a6d3-112">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7a6d3-112">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
