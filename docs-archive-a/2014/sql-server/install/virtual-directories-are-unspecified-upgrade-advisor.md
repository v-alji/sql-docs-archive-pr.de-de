---
title: Virtuelle Verzeichnisse sind nicht angegeben (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 7d32b560-49d6-4558-b5d6-9127067f82d6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e20c48d0bf58d28cb2894baa26c2e11db26fab96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617408"
---
# <a name="virtual-directories-are-unspecified-upgrade-advisor"></a><span data-ttu-id="3240c-102">Virtuelle Verzeichnisse sind nicht angegeben (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="3240c-102">Virtual directories are unspecified (Upgrade Advisor)</span></span>
  <span data-ttu-id="3240c-103">Upgrade Advisor hat keine Einstellungen für virtuelle Verzeichnisse des Report Server-Webdiensts oder des Berichts-Managers erkannt.</span><span class="sxs-lookup"><span data-stu-id="3240c-103">Upgrade Advisor did not detect virtual directory settings for the Report Server Web service or Report Manager.</span></span> <span data-ttu-id="3240c-104">Nach dem Abschluss des Upgrades müssen Sie URL-Reservierungen für den Berichtsserver konfigurieren, indem Sie den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Konfigurations-Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="3240c-104">After upgrade completes, you must configure URL reservations for the report server by using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager.</span></span>  
  
||  
|-|  
|<span data-ttu-id="3240c-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Einheitlicher Modus.</span><span class="sxs-lookup"><span data-stu-id="3240c-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="3240c-106">Komponente</span><span class="sxs-lookup"><span data-stu-id="3240c-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3240c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3240c-107">Description</span></span>  
 <span data-ttu-id="3240c-108">Das Upgrade einer [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installation beinhaltet das Reservieren neuer URLs für den Report Server-Webdienst und den Berichts-Manager.</span><span class="sxs-lookup"><span data-stu-id="3240c-108">Upgrading a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation includes reserving new URLs for the Report Server Web service and Report Manager.</span></span> <span data-ttu-id="3240c-109">Der Upgrade Advisor hat für die zu aktualisierende Instanz keine virtuellen Verzeichnisse für den Berichtsserver oder den Berichts-Manager erkannt. Der Upgradeprozess verfügt somit nicht über ausreichende Informationen, um URL-Reservierungen für den aktualisierten Berichtsserver zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3240c-109">Upgrade Advisor did not detect virtual directories for the report server or Report Manager for the instance to be upgraded, and therefore the upgrade process has insufficient information to create URL reservations for the upgraded report server.</span></span> <span data-ttu-id="3240c-110">Das Upgrade kann fortgesetzt werden, jedoch ist das virtuelle Verzeichnis des Berichtsservers oder Berichts-Managers erst nach der Upgradeinstallation definiert.</span><span class="sxs-lookup"><span data-stu-id="3240c-110">Upgrade can continue, but the report server or Report Manager virtual directory will be undefined after the upgraded installation.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3240c-111">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="3240c-111">Corrective Action</span></span>  
 <span data-ttu-id="3240c-112">Verwenden Sie nach Abschluss des Upgrades den [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Konfigurations-Manager, um die URLs für den Berichtsserver und den Berichts-Manager festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3240c-112">After upgrade finishes, use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration Manager to set the URLs for report server and Report Manager.</span></span> <span data-ttu-id="3240c-113">Verwenden Sie den IIS-Manager, um ggf. alle virtuellen Verzeichnisse zu entfernen, die Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="3240c-113">Use IIS Manager to remove any virtual directories you no longer need.</span></span>  
  
 <span data-ttu-id="3240c-114">Weitere Informationen finden Sie unter [Konfigurieren einer URL &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Online Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="3240c-114">For more information, see [Configure a URL  &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3240c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3240c-115">See Also</span></span>  
 [<span data-ttu-id="3240c-116">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="3240c-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
