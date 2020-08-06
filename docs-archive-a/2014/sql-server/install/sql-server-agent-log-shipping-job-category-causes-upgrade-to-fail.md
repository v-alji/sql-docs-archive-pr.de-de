---
title: SQL Server-Agent Protokoll Versand-Auftrags Kategorie bewirkt, dass das Upgrade fehlschlägt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
- job categories [SQL Server Agent]
ms.assetid: ef05ce53-c6ce-42ec-9df8-46c951626424
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2f5947e8fc8d459388fe35d86c75666e25b5d907
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726458"
---
# <a name="sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail"></a><span data-ttu-id="d518f-102">Fehler beim Upgrade der Auftragskategorie für den SQL Server-Agent-Protokollversand</span><span class="sxs-lookup"><span data-stu-id="d518f-102">SQL Server Agent log shipping job category causes upgrade to fail</span></span>
  <span data-ttu-id="d518f-103">Der Upgradevorgang schlägt fehl, wenn eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agentauftragskategorie mit dem Namen Protokollversand vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d518f-103">The upgrade process will fail if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job category named Log Shipping exists.</span></span>  
  
## <a name="component"></a><span data-ttu-id="d518f-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="d518f-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d518f-105">-Agent</span><span class="sxs-lookup"><span data-stu-id="d518f-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="d518f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d518f-106">Description</span></span>  
 <span data-ttu-id="d518f-107">Es ist eine Systemauftragskategorie mit dem Namen Protokollversand vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d518f-107">There is a system job category named Log Shipping.</span></span> <span data-ttu-id="d518f-108">Wenn eine zu aktualisierende Installation bereits eine von einem Benutzer erstellte Auftragskategorie mit dem Namen Protokollversand enthält, müssen Sie die Auftragskategorie vor dem Upgrade umbenennen. Andernfalls schlägt der Upgradevorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="d518f-108">If an installation that is being upgraded already contains a user-created job category named Log Shipping, you must rename the job category before you upgrade; otherwise, the upgrade process will fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d518f-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d518f-109">See Also</span></span>  
 <span data-ttu-id="d518f-110">[Der Protokoll Versand wird nach dem Upgrade nicht ausgeführt.](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span><span class="sxs-lookup"><span data-stu-id="d518f-110">[Log shipping will not run after upgrading](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md) </span></span>  
 <span data-ttu-id="d518f-111">[Beim Upgrade wird das SQL Server-Agent Benutzer Proxy Konto in das temporäre UpgradedProxyAccount geändert.](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span><span class="sxs-lookup"><span data-stu-id="d518f-111">[Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md) </span></span>  
 [<span data-ttu-id="d518f-112">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="d518f-112">SQL Server Agent Upgrade Issues</span></span>](../../../2014/sql-server/install/sql-server-agent-upgrade-issues.md)  
  
  
