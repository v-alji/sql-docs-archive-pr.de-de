---
title: SQL Server-Agent Upgradeprobleme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server Agent
- SQL Server Agent, upgrades
ms.assetid: 77e303ff-febd-4103-ae5d-6e5b85bc8009
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ac234a757510af5ebfac261ea6d3e7e57d2f426f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700622"
---
# <a name="sql-server-agent-upgrade-issues"></a><span data-ttu-id="abc75-102">Probleme beim Aktualisieren des SQL Server-Agents</span><span class="sxs-lookup"><span data-stu-id="abc75-102">SQL Server Agent Upgrade Issues</span></span>
  <span data-ttu-id="abc75-103">In den folgenden Themen werden die Probleme mit dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent beschrieben, die ein Upgrade beeinflussen können.</span><span class="sxs-lookup"><span data-stu-id="abc75-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent issues that might affect an upgrade.</span></span> <span data-ttu-id="abc75-104">In den Themen werden Aktionen beschrieben, mit denen Sie die Auswirkungen dieser Änderungen auf die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Umgebung reduzieren können.</span><span class="sxs-lookup"><span data-stu-id="abc75-104">The topics describe actions that you can take to help reduce the effect of these changes on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abc75-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="abc75-105">In This Section</span></span>  
  
-   [<span data-ttu-id="abc75-106">Außer Kraft gesetzte Datenbank-Wartungspläne</span><span class="sxs-lookup"><span data-stu-id="abc75-106">Database maintenance plans superseded</span></span>](../../../2014/sql-server/install/database-maintenance-plans-superseded.md)  
  
-   [<span data-ttu-id="abc75-107">Nur Benutzer mit Systemadministratorberechtigungen können Protokolldateien für Auftragsschritte in das Dateisystem schreiben</span><span class="sxs-lookup"><span data-stu-id="abc75-107">Only sysadmin users can write job step log files to the file system</span></span>](../../../2014/sql-server/install/only-sysadmin-users-can-write-job-step-log-files-to-the-file-system.md)  
  
-   [<span data-ttu-id="abc75-108">Ersetzen der erweiterten gespeicherten Prozedur xp_sqlagent_proxy_account durch neue gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="abc75-108">Replace usage of the xp_sqlagent_proxy_account extended stored procedure with new stored procedures</span></span>](../../../2014/sql-server/install/replace-xp-sqlagent-proxy-account-extended-sp-with-new-stored-procedures.md)  
  
-   [<span data-ttu-id="abc75-109">Fehler beim Upgrade der Auftragskategorie für den SQL Server-Agent-Protokollversand</span><span class="sxs-lookup"><span data-stu-id="abc75-109">SQL Server Agent log shipping job category causes upgrade to fail</span></span>](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md)  
  
-   [<span data-ttu-id="abc75-110">Die SQL Server-Authentifizierung kann vom SQL Server-Agent-Dienst nicht verwendet werden</span><span class="sxs-lookup"><span data-stu-id="abc75-110">SQL Server Agent Service cannot use SQL Server Authentication</span></span>](../../../2014/sql-server/install/sql-server-agent-service-cannot-use-sql-server-authentication.md)  
  
-   [<span data-ttu-id="abc75-111">Die Tokensyntax in den Auftragsschritten des SQL Server-Agent wurde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abc75-111">Update token syntax in SQL Server Agent job steps</span></span>](../../../2014/sql-server/install/update-token-syntax-in-sql-server-agent-job-steps.md)  
  
-   [<span data-ttu-id="abc75-112">Durchführen eines Upgrades aller Zielserver vor dem Upgrade des Masterservers</span><span class="sxs-lookup"><span data-stu-id="abc75-112">Upgrade all target servers before upgrading the master server</span></span>](../../../2014/sql-server/install/upgrade-all-target-servers-before-upgrading-the-master-server.md)  
  
-   [<span data-ttu-id="abc75-113">Beim Upgrade wird das Benutzerproxykonto des SQL Server-Agents in das temporäre 'UpgradedProxyAccount' geändert.</span><span class="sxs-lookup"><span data-stu-id="abc75-113">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>](../../../2014/sql-server/install/upgrading-changes-sql-server-agent-user-proxy-account-to-temporary-account.md)  
  
## <a name="see-also"></a><span data-ttu-id="abc75-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="abc75-114">See Also</span></span>  
 <span data-ttu-id="abc75-115">[SQL Server 2014 Upgrade Advisor &#91;neuen&#93;](sql-server-2014-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="abc75-115">[SQL Server 2014 Upgrade Advisor &#91;new&#93;](sql-server-2014-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="abc75-116">Beheben von Upgradeproblemen</span><span class="sxs-lookup"><span data-stu-id="abc75-116">Resolving Upgrade Issues</span></span>](../../../2014/sql-server/install/resolving-upgrade-issues.md)  
  
  
