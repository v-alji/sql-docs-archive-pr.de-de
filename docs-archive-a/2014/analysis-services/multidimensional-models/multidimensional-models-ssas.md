---
title: Mehrdimensionale Modellierung (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 509df042-fdb3-4e2c-a6b8-86943ce1b0fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7348a932eccb62f2e00c0b154ca9efc8086fcd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727250"
---
# <a name="multidimensional-modeling-ssas"></a><span data-ttu-id="f4e2c-102">Mehrdimensionale Modellierung (SSAS)</span><span class="sxs-lookup"><span data-stu-id="f4e2c-102">Multidimensional Modeling (SSAS)</span></span>
  <span data-ttu-id="f4e2c-103">Eine mehrdimensionale Analysis Services-Lösung verwendet Cubestrukturen zum Analysieren von Geschäftsdaten über mehrere Dimensionen hinweg.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-103">An Analysis Services multidimensional solution uses cube structures for analyzing business data across multiple dimensions.</span></span> <span data-ttu-id="f4e2c-104">Der mehrdimensionale Modus ist der standardmäßige Servermodus von Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-104">Multidimensional mode is the default server mode of Analysis Services.</span></span> <span data-ttu-id="f4e2c-105">Die Komponente umfasst eine Abfrage- und Berechnungs-Engine für OLAP-Daten, wobei MOLAP-, ROLAP- und HOLAP-Speichermodi die Leistung durch skalierbare Datenanforderungen ausgleichen.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-105">It includes a query and calculation engine for OLAP data, with MOLAP, ROLAP, and HOLAP storage modes to balance performance with scalable data requirements.</span></span> <span data-ttu-id="f4e2c-106">Die Analysis Services-OLAP-Engine ist ein branchenführender OLAP-Server, der für eine breite Palette von BI-Tools gut geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-106">The Analysis Services OLAP engine is an industry leading OLAP server that works well with a broad range of BI tools.</span></span> <span data-ttu-id="f4e2c-107">Die meisten Analysis Services-Bereitstellungen werden als klassische OLAP-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-107">Most Analysis Services deployments are installed as classic OLAP servers.</span></span>  
  
## <a name="benefits-of-using-multidimensional-solutions"></a><span data-ttu-id="f4e2c-108">Vorteile der Verwendung von mehrdimensionalen Lösungen</span><span class="sxs-lookup"><span data-stu-id="f4e2c-108">Benefits of Using Multidimensional Solutions</span></span>  
 <span data-ttu-id="f4e2c-109">Der Hauptgrund zum Erstellen eines mehrdimensionalen Analysis Services-Modells ist, eine schnelle Leistung von Ad-hoc-Abfragen für Geschäftsdaten zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-109">The primary reason for building an Analysis Services multidimensional model is to achieve fast performance of ad hoc queries against business data.</span></span> <span data-ttu-id="f4e2c-110">Ein mehrdimensionales Modell besteht aus Cubes und Dimensionen, die kommentiert werden können und zur Unterstützung komplexer Abfragekonstruktionen erweitert werden können.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-110">A multidimensional model is composed of cubes and dimensions that can be annotated and extended to support complex query constructions.</span></span> <span data-ttu-id="f4e2c-111">BI-Entwickler erstellen Cubes, um schnelle Antwortzeiten zu unterstützen und eine einzelne Datenquelle zur Geschäftsberichterstellung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-111">BI developers create cubes to support fast response times, and to provide a single data source for business reporting.</span></span> <span data-ttu-id="f4e2c-112">Angesichts der wachsenden Wichtigkeit von Business Intelligence über alle Ebenen einer Organisation hinweg stellt eine einzelne Quelle analytischer Daten sicher, dass Diskrepanzen auf einem Minimum gehalten, wenn nicht sogar ganz ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-112">Given the growing importance of business intelligence across all levels of an organization, having a single source of analytical data ensures that discrepancies are kept to a minimum, if not eliminated entirely.</span></span>  
  
 <span data-ttu-id="f4e2c-113">Ein anderer wichtiger Vorteil der Verwendung von mehrdimensionalen Analysis Services-Datenbanken ist die Integration in häufig verwendete BI-Berichtstools wie Excel, Reporting Services und PerformancePoint sowie in benutzerdefinierte Anwendungen und Lösungen von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="f4e2c-113">Another important benefit to using Analysis Services multidimensional databases is integration with commonly used BI reporting tools such as Excel, Reporting Services, and PerformancePoint, as well as custom applications and third-party solutions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4e2c-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f4e2c-114">In This Section</span></span>  
 [<span data-ttu-id="f4e2c-115">Mehrdimensionale Modelllösungen &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="f4e2c-115">Multidimensional Model Solutions &#40;SSAS&#41;</span></span>](multidimensional-model-solutions-ssas.md)  
  
 [<span data-ttu-id="f4e2c-116">Mehrdimensionale Modelldatenbanken &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="f4e2c-116">Multidimensional Model Databases &#40;SSAS&#41;</span></span>](multidimensional-model-databases-ssas.md)  
  
 [<span data-ttu-id="f4e2c-117">Verarbeitung von mehrdimensionalen Modellobjekten</span><span class="sxs-lookup"><span data-stu-id="f4e2c-117">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
 [<span data-ttu-id="f4e2c-118">Rollen und Berechtigungen &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="f4e2c-118">Roles and Permissions &#40;Analysis Services&#41;</span></span>](roles-and-permissions-analysis-services.md)  
  
 [<span data-ttu-id="f4e2c-119">Power View für mehrdimensionale Modelle</span><span class="sxs-lookup"><span data-stu-id="f4e2c-119">Power View for Multidimensional Models</span></span>](power-view-for-multidimensional-models.md)  
  
 [<span data-ttu-id="f4e2c-120">Verwaltung von mehrdimensionalen Modellassemblys</span><span class="sxs-lookup"><span data-stu-id="f4e2c-120">Multidimensional Model Assemblies Management</span></span>](multidimensional-model-assemblies-management.md)  
  
  
