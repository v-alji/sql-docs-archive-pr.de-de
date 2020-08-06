---
title: Upgrade auf SQL Server 2014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- upgrading SQL Server
ms.assetid: 5064e35b-b70d-4a0b-a9e9-fff04162f9d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 857bbd6d7269b7675653b11a9d7c0acd07927f62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698517"
---
# <a name="upgrade-to-sql-server-2014"></a><span data-ttu-id="4ae65-102">Aktualisieren auf SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4ae65-102">Upgrade to SQL Server 2014</span></span>
  <span data-ttu-id="4ae65-103">Sie können Instanzen von [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]oder [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ae65-103">You can upgrade instances of, [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4ae65-104">Vor dem Ausführen des Setups von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zur Aktualisierung auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], sehen Sie sich das [Technisches Referenzhandbuch für die Aktualisierung auf SQL Server 2014](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (PDF-Download) an, lesen Sie die Themen über den Aktualisierungsprozess in diesem Abschnitt, und lesen Sie die [Versionshinweise für SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296445).</span><span class="sxs-lookup"><span data-stu-id="4ae65-104">Before running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup to upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], check out the [SQL Server 2014 Upgrade Technical Guide](https://download.microsoft.com/download/7/1/5/715BDFA7-51B6-4D7B-AF17-61E78C7E538F/SQL_Server_2014_Upgrade_technical_guide.pdf) (PDF download), review the topics about the upgrade process in this section, and read the [SQL Server 2014 Release Notes](https://go.microsoft.com/fwlink/?LinkID=296445).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ae65-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4ae65-105">In This Section</span></span>  
 <span data-ttu-id="4ae65-106">Dieser Abschnitt enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4ae65-106">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="4ae65-107">Unterstützte Versions- und Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="4ae65-107">Supported Version and Edition Upgrades</span></span>](supported-version-and-edition-upgrades.md)  
  
-   [<span data-ttu-id="4ae65-108">Verwenden von Upgrade Advisor zur Vorbereitung auf Upgrades</span><span class="sxs-lookup"><span data-stu-id="4ae65-108">Use Upgrade Advisor to Prepare for Upgrades</span></span>](../../sql-server/install/use-upgrade-advisor-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="4ae65-109">Vorbereiten von Upgrades mit dem Distributed Replay-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="4ae65-109">Use the Distributed Replay Utility to Prepare for Upgrades</span></span>](../../sql-server/install/use-the-distributed-replay-utility-to-prepare-for-upgrades.md)  
  
-   [<span data-ttu-id="4ae65-110">Aktualisieren von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4ae65-110">Upgrade Analysis Services</span></span>](upgrade-analysis-services.md)  
  
-   [<span data-ttu-id="4ae65-111">Aktualisieren der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="4ae65-111">Upgrade Database Engine</span></span>](upgrade-database-engine.md)  
  
-   [<span data-ttu-id="4ae65-112">Aktualisieren von Data Quality Services</span><span class="sxs-lookup"><span data-stu-id="4ae65-112">Upgrade Data Quality Services</span></span>](upgrade-data-quality-services.md)  
  
-   [<span data-ttu-id="4ae65-113">Upgrade von Integration Services</span><span class="sxs-lookup"><span data-stu-id="4ae65-113">Upgrade Integration Services</span></span>](../../integration-services/install-windows/upgrade-integration-services.md)  
  
-   [<span data-ttu-id="4ae65-114">Aktualisieren von Master Data Services</span><span class="sxs-lookup"><span data-stu-id="4ae65-114">Upgrade Master Data Services</span></span>](upgrade-master-data-services.md)  
  
-   [<span data-ttu-id="4ae65-115">Upgraden von PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="4ae65-115">Upgrade PowerPivot for SharePoint</span></span>](upgrade-power-pivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="4ae65-116">Aktualisieren von replizierten Datenbanken</span><span class="sxs-lookup"><span data-stu-id="4ae65-116">Upgrade Replicated Databases</span></span>](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
-   [<span data-ttu-id="4ae65-117">Aktualisieren und Migrieren von Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4ae65-117">Upgrade and Migrate Reporting Services</span></span>](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md)  
  
-   [<span data-ttu-id="4ae65-118">Aktualisieren der SQL Server-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="4ae65-118">Upgrade SQL Server Management Tools</span></span>](upgrade-sql-server-management-tools.md)  
  
-   [<span data-ttu-id="4ae65-119">Artikel zur Vorgehensweise beim Upgrade</span><span class="sxs-lookup"><span data-stu-id="4ae65-119">Upgrade How-to Topics</span></span>](../../../2014/sql-server/install/upgrade-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ae65-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4ae65-120">See Also</span></span>  
 <span data-ttu-id="4ae65-121">[Aktualisieren der Datenbank-Engine](upgrade-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="4ae65-121">[Upgrade Database Engine](upgrade-database-engine.md) </span></span>  
 <span data-ttu-id="4ae65-122">[Aktualisieren von Analysis Services](upgrade-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ae65-122">[Upgrade Analysis Services](upgrade-analysis-services.md) </span></span>  
 <span data-ttu-id="4ae65-123">[Aktualisieren und Migrieren von Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ae65-123">[Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md) </span></span>  
 <span data-ttu-id="4ae65-124">[Upgrade von Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ae65-124">[Upgrade Integration Services](../../integration-services/install-windows/upgrade-integration-services.md) </span></span>  
 <span data-ttu-id="4ae65-125">[Aktualisieren von replizierten Datenbanken](../../database-engine/install-windows/upgrade-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4ae65-125">[Upgrade Replicated Databases](../../database-engine/install-windows/upgrade-replicated-databases.md) </span></span>  
 <span data-ttu-id="4ae65-126">[Aktualisieren von Master Data Services](upgrade-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="4ae65-126">[Upgrade Master Data Services](upgrade-master-data-services.md) </span></span>  
 <span data-ttu-id="4ae65-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span><span class="sxs-lookup"><span data-stu-id="4ae65-127">[SQL Server 2012 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=29302) </span></span>  
 <span data-ttu-id="4ae65-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span><span class="sxs-lookup"><span data-stu-id="4ae65-128">[SQL Server 2008 R2 Best Practices Analyzer](https://www.microsoft.com/download/details.aspx?id=436) </span></span>  
 [<span data-ttu-id="4ae65-129">Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="4ae65-129">Backward Compatibility</span></span>](../../../2014/getting-started/backward-compatibility.md)  
  
  
