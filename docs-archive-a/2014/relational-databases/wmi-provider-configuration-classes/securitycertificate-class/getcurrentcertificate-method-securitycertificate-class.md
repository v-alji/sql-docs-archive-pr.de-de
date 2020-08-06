---
title: GetCurrentCertificate-Methode (SecurityCertificate-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- GetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- GetCurrentCertificate method
ms.assetid: 987a2671-1801-45c4-93e6-29f883c58720
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ab96b2e2a8fabf9e9ccce647e54be1983fe40ca0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696637"
---
# <a name="getcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="f6862-102">GetCurrentCertificate-Methode (SecurityCertificate-Klasse)</span><span class="sxs-lookup"><span data-stu-id="f6862-102">GetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="f6862-103">Ruft das aktuelle Sicherheitszertifikat ab.</span><span class="sxs-lookup"><span data-stu-id="f6862-103">Gets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6862-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6862-104">Syntax</span></span>  
  
```  
  
object  
.GetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="f6862-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="f6862-105">Parts</span></span>  
 <span data-ttu-id="f6862-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f6862-106">*object*</span></span>  
 <span data-ttu-id="f6862-107">Ein [SecurityCertificate-Klassenobjekt](securitycertificate-class.md) , das ein Sicherheitszertifikat darstellt.</span><span class="sxs-lookup"><span data-stu-id="f6862-107">A [SecurityCertificate Class](securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="f6862-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6862-108">Parameters</span></span>  
  
|<span data-ttu-id="f6862-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6862-109">Parameter</span></span>|<span data-ttu-id="f6862-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6862-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f6862-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="f6862-111">*SHA*</span></span>|<span data-ttu-id="f6862-112">Ein Zeichenfolgen-Objektwert (Ausgabeparameter), der den aktuelln SHA-Fingerabdruck nach Abschluss der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="f6862-112">A string value (output parameter) that specifies the current security certificate SHA thumbprint after the method completes.</span></span>|  
|<span data-ttu-id="f6862-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="f6862-113">*SQLInstance*</span></span>|<span data-ttu-id="f6862-114">Ein Zeichenfolgenwert, der die Instanz angibt, für die das Zertifikat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f6862-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f6862-115">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6862-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="f6862-116">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="f6862-116">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6862-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f6862-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6862-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6862-118">See Also</span></span>  
 <span data-ttu-id="f6862-119">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f6862-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
