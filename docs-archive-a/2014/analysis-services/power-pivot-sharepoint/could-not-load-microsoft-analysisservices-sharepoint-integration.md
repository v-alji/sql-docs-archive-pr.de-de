---
title: Die Datei oder Assembly &#39;"Microsoft. Data. Services, Version = 5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; oder einer ihrer Abhängigkeiten konnte nicht geladen werden. Die angegebene Datei wurde nicht gefunden. | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f9eed7ad90c1e720d07c714e351c24ae6657717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620584"
---
# <a name="could-not-load-file-or-assembly-39microsoftdataservices-version3500-cultureneutral-publickeytokenb77a5c561934e08939-or-one-of-its-dependencies-the-system-cannot-find-the-file-specified"></a><span data-ttu-id="8064c-104">Die Datei oder Assembly &#39;"Microsoft. Data. Services, Version = 5.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089&#39; oder einer ihrer Abhängigkeiten konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="8064c-104">Could not load file or assembly &#39;Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089&#39; or one of its dependencies.</span></span> <span data-ttu-id="8064c-105">Die angegebene Datei wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8064c-105">The system cannot find the file specified.</span></span>
  <span data-ttu-id="8064c-106">In SharePoint 2010-Umgebungen mit PowerPivot für SharePoint tritt dieser Fehler auf, wenn Sie versuchen, einen Datenfeed zu exportieren und das System nicht über die erforderliche Version von Microsoft ADO.NET Data Services verfügt.</span><span class="sxs-lookup"><span data-stu-id="8064c-106">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if you attempt a data feed export and the system is missing the required version of Microsoft ADO.NET Data Services.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8064c-107">Details</span><span class="sxs-lookup"><span data-stu-id="8064c-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8064c-108">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="8064c-108">Applies to</span></span>|<span data-ttu-id="8064c-109">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="8064c-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="8064c-110">Produktversion</span><span class="sxs-lookup"><span data-stu-id="8064c-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="8064c-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8064c-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="8064c-112">Ursache</span><span class="sxs-lookup"><span data-stu-id="8064c-112">Cause</span></span>|<span data-ttu-id="8064c-113">ADO.NET Data Services 3.5 SP1 wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8064c-113">ADO.NET Data Services 3.5 SP1 was not found.</span></span>|  
|<span data-ttu-id="8064c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="8064c-114">Message Text</span></span>|<span data-ttu-id="8064c-115">Die Datei oder Assembly "Microsoft.Data.Services, Version=3 .5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" oder eine Abhängigkeit davon wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8064c-115">Could not load file or assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies.</span></span> <span data-ttu-id="8064c-116">Die angegebene Datei wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8064c-116">The system cannot find the file specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8064c-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="8064c-117">Explanation</span></span>  
 <span data-ttu-id="8064c-118">SharePoint 2010 enthält die Schaltfläche Als Datenfeed exportieren, mit der Sie eine SharePoint-Liste als XML-Datenfeed exportieren können.</span><span class="sxs-lookup"><span data-stu-id="8064c-118">SharePoint 2010 includes an Export as Data Feed button that you can use to export a SharePoint list as an XML data feed.</span></span> <span data-ttu-id="8064c-119">Außerdem unterstützen sowohl Reporting Services in SharePoint-Modus als auch PowerPivot für SharePoint Datenfeedfunktionen, die ADO.NET Data Services erfordern.</span><span class="sxs-lookup"><span data-stu-id="8064c-119">In addition, both Reporting Services in SharePoint mode and PowerPivot for SharePoint support data feed features that require ADO.NET Data Services.</span></span>  
  
 <span data-ttu-id="8064c-120">Wenn ADO.NET Data Services nicht installiert sind, tritt dieser Fehler beim Anfordern eines Datenfeeds auf.</span><span class="sxs-lookup"><span data-stu-id="8064c-120">If ADO.NET Data Services is not installed, this error will occur when you request a data feed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8064c-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="8064c-121">User Action</span></span>  
  
1.  <span data-ttu-id="8064c-122">Wechseln Sie zur Dokumentation zu Hardware-und Softwareanforderungen für SharePoint 2010, und bestimmen Sie die [Hardware-und Softwareanforderungen (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) ( https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="8064c-122">Go to the hardware and software requirements documentation for SharePoint 2010, [Determine Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) (https://go.microsoft.com/fwlink/?LinkId=169734).</span></span>  
  
2.  <span data-ttu-id="8064c-123">Suchen Sie unter **Installieren der erforderlichen Software**den Link für ADO.NET Data Services 3.5, der dem verwendeten Betriebssystem entspricht.</span><span class="sxs-lookup"><span data-stu-id="8064c-123">In **Installing software prerequisites**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using.</span></span>  
  
3.  <span data-ttu-id="8064c-124">Klicken Sie auf den Link, und führen Sie das Setupprogramm aus, durch das der Dienst installiert wird.</span><span class="sxs-lookup"><span data-stu-id="8064c-124">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8064c-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8064c-125">See Also</span></span>  
 [<span data-ttu-id="8064c-126">Bereitstellen von PowerPivot-Lösungen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="8064c-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
