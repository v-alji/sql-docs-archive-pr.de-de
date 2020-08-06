---
title: CSDL-Anmerkungen für Business Intelligence (csdlbi) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: bf6f372a-bc67-45ea-a771-b2dc5b0527e5
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3414b0d8b2614e83f62e85c4f750ee0e8c7397d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616243"
---
# <a name="csdl-annotations-for-business-intelligence-csdlbi"></a><span data-ttu-id="240f3-102">CSDL-Anmerkungen für Business Intelligence (CSDLBI)</span><span class="sxs-lookup"><span data-stu-id="240f3-102">CSDL Annotations for Business Intelligence (CSDLBI)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="240f3-103">unterstützt die Darstellung der Definition eines tabellarischen Modells im XML-Format Conceptual Schema Definition Language mit Business Intelligence-Anmerkungen (CSDLBI).</span><span class="sxs-lookup"><span data-stu-id="240f3-103">supports the presentation of the definition of a tabular model in an XML format called Conceptual Schema Definition Language with Business Intelligence annotations (CSDLBI).</span></span>  
  
 <span data-ttu-id="240f3-104">Dieses Thema bietet eine Übersicht über CSDLBI und seine Verwendung in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenmodellen.</span><span class="sxs-lookup"><span data-stu-id="240f3-104">This topic provides an overview of CSDLBI and how it is used with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data models.</span></span>  
  
## <a name="understanding-the-role-of-csdl"></a><span data-ttu-id="240f3-105">Grundlegendes zur Rolle von CSDL</span><span class="sxs-lookup"><span data-stu-id="240f3-105">Understanding the Role of CSDL</span></span>  
 <span data-ttu-id="240f3-106">Die Conceptual Schema Data Language (CSDL) ist eine XML-basierte Sprache, die Entitäten, Beziehungen und Funktionen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="240f3-106">The Conceptual Schema Data Language (CSDL) is an XML-based language that describes entities, relationships, and functions.</span></span> <span data-ttu-id="240f3-107">CSDL ist als Teil des Entity Data Framework definiert.</span><span class="sxs-lookup"><span data-stu-id="240f3-107">CSDL is defined as part of the Entity Data Framework.</span></span> <span data-ttu-id="240f3-108">Die BI-Anmerkungen sind eine Erweiterung, die entwickelt wurde, um die Datenmodellierung mithilfe von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="240f3-108">The BI annotations are an extension designed to support data modeling using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="240f3-109">Obwohl CSDL mit Entity Data Framework kompatibel ist, müssen Sie das Entitätsbeziehungsmodell nicht verstehen, und Sie benötigen keine besonderen Tools zum Erstellen eines Tabellenmodells oder eines Berichts auf Grundlage eines Modells.</span><span class="sxs-lookup"><span data-stu-id="240f3-109">Although CSDL is compliant with the Entity Data Framework, you do not need to understand the entity-relationship model or have any special tools to build a tabular model or a report based on a model.</span></span> <span data-ttu-id="240f3-110">Modelle werden mithilfe von Clienttools wie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] oder einer API wie AMO erstellt, und anschließend wird das Modell auf einem Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="240f3-110">You build models by using client tools such as [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or an API such as AMO, and deploy the model to a server.</span></span> <span data-ttu-id="240f3-111">Clients stellt mithilfe einer Modelldefinitionsdatei eine Verbindung zum Modell her, die überlichweise in einer SharePoint-Bibliothek veröffentlich wird, wo sie von Berichts-Designern und Berichtskonsumenten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="240f3-111">Clients connect to the model by using a model definition file, typically published to a SharePoint library where it can be used by report designers and report consumers.</span></span> <span data-ttu-id="240f3-112">Weitere Informationen finden Sie in den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="240f3-112">For more information, see these links:</span></span>  
  
-   [<span data-ttu-id="240f3-113">Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="240f3-113">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
-   [<span data-ttu-id="240f3-114">Bereitstellung von Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="240f3-114">Tabular Model Solution Deployment &#40;SSAS Tabular&#41;</span></span>](../tabular-models/tabular-model-solution-deployment-ssas-tabular.md)  
  
-   [<span data-ttu-id="240f3-115">Power Pivot BI-Semantik Modell Verbindung &#40;. bism-&#41;</span><span class="sxs-lookup"><span data-stu-id="240f3-115">PowerPivot BI Semantic Model Connection &#40;.bism&#41;</span></span>](../power-pivot-sharepoint/power-pivot-bi-semantic-model-connection-bism.md)  
  
 <span data-ttu-id="240f3-116">Das CSDLBI-Schema wird vom Analysis Services-Server als Reaktion auf eine Anforderung für eine Modelldefinition von einem Client wie [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] generiert.</span><span class="sxs-lookup"><span data-stu-id="240f3-116">The CSDLBI schema is generated by the Analysis Services server in response to a request for a model definition from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="240f3-117">Die Clientanwendung sendet eine XML-Abfrage an den Analysis Services-Server, der die Modelldaten hostet.</span><span class="sxs-lookup"><span data-stu-id="240f3-117">The client application sends an XML query to the Analysis Services server that hosts the model data.</span></span> <span data-ttu-id="240f3-118">Im Gegenzug sendet der Server mithilfe der CSDLBI-Anmerkungen eine XML-Meldung, die eine Definition der Entitäten im Modell enthält.</span><span class="sxs-lookup"><span data-stu-id="240f3-118">In response, the server sends an XML message containing a definition of the entities in the model, using the CSDLBI annotations.</span></span> <span data-ttu-id="240f3-119">Der Berichtsclient verwendet dann die Informationen zur Darstellung der im Modell verfügbaren Felder, Aggregationen und Measures.</span><span class="sxs-lookup"><span data-stu-id="240f3-119">The reporting client then uses the information to present the fields, aggregations, and measures that are available in the model.</span></span> <span data-ttu-id="240f3-120">Die CSDLBI-Anmerkungen enthalten auch Informationen zum Gruppieren, Sortieren und Formatieren der Daten.</span><span class="sxs-lookup"><span data-stu-id="240f3-120">The CSDLBI annotations also provide information about how to group, sort, and format the data.</span></span>  
  
 <span data-ttu-id="240f3-121">Allgemeine Informationen zu csdlbi finden Sie unter [csdlbi-Konzepte](/analysis-services/csdlbi/csdlbi-concepts).</span><span class="sxs-lookup"><span data-stu-id="240f3-121">For general information about CSDLBI, see [CSDLBI Concepts](/analysis-services/csdlbi/csdlbi-concepts).</span></span>  
  
### <a name="working-with-csdl"></a><span data-ttu-id="240f3-122">Arbeiten mit CSDL</span><span class="sxs-lookup"><span data-stu-id="240f3-122">Working with CSDL</span></span>  
 <span data-ttu-id="240f3-123">Der Satz von CSDLBI-Anmerkungen, der ein bestimmtes tabellarische Modell darstellt, ist ein XML-Dokument, das eine Auflistung einfacher und komplexer Entitäten enthält.</span><span class="sxs-lookup"><span data-stu-id="240f3-123">The set of CSDLBI annotations that represents any particular tabular model is an XML document containing a collection of entities, both simple and complex.</span></span> <span data-ttu-id="240f3-124">Die Entitäten definieren Tabellen (oder Dimensionen), Spalten (Attribute), Zuordnungen (Beziehungen) und Formeln in berechneten Spalten, Measures oder KPIs.</span><span class="sxs-lookup"><span data-stu-id="240f3-124">The entities define tables (or dimensions), columns (attributes), associations (relationships), and formulas included in calculated columns, measure, or KPIs.</span></span>  
  
 <span data-ttu-id="240f3-125">Sie können diese Objekte nicht direkt ändern, sondern müssen auf für die Arbeit mit Tabellenmodellen bereitgestellte Clienttools und Anwendungsprogrammierschnittstellen (APIs) zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="240f3-125">You cannot modify these objects directly, but must use the client tools and application programming interfaces (APIs) provided for working with tabular models.</span></span>  
  
 <span data-ttu-id="240f3-126">Sie können die CSDL für ein Modell abrufen, indem Sie eine DISCOVER-Anforderung an den Server senden, der das Modell hostet.</span><span class="sxs-lookup"><span data-stu-id="240f3-126">You can obtain the CSDL for a model by sending a DISCOVER request to the server that hosts the model.</span></span> <span data-ttu-id="240f3-127">Die Anforderung muss qualifiziert werden, indem der Server und das Modell und optional eine Sicht oder Perspektive angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="240f3-127">The request must be qualified by specifying the server and the model, and, optionally, a view or perspective.</span></span> <span data-ttu-id="240f3-128">Die zurückgegebene Meldung ist eine XML-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="240f3-128">The returned message is an XML string.</span></span> <span data-ttu-id="240f3-129">Bestimmte Elemente sind sprachabhängig und geben je nach Sprache der aktuellen Verbindung unter Umständen andere Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="240f3-129">Certain elements are language-dependent and may return different values depending on the language of the current connection.</span></span> <span data-ttu-id="240f3-130">Weitere Informationen finden Sie unter [DISCOVER_CSDL_METADATA-Rowsets](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/discover-csdl-metadata-rowset).</span><span class="sxs-lookup"><span data-stu-id="240f3-130">For more information, see [DISCOVER_CSDL_METADATA Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/discover-csdl-metadata-rowset).</span></span>  
  
### <a name="csdlbi-versions"></a><span data-ttu-id="240f3-131">CSDLBI-Versionen</span><span class="sxs-lookup"><span data-stu-id="240f3-131">CSDLBI Versions</span></span>  
 <span data-ttu-id="240f3-132">Die ursprüngliche CSDL-Spezifikation (aus dem Entity Data Framework) stellt die meisten Entitäten und Eigenschaften bereit, die zur Unterstützung der Modellierung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="240f3-132">The original CSDL specification (from the Entity Data Framework) provides for most of the entities and properties that are needed to support modeling.</span></span> <span data-ttu-id="240f3-133">Die BI-Anmerkungen unterstützen besondere Anforderungen von tabellarischen Modellen, Berichtseigenschaften, die für Clients wie [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)]erforderlich sind, sowie zusätzliche Metadaten, die für mehrdimensionale Modelle erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="240f3-133">The BI annotations support special requirements of tabular models, reporting properties required for clients such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], and additional metadata required for multidimensional models.</span></span> <span data-ttu-id="240f3-134">In diesem Abschnitt werden die Updates der einzelnen Versionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="240f3-134">This section describes the updates in each version.</span></span>  
  
 <span data-ttu-id="240f3-135">**CSDLBI 1.0**</span><span class="sxs-lookup"><span data-stu-id="240f3-135">**CSDLBI 1.0**</span></span>  
  
 <span data-ttu-id="240f3-136">Der Anfangssatz von Ergänzungen zum CSDL-Schema für die Unterstützung tabellarischer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Modelle enthielt Anmerkungen für die Datenmodellierung sowie für benutzerdefinierte Berechnungen und verbesserte Präsentationen:</span><span class="sxs-lookup"><span data-stu-id="240f3-136">The initial set of additions to the CSDL schema to support [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tabular models contained annotations in support of data modeling, custom calculations, and enhanced presentation:</span></span>  
  
-   <span data-ttu-id="240f3-137">Neue Elemente und Eigenschaften zur Unterstützung tabellarischer Modelle.</span><span class="sxs-lookup"><span data-stu-id="240f3-137">New elements and properties to support tabular models.</span></span> <span data-ttu-id="240f3-138">Beispielsweise wurde eine Eigenschaft hinzugefügt, um den Typ der Datenbankabfrage zum Füllen des Modells anzugeben.</span><span class="sxs-lookup"><span data-stu-id="240f3-138">For example, a property was added to specify the type of database query used to populate the model.</span></span>  
  
-   <span data-ttu-id="240f3-139">Neue Eigenschaften und Erweiterungen für vorhandene Entitäten.</span><span class="sxs-lookup"><span data-stu-id="240f3-139">New properties and extensions to existing entities.</span></span>  <span data-ttu-id="240f3-140">So wurde das Zuordnungselement erweitert, um Beziehungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="240f3-140">For example, the Association element was extended to support relationships.</span></span>  
  
-   <span data-ttu-id="240f3-141">Visualisierungs- und Navigationseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="240f3-141">Visualization and navigation properties.</span></span> <span data-ttu-id="240f3-142">Beispielsweise wurden Eigenschaften hinzugefügt, um u. a. benutzerdefinierte Sortierfelder und Standardbilder zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="240f3-142">For example, properties were added to support custom sorting fields, default images, and</span></span>  
  
 <span data-ttu-id="240f3-143">**CSDLBI 1.1**</span><span class="sxs-lookup"><span data-stu-id="240f3-143">**CSDLBI 1.1**</span></span>  
  
 <span data-ttu-id="240f3-144">Diese Version des CSDLBI-Schemas enthält Erweiterungen zur Unterstützung mehrdimensionaler Datenbanken (wie OLAP-Cubes).</span><span class="sxs-lookup"><span data-stu-id="240f3-144">This version of the CSDLBI schema includes additions in support of multidimensional databases (such as OLAP cubes).</span></span> <span data-ttu-id="240f3-145">Die neuen Elemente und Eigenschaften sind nachstehend aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="240f3-145">The new elements and properties are as follows:</span></span>  
  
-   <span data-ttu-id="240f3-146">Unterstützung für Dimensionen als Entitäten.</span><span class="sxs-lookup"><span data-stu-id="240f3-146">Support for dimensions as entities.</span></span>  
  
-   <span data-ttu-id="240f3-147">Unterstützung für Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="240f3-147">Support for hierarchies.</span></span>  
  
-   <span data-ttu-id="240f3-148">Macht ROLAP-Partitionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="240f3-148">Exposes ROLAP partitions.</span></span>  
  
-   <span data-ttu-id="240f3-149">Unterstützung für Übersetzungen.</span><span class="sxs-lookup"><span data-stu-id="240f3-149">Support for translations.</span></span>  
  
-   <span data-ttu-id="240f3-150">Unterstützung für Perspektiven.</span><span class="sxs-lookup"><span data-stu-id="240f3-150">Support for perspectives.</span></span>  
  
 <span data-ttu-id="240f3-151">Ausführliche Informationen zu einzelnen Elementen in den csdlbi-Anmerkungen finden Sie unter [Technische Referenz für BI-Anmerkungen zu CSDL](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl).</span><span class="sxs-lookup"><span data-stu-id="240f3-151">For detailed information about individual elements in the CSDLBI annotations, see [Technical Reference for BI Annotations to CSDL](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl).</span></span> <span data-ttu-id="240f3-152">Weitere Informationen zur CSDL-Kern Spezifikation finden Sie in der [CSDL V3-Spezifikation](https://docs.microsoft.com/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span><span class="sxs-lookup"><span data-stu-id="240f3-152">For information about the core CSDL specification, see the [CSDL v3 Specification](https://docs.microsoft.com/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="240f3-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="240f3-153">See Also</span></span>  
 <span data-ttu-id="240f3-154">[Grundlegendes zum tabellarischen Objektmodell](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md) </span><span class="sxs-lookup"><span data-stu-id="240f3-154">[Understanding the Tabular Object Model](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md) </span></span>  
 <span data-ttu-id="240f3-155">[Csdlbi-Konzepte](/analysis-services/csdlbi/csdlbi-concepts) </span><span class="sxs-lookup"><span data-stu-id="240f3-155">[CSDLBI Concepts](/analysis-services/csdlbi/csdlbi-concepts) </span></span>  
 [<span data-ttu-id="240f3-156">Grundlegendes zum tabellarischen Objektmodell</span><span class="sxs-lookup"><span data-stu-id="240f3-156">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
  