---
title: Installations Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- SCC
- System Configuration Check, Setup
helpviewer_keywords:
- System Configuration Check page [SQL Server Installation Wizard]
- SQL Server Installation Wizard, System Configuration Check page
- SCC [SQL Server]
ms.assetid: 168c0445-5651-42fc-91f4-d9f27d9e2281
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3d9fe413174613cadc9277e5c7f21695a4021c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722282"
---
# <a name="install-rules"></a><span data-ttu-id="639ea-102">Installationsregeln</span><span class="sxs-lookup"><span data-stu-id="639ea-102">Install Rules</span></span>
  <span data-ttu-id="639ea-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Setup überprüft die Computerkonfiguration, bevor der Setupvorgang abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="639ea-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="639ea-104">Während des Setups von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchsucht die Systemkonfigurationsprüfung (System Configuration Checker, SCC) den Computer, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="639ea-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the System Configuration Checker (SCC) scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed.</span></span> <span data-ttu-id="639ea-105">SCC sucht nach Bedingungen, die ein erfolgreiches Setup von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verhindern.</span><span class="sxs-lookup"><span data-stu-id="639ea-105">The SCC checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="639ea-106">Bevor Setup den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installations-Assistenten startet, ruft SCC den Status jedes Elements ab.</span><span class="sxs-lookup"><span data-stu-id="639ea-106">Before Setup starts the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard, the SCC retrieves the status of each item.</span></span> <span data-ttu-id="639ea-107">SCC vergleicht dann das Ergebnis mit den erforderlichen Bedingungen und gibt Anweisungen zum Entfernen der Blockierungsprobleme.</span><span class="sxs-lookup"><span data-stu-id="639ea-107">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="639ea-108">Die Systemkonfigurationsprüfung generiert einen Bericht, der eine kurze Beschreibung für jede ausgeführte Regel sowie den Ausführungsstatus enthält.</span><span class="sxs-lookup"><span data-stu-id="639ea-108">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="639ea-109">Der Bericht der Systemkonfigurations Prüfung befindet sich unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="639ea-109">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="639ea-110">Bevor Sie Setup ausführen, lesen Sie die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="639ea-110">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="639ea-111">Hardware- und Softwareanforderungen für die Installation von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="639ea-111">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="639ea-112">Von den Editionen von SQL Server 2014 unterstützte Features</span><span class="sxs-lookup"><span data-stu-id="639ea-112">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="639ea-113">Überlegungen zur Sicherheit bei SQL Server-Installationen</span><span class="sxs-lookup"><span data-stu-id="639ea-113">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="639ea-114">Lokale Sprachversionen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="639ea-114">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="639ea-115">Weitere Referenzen:</span><span class="sxs-lookup"><span data-stu-id="639ea-115">Other references:</span></span>  
  
1.  [<span data-ttu-id="639ea-116">Unterstützte Versions- und Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="639ea-116">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="639ea-117">Vor dem Installieren des Failoverclusterings</span><span class="sxs-lookup"><span data-stu-id="639ea-117">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="additional-rule-topics"></a><span data-ttu-id="639ea-118">Weitere Themen zu Regeln</span><span class="sxs-lookup"><span data-stu-id="639ea-118">Additional Rule topics</span></span>  
 <span data-ttu-id="639ea-119">Szenariospezifische Setupregeln finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="639ea-119">See the following topics for scenario-specific Setup rules:</span></span>  
  
-   [<span data-ttu-id="639ea-120">Installation Rules</span><span class="sxs-lookup"><span data-stu-id="639ea-120">Installation Rules</span></span>](../../../2014/sql-server/install/installation-rules.md)  
  
-   [<span data-ttu-id="639ea-121">Funktions Regeln &#40;Upgrade&#41;</span><span class="sxs-lookup"><span data-stu-id="639ea-121">Feature Rules &#40;Upgrade&#41;</span></span>](../../../2014/sql-server/install/feature-rules-upgrade.md)  
  
-   [<span data-ttu-id="639ea-122">Upgraderegeln für Editionen</span><span class="sxs-lookup"><span data-stu-id="639ea-122">Edition Upgrade Rules</span></span>](../../../2014/sql-server/install/edition-upgrade-rules.md)  
  
-   [<span data-ttu-id="639ea-123">Deinstallationsregeln</span><span class="sxs-lookup"><span data-stu-id="639ea-123">Uninstallation rules</span></span>](../../../2014/sql-server/install/uninstallation-rules.md)  
  
-   [<span data-ttu-id="639ea-124">Regeln zum Vorbereiten des Images</span><span class="sxs-lookup"><span data-stu-id="639ea-124">Prepare Image Rules</span></span>](../../../2014/sql-server/install/prepare-image-rules.md)  
  
-   [<span data-ttu-id="639ea-125">Regeln zum Abschließen des Images</span><span class="sxs-lookup"><span data-stu-id="639ea-125">Complete Image Rules</span></span>](../../../2014/sql-server/install/complete-image-rules.md)  
  
  
