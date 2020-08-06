---
title: Funktions Regeln (Upgrade) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 653b15db-a984-4b4b-b224-81b0285b099b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0527c1ba26fed86a6c1a3d3a2ea7c11b096474f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620181"
---
# <a name="feature-rules-upgrade"></a><span data-ttu-id="98ec1-102">Funktionsregeln (Upgrade)</span><span class="sxs-lookup"><span data-stu-id="98ec1-102">Feature Rules (Upgrade)</span></span>
  <span data-ttu-id="98ec1-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Setup überprüft die Computerkonfiguration, bevor der Setupvorgang abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="98ec1-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup validates your computer configuration before the Setup operation completes.</span></span> <span data-ttu-id="98ec1-104">Beim Setup von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durchsucht das System den Computer, auf dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installiert wird. Außerdem wird nach Bedingungen gesucht, die ein erfolgreiches Durchführen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setups verhindern.</span><span class="sxs-lookup"><span data-stu-id="98ec1-104">During [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup, the system scans the computer where [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will be installed and checks for conditions that prevent a successful [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] setup operation.</span></span> <span data-ttu-id="98ec1-105">Bevor Setup den Upgrade-Assistenten startet, wird der Status jedes Elements abgerufen.</span><span class="sxs-lookup"><span data-stu-id="98ec1-105">Before Setup starts the upgrade wizard, it retrieves the status of each item.</span></span> <span data-ttu-id="98ec1-106">SCC vergleicht dann das Ergebnis mit den erforderlichen Bedingungen und gibt Anweisungen zum Entfernen der Blockierungsprobleme.</span><span class="sxs-lookup"><span data-stu-id="98ec1-106">It then compares the result with required conditions and provides guidance for removal of blocking issues.</span></span>  
  
 <span data-ttu-id="98ec1-107">Die Systemkonfigurationsprüfung generiert einen Bericht, der eine kurze Beschreibung für jede ausgeführte Regel sowie den Ausführungsstatus enthält.</span><span class="sxs-lookup"><span data-stu-id="98ec1-107">The system configuration check generates a report which contains a short description for each executed rule, and the execution status.</span></span> <span data-ttu-id="98ec1-108">Der Bericht der Systemkonfigurations Prüfung befindet sich unter% Program Files% \\ [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \120\setup Bootstrap\LOG \\<YYYYMMDD_HHMM>\\ .</span><span class="sxs-lookup"><span data-stu-id="98ec1-108">The system configuration check report is located at %programfiles%\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\120\Setup Bootstrap\Log\\<YYYYMMDD_HHMM>\\.</span></span>  
  
 <span data-ttu-id="98ec1-109">Bevor Sie Setup ausführen, lesen Sie die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="98ec1-109">Before you run the setup operation, review the following topics:</span></span>  
  
1.  [<span data-ttu-id="98ec1-110">Hardware- und Softwareanforderungen für die Installation von SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="98ec1-110">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
2.  [<span data-ttu-id="98ec1-111">Von den Editionen von SQL Server 2014 unterstützte Features</span><span class="sxs-lookup"><span data-stu-id="98ec1-111">Features Supported by the Editions of SQL Server 2014</span></span>](../../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
3.  [<span data-ttu-id="98ec1-112">Überlegungen zur Sicherheit bei SQL Server-Installationen</span><span class="sxs-lookup"><span data-stu-id="98ec1-112">Security Considerations for a SQL Server Installation</span></span>](../../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
4.  [<span data-ttu-id="98ec1-113">Lokale Sprachversionen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="98ec1-113">Local Language Versions in SQL Server</span></span>](../../../2014/sql-server/install/local-language-versions-in-sql-server.md)  
  
 <span data-ttu-id="98ec1-114">Weitere Referenzen:</span><span class="sxs-lookup"><span data-stu-id="98ec1-114">Other references:</span></span>  
  
1.  [<span data-ttu-id="98ec1-115">Unterstützte Versions- und Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="98ec1-115">Supported Version and Edition Upgrades</span></span>](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)  
  
2.  [<span data-ttu-id="98ec1-116">Vor dem Installieren des Failoverclusterings</span><span class="sxs-lookup"><span data-stu-id="98ec1-116">Before Installing Failover Clustering</span></span>](../failover-clusters/install/before-installing-failover-clustering.md)  
  
## <a name="see-also"></a><span data-ttu-id="98ec1-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98ec1-117">See Also</span></span>  
 [<span data-ttu-id="98ec1-118">Installationsregeln</span><span class="sxs-lookup"><span data-stu-id="98ec1-118">Install Rules</span></span>](../../../2014/sql-server/install/install-rules.md)  
  
  
