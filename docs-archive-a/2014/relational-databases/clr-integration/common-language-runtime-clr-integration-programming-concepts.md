---
title: Programmier Konzepte für die Common Language Runtime (CLR)-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- CLR [SQL Server] See common language runtime [SQL Server]
- Database Engine [SQL Server], .NET Framework
- .NET Framework [SQL Server], Database Engine programming
- common language runtime [SQL Server]
- .NET Framework [SQL Server]
ms.assetid: 951bf851-3e6e-4361-ae6a-2bcd5b837ebd
author: rothja
ms.author: jroth
ms.openlocfilehash: 38323b0145132ad60d59c001d5147a7d19942462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616586"
---
# <a name="common-language-runtime-clr-integration-programming-concepts"></a><span data-ttu-id="c40ac-102">Programmierkonzepte für die Common Language Runtime (CLR)-Integration</span><span class="sxs-lookup"><span data-stu-id="c40ac-102">Common Language Runtime (CLR) Integration Programming Concepts</span></span>
  <span data-ttu-id="c40ac-103">Ab [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]enthält [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Integration der CLR-Komponente (Common Language Runtime) des .NET Framework für [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="c40ac-103">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features the integration of the common language runtime (CLR) component of the .NET Framework for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span></span> <span data-ttu-id="c40ac-104">Das bedeutet, dass Sie jetzt gespeicherte Prozeduren, Trigger, benutzerdefinierte Typen, benutzerdefinierte Funktionen, benutzerdefinierte Aggregate und Streaming-Tabellenwertfunktionen mit einer beliebigen .NET Framework-Sprache schreiben können, einschließlich [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET und [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="c40ac-104">This means that you can now write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
 <span data-ttu-id="c40ac-105">Der Microsoft.SqlServer.Server-Namespace beinhaltet Kernfunktionalität für die CLR-Programmierung in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c40ac-105">The Microsoft.SqlServer.Server namespace includes core functionality for CLR programming in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c40ac-106">Der Microsoft.SqlServer.Server-Namespace hingegen ist im NET Framework SDK dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="c40ac-106">However, the Microsoft.SqlServer.Server namespace is documented in the .NET Framework SDK.</span></span> <span data-ttu-id="c40ac-107">Diese Dokumentation ist nicht in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] der Onlinedokumentation enthalten.</span><span class="sxs-lookup"><span data-stu-id="c40ac-107">This documentation is not included in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c40ac-108">Standardmäßig ist .NET Framework unter [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]installiert; dies gilt jedoch nicht für .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="c40ac-108">By default, the .NET Framework is installed with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but the .NET Framework SDK is not.</span></span> <span data-ttu-id="c40ac-109">Wenn SDK auf Ihrem Computer nicht installiert ist und nicht in der Onlinedokumentation aufgeführt wird, funktionieren die in diesem Abschnitt aufgeführten Links zu SDK-Inhalten nicht.</span><span class="sxs-lookup"><span data-stu-id="c40ac-109">Without the SDK installed on your computer and included in the Books Online collection, links to SDK content in this section do not work.</span></span> <span data-ttu-id="c40ac-110">Installieren Sie das .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="c40ac-110">Install the .NET Framework SDK.</span></span> <span data-ttu-id="c40ac-111">Fügen Sie das SDK nach der Installation der Onlinedokumentation und dem Inhaltsverzeichnis hinzu, indem Sie die Anweisungen unter [Installieren des .NET Framework SDKs](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)befolgen.</span><span class="sxs-lookup"><span data-stu-id="c40ac-111">Once installed, add the SDK to the Books Online collection and table of contents by following the instructions in [Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx).</span></span>  
  
 <span data-ttu-id="c40ac-112">In der folgenden Tabelle sind die Themen dieses Abschnitts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c40ac-112">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="c40ac-113">Übersicht über die CLR-&#41; Integration in Common Language Runtime &#40;</span><span class="sxs-lookup"><span data-stu-id="c40ac-113">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](common-language-runtime-integration-overview.md)  
 <span data-ttu-id="c40ac-114">Bietet eine kurze Übersicht über CLR und beschreibt die Verwendung dieser Technologie in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c40ac-114">Provides a brief overview of the CLR, and describes how and why this technology has been used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c40ac-115">Beschreibt die Vorteile der Verwendung von CLR zur Erstellung von Datenbankobjekten.</span><span class="sxs-lookup"><span data-stu-id="c40ac-115">Describes the benefits of using the CLR to create database objects.</span></span>  
  
 [<span data-ttu-id="c40ac-116">Assemblys &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="c40ac-116">Assemblies &#40;Database Engine&#41;</span></span>](assemblies-database-engine.md)  
 <span data-ttu-id="c40ac-117">Beschreibt, wie Assemblys in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet werden, um Funktionen, gespeicherte Prozeduren, Trigger, benutzerdefinierte Aggregate und benutzerdefinierte Typen bereitzustellen, die in einer der verwalteten Codesprachen geschrieben wurden, die von der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework-CLR (Common Language Runtime) gehostet werden, und nicht in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c40ac-117">Describes how assemblies are used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework common language runtime (CLR), and not written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 [<span data-ttu-id="c40ac-118">Aufbauen von Datenbankobjekten mit CLR-&#41; Integration (Common Language Runtime) &#40;</span><span class="sxs-lookup"><span data-stu-id="c40ac-118">Building Database Objects with Common Language Runtime &#40;CLR&#41; Integration</span></span>](database-objects/building-database-objects-with-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="c40ac-119">Beschreibt, welche Objekte mit CLR erstellt werden können, sowie die Anforderungen zur Erstellung von CLR-Datenbankobjekten.</span><span class="sxs-lookup"><span data-stu-id="c40ac-119">Describes the kinds of objects that can be built using the CLR, and reviews the requirements for building CLR database objects.</span></span>  
  
 [<span data-ttu-id="c40ac-120">Data Access from CLR Database Objects</span><span class="sxs-lookup"><span data-stu-id="c40ac-120">Data Access from CLR Database Objects</span></span>](data-access/data-access-from-clr-database-objects.md)  
 <span data-ttu-id="c40ac-121">Beschreibt, wie eine CLR-Routine auf Daten zugreifen kann, die in einer Instanz von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c40ac-121">Describes how a CLR routine can access data stored in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c40ac-122">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="c40ac-122">CLR Integration Security</span></span>](security/clr-integration-security.md)  
 <span data-ttu-id="c40ac-123">Beschreibt das Sicherheitsmodell der CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="c40ac-123">Describes the CLR integration security model.</span></span>  
  
 [<span data-ttu-id="c40ac-124">Debuggen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="c40ac-124">Debugging CLR Database Objects</span></span>](debugging-clr-database-objects.md)  
 <span data-ttu-id="c40ac-125">Beschreibt Einschränkungen und Anforderungen des Debuggens von CLR-Datenbankobjekten.</span><span class="sxs-lookup"><span data-stu-id="c40ac-125">Describes limitations of and requirements for debugging CLR database objects.</span></span>  
  
 [<span data-ttu-id="c40ac-126">Bereitstellen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="c40ac-126">Deploying CLR Database Objects</span></span>](deploying-clr-database-objects.md)  
 <span data-ttu-id="c40ac-127">Beschreibt die Bereitstellung von Assemblys auf Produktionsservern.</span><span class="sxs-lookup"><span data-stu-id="c40ac-127">Describes deploying assemblies to production servers.</span></span>  
  
 [<span data-ttu-id="c40ac-128">Verwalten von CLR-Integrationsassemblys</span><span class="sxs-lookup"><span data-stu-id="c40ac-128">Managing CLR Integration Assemblies</span></span>](assemblies/managing-clr-integration-assemblies.md)  
 <span data-ttu-id="c40ac-129">Beschreibt das Erstellen und Löschen der Assemblys zur CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="c40ac-129">Describes how to create and drop CLR integration assemblies.</span></span>  
  
 [<span data-ttu-id="c40ac-130">Überwachung und Problembehandlung von verwalteten Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="c40ac-130">Monitoring and Troubleshooting Managed Database Objects</span></span>](monitoring-and-troubleshooting-managed-database-objects.md)  
 <span data-ttu-id="c40ac-131">Enthält Informationen zu den Tools, die zum Überwachen und zur Problembehandlung von verwalteten Datenbankobjekten und Assemblys in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c40ac-131">Provides information about the tools that can be used to monitor and troubleshoot managed database objects and assemblies running in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c40ac-132">Verwendungsszenarios und Beispiele für Common Language Runtime-Integration &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="c40ac-132">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
 <span data-ttu-id="c40ac-133">Beschreibt Verwendungsszenarien und Codebeispiele mit CLR-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c40ac-133">Describes usage scenarios and code samples using CLR objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40ac-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c40ac-134">See Also</span></span>  
 <span data-ttu-id="c40ac-135">[Assemblys &#40;Datenbank-Engine&#41;](assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="c40ac-135">[Assemblies &#40;Database Engine&#41;](assemblies-database-engine.md) </span></span>  
 <span data-ttu-id="c40ac-136">[Installieren des .NET Framework SDKs](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="c40ac-136">[Installing the .NET Framework SDK](https://technet.microsoft.com/library/bb686823\(v=SQL.105\).aspx)</span></span>  
  
  
