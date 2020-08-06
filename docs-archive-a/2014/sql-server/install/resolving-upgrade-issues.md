---
title: Beheben von Upgradeproblemen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- installing Upgrade Advisor
- Upgrade Advisor [SQL Server], reference
- component issue resolution [Upgrade Advisor]
- resolving upgrade issues
- upgrade blocks [Upgrade Advisor]
- detecting upgrade issues
- finding upgrade issues
- Upgrade Advisor [SQL Server], blocking issues
- configurations preventing upgrading [Upgrade Advisor]
- locating upgrade issues
- blocking issues [Upgrade Advisor]
- issues preventing upgrading [Upgrade Advisor]
- Setup [Upgrade Advisor]
- SQL Server Upgrade Advisor, reference
- analyzing system [Upgrade Advisor], resolving issues
- settings preventing upgrading [Upgrade Advisor]
- upgrade issue reference [Upgrade Advisor]
- identifying upgrade issues
- fixing upgrade issues [Upgrade Advisor]
ms.assetid: 113eb435-8d36-4ed6-9790-b5e4c14809c8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: c00b08d40bc8c17013e6af19b5d11b0b7ad78c4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622389"
---
# <a name="resolving-upgrade-issues"></a><span data-ttu-id="7024a-102">Beheben von Upgradeproblemen</span><span class="sxs-lookup"><span data-stu-id="7024a-102">Resolving Upgrade Issues</span></span>
  <span data-ttu-id="7024a-103">Die Themen in diesem Abschnitt beschreiben sowohl Upgradeprobleme, die erkannt werden können, als auch solche, die nicht erkannt werden können. Beide wirken sich möglicherweise beim Upgrade oder zu einem späteren Zeitpunkt aus.</span><span class="sxs-lookup"><span data-stu-id="7024a-103">The topics in this section describe upgrade issues that can be detected as well as those that cannot be detected, but that might affect the upgrade or post-upgrade experience.</span></span> <span data-ttu-id="7024a-104">Die Probleme sind nach [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten organisiert.</span><span class="sxs-lookup"><span data-stu-id="7024a-104">The issues are organized by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] component.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7024a-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7024a-105">In This Section</span></span>  
  
-   [<span data-ttu-id="7024a-106">Aktuelle Upgradeprobleme</span><span class="sxs-lookup"><span data-stu-id="7024a-106">Late-Breaking Upgrade Issues</span></span>](../../../2014/sql-server/install/late-breaking-upgrade-issues.md)  
  
-   [<span data-ttu-id="7024a-107">Probleme beim Upgrade der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="7024a-107">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
-   [<span data-ttu-id="7024a-108">Probleme beim Upgrade der Volltextsuche</span><span class="sxs-lookup"><span data-stu-id="7024a-108">Full-Text Search Upgrade Issues</span></span>](../../../2014/sql-server/install/full-text-search-upgrade-issues.md)  
  
-   [<span data-ttu-id="7024a-109">Probleme beim Replikationsupgrade</span><span class="sxs-lookup"><span data-stu-id="7024a-109">Replication Upgrade Issues</span></span>](../../../2014/sql-server/install/replication-upgrade-issues.md)  
  
-   [<span data-ttu-id="7024a-110">Reporting Services Upgradeprobleme &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="7024a-110">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
-   [<span data-ttu-id="7024a-111">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="7024a-111">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
## <a name="issues-that-prevent-upgrading"></a><span data-ttu-id="7024a-112">Probleme, die ein Upgrade verhindern</span><span class="sxs-lookup"><span data-stu-id="7024a-112">Issues That Prevent Upgrading</span></span>  
 <span data-ttu-id="7024a-113">Einige Konfigurationen oder Einstellungen in einer früheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können ein Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] verhindern.</span><span class="sxs-lookup"><span data-stu-id="7024a-113">A few configurations or settings in a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can prevent you from upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7024a-114">Wenn das Setup solche Probleme bei der Installation von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] erkennt, hält es den Upgradeprozess an und fordert Sie auf, den Upgrade Advisor auszuführen und blockierende Probleme zu beseitigen.</span><span class="sxs-lookup"><span data-stu-id="7024a-114">If Setup detects these issues when you install [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], Setup stops the upgrade process and requests that you run Upgrade Advisor and fix any blocking issues.</span></span>  
  
### [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
 <span data-ttu-id="7024a-115">Wenn die folgenden Tasks im [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Upgradebericht enthalten sind, müssen Sie die erforderlichen Aktionen durchführen, bevor Sie ein Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7024a-115">If the following tasks are listed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)] upgrade report, you must perform the required actions before you upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]:</span></span>  
  
-   [<span data-ttu-id="7024a-116">Datenbank-ID 32767 trennen</span><span class="sxs-lookup"><span data-stu-id="7024a-116">Detach database ID 32767</span></span>](../../../2014/sql-server/install/detach-database-id-32767.md)  
  
-   [<span data-ttu-id="7024a-117">Umbenennen von Anmeldungen, die mit Namen fester Serverrollen identisch sind</span><span class="sxs-lookup"><span data-stu-id="7024a-117">Rename logins matching fixed server role names</span></span>](../../../2014/sql-server/install/rename-logins-matching-fixed-server-role-names.md)  
  
-   [<span data-ttu-id="7024a-118">Benennen Sie den Benutzer 'sys' um</span><span class="sxs-lookup"><span data-stu-id="7024a-118">Rename user sys</span></span>](../../../2014/sql-server/install/rename-user-sys.md)  
  
-   [<span data-ttu-id="7024a-119">Verwenden Sie bei doppelten Indexnamen 'sp_rename' zum Umbenennen</span><span class="sxs-lookup"><span data-stu-id="7024a-119">Use sp_rename to rename duplicate index name</span></span>](../../../2014/sql-server/install/use-sp-rename-to-rename-duplicate-index-name.md)  
  
## <a name="see-also"></a><span data-ttu-id="7024a-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7024a-120">See Also</span></span>  
 [<span data-ttu-id="7024a-121">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="7024a-121">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
