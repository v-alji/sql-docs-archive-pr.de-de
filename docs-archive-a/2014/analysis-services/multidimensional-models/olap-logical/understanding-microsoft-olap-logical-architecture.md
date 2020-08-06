---
title: Logische Architektur (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, architecture
- logical architecture [Analysis Services Multidimensional Data]
ms.assetid: 1b9cae0a-8990-4194-af5f-a1ea5f2aff06
author: minewiskan
ms.author: owend
ms.openlocfilehash: d93361fb14bc6544ffa7376439c2da0c8e06c3fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620599"
---
# <a name="logical-architecture-analysis-services---multidimensional-data"></a><span data-ttu-id="7c24c-102">Logische Architektur (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="7c24c-102">Logical Architecture (Analysis Services - Multidimensional Data)</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="7c24c-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] verwendet sowohl Server-als auch Client Komponenten zum Bereitstellen von OLAP-Funktionen (Online Analytical Processing) und Data Mining Funktionen für Business Intelligence-Anwendungen:</span><span class="sxs-lookup"><span data-stu-id="7c24c-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] uses both server and client components to supply online analytical processing (OLAP) and data mining functionality for business intelligence applications:</span></span>  
  
-   <span data-ttu-id="7c24c-104">Die Serverkomponente von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] wird als Microsoft Windows-Dienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="7c24c-104">The server component of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] is implemented as a Microsoft Windows service.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="7c24c-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]unterstützt mehrere Instanzen auf demselben Computer, wobei jede Instanz von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] als separate Instanz des Windows-Dienstanbieter implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="7c24c-105">[!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] supports multiple instances on the same computer, with each instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] implemented as a separate instance of the Windows service.</span></span>  
  
-   <span data-ttu-id="7c24c-106">Clients kommunizieren mit [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] mithilfe des öffentlichen Standards für XMLA (XML for Analysis). Hierbei handelt es sich um ein SOAP-basiertes Protokoll für die Ausgabe von Befehlen und den Empfang von Antworten in Form eines Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="7c24c-106">Clients communicate with [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] using the public standard XML for Analysis (XMLA), a SOAP-based protocol for issuing commands and receiving responses, exposed as a Web service.</span></span> <span data-ttu-id="7c24c-107">Clientobjektmodelle werden ebenfalls über XMLA bereitgestellt. Auf diese Modelle kann sowohl ein verwalteter Anbieter (ADOMD.NET) als auch ein eigener OLE DB-Anbieter zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7c24c-107">Client object models are also provided over XMLA, and can be accessed either by using a managed provider, such as ADOMD.NET, or a native OLE DB provider.</span></span>  
  
-   <span data-ttu-id="7c24c-108">Abfragebefehle können mithilfe der folgenden Abfragesprachen ausgegeben werden: SQL; MDX (Multidimensional Expressions), eine Abfragesprache nach Industriestandard für Analysen; oder DMX (Data Mining Extensions), eine am Data Mining orientierte Abfragesprache nach Industriestandard.</span><span class="sxs-lookup"><span data-stu-id="7c24c-108">Query commands can be issued using the following languages: SQL; Multidimensional Expressions (MDX), an industry standard query language for analysis; or Data Mining Extensions (DMX), an industry standard query language oriented toward data mining.</span></span> <span data-ttu-id="7c24c-109">ASSL (Analysis Services Scripting Language) kann außerdem zum Verwalten von [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Datenbankobjekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c24c-109">Analysis Services Scripting Language (ASSL) can also be used to manage [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] database objects.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] <span data-ttu-id="7c24c-110">unterstützt darüber hinaus eine lokale Cube-Engine, mit deren Hilfe Anwendungen auf nicht verbundenen Clients lokal gespeicherte mehrdimensionale Daten suchen können.</span><span class="sxs-lookup"><span data-stu-id="7c24c-110">also supports a local cube engine that enables applications on disconnected clients to browse locally stored multidimensional data.</span></span> <span data-ttu-id="7c24c-111">Weitere Informationen finden Sie unter [Anforderungen an die Client Architektur für die Analysis Services Entwicklung](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span><span class="sxs-lookup"><span data-stu-id="7c24c-111">For more information, see [Client Architecture Requirements for Analysis Services Development](../olap-physical/client-architecture-requirements-for-analysis-services-development.md)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c24c-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7c24c-112">In This Section</span></span>  
 <span data-ttu-id="7c24c-113">**Übersicht über logische Architektur**</span><span class="sxs-lookup"><span data-stu-id="7c24c-113">**Logical Architecture Overview**</span></span>  
 [<span data-ttu-id="7c24c-114">Übersicht über die logische Architektur &#40;Analysis Services mehrdimensionalen Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7c24c-114">Logical Architecture Overview &#40;Analysis Services - Multidimensional Data&#41;</span></span>](logical-architecture-overview-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="7c24c-115">**Server Objekte**</span><span class="sxs-lookup"><span data-stu-id="7c24c-115">**Server Objects**</span></span>  
 [<span data-ttu-id="7c24c-116">Server Objekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7c24c-116">Server Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](server-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="7c24c-117">**Datenbankobjekte**</span><span class="sxs-lookup"><span data-stu-id="7c24c-117">**Database Objects**</span></span>  
 [<span data-ttu-id="7c24c-118">Datenbankobjekte &#40;Analysis Services – Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7c24c-118">Database Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](database-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="7c24c-119">**Dimensionsobjekte**</span><span class="sxs-lookup"><span data-stu-id="7c24c-119">**Dimension Objects**</span></span>  
 [<span data-ttu-id="7c24c-120">Dimensions Objekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7c24c-120">Dimension Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimension-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="7c24c-121">**Cubeobjekte**</span><span class="sxs-lookup"><span data-stu-id="7c24c-121">**Cube Objects**</span></span>  
 [<span data-ttu-id="7c24c-122">Cubeobjekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7c24c-122">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
 <span data-ttu-id="7c24c-123">**Sicherheit für den Benutzerzugriff**</span><span class="sxs-lookup"><span data-stu-id="7c24c-123">**User Access Security**</span></span>  
 [<span data-ttu-id="7c24c-124">Sicherheitsarchitektur für den Benutzerzugriff</span><span class="sxs-lookup"><span data-stu-id="7c24c-124">User Access Security Architecture</span></span>](understanding-microsoft-olap-logical-architecture.md)  
  
## <a name="see-also"></a><span data-ttu-id="7c24c-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c24c-125">See Also</span></span>  
 <span data-ttu-id="7c24c-126">[Grundlegendes zur Microsoft OLAP-Architektur](../olap-physical/understanding-microsoft-olap-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="7c24c-126">[Understanding Microsoft OLAP Architecture](../olap-physical/understanding-microsoft-olap-architecture.md) </span></span>  
 [<span data-ttu-id="7c24c-127">Physische Architektur &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="7c24c-127">Physical Architecture &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../olap-physical/understanding-microsoft-olap-physical-architecture.md)  
  
  
