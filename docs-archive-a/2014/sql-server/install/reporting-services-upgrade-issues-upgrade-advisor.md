---
title: Reporting Services Upgradeprobleme (Upgrade Advisor) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], upgrade issues
- Reporting Services, upgrades
- upgrading Reporting Services
- report servers [Reporting Services], upgrade issues
ms.assetid: d9663f25-98d7-4508-ae3c-55a7277211bd
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 569afe735d68a724c0b4cc61ad2b7767088c2b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622392"
---
# <a name="reporting-services-upgrade-issues-upgrade-advisor"></a><span data-ttu-id="980d2-102">Upgradeprobleme bei Reporting Services (Upgrade Advisor)</span><span class="sxs-lookup"><span data-stu-id="980d2-102">Reporting Services Upgrade Issues (Upgrade Advisor)</span></span>
  <span data-ttu-id="980d2-103">In den folgenden Themen werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Probleme beschrieben, die sich möglicherweise auf das Upgrade auf auswirken [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="980d2-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] issues that might affect your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="980d2-104">In den Themen werden Aktionen beschrieben, mit denen Sie die Auswirkungen dieser Änderungen auf Ihre Umgebung mindern können.</span><span class="sxs-lookup"><span data-stu-id="980d2-104">The topics describe actions that you can take to mitigate the effect of these changes on your environment.</span></span>  
  
 <span data-ttu-id="980d2-105">Der Updateratgeber analysiert eine Berichtsserverinstallation.</span><span class="sxs-lookup"><span data-stu-id="980d2-105">Upgrade Advisor analyzes a report server installation.</span></span> <span data-ttu-id="980d2-106">Wenn nur Clientkomponenten installiert sind (wenn z. B. der Berichts-Designer als einzige [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Komponente auf dem Computer installiert ist), werden keine Probleme gemeldet.</span><span class="sxs-lookup"><span data-stu-id="980d2-106">If only client components are installed (for example, if Report Designer is the only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component installed on the computer), no issues will be reported.</span></span>  
  
 <span data-ttu-id="980d2-107">Abhängig von der Konfiguration der Installation können weitere Probleme auftreten, die vom Updateratgeber nicht gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="980d2-107">Depending on how you configured your installation, you may encounter additional issues that are not reported by Upgrade Advisor.</span></span> <span data-ttu-id="980d2-108">Diese Probleme lassen ein [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Update nicht scheitern, sie können sich aber auf die Ausführung von Berichten und Anwendungen nach Abschluss des Updates auswirken.</span><span class="sxs-lookup"><span data-stu-id="980d2-108">These issues do not prevent a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] upgrade from succeeding, but they may affect how reports and applications run after an upgrade is finished.</span></span> <span data-ttu-id="980d2-109">Informationen zu diesen Problemen finden Sie unter "Abwärtskompatibilität von Reporting Services" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="980d2-109">To learn about these issues, see "Reporting Services Backward Compatibility" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="980d2-110">Wenn Sie nicht das Setup zum Upgrade der [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]-Installation verwenden können, können Sie eine neue Instanz von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installieren und die bestehende Installation zur neuen Instanz migrieren.</span><span class="sxs-lookup"><span data-stu-id="980d2-110">If you cannot use Setup to upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can install a new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and migrate your existing installation to the new instance.</span></span> <span data-ttu-id="980d2-111">Weitere Informationen finden Sie unter "Upgrade und Migration Reporting Services" in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Online Dokumentation, [aktualisieren und Migrieren von Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="980d2-111">For more information, see "Upgrade and Migrate Reporting Services" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online, [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
 <span data-ttu-id="980d2-112">In den folgenden Themen werden bekannte Probleme beschrieben, die vom Updateratgeber gemeldet werden. Außerdem wird erläutert, wie Sie die vorhandene Installation ändern können, um ein Upgrade zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="980d2-112">The following topics describe known issues that are reported by Upgrade Advisor, and explain how you can modify your existing installation to allow an upgrade to occur.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="980d2-113">Upgrade Advisor muss auf dem Berichtsserver installiert werden, um eine Instanz von [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="980d2-113">Upgrade Advisor must be installed on the report server to analyze an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="980d2-114">unterstützt keine Remoteanalyse.</span><span class="sxs-lookup"><span data-stu-id="980d2-114">does not support remote analysis.</span></span>  
>   
>  <span data-ttu-id="980d2-115">Weitere Informationen finden Sie unter [Installieren des Upgrade Advisors](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="980d2-115">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="980d2-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="980d2-116">In This Section</span></span>  
  
-   [<span data-ttu-id="980d2-117">Client Zertifikate auf der Berichts Server-Website &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-117">Client certificates on the report server web site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/client-certificates-on-the-report-server-web-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-118">Auf dem Berichts Server &#40;Upgrade Advisor wurden benutzerdefinierte Erweiterungen erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-118">Custom extensions were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-extensions-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-119">Auf dem Berichts Server &#40;Upgrade Advisor wurden benutzerdefinierte Berichts Elemente erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-119">Custom report items were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-report-items-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-120">IIS-abwärts Kompatibilitäts Komponenten wurden &#40;Upgrade Advisor nicht erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-120">IIS backward compatibility components were not detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/iis-backward-compatibility-components-were-not-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-121">Die IP-Adress Einschränkung wurde &#40;Upgrade Advisor erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-121">IP address restriction detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/ip-address-restriction-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-122">ISAPI-Filter wurden auf der Berichts Server Website &#40;Upgrade Advisor erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-122">ISAPI filters detected on the report server site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/isapi-filters-detected-on-the-report-server-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-123">Veraltete Erweiterungen wurden auf dem Berichts Server Computer &#40;Upgrade Advisor erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-123">Obsolete extensions were detected on the report server computer &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-124">Die Berichts Server-Datenbank ist &#40;Upgrade Advisor nicht konfiguriert&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-124">Report server database is not configured &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/report-server-database-is-not-configured-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-125">&#40;Upgrade Advisor wurde SQL Server 2005-Berichts Server-Webdienst Gruppe erkannt&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-125">SQL Server 2005 Report Server Web Service group detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-2005-report-server-web-service-group-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-126">Virtuelle Verzeichnisse sind nicht angegeben &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-126">Virtual directories are unspecified &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directories-are-unspecified-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-127">Das virtuelle Verzeichnis verfügt über eine nicht unterstützte Authentifizierungsmethode &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-127">Virtual directory has unsupported authentication method &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directory-has-unsupported-authentication-method-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-128">Änderungen an den CPU-und Arbeitsspeicher Limits für SQL Server Standard und Enterprise &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-128">Changes to CPU and memory limits for SQL Server Standard and Enterprise &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/cpu-memory-limits-changes-sql-server-standard-enterprise-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-129">Erforderliche Domänen Konten für die SharePoint-Farm &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-129">Domain accounts required for SharePoint farm &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/domain-accounts-required-for-sharepoint-farm-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-130">Direktes Navigieren zum Berichts Server &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-130">Direct Browsing to Report Server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/direct-browsing-to-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-131">Microsoft SharePoint 2007 wird &#40;Upgrade Advisor installiert&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-131">Microsoft SharePoint 2007 is Installed &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/microsoft-sharepoint-2007-is-installed-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-132">Microsoft SQL Server Reporting Services gemeinsamer SharePoint-Dienst wird parallel &#40;Upgrade Advisor installiert&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-132">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-reporting-services-sharepoint-shared-service-side-by-side-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-133">Nicht kompatible Datenbank-Engine Server-Sortierung &#40;Upgrade Advisor&#41;</span><span class="sxs-lookup"><span data-stu-id="980d2-133">Incompatible Database Engine Server Collation &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/incompatible-database-engine-server-collation-upgrade-advisor.md)  
  
-   [<span data-ttu-id="980d2-134">Weitere Upgradeprobleme bei Reporting Services</span><span class="sxs-lookup"><span data-stu-id="980d2-134">Other Reporting Services Upgrade Issues</span></span>](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md)  
  
  
