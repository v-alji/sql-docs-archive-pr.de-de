---
title: Grundlegendes zur Microsoft OLAP-Architektur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- multidimensional data [Analysis Services], about multidimensional data
ms.assetid: a2eaaee8-7b06-48af-ba44-e21a3678c4c4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1abbbbd7c2f7caa99407bbcd17ace07deac5dfeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619409"
---
# <a name="understanding-microsoft-olap-architecture"></a><span data-ttu-id="bfbb6-102">Grundlegendes zur Microsoft OLAP-Architektur</span><span class="sxs-lookup"><span data-stu-id="bfbb6-102">Understanding Microsoft OLAP Architecture</span></span>
  <span data-ttu-id="bfbb6-103">Diese Themen erläutern die Funktionsweise der mehrdimensionalen [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-Datenbanken und helfen bei der Planung der Implementierung von mehrdimensionalen Datenbanken in Ihrer Business Intelligence-Lösung.</span><span class="sxs-lookup"><span data-stu-id="bfbb6-103">Use these topics to better understand [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] multidimensional databases and plan how to implement multidimensional databases in your business intelligence solution.</span></span>  
  
 <span data-ttu-id="bfbb6-104">![Kleines Datei Ordnersymbol](../../../integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") **logische Architektur**</span><span class="sxs-lookup"><span data-stu-id="bfbb6-104">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Logical Architecture**</span></span>  
 [<span data-ttu-id="bfbb6-105">Server Objekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-105">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-logical/server-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="bfbb6-106">Dimensions Objekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-106">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="bfbb6-107">Cubeobjekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-107">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="bfbb6-108">Weitere Informationen...</span><span class="sxs-lookup"><span data-stu-id="bfbb6-108">More...</span></span>](../olap-logical/understanding-microsoft-olap-logical-architecture.md)  
  
 <span data-ttu-id="bfbb6-109">![Kleines Datei Ordnersymbol](../../../integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") **physische Architektur**</span><span class="sxs-lookup"><span data-stu-id="bfbb6-109">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Physical Architecture**</span></span>  
 [<span data-ttu-id="bfbb6-110">OLAP-Engine-Serverkomponenten</span><span class="sxs-lookup"><span data-stu-id="bfbb6-110">OLAP Engine Server Components</span></span>](olap-engine-server-components.md)  
  
 [<span data-ttu-id="bfbb6-111">Lokale Cubes &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-111">Local Cubes &#40;Analysis Services - Multidimensional Data&#41;</span></span>](local-cubes-analysis-services-multidimensional-data.md)  
  
 [<span data-ttu-id="bfbb6-112">Weitere Informationen...</span><span class="sxs-lookup"><span data-stu-id="bfbb6-112">More...</span></span>](understanding-microsoft-olap-physical-architecture.md)  
  
 <span data-ttu-id="bfbb6-113">![Kleines Datei Ordnersymbol](../../../integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") **Programmier Architektur**</span><span class="sxs-lookup"><span data-stu-id="bfbb6-113">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **Programming Architecture**</span></span>  
 [<span data-ttu-id="bfbb6-114">Entwickeln mit Analysis Management Objects &#40;AMO&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-114">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
  
 [<span data-ttu-id="bfbb6-115">Entwickeln mit Analysis Services Scripting Language &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-115">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
  
 [<span data-ttu-id="bfbb6-116">Entwickeln mit ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="bfbb6-116">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
  
 <span data-ttu-id="bfbb6-117">![Kleines Datei Ordnersymbol](../../../integration-services/media/filefolder-small.gif "Kleines Dateiordnersymbol") **Internationale Überlegungen**</span><span class="sxs-lookup"><span data-stu-id="bfbb6-117">![Small File Folder Icon](../../../integration-services/media/filefolder-small.gif "Small File Folder Icon") **International Considerations**</span></span>  
 [<span data-ttu-id="bfbb6-118">Globalisierungsszenarien für Analysis Services Multidimensional</span><span class="sxs-lookup"><span data-stu-id="bfbb6-118">Globalization scenarios for Analysis Services Multiidimensional</span></span>](../../globalization-scenarios-for-analysis-services-multiidimensional.md)  
  
## <a name="see-also"></a><span data-ttu-id="bfbb6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfbb6-119">See Also</span></span>  
 [<span data-ttu-id="bfbb6-120">Technische Referenz &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="bfbb6-120">Technical Reference &#40;SSAS&#41;</span></span>](../../powershell/technical-reference-ssas.md)  
  
  
