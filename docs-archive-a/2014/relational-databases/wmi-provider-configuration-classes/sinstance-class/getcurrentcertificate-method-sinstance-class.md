---
title: GetCurrentCertificate-Methode (SInstance-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 9d2b72df-cb21-414a-abef-917f13d4de62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 47838190e3791e01f8482e3fb064a9dca3a764af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630554"
---
# <a name="getcurrentcertificate-method-sinstance-class"></a><span data-ttu-id="7d56a-102">GetCurrentCertificate-Methode (SInstance-Klasse)</span><span class="sxs-lookup"><span data-stu-id="7d56a-102">GetCurrentCertificate Method (SInstance Class)</span></span>
  <span data-ttu-id="7d56a-103">Ruft das aktuelle Sicherheitszertifikat ab.</span><span class="sxs-lookup"><span data-stu-id="7d56a-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d56a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d56a-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7d56a-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7d56a-105">Parts</span></span>  
 <span data-ttu-id="7d56a-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7d56a-106">*object*</span></span>  
 <span data-ttu-id="7d56a-107">Ein [SInstance-Klassenobjekt](sinstance-class.md) , das die Servereinstellungen in einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d56a-107">An [SInstance Class](sinstance-class.md) object that represents the server settings on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="7d56a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d56a-108">Parameters</span></span>  
  
|<span data-ttu-id="7d56a-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d56a-109">Parameter</span></span>|<span data-ttu-id="7d56a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7d56a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d56a-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="7d56a-111">*SHA*</span></span>|<span data-ttu-id="7d56a-112">Ein Zeichenfolgen-Objektwert (Ausgabeparameter), das das aktuelle Sicherheitszertifikat nach Abschluss der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="7d56a-112">A string object value (output parameter) that specifies the current security certificate after the method completes.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7d56a-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d56a-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="7d56a-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="7d56a-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d56a-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7d56a-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d56a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d56a-116">See Also</span></span>  
 <span data-ttu-id="7d56a-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7d56a-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
