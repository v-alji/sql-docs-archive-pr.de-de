---
title: Auf der Berichts Serversite wurden ISAPI-Filter erkannt (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- ISAPI filters
- report servers [Reporting Services], upgrade issues
ms.assetid: dd30560d-9e16-47c7-ba68-a9743a657e4e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: bff1834ddf1b8f90787a47a8fd58a240d2b715d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724397"
---
# <a name="isapi-filters-detected-on-the-report-server-site-upgrade-advisor"></a><span data-ttu-id="0e019-102">Auf der Berichtsserversite wurden ISAPI-Filter erkannt (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="0e019-102">ISAPI filters detected on the report server site (Upgrade Advisor)</span></span>
  <span data-ttu-id="0e019-103">Upgrade Advisor hat mindestens einen ISAPI-Filter auf der Website gefunden, die die virtuellen Verzeichnisse des Berichtsservers und des Berichts-Managers hostet.</span><span class="sxs-lookup"><span data-stu-id="0e019-103">Upgrade Advisor detected one or more ISAPI filters on the Web site that hosts the report server and Report Manager virtual directories.</span></span> <span data-ttu-id="0e019-104">ISAPI-Filter werden in nicht unterstützt [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e019-104">ISAPI filters are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
||  
|-|  
|<span data-ttu-id="0e019-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheimischen.</span><span class="sxs-lookup"><span data-stu-id="0e019-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native .</span></span>|  
  
## <a name="component"></a><span data-ttu-id="0e019-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="0e019-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="0e019-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e019-107">Description</span></span>  
 <span data-ttu-id="0e019-108">Überprüfen Sie vor dem Upgrade, ob die ISAPI-Filter der Website von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0e019-108">Before upgrading, verify whether the ISAPI filters on the Web site are used by [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] applications.</span></span> <span data-ttu-id="0e019-109">Wenn Sie den ISAPI-Filter nicht benötigen, können Sie den Berichtsserver aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="0e019-109">If you do not require the ISAPI filter, you can upgrade the report server.</span></span> <span data-ttu-id="0e019-110">Setup erstellt die Standard-URLs ohne Unterstützung für den ISAPI-Filter, der in IIS ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0e019-110">Setup will create the default URLs, without support for the ISAPI filter that runs in IIS.</span></span> <span data-ttu-id="0e019-111">Wenn Sie den ISAPI-Filter benötigen, dürfen Sie das Upgrade erst durchführen, wenn Sie eine Alternative zum Hosten des ISAPI-Filters gefunden haben (indem Sie z. B. den ISA Server verwenden oder den ISAPI-Filter weiterhin in IIS hosten).</span><span class="sxs-lookup"><span data-stu-id="0e019-111">If you require the ISAPI filter, do not upgrade until you find an alternative way of hosting the ISAPI filter (for example, using ISA Server or continuing to host the ISAPI filter in IIS).</span></span> <span data-ttu-id="0e019-112">Der Berichtsserver unterstützt in bestimmten Szenarios HttpModules von ASP.NET als Ersatz für ISAPI-Filter.</span><span class="sxs-lookup"><span data-stu-id="0e019-112">The report server supports ASP.NET HTTPModules as a replacement for ISAPI filters in certain scenarios.</span></span> <span data-ttu-id="0e019-113">Weitere Informationen finden Sie in der Dokumentation zu ASP.NET in MSDN.</span><span class="sxs-lookup"><span data-stu-id="0e019-113">For more information, see the ASP.NET documentation on MSDN.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0e019-114">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="0e019-114">Corrective Action</span></span>  
 <span data-ttu-id="0e019-115">Analysieren und verwenden Sie eine separate Lösung zum Hosten der ISAPI-Filter, die für die Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0e019-115">Evaluate and use a separate solution for hosting ISAPI filters required by your deployment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e019-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e019-116">See Also</span></span>  
 [<span data-ttu-id="0e019-117">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="0e019-117">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
