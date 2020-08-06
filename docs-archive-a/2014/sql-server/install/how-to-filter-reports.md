---
title: 'Vorgehensweise: Filtern von Berichten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reports [Upgrade Advisor], filtering
- filtering reports [Reporting Services]
ms.assetid: bc3dbe16-f6c1-4f07-8d88-2b8e86302c7e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4946b9ea208c0fad98426b7c7fc4247cfaa47680
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621847"
---
# <a name="how-to-filter-reports"></a><span data-ttu-id="6ec69-102">Gewusst wie: Filtern von Berichten</span><span class="sxs-lookup"><span data-stu-id="6ec69-102">How to: Filter Reports</span></span>
  <span data-ttu-id="6ec69-103">In diesem Thema wird beschrieben, wie Sie mit dem Berichts-Viewer von Upgrade Advisor Filter auf einen Bericht anwenden können.</span><span class="sxs-lookup"><span data-stu-id="6ec69-103">This topic describes how you can use the Upgrade Advisor Report Viewer to apply filters to a report.</span></span>  
  
### <a name="to-filter-reports"></a><span data-ttu-id="6ec69-104">So filtern Sie Berichte</span><span class="sxs-lookup"><span data-stu-id="6ec69-104">To filter reports</span></span>  
  
1.  <span data-ttu-id="6ec69-105">Zeigen Sie im Berichts-Viewer den Bericht an, den Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="6ec69-105">In the report viewer, display the report that you want to filter.</span></span> <span data-ttu-id="6ec69-106">Anweisungen finden Sie unter Gewusst [wie: Anzeigen eines Berichts des Upgrade Advisors](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md).</span><span class="sxs-lookup"><span data-stu-id="6ec69-106">For instructions, see [How to: View an Upgrade Advisor Report](../../../2014/sql-server/install/how-to-view-an-upgrade-advisor-report.md).</span></span>  
  
2.  <span data-ttu-id="6ec69-107">Wählen Sie in der Liste **Filtern nach** einen Problemtyp aus, der angezeigt werden soll:</span><span class="sxs-lookup"><span data-stu-id="6ec69-107">In the **Filter by** list, select a type of issue to view:</span></span>  
  
    -   <span data-ttu-id="6ec69-108">**Alle Probleme**.</span><span class="sxs-lookup"><span data-stu-id="6ec69-108">**All issues**.</span></span> <span data-ttu-id="6ec69-109">Damit werden alle Probleme angezeigt, die nicht als gelöst markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6ec69-109">This displays all issues that have not been marked as resolved.</span></span>  
  
    -   <span data-ttu-id="6ec69-110">**Alle Upgradeprobleme**.</span><span class="sxs-lookup"><span data-stu-id="6ec69-110">**All upgrade issues**.</span></span> <span data-ttu-id="6ec69-111">Damit werden alle Probleme angezeigt, die das Update auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] betreffen.</span><span class="sxs-lookup"><span data-stu-id="6ec69-111">This displays all issues that are related to upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    -   <span data-ttu-id="6ec69-112">**Probleme vor dem Upgrade**.</span><span class="sxs-lookup"><span data-stu-id="6ec69-112">**Pre-upgrade issues**.</span></span> <span data-ttu-id="6ec69-113">Damit werden alle Probleme angezeigt, die vor dem Update auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] behoben werden sollten oder müssen.</span><span class="sxs-lookup"><span data-stu-id="6ec69-113">This displays all issues that should or must be fixed before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    -   <span data-ttu-id="6ec69-114">**Alle Migrationsprobleme**.</span><span class="sxs-lookup"><span data-stu-id="6ec69-114">**All migration issues**.</span></span> <span data-ttu-id="6ec69-115">Damit werden alle Probleme angezeigt, die sich auf die Migration von Daten oder Anwendungen zu [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] beziehen.</span><span class="sxs-lookup"><span data-stu-id="6ec69-115">This displays all issues that are related to migrating data or applications to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
    -   <span data-ttu-id="6ec69-116">Behobene **Probleme**.</span><span class="sxs-lookup"><span data-stu-id="6ec69-116">**Resolved Issues**.</span></span> <span data-ttu-id="6ec69-117">Damit werden alle Probleme angezeigt, die als gelöst markiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6ec69-117">This displays all issues that have been marked as resolved.</span></span>  
  
    -   <span data-ttu-id="6ec69-118">Nicht **aufgelöste Probleme**.</span><span class="sxs-lookup"><span data-stu-id="6ec69-118">**Unresolved Issues**.</span></span> <span data-ttu-id="6ec69-119">Damit werden alle Probleme angezeigt, die noch nicht gelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="6ec69-119">This displays all issues that have not yet been resolved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec69-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ec69-120">See Also</span></span>  
 <span data-ttu-id="6ec69-121">[Vorgehensweise: Ausführen des Analyse-Assistenten des Upgrade Advisors](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="6ec69-121">[How to: Run the Upgrade Advisor Analysis Wizard](../../../2014/sql-server/install/how-to-run-the-upgrade-advisor-analysis-wizard.md) </span></span>  
 <span data-ttu-id="6ec69-122">[Beheben von Upgradeproblemen](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6ec69-122">[Resolving Upgrade Issues](../../../2014/sql-server/install/resolving-upgrade-issues.md) </span></span>  
 <span data-ttu-id="6ec69-123">[Gewusst-wie-Themen zum Upgrade Advisor](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="6ec69-123">[Upgrade Advisor How-to Topics](../../../2014/sql-server/install/upgrade-advisor-how-to-topics.md) </span></span>  
 [<span data-ttu-id="6ec69-124">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="6ec69-124">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
