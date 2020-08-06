---
title: Übersicht über den Upgradeprozess | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
- Upgrade Advisor [SQL Server], process description
- SQL Server Upgrade Advisor, process description
- upgrade process [Upgrade Advisor]
ms.assetid: f77ffbab-a195-4124-acce-9c538f7ca9ce
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5da6dc3b3e6d6c7058193801100bf2552bfde7cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726454"
---
# <a name="upgrade-process-overview"></a><span data-ttu-id="99a1f-102">Übersicht über den Upgradeprozess</span><span class="sxs-lookup"><span data-stu-id="99a1f-102">Upgrade Process Overview</span></span>
  <span data-ttu-id="99a1f-103">Dieses Thema bietet Informationen zu bewährten Methoden für den Upgrade Advisor von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] sowie eine Zusammenfassung des empfohlenen Prozesses für das Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99a1f-103">This topic provides best practice information for [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade Advisor and a summary of the recommended process for upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="upgrade-process"></a><span data-ttu-id="99a1f-104">Upgradeprozess</span><span class="sxs-lookup"><span data-stu-id="99a1f-104">Upgrade Process</span></span>  
 <span data-ttu-id="99a1f-105">Server, auf denen [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] oder [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ausgeführt wird, können auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="99a1f-105">Servers that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] can be upgraded to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="99a1f-106">Manche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten können direkt aktualisiert werden, während andere migriert und wieder andere durch neue Komponenten ersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="99a1f-106">Whereas some [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components can be upgraded in place, others must be migrated, and still others have been superseded by new components.</span></span> <span data-ttu-id="99a1f-107">Ab [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) werden z. B. die Data Transformation Services (DTS) abgelöst, und DTS wird in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99a1f-107">For example, starting with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) supersedes Data Transformation Services (DTS), and DTS is no longer supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="99a1f-108">Beim Erstellen Ihres Upgradeplans kann es erforderlich sein, die Aktualisierung Ihrer aktuellen DTS-Pakete auf [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Pakete zu planen.</span><span class="sxs-lookup"><span data-stu-id="99a1f-108">When you formulate your upgrade plan, you might need to plan for updating your current DTS packages to [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages.</span></span>  
  
 <span data-ttu-id="99a1f-109">Mit dem Upgrade Advisor können Sie aktuelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Installationen, -Komponenten und zugehörige Dateien auswerten, um bekannte Probleme zu identifizieren, die sowohl während als auch nach dem Upgrade auf oder der Migration zu [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="99a1f-109">Upgrade Advisor enables you to evaluate current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installations, components, and related files to identify known issues that will cause problems both during and after you upgrade or migrate to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="99a1f-110">Einige dieser bekannten Probleme blockieren das [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Upgrade.</span><span class="sxs-lookup"><span data-stu-id="99a1f-110">A few of these known issues block the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] upgrade.</span></span> <span data-ttu-id="99a1f-111">Im Bericht des Upgrade Advisors werden diese Probleme als Upgrade Blocker identifiziert.</span><span class="sxs-lookup"><span data-stu-id="99a1f-111">In the Upgrade Advisor report, these issues are identified as Upgrade Blockers.</span></span> <span data-ttu-id="99a1f-112">Wenn Sie die Upgrade Blocker vor dem Ausführen von Setup nicht beseitigen, wird [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]-Setup beendet. Außerdem wird die Ausführung des Upgrade Advisors empfohlen, um die spezifischen Probleme zu identifizieren, die das Upgrade blockieren.</span><span class="sxs-lookup"><span data-stu-id="99a1f-112">If you have not addressed the Upgrade Blockers before you run Setup, [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup exits and recommends that you run Upgrade Advisor to identify the specific issues that are blocking the upgrade.</span></span>  
  
 <span data-ttu-id="99a1f-113">Als bewährte Methode vor dem Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] empfiehlt es sich, eine Sicherungskopie der Daten und Systemeinstellungen zu erstellen und die strategischen Schritte auszuführen, die in den für Ihr Unternehmen definierten Betriebsrichtlinien beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="99a1f-113">As a best practice before upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], we recommend that you back up your data and system settings, and take strategic steps as outlined in the operational guidelines defined for your organization.</span></span> <span data-ttu-id="99a1f-114">Führen Sie die folgenden Schritte aus, um das Upgrade auszuführen:</span><span class="sxs-lookup"><span data-stu-id="99a1f-114">Use the following steps to complete the upgrade:</span></span>  
  
1.  <span data-ttu-id="99a1f-115">Informieren Sie sich unter [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="99a1f-115">Review [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="99a1f-116">Erstellen Sie eine Sicherungskopie der Daten und Systemeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="99a1f-116">Back up data and system settings.</span></span>  
  
3.  <span data-ttu-id="99a1f-117">Führen Sie den Upgrade Advisor aus.</span><span class="sxs-lookup"><span data-stu-id="99a1f-117">Run Upgrade Advisor.</span></span>  
  
     <span data-ttu-id="99a1f-118">Der Upgrade Advisor nimmt keine Änderungen an den Daten oder Einstellungen auf dem Computer vor.</span><span class="sxs-lookup"><span data-stu-id="99a1f-118">Upgrade Advisor does not modify your data or change settings on your computer.</span></span>  
  
4.  <span data-ttu-id="99a1f-119">Überprüfen Sie die im Bericht des Upgrade Advisors angegebenen Probleme.</span><span class="sxs-lookup"><span data-stu-id="99a1f-119">Review the issues identified in the Upgrade Advisor report.</span></span>  
  
5.  <span data-ttu-id="99a1f-120">Beheben Sie alle Blockierungsprobleme, die eine Aktualisierung auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] verhindern würden.</span><span class="sxs-lookup"><span data-stu-id="99a1f-120">Resolve any blocking issues that would prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
6.  <span data-ttu-id="99a1f-121">Beheben Sie alle weiteren Probleme vor dem Upgrade.</span><span class="sxs-lookup"><span data-stu-id="99a1f-121">Resolve any other pre-upgrade issues.</span></span>  
  
7.  <span data-ttu-id="99a1f-122">Führen Sie den Upgrade Advisor aus, um zu überprüfen, ob alle bekannten Probleme behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="99a1f-122">Run Upgrade Advisor to verify that all known issues have been addressed.</span></span>  
  
8.  <span data-ttu-id="99a1f-123">Führen Sie [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup aus.</span><span class="sxs-lookup"><span data-stu-id="99a1f-123">Run [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Setup.</span></span>  
  
9. <span data-ttu-id="99a1f-124">Beheben Sie alle Probleme nach dem Upgrade sowie alle Migrationsprobleme.</span><span class="sxs-lookup"><span data-stu-id="99a1f-124">Resolve any post-upgrade and migration issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99a1f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99a1f-125">See Also</span></span>  
 <span data-ttu-id="99a1f-126">[Ausführen des Upgrade Advisors &#40;Benutzeroberfläche&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="99a1f-126">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 <span data-ttu-id="99a1f-127">[Verwenden von Berichten](../../../2014/sql-server/install/using-reports.md) </span><span class="sxs-lookup"><span data-stu-id="99a1f-127">[Using Reports](../../../2014/sql-server/install/using-reports.md) </span></span>  
 [<span data-ttu-id="99a1f-128">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="99a1f-128">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
