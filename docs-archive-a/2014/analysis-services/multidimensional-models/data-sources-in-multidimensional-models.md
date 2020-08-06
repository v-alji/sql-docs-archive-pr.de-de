---
title: Datenquellen in mehrdimensionalen Modellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- metadata [Analysis Services]
- Analysis Services objects, data sources
- storing data [Analysis Services], data sources
- data sources [Analysis Services], about data sources
- security [Analysis Services], data sources
- data sources [Analysis Services]
- storage [Analysis Services], data sources
ms.assetid: a16469d9-9d53-4e35-9982-fc06327a9d33
author: minewiskan
ms.author: owend
ms.openlocfilehash: 41386c1c7abb0324aa17df24b3c427ca8cbb5615
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621227"
---
# <a name="data-sources-in-multidimensional-models"></a><span data-ttu-id="18aa3-102">Datenquellen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="18aa3-102">Data Sources in Multidimensional Models</span></span>
  <span data-ttu-id="18aa3-103">Alle Daten, die Sie importieren oder in ein mehrdimensionales Modell laden, stammen aus einer externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="18aa3-103">All data that you import or load into a multidimensional model originates from an external data source.</span></span> <span data-ttu-id="18aa3-104">In der Regel stammen Quelldaten aus einem Data Warehouse, das für Berichtszwecke entworfen wurde, sie können jedoch auch aus einer beliebigen relationalen Datenbank stammen, auf die direkt oder indirekt über einen Mittler zugegriffen wird, z. B. ein [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="18aa3-104">Typically, source data is from a data warehouse designed for reporting purposes, but it could come from any relational database that is accessed directly or indirectly through an intermediary, such as an [!INCLUDE[ssIS](../../includes/ssis-md.md)] package.</span></span>  
  
 <span data-ttu-id="18aa3-105">Die direkte Verbindung mit einer externen Datenquelle wird von einem **Datenquellenobjekt** in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] angegeben.</span><span class="sxs-lookup"><span data-stu-id="18aa3-105">A **data source** object in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] specifies a direct connection to an external data source.</span></span> <span data-ttu-id="18aa3-106">Neben dem physischen Speicherort gibt ein Datenquellenobjekt die Verbindungszeichenfolge, den Datenanbieter, die Anmeldeinformationen und weitere Eigenschaften an, die das Verbindungsverhalten steuern.</span><span class="sxs-lookup"><span data-stu-id="18aa3-106">In addition to physical location, a data source object specifies the connection string, data provider, credentials, and other properties that control connection behavior.</span></span>  
  
 <span data-ttu-id="18aa3-107">Die vom Datenquellenobjekt bereitgestellten Informationen werden während der folgenden Vorgänge verwendet:</span><span class="sxs-lookup"><span data-stu-id="18aa3-107">Information provided by the data source object is used during the following operations:</span></span>  
  
-   <span data-ttu-id="18aa3-108">Abrufen von Schemainformationen und anderen Metadaten, die zum Generieren von Datenquellensichten in einem Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18aa3-108">Get schema information and other metadata used to generate data source views into a model.</span></span>  
  
-   <span data-ttu-id="18aa3-109">Abfragen oder Laden von Daten in ein Modell während der Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="18aa3-109">Query or load data into a model during processing.</span></span>  
  
-   <span data-ttu-id="18aa3-110">Ausführen von Abfragen für mehrdimensionale oder Data Mining-Modelle, die den ROLAP-Speichermodus verwenden</span><span class="sxs-lookup"><span data-stu-id="18aa3-110">Run queries against multidimensional or data mining models that use ROLAP storage mode.</span></span>  
  
-   <span data-ttu-id="18aa3-111">Lesen oder Schreiben in Remotepartitionen</span><span class="sxs-lookup"><span data-stu-id="18aa3-111">Read or write to remote partitions.</span></span>  
  
-   <span data-ttu-id="18aa3-112">Herstellen einer Verbindung mit verknüpften Objekten sowie Synchronisieren von Ziel zu Quelle</span><span class="sxs-lookup"><span data-stu-id="18aa3-112">Connect to linked objects, as well as synchronize from target to source.</span></span>  
  
-   <span data-ttu-id="18aa3-113">Ausführen von Rückschreibevorgängen, die in einer relationalen Datenbank gespeicherte Faktentabellendaten aktualisieren</span><span class="sxs-lookup"><span data-stu-id="18aa3-113">Perform write back operations that update fact table data stored in a relational database.</span></span>  
  
 <span data-ttu-id="18aa3-114">Wenn Sie ein mehrdimensionales Modell komplett neu erstellen, beginnen Sie, indem Sie das Datenquellenobjekt erstellen, und verwenden dieses dann zum Generieren des nächsten Objekts, einer **Datenquellensicht**.</span><span class="sxs-lookup"><span data-stu-id="18aa3-114">When building a multidimensional model from the bottom up, you start by creating the data source object, and then use it to generate the next object, a **data source view**.</span></span> <span data-ttu-id="18aa3-115">Die Datenquellensicht bildet die Datenabstraktionsebene im Modell.</span><span class="sxs-lookup"><span data-stu-id="18aa3-115">A data source view is the data abstraction layer in the model.</span></span> <span data-ttu-id="18aa3-116">Sie wird in der Regel nach dem Datenquellenobjekt erstellt, wobei das Schema der Quelldatenbank als Grundlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="18aa3-116">It is typically created after the data source object, using the schema of the source database as the basis.</span></span> <span data-ttu-id="18aa3-117">Sie können jedoch auch andere Möglichkeiten zum Erstellen eines Modells wählen, u. a. den Beginn mit Cubes und Dimensionen oder das Generieren des Schemas, das Ihren Entwurf am besten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18aa3-117">However, you can choose other ways to build a model, including starting with cubes and dimensions, and generating the schema that best supports your design.</span></span>  
  
 <span data-ttu-id="18aa3-118">Unabhängig davon, wie Sie das Modell erstellen, benötigt jedes mindestens ein Datenquellenobjekt, das eine Verbindung mit den Quelldaten angibt.</span><span class="sxs-lookup"><span data-stu-id="18aa3-118">Regardless of how you build it, each model requires at least one data source object that specifies a connection to source data.</span></span> <span data-ttu-id="18aa3-119">Sie können in einem einzelnen Modell mehrere Datenquellenobjekte erstellen, um Daten aus verschiedenen Quellen zu verwenden oder die Verbindungseigenschaften für bestimmte Objekte zu variieren.</span><span class="sxs-lookup"><span data-stu-id="18aa3-119">You can create multiple data source objects in a single model to use data from different sources or vary connection properties for specific objects.</span></span>  
  
 <span data-ttu-id="18aa3-120">Datenquellenobjekte können unabhängig von anderen Objekten im Modell verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="18aa3-120">Data source objects can be managed independently of other objects in your model.</span></span> <span data-ttu-id="18aa3-121">Wenn Sie eine Datenquelle erstellt haben, können Sie deren Eigenschaften später ändern und dann das Modell vorverarbeiten, um sicherzustellen, dass die Daten ordnungsgemäß abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="18aa3-121">After you create a data source, you can change its properties later, and then preprocess the model to ensure the data is retrieved correctly.</span></span>  
  
## <a name="related-topics-and-tasks"></a><span data-ttu-id="18aa3-122">Verwandte Themen und Tasks</span><span class="sxs-lookup"><span data-stu-id="18aa3-122">Related Topics and Tasks</span></span>  
  
|<span data-ttu-id="18aa3-123">Thema</span><span class="sxs-lookup"><span data-stu-id="18aa3-123">Topic</span></span>|<span data-ttu-id="18aa3-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="18aa3-124">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="18aa3-125">Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="18aa3-125">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)|<span data-ttu-id="18aa3-126">Beschreibt die Datenquellentypen, die in einem tabellarischen Modell verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="18aa3-126">Describes the types of data sources that can be used in a multidimensional model.</span></span>|  
|[<span data-ttu-id="18aa3-127">Erstellen einer Datenquelle (SSAS: mehrdimensional)</span><span class="sxs-lookup"><span data-stu-id="18aa3-127">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](create-a-data-source-ssas-multidimensional.md)|<span data-ttu-id="18aa3-128">Erklärt, wie einem mehrdimensionalen Modell ein Datenquellenobjekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="18aa3-128">Explains how to add a data source object to a multidimensional model.</span></span>|  
|[<span data-ttu-id="18aa3-129">Löschen einer Datenquelle in Projektmappen-Explorer &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="18aa3-129">Delete a Data Source in Solution Explorer &#40;SSAS Multidimensional&#41;</span></span>](delete-a-data-source-in-solution-explorer-ssas-multidimensional.md)|<span data-ttu-id="18aa3-130">Verwenden Sie diese Vorgehensweise, um ein Datenquellenobjekt aus einem mehrdimensionalen Modell zu löschen.</span><span class="sxs-lookup"><span data-stu-id="18aa3-130">Use this procedure to delete a data source object from a multidimensional model.</span></span>|  
|[<span data-ttu-id="18aa3-131">Festlegen von Datenquelleneigenschaften &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="18aa3-131">Set Data Source Properties &#40;SSAS Multidimensional&#41;</span></span>](set-data-source-properties-ssas-multidimensional.md)|<span data-ttu-id="18aa3-132">Beschreibt jede Eigenschaft und erläutert deren Festlegung.</span><span class="sxs-lookup"><span data-stu-id="18aa3-132">Describes each property and explains how to set each one.</span></span>|  
|[<span data-ttu-id="18aa3-133">Festlegen von Identitätswechseloptionen &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="18aa3-133">Set Impersonation Options &#40;SSAS - Multidimensional&#41;</span></span>](set-impersonation-options-ssas-multidimensional.md)|<span data-ttu-id="18aa3-134">Erklärt, wie die Optionen im Dialogfeld "Identitätswechselinformationen" konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="18aa3-134">Explains how to configure options in the Impersonation Information dialog box.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18aa3-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="18aa3-135">See Also</span></span>  
 <span data-ttu-id="18aa3-136">[Datenbankobjekte &#40;Analysis Services Mehrdimensionale Daten&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="18aa3-136">[Database Objects &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/database-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="18aa3-137">[Logische Architektur &#40;Analysis Services Mehrdimensionale Daten&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="18aa3-137">[Logical Architecture &#40;Analysis Services - Multidimensional Data&#41;](olap-logical/understanding-microsoft-olap-logical-architecture.md) </span></span>  
 <span data-ttu-id="18aa3-138">[Datenquellen Sichten in mehrdimensionalen Modellen](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="18aa3-138">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="18aa3-139">Datenquellen und Bindungen &#40;SSAS – mehrdimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="18aa3-139">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](data-sources-and-bindings-ssas-multidimensional.md)  
  
  
