---
title: Analysis Services OLE DB-Anbieter (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services OLE DB Provider
ms.assetid: cdeecd50-1d91-4162-a4a2-01c7799b02a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c0348a23a6def4c3cdbd083354083947ce1390b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622945"
---
# <a name="analysis-services-ole-db-provider-analysis-services---multidimensional-data"></a><span data-ttu-id="4829e-102">OLE DB-Anbieter für Analysis Services (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="4829e-102">Analysis Services OLE DB Provider (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4829e-103">Der-Analysis Services OLE DB-Anbieter ist eine Schnittstelle für Anwendungen, die mit interagieren [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4829e-103">The Analysis Services OLE DB Provider is an interface for applications interacting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4829e-104">Er wird verwendet, um Clientanwendungen zu erstellen, die mit mehrdimensionalen Daten interagieren.</span><span class="sxs-lookup"><span data-stu-id="4829e-104">It is used to build client applications that interact with multidimensional data.</span></span> <span data-ttu-id="4829e-105">Dieser Anbieter stellt auch Methoden für Online- und Offline-Data Mining-Analysen von mehrdimensionalen Daten und relationalen Daten bereit und ist Bestandteil von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4829e-105">This provider also provides methods for online and offline data mining analysis of multidimensional data and relational data, and is included as part of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4829e-106">Er kann von Clientanwendungen eines Drittanbieters verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4829e-106">It can be redistributed by third-party client applications.</span></span>  
  
 <span data-ttu-id="4829e-107">Der OLE DB-Anbieter für Analysis Services ist die Hauptmethode für die Interaktion mit [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] zur Ausführung von Aufgaben wie dem Verbinden mit einem Cube oder Data Mining-Modell, dem Abfragen eines Cubes oder Data Mining-Modells und dem Abrufen von Schemainformationen.</span><span class="sxs-lookup"><span data-stu-id="4829e-107">The Analysis Services OLE DB Provider is the primary method for interacting with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in order to accomplish such tasks as connecting to a cube or data mining model, querying a cube or data mining model, and retrieving schema information.</span></span>  
  
 <span data-ttu-id="4829e-108">Als eigenständiger Anbieter stellt der OLE DB-Anbieter für Analysis Services Clientanwendungen mit der Fähigkeit bereit, lokale Cubedateien und Mining-Modelle aus relationalen und mehrdimensionalen Quellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4829e-108">As a stand-alone provider, the Analysis Services OLE DB Provider provides client applications with the ability to create local cube files and mining models from relational and multidimensional sources.</span></span> <span data-ttu-id="4829e-109">Clientanwendungen können Verbindungen mit einem lokalen Cube herstellen und mithilfe von Multidimensional Expressions (MDX) Abfragen durchführen, ohne mit dem Server zu interagieren, auf dem die Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4829e-109">Client applications can connect to a local cube and execute queries using Multidimensional Expressions (MDX) without interacting with the full-scale server running the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4829e-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4829e-110">See Also</span></span>  
 [<span data-ttu-id="4829e-111">Datenzugriff auf mehrdimensionale Modelle &#40;Analysis Services-mehrdimensionalen Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="4829e-111">Multidimensional Model Data Access &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/mdx/multidimensional-model-data-access-analysis-services-multidimensional-data.md)  
  
  
