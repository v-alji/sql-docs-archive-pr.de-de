---
title: Architektur der CLR-Integration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], architecture
- architecture [CLR integration]
ms.assetid: 05e4b872-3d21-46de-b4d5-739b5f2a0cf9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bb32e2c7f5eb2079146a2fee64af2e2dbc1d3356
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615546"
---
# <a name="architecture-of-clr-integration"></a><span data-ttu-id="e0e5b-102">Architektur der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e0e5b-102">Architecture of CLR Integration</span></span>
  <span data-ttu-id="e0e5b-103">Die Integration von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in die .NET Framework-CLR (Common Language Runtime) ermöglicht Datenbankprogrammierern die Verwendung von Sprachen wie Visual C#, Visual Basic .NET und Visual C++.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR) enables database programmers to use languages such as Visual C#, Visual Basic .NET, and Visual C++.</span></span> <span data-ttu-id="e0e5b-104">Funktionen, gespeicherte Prozeduren, Trigger, Datentypen und Aggregate gehören zu den Arten von Geschäftslogik, die Programmierer in diesen Sprachen schreiben können.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-104">Functions, stored procedures, triggers, data types, and aggregates are among the kinds of business logic that programmers can write with these languages.</span></span>  
  
 <span data-ttu-id="e0e5b-105">In diesem Abschnitt wird die Architektur der CLR-Integration in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beschrieben und erläutert, auf welche Weise diese Architektur eine sichere, skalierbare, geschützte und effiziente Umgebung zur Ausführung von Benutzercode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-105">This section describes the architecture of CLR integration inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and how this architecture provides a safe, scalable, secure, and efficient environment to run user code.</span></span>  
  
 <span data-ttu-id="e0e5b-106">In der folgenden Tabelle sind die Themen dieses Abschnitts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="e0e5b-107">Gehostete CLR-Umgebung</span><span class="sxs-lookup"><span data-stu-id="e0e5b-107">CLR Hosted Environment</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-clr-hosted-environment.md)  
 <span data-ttu-id="e0e5b-108">Erläutert architektonische Entwurfsziele, Mechanismen und Vorteile der CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-108">Discusses architectural design goals, mechanisms, and benefits of CLR integration.</span></span>  
  
 [<span data-ttu-id="e0e5b-109">Leistungsfähigkeit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e0e5b-109">Performance of CLR Integration</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-performance.md)  
 <span data-ttu-id="e0e5b-110">Behandelt leistungsbezogene Überlegungen zur Architektur der CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="e0e5b-110">Covers performance considerations of the CLR integration architecture.</span></span>  
  
  
