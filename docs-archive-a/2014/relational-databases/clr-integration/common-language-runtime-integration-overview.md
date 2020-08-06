---
title: Übersicht über die CLR-Integration (Common Language Runtime) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- managed code [SQL Server]
- common language runtime [SQL Server], about CLR integration
- cross-language integration
- integrating CLR [SQL Server]
- .NET Framework [SQL Server], common language runtime
- code access security [CLR integration]
- managed code [SQL Server], CLR integration
ms.assetid: 7be9e644-36a2-48fc-9206-faf59fdff4d7
author: rothja
ms.author: jroth
ms.openlocfilehash: 25345fd39fb8a77f62e4e352b75629a98cb9d7af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617119"
---
# <a name="common-language-runtime-clr-integration-overview"></a><span data-ttu-id="6d352-102">Übersicht über die CLR-Integration (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="6d352-102">Common Language Runtime (CLR) Integration Overview</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="6d352-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]bietet jetzt die Integration der Common Language Runtime (CLR)-Komponente des .NET Framework für [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="6d352-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] now features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="6d352-104">Die CLR-Komponente stellt verwalteten Code mit Diensten bereit, wie z. B. sprachübergreifende Integration, Codezugriffssicherheit, Verwaltung der Objektlebensdauer und Debug- und Profilerstellungsunterstützung.</span><span class="sxs-lookup"><span data-stu-id="6d352-104">The CLR supplies managed code with services such as cross-language integration, code access security, object lifetime management, and debugging and profiling support.</span></span> <span data-ttu-id="6d352-105">Für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Benutzer und -Anwendungsentwickler bedeutet die CLR-Integration, dass sie nunmehr gespeicherte Prozeduren, Trigger, benutzerdefinierte Typen, benutzerdefinierte Funktionen (Skalar- und Tabellenwertfunktionen) sowie benutzerdefinierte Aggregatfunktionen mit einer beliebigen .NET Framework-Sprache, einschließlich [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET und [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#, schreiben können.</span><span class="sxs-lookup"><span data-stu-id="6d352-105">For [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] users and application developers, CLR integration means that you can now write stored procedures, triggers, user-defined types, user-defined functions (scalar and table-valued), and user-defined aggregate functions using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span> <span data-ttu-id="6d352-106">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ist .NET Framework, Version 4, vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="6d352-106">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] includes the .NET Framework version 4 pre-installed.</span></span>  
  
 <span data-ttu-id="6d352-107">Zu den Hauptvorteilen dieser Integration zählen folgende:</span><span class="sxs-lookup"><span data-stu-id="6d352-107">Among the major benefits of this integration are:</span></span>  
  
-   <span data-ttu-id="6d352-108">**Ein besseres Programmiermodell.**</span><span class="sxs-lookup"><span data-stu-id="6d352-108">**A better programming model.**</span></span> <span data-ttu-id="6d352-109">Die .NET Framework-Sprachen sind in vielerlei Hinsicht umfassender als Transact-SQL. Sie bieten Konstrukte und Fähigkeiten, die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Entwicklern zuvor nicht zur Verfügung standen.</span><span class="sxs-lookup"><span data-stu-id="6d352-109">The .NET Framework languages are in many respects richer than Transact-SQL, offering constructs and capabilities previously not available to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developers.</span></span> <span data-ttu-id="6d352-110">Entwickler können zudem die leistungsfähigen Funktionen der .NET Framework-Bibliothek nutzen, die einen umfassenden Satz Klassen bereitstellt. Diese ermöglichen es, Programmierungsprobleme schnell und effizient zu lösen.</span><span class="sxs-lookup"><span data-stu-id="6d352-110">Developers may also leverage the power of the .NET Framework Library, which provides an extensive set of classes that can be used to quickly and efficiently solve programming problems.</span></span>  
  
-   <span data-ttu-id="6d352-111">**Verbesserte Sicherheit und Zuverlässigkeit.**</span><span class="sxs-lookup"><span data-stu-id="6d352-111">**Improved safety and security.**</span></span> <span data-ttu-id="6d352-112">Verwalteter Code wird in einer von der Datenbank-Engine gehosteten Common Language Runtime-Umgebung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d352-112">Managed code runs in a common language run-time environment, hosted by the Database Engine.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="6d352-113">nutzt dies, um eine sicherere Alternative zu den erweiterten gespeicherten Prozeduren zu bieten, die in früheren Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="6d352-113">leverages this to provide a safer and more secure alternative to the extended stored procedures available in earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6d352-114">**Fähigkeit, Datentypen und Aggregatsfunktionen zu definieren.**</span><span class="sxs-lookup"><span data-stu-id="6d352-114">**Ability to define data types and aggregate functions.**</span></span> <span data-ttu-id="6d352-115">Benutzerdefinierte Typen und benutzerdefinierte Aggregate sind zwei neue verwaltete Datenbankobjekte, die die Speicher- und Abfragefunktionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erweitern.</span><span class="sxs-lookup"><span data-stu-id="6d352-115">User defined types and user defined aggregates are two new managed database objects which expand the storage and querying capabilities of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="6d352-116">**Rationalisierte Entwicklung durch eine standardisierte Umgebung.**</span><span class="sxs-lookup"><span data-stu-id="6d352-116">**Streamlined development through a standardized environment.**</span></span> <span data-ttu-id="6d352-117">Die Datenbankentwicklung ist in zukünftige Versionen der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET-Entwicklungsumgebung integriert.</span><span class="sxs-lookup"><span data-stu-id="6d352-117">Database development is integrated into future releases of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio .NET development environment.</span></span> <span data-ttu-id="6d352-118">Entwickler verwenden für das Entwickeln und Debuggen von Datenbankobjekten und Skripts dieselben Tools wie für das Schreiben von .NET Framework-Komponenten und -Diensten auf mittlerer Ebene oder Clientebene.</span><span class="sxs-lookup"><span data-stu-id="6d352-118">Developers use the same tools for developing and debugging database objects and scripts as they use to write middle-tier or client-tier .NET Framework components and services.</span></span>  
  
-   <span data-ttu-id="6d352-119">**Potenziell verbesserte Leistung und Skalierbarkeit.**</span><span class="sxs-lookup"><span data-stu-id="6d352-119">**Potential for improved performance and scalability.**</span></span> <span data-ttu-id="6d352-120">In vielen Situationen sorgen die Kompilierungs- und Ausführungsmodelle der .NET Framework-Sprachen für eine verbesserte Leistungsfähigkeit gegenüber Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="6d352-120">In many situations, the .NET Framework language compilation and execution models deliver improved performance over Transact-SQL.</span></span>  
  
 <span data-ttu-id="6d352-121">In der folgenden Tabelle sind die Themen in diesem Abschnitt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6d352-121">This following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="6d352-122">Übersicht über die CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="6d352-122">Overview of CLR Integration</span></span>](clr-integration-overview.md)  
 <span data-ttu-id="6d352-123">Beschreibt, welche Objekte mit der CLR-Integration erstellt werden können, und beschreibt die Anforderungen zur Erstellung von Datenbankobjekten mithilfe der CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="6d352-123">Describes the kinds of objects that can be built using CLR integration, and reviews the requirements for building database objects using CLR integration.</span></span>  
  
 [<span data-ttu-id="6d352-124">Neuigkeiten bei der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="6d352-124">What's New in CLR Integration</span></span>](clr-integration-what-s-new.md)  
 <span data-ttu-id="6d352-125">Beschreibt die neuen Funktionen in dieser Version.</span><span class="sxs-lookup"><span data-stu-id="6d352-125">Describes the new features in this release.</span></span>  
  
 [<span data-ttu-id="6d352-126">Architektur der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="6d352-126">Architecture of CLR Integration</span></span>](../../database-engine/dev-guide/architecture-of-clr-integration.md)  
 <span data-ttu-id="6d352-127">Beschreibt die Entwurfsziele der CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="6d352-127">Describes the design goals of CLR integration.</span></span>  
  
 [<span data-ttu-id="6d352-128">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="6d352-128">Enabling CLR Integration</span></span>](clr-integration-enabling.md)  
 <span data-ttu-id="6d352-129">Beschreibt, wie die CLR-Integration aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="6d352-129">Describes how to enable CLR integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d352-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d352-130">See Also</span></span>  
 <span data-ttu-id="6d352-131">[Installieren des .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span><span class="sxs-lookup"><span data-stu-id="6d352-131">[Installing the .NET Framework](https://technet.microsoft.com/library/ms166014\(v=SQL.105\).aspx) </span></span>  
 [<span data-ttu-id="6d352-132">Leistungsfähigkeit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="6d352-132">Performance of CLR Integration</span></span>](clr-integration-architecture-performance.md)  
  
  
