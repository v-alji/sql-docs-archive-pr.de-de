---
title: Der Protokoll Versand wird nach dem Upgrade nicht ausgeführt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server]
ms.assetid: 6727cb7d-ac01-4972-a730-dbb7cdc29705
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b2af60743cb2cbf9bf455397fe052c4e81f5a06d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622402"
---
# <a name="log-shipping-will-not-run-after-upgrading"></a><span data-ttu-id="825bf-102">Protokollversand wird nach Update nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="825bf-102">Log shipping will not run after upgrading</span></span>
  <span data-ttu-id="825bf-103">Der Upgrade Advisor hat festgestellt, dass Sie den Protokollversand verwenden.</span><span class="sxs-lookup"><span data-stu-id="825bf-103">Upgrade Advisor has detected that you are using log shipping.</span></span> <span data-ttu-id="825bf-104">Der Protokollversand in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ist nicht mit dem Protokollversand in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] kompatibel und kann nicht direkt aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="825bf-104">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] log shipping is incompatible with log shipping in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] and cannot be upgraded directly.</span></span> <span data-ttu-id="825bf-105">Konfigurieren Sie nach dem Upgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]den Protokollversand mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder mithilfe gespeicherter Prozeduren neu.</span><span class="sxs-lookup"><span data-stu-id="825bf-105">After upgrading to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], reconfigure log shipping using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or stored procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825bf-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="825bf-106">See Also</span></span>  
 <span data-ttu-id="825bf-107">[SQL Server-Agent Protokoll Versand-Auftrags Kategorie bewirkt, dass das Upgrade fehlschlägt](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="825bf-107">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 <span data-ttu-id="825bf-108">[Beim Upgrade wird das SQL Server-Agent Benutzer Proxy Konto in das temporäre UpgradedProxyAccount geändert.](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="825bf-108">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 <span data-ttu-id="825bf-109">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="825bf-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="825bf-110">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="825bf-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
