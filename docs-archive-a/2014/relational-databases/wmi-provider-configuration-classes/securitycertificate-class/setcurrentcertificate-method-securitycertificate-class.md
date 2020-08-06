---
title: SetCurrentCertificate-Methode (SecurityCertificate-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetCurrentCertificate Method (SecurityCertificate Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetCurrentCertificate method
ms.assetid: 04b1a76a-932d-4824-8506-e346afe7554e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4c7065946c858b775e319578eb67c2b7186338f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615901"
---
# <a name="setcurrentcertificate-method-securitycertificate-class"></a><span data-ttu-id="5ee23-102">SetCurrentCertificate-Methode (SecurityCertificate-Klasse)</span><span class="sxs-lookup"><span data-stu-id="5ee23-102">SetCurrentCertificate Method (SecurityCertificate Class)</span></span>
  <span data-ttu-id="5ee23-103">Legt das aktuelle Sicherheitszertifikat fest.</span><span class="sxs-lookup"><span data-stu-id="5ee23-103">Sets the current security certificate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ee23-104">Syntax</span></span>  
  
```  
  
object  
.SetCurrentCertificate(  
SHA , SQLInstance  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="5ee23-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="5ee23-105">Parts</span></span>  
 <span data-ttu-id="5ee23-106">*object*</span><span class="sxs-lookup"><span data-stu-id="5ee23-106">*object*</span></span>  
 <span data-ttu-id="5ee23-107">Ein SecurityCertificate-Class.MD-Objekt (SecurityCertificate-Klasse]), das ein Sicherheitszertifikat darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ee23-107">A [SecurityCertificate Class]securitycertificate-class.md) object that represents a security certificate.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="5ee23-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ee23-108">Parameters</span></span>  
  
|<span data-ttu-id="5ee23-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ee23-109">Parameter</span></span>|<span data-ttu-id="5ee23-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5ee23-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ee23-111">*SHA*</span><span class="sxs-lookup"><span data-stu-id="5ee23-111">*SHA*</span></span>|<span data-ttu-id="5ee23-112">Ein Zeichenfolgenwert, der den Secure Hash Algorithm (SHA)-Fingerabdruck für das erforderliche Sicherheitszertifikat angibt.</span><span class="sxs-lookup"><span data-stu-id="5ee23-112">A string value that specifies the secure hash algorithm (SHA) thumbprint for the required security certificate.</span></span>|  
|<span data-ttu-id="5ee23-113">*SQLInstance*</span><span class="sxs-lookup"><span data-stu-id="5ee23-113">*SQLInstance*</span></span>|<span data-ttu-id="5ee23-114">Ein Zeichenfolgenwert, der die Instanz angibt, für die das Zertifikat erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5ee23-114">A string value that specifies the instance for which the certificate is required.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5ee23-115">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ee23-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="5ee23-116">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="5ee23-116">A uint32 value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee23-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5ee23-117">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee23-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ee23-118">See Also</span></span>  
 <span data-ttu-id="5ee23-119">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5ee23-119">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
