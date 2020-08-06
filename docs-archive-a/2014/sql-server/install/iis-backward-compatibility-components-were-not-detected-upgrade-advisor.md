---
title: IIS-abwärts Kompatibilitäts Komponenten wurden nicht erkannt (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IIS [Reporting Services]
ms.assetid: e794185a-0a77-480a-9aea-d09f8760a6b8
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: a5aad54a01b3840e121c6a63de0ea26f35921fa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621826"
---
# <a name="iis-backward-compatibility-components-were-not-detected-upgrade-advisor"></a><span data-ttu-id="fbdf4-102">IIS-Abwärtskompatibilitätskomponenten wurden nicht erkannt (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="fbdf4-102">IIS backward compatibility components were not detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="fbdf4-103">Upgrade Advisor hat keine IIS-Komponenten und -Einstellungen erkannt, die Informationen bereitstellen, mit denen Setup neue [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-URLs erstellt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-103">Upgrade Advisor did not detect IIS components and settings that provide information used by Setup to create new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] URLS.</span></span>  
  
||  
|-|  
|<span data-ttu-id="fbdf4-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheitlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="fbdf4-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="fbdf4-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="fbdf4-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fbdf4-106">Description</span></span>  
 <span data-ttu-id="fbdf4-107">IIS enthält Komponenten, die Informationen über die virtuellen Verzeichnisse des Berichtsservers und des Berichts-Managers bereitstellen. Diese Komponenten sind nicht auf dem Computer mit dem Berichtsserver installiert.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-107">IIS includes components that provide information about the report server and Report Manager virtual directories, and those components are not installed on the report server computer.</span></span> <span data-ttu-id="fbdf4-108">Das Upgrade kann fortgesetzt werden, die URLs für den Berichtsserver oder den Berichts-Manager werden beim Upgrade jedoch nicht neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-108">Upgrade can continue, but URLs for the report server or Report Manager will not be recreated by upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="fbdf4-109">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="fbdf4-109">Corrective Action</span></span>  
 <span data-ttu-id="fbdf4-110">Verwenden Sie nach Abschluss des Upgrades das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Konfigurationstool, um die URLs für den Berichtsserver oder den Berichts-Manager festzulegen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-110">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool to set the URLs for report server or Report Manager.</span></span> <span data-ttu-id="fbdf4-111">Verwenden Sie IIS-Manager, um die virtuellen Verzeichnisse zu entfernen, die Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-111">Use IIS Manager to remove the virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="fbdf4-112">Weitere Informationen finden Sie unter [Konfigurieren einer URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Online Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="fbdf4-112">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdf4-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbdf4-113">See Also</span></span>  
 [<span data-ttu-id="fbdf4-114">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="fbdf4-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
