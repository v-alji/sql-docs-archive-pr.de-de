---
title: SetCurrentCertificate-Methode (SInstance-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 7349fb87-b973-4160-a2be-cab73abf5b31
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 44e65ab30659cacca09e63a94a1f3596a182dda5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696594"
---
# <a name="setcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="d5891-102">SetCurrentCertificate-Methode (SInstance-Klasse)</span><span class="sxs-lookup"><span data-stu-id="d5891-102">SetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="d5891-103">Legt das aktuelle Sicherheitszertifikat fest.</span><span class="sxs-lookup"><span data-stu-id="d5891-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5891-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5891-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="d5891-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="d5891-105">Parts</span></span>  
 <span data-ttu-id="d5891-106">*object*</span><span class="sxs-lookup"><span data-stu-id="d5891-106">*object*</span></span>  
 <span data-ttu-id="d5891-107">Ein [SInstance-Klassenobjekt](sinstance-class.md) , das die Servereinstellungen in einer Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5891-107">An [SInstance Class](sinstance-class.md) object that represents the server setting on an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="d5891-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5891-108">Parameters</span></span>  
  
|<span data-ttu-id="d5891-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5891-109">Parameter</span></span>|<span data-ttu-id="d5891-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5891-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5891-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="d5891-111">*SHA*</span></span>|<span data-ttu-id="d5891-112">Ein Zeichenfolgenwert, der das aktuelle Sicherheitszertifikat angibt.</span><span class="sxs-lookup"><span data-stu-id="d5891-112">A string value that specifies the current security certificate.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d5891-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d5891-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="d5891-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="d5891-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5891-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d5891-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5891-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5891-116">See Also</span></span>  
 <span data-ttu-id="d5891-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d5891-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
