---
title: Erstellen einer DMX-Abfrage in SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20fc7a618f4977058203d8f35d235b543609dd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619457"
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="b30fd-102">Erstellen einer DMX-Abfrage in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b30fd-102">Create a DMX Query in SQL Server Management Studio</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b30fd-103">stellt einen Satz von Funktionen bereit, um Sie bei der Erstellung von Vorhersage-, Inhalts- und Datendefinitionsabfragen gegen Miningmodelle und Miningstrukturen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b30fd-103">provides a set of features to help you create prediction queries, content queries, and data definition queries against mining models and mining structures.</span></span>  
  
-   <span data-ttu-id="b30fd-104">Der grafische Generator für Vorhersageabfragen ist sowohl über [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] als auch [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]verfügbar, um den Prozess des Schreibens von Vorhersageabfragen und des Zuordnens von Datasets zu Modellen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="b30fd-104">The graphical Prediction Query Builder is available in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], to simplify the process of writing prediction queries and mapping data sets to a model.</span></span>  
  
-   <span data-ttu-id="b30fd-105">Die Abfragevorlagen ermöglichen im beschleunigten Vorlagen-Explorer die Erstellung vieler verschiedener Arten von DMX-Abfragen, einschließlich verschiedener Typen von Vorhersageabfragen.</span><span class="sxs-lookup"><span data-stu-id="b30fd-105">The query templates provided in the Template Explorer jump-start the creation of many kinds of DMX queries, including many types of prediction queries.</span></span> <span data-ttu-id="b30fd-106">Die Vorlagen werden für Inhaltsabfragen, für in geschachtelten Datasets verwendete Abfragen, für Abfragen, die Fälle von der Miningstruktur zurückgeben, und sogar für Datendefinitionsabfragen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b30fd-106">Templates are provided for content queries, queries used nested data sets, queries that return cases from the mining structure, and even data definition queries.</span></span>  
  
-   <span data-ttu-id="b30fd-107">Der Metadaten-Explorer in den MDX- und DMX-Abfragebereichen stellt eine Liste von verfügbaren Modellen und Strukturen, die Sie per Drag & Drop in den Abfrage-Generator einbinden können, sowie eine Liste von DMX-Funktionen bereit.</span><span class="sxs-lookup"><span data-stu-id="b30fd-107">The Metadata Explorer in the MDX and DMX query panes provides a list of available models and structures that you can drag and drop into the query builder, as well as a list of DMX functions.</span></span> <span data-ttu-id="b30fd-108">Diese Funktion vereinfacht einen korrekten Abruf von Objektnamen ohne Typisierung.</span><span class="sxs-lookup"><span data-stu-id="b30fd-108">This feature makes it easy to get object names right, without typing.</span></span>  
  
 <span data-ttu-id="b30fd-109">In diesem Thema wird beschrieben, wie eine DMX-Abfrage erstellt wird, indem der Metadaten-Explorer und der DMX-Abfrage-Editor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b30fd-109">This topic describes how to build a DMX query by using the Metadata Explorer and the DMX query editor.</span></span>  
  
##  <a name="dmx-query-templates"></a><a name="BKMK_Templates"></a> <span data-ttu-id="b30fd-110">DMX-Abfragevorlagen</span><span class="sxs-lookup"><span data-stu-id="b30fd-110">DMX Query Templates</span></span>  
 <span data-ttu-id="b30fd-111">Zum Erstellen von grundlegenden DMX-Abfragen stehen Vorlagen im Vorlagen-Explorer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b30fd-111">Templates for creating basic DMX queries are available in Template Explorer.</span></span> <span data-ttu-id="b30fd-112">Der **DMX** -Ordner enthält Data Mining-Vorlagen, die in die folgenden Kategorien unterteilt sind:</span><span class="sxs-lookup"><span data-stu-id="b30fd-112">The **DMX** folder contains data mining templates, which are divided into these categories:</span></span>  
  
-   <span data-ttu-id="b30fd-113">**Modell Inhalt**</span><span class="sxs-lookup"><span data-stu-id="b30fd-113">**Model Content**</span></span>  
  
-   <span data-ttu-id="b30fd-114">**Modellverwaltung**</span><span class="sxs-lookup"><span data-stu-id="b30fd-114">**Model Management**</span></span>  
  
-   <span data-ttu-id="b30fd-115">**Vorhersageabfragen**</span><span class="sxs-lookup"><span data-stu-id="b30fd-115">**Prediction Queries**</span></span>  
  
-   <span data-ttu-id="b30fd-116">**Strukturieren von Inhalt**</span><span class="sxs-lookup"><span data-stu-id="b30fd-116">**Structure Content**</span></span>  
  
 <span data-ttu-id="b30fd-117">Sie können auch benutzerdefinierte Vorlagen für jene Abfragen oder Befehle erstellen, die Sie häufig ausführen.</span><span class="sxs-lookup"><span data-stu-id="b30fd-117">You can also create custom templates, for queries or commands that you run frequently.</span></span>  
  
## <a name="xmla-query-templates"></a><span data-ttu-id="b30fd-118">XMLA-Abfragevorlagen</span><span class="sxs-lookup"><span data-stu-id="b30fd-118">XMLA Query Templates</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="b30fd-119">stellt auch Vorlagen für XMLA-Abfragen bereit.</span><span class="sxs-lookup"><span data-stu-id="b30fd-119">also provides templates for XMLA queries.</span></span>  
  
 <span data-ttu-id="b30fd-120">Zwischen den Typen der Abfragen, die Sie mit XMLA oder DMX ausführen können, tritt ein gewisses Maß an Überschneidung auf.</span><span class="sxs-lookup"><span data-stu-id="b30fd-120">There is some overlap between the types of queries that you can perform by using XMLA and DMX.</span></span> <span data-ttu-id="b30fd-121">Sie können z. B. einige Modellinhaltsabfragen erstellen, indem Sie entweder DMX oder die Data Mining-Schemarowsets verwenden. Die Schemarowsets enthalten allerdings gelegentlich Informationen, die in DMX-Inhaltsabfragen nicht verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b30fd-121">For example, you can create some model content queries by using either DMX or the data mining schema rowsets, but the schema rowsets sometimes contain information that is not exposed in DMX content queries.</span></span>  
  
 <span data-ttu-id="b30fd-122">Außerdem gibt es einige wesentliche Unterschiede bezüglich der Art, wie Vorgänge in DMX oder in XMLA verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b30fd-122">There are also some key differences in the way that operations are handled in DMX and in XMLA.</span></span> <span data-ttu-id="b30fd-123">Sie können XMLA z.B. verwenden, um Administratorvorgänge wie etwa die Sicherung einer gesamten [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbank auszuführen. Wenn Sie jedoch ein einzelnes Miningmodell sichern möchten, stellt DMX einen einfachen Befehl bereit ([EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx)), der zu diesem Zweck besser geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="b30fd-123">For example, you can use XMLA to perform administrative operations such as backup of an entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, but if you want to back up a single mining model, DMX provides a simple command, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), that is better suited to that purpose.</span></span>  
  
##  <a name="build-and-run-a-dmx-query"></a><a name="BKMK_Building_Queries"></a> <span data-ttu-id="b30fd-124">Erstellen und Ausführen einer DMX-Abfrage</span><span class="sxs-lookup"><span data-stu-id="b30fd-124">Build and Run a DMX Query</span></span>  
  
#### <a name="open-a-new-dmx-query-window"></a><span data-ttu-id="b30fd-125">Öffnen eines neuen DMX-Abfragefensters</span><span class="sxs-lookup"><span data-stu-id="b30fd-125">Open a new DMX Query window</span></span>  
  
1.  <span data-ttu-id="b30fd-126">Klicken Sie auf **Neue Abfrage** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]. Wählen Sie anschließend **DMX-Abfrage für Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="b30fd-126">Click **New Query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then select **New Analysis Server DMX Query**.</span></span>  
  
2.  <span data-ttu-id="b30fd-127">Wenn das Dialogfeld **Verbindung mit Server herstellen** angezeigt wird, wählen Sie die Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] aus, die die zu verwendenden Miningmodelle enthält.</span><span class="sxs-lookup"><span data-stu-id="b30fd-127">When the **Connect to Server** dialog box appears, select the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining models you want to work with.</span></span>  
  
#### <a name="open-template-explorer"></a><span data-ttu-id="b30fd-128">Öffnen des Vorlagen-Explorers</span><span class="sxs-lookup"><span data-stu-id="b30fd-128">Open Template Explorer</span></span>  
  
1.  <span data-ttu-id="b30fd-129">Wählen Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** den **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b30fd-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="b30fd-130">Klicken Sie auf **Analysis-Server** , um eine Strukturansicht der Vorlagen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b30fd-130">Click **Analysis Server** to see a tree view of the templates that apply to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
#### <a name="apply-a-template-to-build-a-query"></a><span data-ttu-id="b30fd-131">Übernehmen einer Vorlage zum Erstellen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="b30fd-131">Apply a template to build a query</span></span>  
  
-   <span data-ttu-id="b30fd-132">Klicken Sie mit der rechten Maustaste auf den entsprechenden Abfragetyp. Wählen Sie **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="b30fd-132">Right-click the appropriate query type and select **Open**.</span></span>  
  
-   <span data-ttu-id="b30fd-133">Oder ziehen Sie die Vorlage in den Abfrage-Editor.</span><span class="sxs-lookup"><span data-stu-id="b30fd-133">Or, drag the template into the query editor.</span></span>  
  
-   <span data-ttu-id="b30fd-134">Sie können die Parameter für die Abfrage auch mit der Option **MT+++Werte für Vorlagenparameter angeben**aus dem Menü **Abfrage** eingeben.</span><span class="sxs-lookup"><span data-stu-id="b30fd-134">You can also fill in the parameters for the query by using the option, **Specify Values for Parameters**, from the **Query** menu.</span></span>  
  
 <span data-ttu-id="b30fd-135">Beispiele hinsichtlich des Erstellens spezieller Typen von Abfragen aus Vorlagen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="b30fd-135">For examples of how to create specific types of queries from templates, see the following topics:</span></span>  
  
 [<span data-ttu-id="b30fd-136">Erstellen einer SINGLETON-Vorhersageabfrage aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="b30fd-136">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
  
 [<span data-ttu-id="b30fd-137">Erstellen einer Miningmodell-Inhaltsabfrage</span><span class="sxs-lookup"><span data-stu-id="b30fd-137">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="b30fd-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b30fd-138">See Also</span></span>  
 <span data-ttu-id="b30fd-139">[Schnittstellen für Data Mining-Abfragen](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b30fd-139">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="b30fd-140">Data Mining-Erweiterungen &#40;DMX&#41; – Referenz</span><span class="sxs-lookup"><span data-stu-id="b30fd-140">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
