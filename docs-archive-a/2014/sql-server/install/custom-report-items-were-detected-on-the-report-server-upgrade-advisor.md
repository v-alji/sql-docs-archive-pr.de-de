---
title: Auf dem Berichts Server wurden benutzerdefinierte Berichts Elemente erkannt (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- custom report items, upgrading
ms.assetid: aee32006-65b2-4dfe-9570-d85a249d17b2
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: feacf6aa6f233f85a67b43e7b72d3a50913991bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615769"
---
# <a name="custom-report-items-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="80b14-102">Auf dem Berichtsserver wurden benutzerdefinierte Berichtselemente erkannt (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="80b14-102">Custom report items were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="80b14-103">Benutzerdefinierte Berichts Elemente, die für vorherige Versionen von erstellt wurden, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] sind nicht mit kompatibel [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="80b14-103">Custom report items that were created for previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] are not compatible with [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="80b14-104">Das Upgrade kann fortgesetzt werden, jedoch werden Berichte, die das benutzerdefinierte Berichtselement verwenden, nicht wie erwartet ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="80b14-104">Upgrade can continue, but reports that use the custom report item will not run as expected.</span></span> <span data-ttu-id="80b14-105">Der Upgrade Advisor hat benutzerdefinierte Berichtselemente erkannt.</span><span class="sxs-lookup"><span data-stu-id="80b14-105">Upgrade Advisor detected custom report items.</span></span> <span data-ttu-id="80b14-106">Das Upgrade kann fortgesetzt werden, Sie müssen jedoch die benutzerdefinierten Berichts Element Dateien manuell in den neuen Installationsordner verschieben, nachdem das Upgrade abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="80b14-106">Upgrade can continue, but you must manually move the custom report item files to the new installation folder after upgrade completes.</span></span>  
  
||  
|-|  
|<span data-ttu-id="80b14-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im einheitlichen Modus &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="80b14-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="80b14-108">Komponente</span><span class="sxs-lookup"><span data-stu-id="80b14-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="80b14-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="80b14-109">Description</span></span>  
 <span data-ttu-id="80b14-110">Der Upgrade Advisor hat benutzerdefinierte [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Erweiterungseinstellungen in den Konfigurationsdateien gefunden. Dies ist ein Hinweis darauf, dass die Installation mindestens eine benutzerdefinierte Assembly für Berichte enthält.</span><span class="sxs-lookup"><span data-stu-id="80b14-110">Upgrade Advisor detected custom [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] extension settings in the configuration files, indicating that your installation includes one or more custom assemblies for reports.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="80b14-111">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="80b14-111">Corrective Action</span></span>  
 <span data-ttu-id="80b14-112">Das Upgrade kann fortgesetzt werden; Sie müssen jedoch die Dateien für die benutzerdefinierten Berichtselemente nach Abschluss des Upgrades manuell in den neuen Installationsordner verschieben.</span><span class="sxs-lookup"><span data-stu-id="80b14-112">After upgrade completes, manually move the custom report item files to the new installation folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b14-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80b14-113">See Also</span></span>  
 [<span data-ttu-id="80b14-114">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="80b14-114">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
