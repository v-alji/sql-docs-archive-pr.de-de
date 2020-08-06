---
title: Analysis Services Abwärtskompatibilität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- installing Analysis Services, backward compatibility
- backward compatibility [Analysis Services]
- compatibility [Analysis Services]
- Analysis Services, backward compatibility
- upgrading Analysis Services
- SSAS, backward compatibility
- SQL Server Analysis Services, backward compatibility
ms.assetid: 618b6c3a-e20d-47a9-b2c6-6d848dfba05a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44a5296bfbd2bae746eb9936d416fd696de16cb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615215"
---
# <a name="analysis-services-backward-compatibility"></a><span data-ttu-id="b0751-102">Analysis Services Backward Compatibility</span><span class="sxs-lookup"><span data-stu-id="b0751-102">Analysis Services Backward Compatibility</span></span>
  <span data-ttu-id="b0751-103">In den Themen in diesem Abschnitt werden die Verhaltensänderungen zwischen den Versionen von beschrieben [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b0751-103">The topics in this section describe the changes in behavior between versions of  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0751-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b0751-104">In This Section</span></span>  
  
|<span data-ttu-id="b0751-105">Themen</span><span class="sxs-lookup"><span data-stu-id="b0751-105">Topics</span></span>|<span data-ttu-id="b0751-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b0751-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0751-107">Veraltete Analysis Services-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b0751-107">Deprecated Analysis Services Features in SQL Server 2014</span></span>](deprecated-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="b0751-108">Beschreibt Funktionen, die in der aktuellen Version aus Gründen der Abwärtskompatibilität beibehalten wurden, jedoch in einer zukünftigen Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="b0751-108">Describes features that have been retained in the current version to maintain backward compatibility,  but which will be removed in a future version of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="b0751-109">Nicht mehr unterstützte Analysis Services-Funktionalität in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b0751-109">Discontinued Analysis Services Functionality in SQL Server 2014</span></span>](discontinued-analysis-services-functionality-in-sql-server-2014.md)|<span data-ttu-id="b0751-110">Beschreibt Funktionen, die in früheren Versionen von  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] vorhanden waren, jedoch in späteren Versionen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="b0751-110">Describes features that existed in earlier versions of  [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] but that have since been removed in later versions.</span></span>|  
|[<span data-ttu-id="b0751-111">Wichtige Änderungen von Analysis Services-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b0751-111">Breaking Changes to Analysis Services Features in SQL Server 2014</span></span>](breaking-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="b0751-112">Beschreibt Codeänderungen in dieser Version von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , die in Modellen oder benutzerdefinierten Anwendungen oder Skripts, die in früheren Versionen der Software erstellt wurden, zu schwerwiegenden Fehlern führen können.</span><span class="sxs-lookup"><span data-stu-id="b0751-112">Describes code changes introduced in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that could potentially break a model or custom applications or script created in previous versions of the software .</span></span>|  
|[<span data-ttu-id="b0751-113">Verändertes Verhalten von Analysis Services-Funktionen in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b0751-113">Behavior Changes to Analysis Services Features in SQL Server 2014</span></span>](behavior-changes-to-analysis-services-features-in-sql-server-2014.md)|<span data-ttu-id="b0751-114">Beschreibt vorhandene Funktionen, die in dieser Version von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]abweichende Verhaltensweisen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b0751-114">Describes existing features that have different behaviors in this release of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="b0751-115">Häufige Beispiele sind z. B. das Ändern von Standardwerten in neue oder abweichende Werte, die eine zuvor zulässige Operation oder Konfiguration verhindern oder dazu führen, dass eine Einstellung oder Konfiguration manuell geändert oder ersetzt werden muss, die während des Upgrades verloren gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="b0751-115">Common examples include changing a default to a new or different value, disallowing a previously allowable operation or configuration, or a introducing a requirement to manually revise or replace a setting or configuration that is lost during upgrade.</span></span><br /> <span data-ttu-id="b0751-116">.</span><span class="sxs-lookup"><span data-stu-id="b0751-116">.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0751-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0751-117">See Also</span></span>  
 <span data-ttu-id="b0751-118">[Neues in Analysis Services und Business Intelligence](what-s-new-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b0751-118">[What's New in Analysis Services and Business Intelligence](what-s-new-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="b0751-119">Aktualisieren von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b0751-119">Upgrade Analysis Services</span></span>](../database-engine/install-windows/upgrade-analysis-services.md)  
  
  
