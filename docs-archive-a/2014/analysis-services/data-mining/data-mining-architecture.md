---
title: Data Mining-Architektur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 105f52e1-ad3b-4cd0-b67b-06dbb451c304
author: minewiskan
ms.author: owend
ms.openlocfilehash: a372972fd7fa39f7bcfd2e10abbc4fbf8f8c10aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621270"
---
# <a name="data-mining-architecture"></a><span data-ttu-id="bfc42-102">Data Mining-Architektur</span><span class="sxs-lookup"><span data-stu-id="bfc42-102">Data Mining Architecture</span></span>
  <span data-ttu-id="bfc42-103">In diesem Abschnitt wird die Architektur von Data Mining-Lösungen beschrieben, die in einer Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="bfc42-103">This section describes the architecture of data mining solutions that are hosted in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="bfc42-104">In den Themen dieses Abschnitts werden die logische und physische Architektur einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz beschrieben, die Data Mining unterstützt. Darüber hinaus enthalten sie Informationen zu den Clients, Anbietern und Protokollen, die für die Kommunikation mit Data Mining-Servern und die lokale oder Remote-Bearbeitung von Data Mining-Objekten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bfc42-104">The topics in this section describe the logical and physical architecture of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that supports data mining, and also provide information about the clients, providers, and protocols that can be used to communicate with data mining servers, and to work with data mining objects either locally or remotely.</span></span>  
  
 <span data-ttu-id="bfc42-105">Im Allgemeinen ist SQL Server Data Mining ein Dienst, der als ein Teil einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz bereitgestellt und im mehrdimensionalen Modus ausgeführt wird. Daher empfiehlt es sich, dass Sie auch die folgenden Abschnitte in der Onlinedokumentation lesen, in denen Betrieb, Wartung und Konfiguration von mehrdimensionalen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Lösungen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="bfc42-105">In general, SQL Server Data Mining operates as a service that is provided as part of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance running in multidimensional mode; therefore, we recommend that you also review the following sections of Books Online that describe the operation, maintenance, and configuration of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] multidimensional solutions.</span></span>  
  
 [<span data-ttu-id="bfc42-106">Verarbeitung von mehrdimensionalen Modellobjekten</span><span class="sxs-lookup"><span data-stu-id="bfc42-106">Multidimensional Model Object Processing</span></span>](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="bfc42-107">Verbindung mit Analysis Services herstellen</span><span class="sxs-lookup"><span data-stu-id="bfc42-107">Connect to Analysis Services</span></span>](../instances/connect-to-analysis-services.md)  
  
 [<span data-ttu-id="bfc42-108">Datenbankspeicherort</span><span class="sxs-lookup"><span data-stu-id="bfc42-108">Database Storage Location</span></span>](../multidimensional-models/database-storage-location.md)  
  
 [<span data-ttu-id="bfc42-109">Umschalten einer Analysis Services-Datenbank zwischen schreibgeschütztem Modus und Lese-/Schreibmodus</span><span class="sxs-lookup"><span data-stu-id="bfc42-109">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>](../multidimensional-models/switch-an-analysis-services-database-between-readonly-and-readwrite-modes.md)  
  
 <span data-ttu-id="bfc42-110">Weitere Informationen darüber, wie Sie Data Mining in Ihrer Business Intelligence-Lösung implementieren, finden Sie im Abschnitt zu Lösungshandbüchern der MSDN-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="bfc42-110">For more information about how you can implement data mining in your business intelligence solution, see the Solution Guides section of the MSDN Library.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bfc42-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bfc42-111">In This Section</span></span>  
 [<span data-ttu-id="bfc42-112">Logische Architektur &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bfc42-112">Logical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](logical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="bfc42-113">Physische Architektur &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bfc42-113">Physical Architecture &#40;Analysis Services - Data Mining&#41;</span></span>](physical-architecture-analysis-services-data-mining.md)  
  
 [<span data-ttu-id="bfc42-114">Data Mining-Dienste und Datenquellen</span><span class="sxs-lookup"><span data-stu-id="bfc42-114">Data Mining Services and Data Sources</span></span>](data-mining-services-and-data-sources.md)  
  
 [<span data-ttu-id="bfc42-115">Verwaltung von Data Mining-Lösungen und -Objekten</span><span class="sxs-lookup"><span data-stu-id="bfc42-115">Management of Data Mining Solutions and Objects</span></span>](management-of-data-mining-solutions-and-objects.md)  
  
 [<span data-ttu-id="bfc42-116">Sicherheitsübersicht &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bfc42-116">Security Overview &#40;Data Mining&#41;</span></span>](security-overview-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="bfc42-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfc42-117">See Also</span></span>  
 <span data-ttu-id="bfc42-118">[Mehrdimensionale Modell Programmierung](../multidimensional-models/multidimensional-model-programming.md) </span><span class="sxs-lookup"><span data-stu-id="bfc42-118">[Multidimensional Model Programming](../multidimensional-models/multidimensional-model-programming.md) </span></span>  
 [<span data-ttu-id="bfc42-119">Data Mining-Programmierung</span><span class="sxs-lookup"><span data-stu-id="bfc42-119">Data Mining Programming</span></span>](../dev-guide/data-mining-programming.md)  
  
  
