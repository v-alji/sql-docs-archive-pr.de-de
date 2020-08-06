---
title: ADOMD.NET-Server Programmierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- programming [ADOMD.NET]
- ADOMD.NET, programming
ms.assetid: 7f7ff5be-3826-43a5-b94d-ddeec5ddb2eb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 522478af0b19f1745d80f167e40345d4751136b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694798"
---
# <a name="adomdnet-server-programming"></a><span data-ttu-id="0818b-102">ADOMD.NET-Serverprogrammierung</span><span class="sxs-lookup"><span data-stu-id="0818b-102">ADOMD.NET Server Programming</span></span>
  <span data-ttu-id="0818b-103">Die ADOMD.NET-Serverkomponenten von ADOMD.NET befinden sich innerhalb des `Microsoft.AnalysisServices.AdomdServer`-Namespace (in msmgdsrv.dll).</span><span class="sxs-lookup"><span data-stu-id="0818b-103">The ADOMD.NET server components of ADOMD.NET reside within the `Microsoft.AnalysisServices.AdomdServer` namespace (in msmgdsrv.dll).</span></span> <span data-ttu-id="0818b-104">Sie verwenden diese Serverkomponenten, um benutzerdefinierte MDX-Funktionen (Multidimensional Expressions) und gespeicherte Prozeduren zu erstellen, die auf einer Instanz von ausgeführt werden [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0818b-104">You use these server components to create custom Multidimensional Expressions (MDX) functions and stored procedures that are run on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="0818b-105">Die Serverobjekte stellen die Funktionen für die Abfrage von Cubes und Miningmodellen und für die Bewertung von Ausdrücken in einem gegebenen Kontext bereit.</span><span class="sxs-lookup"><span data-stu-id="0818b-105">The server objects provide the capabilities for querying cubes and mining models, and for evaluating expressions in a given context.</span></span> <span data-ttu-id="0818b-106">Zu den Vorteilen der Erstellung benutzerdefinierter Funktionen und gespeicherter Prozeduren gehören eine schnelle Ausführung, eine zentralisierte Bereitstellung und eine verbesserte Wartungsfreundlichkeit.</span><span class="sxs-lookup"><span data-stu-id="0818b-106">The benefits for creating custom functions and stored procedures include fast execution, centralized deployment, and improved maintainability.</span></span>  
  
 <span data-ttu-id="0818b-107">Die Themen in der folgenden Tabelle helfen Ihnen, ADOMD.NET-Serveranwendungen zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="0818b-107">The topics in the following table will help you develop ADOMD.NET server applications.</span></span>  
  
|<span data-ttu-id="0818b-108">Thema</span><span class="sxs-lookup"><span data-stu-id="0818b-108">Topic</span></span>|<span data-ttu-id="0818b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0818b-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0818b-110">ADOMD.NET-Serverfunktionalität</span><span class="sxs-lookup"><span data-stu-id="0818b-110">ADOMD.NET Server Functionality</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-functionality)|<span data-ttu-id="0818b-111">Beschreibt die Verwendungen für ADOMD.NET-Serverobjekte.</span><span class="sxs-lookup"><span data-stu-id="0818b-111">Describes the uses for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="0818b-112">ADOMD.NET-Serverobjektarchitektur</span><span class="sxs-lookup"><span data-stu-id="0818b-112">ADOMD.NET Server Object Architecture</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-object-architecture)|<span data-ttu-id="0818b-113">Beschreibt die Objektarchitektur für ADOMD.NET-Serverobjekte.</span><span class="sxs-lookup"><span data-stu-id="0818b-113">Describes the object architecture for ADOMD.NET server objects.</span></span>|  
|[<span data-ttu-id="0818b-114">Benutzerdefinierte Funktionen und gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0818b-114">User Defined Functions and Stored Procedures</span></span>](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-server/user-defined-functions-and-stored-procedures)|<span data-ttu-id="0818b-115">Führt Sie durch den Prozess der Erstellung einer benutzerdefinierten Funktion oder gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0818b-115">Walks you through the process of creating a user defined function or stored Procedure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0818b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0818b-116">See Also</span></span>  
 <span data-ttu-id="0818b-117">[ADOMD.NET-Client Programmierung](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span><span class="sxs-lookup"><span data-stu-id="0818b-117">[ADOMD.NET Client Programming](https://docs.microsoft.com/analysis-services/adomd/multidimensional-models-adomd-net-client/adomd-net-client-programming) </span></span>  
 [<span data-ttu-id="0818b-118">Entwickeln mit ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="0818b-118">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
  
