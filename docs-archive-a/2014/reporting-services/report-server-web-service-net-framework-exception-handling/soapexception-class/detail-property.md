---
title: Detail-Eigenschaft | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Detail property
- SoapException class
ms.assetid: c1ddaeb6-c540-49fa-b06e-b6359d377ee8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 060fbaba2b8d4f5a5171e8aa7995432622ba2ba0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719534"
---
# <a name="detail-property"></a><span data-ttu-id="e96da-102">Detail-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e96da-102">Detail Property</span></span>
  <span data-ttu-id="e96da-103">Die XML-Struktur der **Detail**-Eigenschaft der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException**-Klasse in  sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e96da-103">The **Detail** property of the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] **SoapException** class has the following XML structure:</span></span>  
  
## <a name="elements"></a><span data-ttu-id="e96da-104">Elemente</span><span class="sxs-lookup"><span data-stu-id="e96da-104">Elements</span></span>  
 <span data-ttu-id="e96da-105">**Detail**</span><span class="sxs-lookup"><span data-stu-id="e96da-105">**Detail**</span></span>  
 <span data-ttu-id="e96da-106">Das Element der obersten Ebene, das alle anderen Fehlerdetailelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="e96da-106">The top-level element that contains all other error detail elements.</span></span>  
  
 <span data-ttu-id="e96da-107">**ErrorCode**</span><span class="sxs-lookup"><span data-stu-id="e96da-107">**ErrorCode**</span></span>  
 <span data-ttu-id="e96da-108">Der [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-spezifische Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e96da-108">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-specific error code.</span></span>  
  
 <span data-ttu-id="e96da-109">**HttpStatus**</span><span class="sxs-lookup"><span data-stu-id="e96da-109">**HttpStatus**</span></span>  
 <span data-ttu-id="e96da-110">Der HTTP-Statuscode.</span><span class="sxs-lookup"><span data-stu-id="e96da-110">The HTTP status code.</span></span>  
  
 <span data-ttu-id="e96da-111">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e96da-111">**Message**</span></span>  
 <span data-ttu-id="e96da-112">Die Fehlermeldung und der Fehlercode, die vom Berichtsserver zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e96da-112">The error message and the error code assigned by the report server.</span></span>  
  
 <span data-ttu-id="e96da-113">**HelpLink**</span><span class="sxs-lookup"><span data-stu-id="e96da-113">**HelpLink**</span></span>  
 <span data-ttu-id="e96da-114">Die HelpLink-URL zu einer Website, unter der weitere Informationen zum Fehler zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e96da-114">The Help link URL to a Web site at which further information about the error can be found.</span></span> <span data-ttu-id="e96da-115">Weitere Informationen finden Sie unter [HelpLink-Element](helplink-element.md).</span><span class="sxs-lookup"><span data-stu-id="e96da-115">For more information, see [HelpLink Element](helplink-element.md).</span></span>  
  
 <span data-ttu-id="e96da-116">**LinkID**</span><span class="sxs-lookup"><span data-stu-id="e96da-116">**LinkID**</span></span>  
 <span data-ttu-id="e96da-117">Die dem Link zugewiesene ID.</span><span class="sxs-lookup"><span data-stu-id="e96da-117">The ID assigned to the link.</span></span>  
  
 <span data-ttu-id="e96da-118">**ProductName**</span><span class="sxs-lookup"><span data-stu-id="e96da-118">**ProductName**</span></span>  
 <span data-ttu-id="e96da-119">Der Name des Produkts.</span><span class="sxs-lookup"><span data-stu-id="e96da-119">The name of the product.</span></span> <span data-ttu-id="e96da-120">Der Standardwert ist **Microsoft SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="e96da-120">The default value is **Microsoft SQL Server Reporting Services**.</span></span>  
  
 <span data-ttu-id="e96da-121">**ProductVersion**</span><span class="sxs-lookup"><span data-stu-id="e96da-121">**ProductVersion**</span></span>  
 <span data-ttu-id="e96da-122">Die Version von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e96da-122">The version of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="e96da-123">Die maximale Länge beträgt 15 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e96da-123">The maximum length is 15 characters.</span></span> <span data-ttu-id="e96da-124">Das Format der Versionsnummer sollte folgendermaßen sein: 8.00.0xxx.00.</span><span class="sxs-lookup"><span data-stu-id="e96da-124">The format of the version number should be as follows: 8.00.0xxx.00.</span></span>  
  
 <span data-ttu-id="e96da-125">**ProductLocaleId**</span><span class="sxs-lookup"><span data-stu-id="e96da-125">**ProductLocaleId**</span></span>  
 <span data-ttu-id="e96da-126">Die Gebietsschema- oder Sprach-ID der INTL DLL (z.B. 0x41A) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e96da-126">The locale ID or language ID of the application's INTL DLL (for example, 0x41A).</span></span>  
  
 <span data-ttu-id="e96da-127">**OperatingSystem**</span><span class="sxs-lookup"><span data-stu-id="e96da-127">**OperatingSystem**</span></span>  
 <span data-ttu-id="e96da-128">Das Betriebssystem, auf dem [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e96da-128">The operating system [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is installed on.</span></span> <span data-ttu-id="e96da-129">Gültige Werte sind: **0** für betriebssystemunabhängig, **1** für [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)] und **16** für Windows XP.</span><span class="sxs-lookup"><span data-stu-id="e96da-129">Valid values include **0** for operating system independent, **1** for [!INCLUDE[win2kfamily](../../../includes/win2kfamily-md.md)], and **16** for Windows XP.</span></span>  
  
 <span data-ttu-id="e96da-130">**CountryLocaleId**</span><span class="sxs-lookup"><span data-stu-id="e96da-130">**CountryLocaleId**</span></span>  
 <span data-ttu-id="e96da-131">Die Gebietsschema- oder Sprach-ID des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="e96da-131">The locale ID or language ID of the operating system.</span></span> <span data-ttu-id="e96da-132">Der Wert für die französische Version von Windows kann z. B. "0x040c" sein.</span><span class="sxs-lookup"><span data-stu-id="e96da-132">For example, the value for the French version of Windows is 0x040c.</span></span>  
  
 <span data-ttu-id="e96da-133">**MoreInformation**</span><span class="sxs-lookup"><span data-stu-id="e96da-133">**MoreInformation**</span></span>  
 <span data-ttu-id="e96da-134">Eine XML-Zeichenfolge, die geschachtelte Ausnahmen enthält, die während der Ausführung der Methode aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="e96da-134">An XML string that contains nested exceptions that occurred while the method ran.</span></span>  
  
 <span data-ttu-id="e96da-135">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="e96da-135">**Source**</span></span>  
 <span data-ttu-id="e96da-136">Ein untergeordnetes Element von **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="e96da-136">A child element of **MoreInformation**.</span></span> <span data-ttu-id="e96da-137">Die Ursache des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="e96da-137">The source of the error.</span></span>  
  
 <span data-ttu-id="e96da-138">**Meldung**</span><span class="sxs-lookup"><span data-stu-id="e96da-138">**Message**</span></span>  
 <span data-ttu-id="e96da-139">Ein untergeordnetes Element von **MoreInformation**.</span><span class="sxs-lookup"><span data-stu-id="e96da-139">A child element of **MoreInformation**.</span></span> <span data-ttu-id="e96da-140">Die Fehlermeldung einer verschachtelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="e96da-140">The error message of a nested exception.</span></span> <span data-ttu-id="e96da-141">Dieses Element enthält XML-Attribute für **ErrorCode** und **HelpLink**.</span><span class="sxs-lookup"><span data-stu-id="e96da-141">This element includes XML attributes for **ErrorCode** and **HelpLink**.</span></span>  
  
 <span data-ttu-id="e96da-142">**Warnungen**</span><span class="sxs-lookup"><span data-stu-id="e96da-142">**Warnings**</span></span>  
 <span data-ttu-id="e96da-143">Eine XML-Zeichenfolge, die die von der Berichtsverarbeitung zurückgegebenen Warnungen enthält.</span><span class="sxs-lookup"><span data-stu-id="e96da-143">An XML string that contains the warnings returned from report processing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96da-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e96da-144">See Also</span></span>  
 <span data-ttu-id="e96da-145">[Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e96da-145">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="e96da-146">[Reporting Services SoapException-Klasse](reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="e96da-146">[Reporting Services SoapException Class](reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="e96da-147">Verwenden der Detail-Eigenschaft zur Handhabung bestimmter Fehler</span><span class="sxs-lookup"><span data-stu-id="e96da-147">Using the Detail Property to Handle Specific Errors</span></span>](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
