---
title: XML-Editor
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.editorxml.f1
- sql12.swb.xmleditor.f1
- vs.xmleditor
- sql12.swb.editor.xml.f1
helpviewer_keywords:
- XML Designer [SQL Server Management Studio]
ms.assetid: 0824a5ce-e67b-4b53-98d9-d371faf2d23c
author: rothja
ms.author: jroth
ms.openlocfilehash: b7c3bbbda4f5a31c4d83b559c1aa623ca2aff89f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621450"
---
# <a name="xml-editor-sql-server-management-studio"></a><span data-ttu-id="cfe6b-102">XML-Editor (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cfe6b-102">XML Editor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cfe6b-103">Stellt eine Anzahl visueller Tools zur Arbeit mit XML-Schemas, ADO.NET-Datasets und XML-Dokumenten bereit.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-103">Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents.</span></span> <span data-ttu-id="cfe6b-104">Der XML-Designer unterstützt die vom World Wide Web Consortium (W3C) definierte XSD-Sprache (XML Schema Definition).</span><span class="sxs-lookup"><span data-stu-id="cfe6b-104">The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3).</span></span> <span data-ttu-id="cfe6b-105">DTDs (Document Type Definitions) oder andere XML-Schemasprachen, wie XDR (XML-Data Reduced), werden vom Designer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-105">The designer does not support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).</span></span>  
  
 <span data-ttu-id="cfe6b-106">Fügen Sie zum Anzeigen des Designers ein Dataset, XML-Schema oder eine XML-Datei dem Projekt hinzu, oder öffnen Sie einen der in der folgenden Tabelle aufgeführten Dateitypen.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-106">To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the table below.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="cfe6b-107">Bei der Arbeit in der Schemasicht steht kein Befehl **Rückgängig** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-107">There is no **Undo** command when working in Schema view.</span></span> <span data-ttu-id="cfe6b-108">Planen Sie die Arbeit sorgfältig, und speichern Sie die Dateien regelmäßig.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-108">Plan your work carefully and save your files often.</span></span>  
  
 <span data-ttu-id="cfe6b-109">Für die Arbeit an XML-Dateien, XML-Schemas und Datasets stehen im Designer die folgenden drei Sichten (oder Modi) zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="cfe6b-109">The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:</span></span>  
  
|<span data-ttu-id="cfe6b-110">Sicht</span><span class="sxs-lookup"><span data-stu-id="cfe6b-110">View</span></span>|<span data-ttu-id="cfe6b-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cfe6b-111">Description</span></span>|<span data-ttu-id="cfe6b-112">Unterstützte Dateitypen</span><span class="sxs-lookup"><span data-stu-id="cfe6b-112">File types supported</span></span>|  
|----------|-----------------|--------------------------|  
|<span data-ttu-id="cfe6b-113">**Schema**</span><span class="sxs-lookup"><span data-stu-id="cfe6b-113">**Schema**</span></span>|<span data-ttu-id="cfe6b-114">Zum visuellen Erstellen und Ändern von XML-Schemas und ADO.NET-Datasets.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-114">For visually creating and modifying XML Schemas and ADO.NET datasets.</span></span>|<span data-ttu-id="cfe6b-115">.xsd</span><span class="sxs-lookup"><span data-stu-id="cfe6b-115">.xsd</span></span>|  
|<span data-ttu-id="cfe6b-116">**Daten**</span><span class="sxs-lookup"><span data-stu-id="cfe6b-116">**Data**</span></span>|<span data-ttu-id="cfe6b-117">Zum visuellen Ändern von XML-Datendateien in einem strukturierten Datenraster.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-117">For visually modifying XML data files in a structured data grid.</span></span>|<span data-ttu-id="cfe6b-118">.xml</span><span class="sxs-lookup"><span data-stu-id="cfe6b-118">.xml</span></span>|  
|<span data-ttu-id="cfe6b-119">**XML**</span><span class="sxs-lookup"><span data-stu-id="cfe6b-119">**XML**</span></span>|<span data-ttu-id="cfe6b-120">Zum Bearbeiten von XML. Der Quellen-Editor stellt Funktionen wie Farbcodierung und IntelliSense bereit, einschließlich Wort vervollständigen und Member auflisten.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-120">For editing XML; the source editor provides color-coding and IntelliSense, including Complete Word and List Members.</span></span>|<span data-ttu-id="cfe6b-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span><span class="sxs-lookup"><span data-stu-id="cfe6b-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span></span>|  
|<span data-ttu-id="cfe6b-122">**Showplan**</span><span class="sxs-lookup"><span data-stu-id="cfe6b-122">**ShowPlan**</span></span>|<span data-ttu-id="cfe6b-123">Zeigt mithilfe der Option SET SHOWPLAN_XML ON erstellte XML-Abfragepläne an.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-123">Displays xml query plans created using the SET SHOWPLAN_XML ON option.</span></span>|<span data-ttu-id="cfe6b-124">.showplan</span><span class="sxs-lookup"><span data-stu-id="cfe6b-124">.showplan</span></span>|  
  
## <a name="schema-view"></a><span data-ttu-id="cfe6b-125">Schemasicht</span><span class="sxs-lookup"><span data-stu-id="cfe6b-125">Schema View</span></span>  
 <span data-ttu-id="cfe6b-126">Die Schemasicht bietet eine visuelle Darstellung der Elemente, Attribute, Typen usw., aus denen XML-Schemas und ADO.NET-Datasets bestehen.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-126">Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.</span></span>  
  
 <span data-ttu-id="cfe6b-127">In der Schemasicht können Sie Schemas und Datasets erstellen, indem Sie Elemente entweder aus der Toolbox der Registerkarte XML-Schema oder aus dem Server-Explorer per Drag und Drop auf die Entwurfsoberfläche ziehen.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-127">In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer.</span></span> <span data-ttu-id="cfe6b-128">Darüber hinaus können Sie Elemente zum Designer hinzufügen, indem Sie mit der rechten Maustaste auf die Entwurfsoberfläche klicken und aus dem Kontextmenü die Option Hinzufügen auswählen.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-128">Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.</span></span>  
  
 <span data-ttu-id="cfe6b-129">In der Schemasicht können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="cfe6b-129">In Schema view you can:</span></span>  
  
-   <span data-ttu-id="cfe6b-130">Vorhandene XML-Schemas und ADO.NET-Datasets erstellen und ändern</span><span class="sxs-lookup"><span data-stu-id="cfe6b-130">Construct and modify existing XML Schemas and ADO.NET datasets</span></span>  
  
-   <span data-ttu-id="cfe6b-131">Beziehungen zwischen Tabellen erstellen und bearbeiten</span><span class="sxs-lookup"><span data-stu-id="cfe6b-131">Create and edit relationships between tables</span></span>  
  
-   <span data-ttu-id="cfe6b-132">Schlüssel erstellen und bearbeiten</span><span class="sxs-lookup"><span data-stu-id="cfe6b-132">Create and edit keys</span></span>  
  
-   <span data-ttu-id="cfe6b-133">ADO.NET-Datasets aus XML-Schemas generieren</span><span class="sxs-lookup"><span data-stu-id="cfe6b-133">Generate ADO.NET datasets from XML Schemas</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfe6b-134">Das Layout der Elemente in der Schemasicht wird in der XSX-Datei gespeichert. Sie können die Datei anzeigen, indem Sie auf der Symbolleiste Projektmappen-Explorer auf **Alle Dateien anzeigen** klicken und dann die XSD-Datei erweitern.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-134">The layout of elements in Schema view is stored in the .xsx file, which can be seen by clicking **Show All Files** in the Solution Explorer toolbar, and then expanding the .xsd file.</span></span> <span data-ttu-id="cfe6b-135">Wenn keine XSX-Datei vorhanden ist, bedeutet dies, dass die XSD-Datei zuvor noch nie im XML-Designer geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-135">If there is no .xsx file present, it means the .xsd file has never been opened in the XML Designer.</span></span>  
  
### <a name="customizing-schema-view"></a><span data-ttu-id="cfe6b-136">Anpassen der Schemasicht</span><span class="sxs-lookup"><span data-stu-id="cfe6b-136">Customizing Schema View</span></span>  
 <span data-ttu-id="cfe6b-137">Mithilfe der folgenden Funktionen können Sie das visuelle Layout der Elemente in der Schemasicht ändern:</span><span class="sxs-lookup"><span data-stu-id="cfe6b-137">The following features modify the visual layout of elements in Schema view:</span></span>  
  
-   <span data-ttu-id="cfe6b-138">Zoomen</span><span class="sxs-lookup"><span data-stu-id="cfe6b-138">Zooming</span></span>  
  
-   <span data-ttu-id="cfe6b-139">Erweitern oder Reduzieren verschachtelter Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe6b-139">Expanding or collapsing of nested elements</span></span>  
  
-   <span data-ttu-id="cfe6b-140">Automatisches Anordnen des Layouts der Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe6b-140">Automatically arranging layout of elements</span></span>  
  
-   <span data-ttu-id="cfe6b-141">Wiederherstellen des Standardstatus der reduzierten Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe6b-141">Resetting default state of collapsed elements</span></span>  
  
##### <a name="to-expand-hidden-nested-elements"></a><span data-ttu-id="cfe6b-142">So erweitern Sie ausgeblendete verschachtelte Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe6b-142">To expand hidden nested elements</span></span>  
  
-   <span data-ttu-id="cfe6b-143">Klicken Sie auf das Plussymbol unten am Element.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-143">Click the plus icon on the bottom of the element.</span></span>  
  
##### <a name="to-collapse-nested-elements"></a><span data-ttu-id="cfe6b-144">So reduzieren Sie verschachtelte Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe6b-144">To collapse nested elements</span></span>  
  
-   <span data-ttu-id="cfe6b-145">Klicken Sie auf das Minussymbol für das am weitesten unten gelegene Element, das im Designer angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-145">Click the minus icon on the bottom-most element that you want to appear on the designer.</span></span>  
  
## <a name="data-view"></a><span data-ttu-id="cfe6b-146">Datensicht</span><span class="sxs-lookup"><span data-stu-id="cfe6b-146">Data View</span></span>  
 <span data-ttu-id="cfe6b-147">Die Datensicht bietet einen Datenraster, der zum Ändern von XML-Dateien verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-147">Data view provides a data grid that can be used to modify .xml files.</span></span> <span data-ttu-id="cfe6b-148">In der Datensicht kann nur der Inhalt (nicht jedoch die Struktur und die Tags) einer XML-Datei bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-148">Only the content (but not the tags and structure) in an XML file can be edited in Data view.</span></span>  
  
 <span data-ttu-id="cfe6b-149">Es gibt zwei separate Bereiche in der Datensicht: **Datentabellen** und **Daten**.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-149">There are two separate areas in Data view: **Data Tables** and **Data**.</span></span> <span data-ttu-id="cfe6b-150">Der Bereich **Datentabellen** stellt eine Liste der in der XML-Datei definierten Beziehungen in der Reihenfolge ihrer Verschachtelung (von außen nach innen) dar.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-150">The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost).</span></span> <span data-ttu-id="cfe6b-151">Der Bereich **Daten** ist ein Datenraster, das Daten basierend auf der Auswahl im Bereich Datentabellen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-151">The **Data** area is a data grid that displays data based on the selection in the Data Tables area.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfe6b-152">Neu erstellte XML-Dateien enthalten keine Daten und können daher in der Datensicht nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-152">Newly created XML files contain no data and therefore cannot be displayed in Data view.</span></span> <span data-ttu-id="cfe6b-153">Es gibt auch einige Instanzen von XML-Dokumenten, bei denen die Datensicht nicht aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-153">There are also some instances of XML documents where data view cannot be invoked at all.</span></span> <span data-ttu-id="cfe6b-154">Auch wenn das XML-Dokument ordnungsgemäß aufgebaut ist, können strukturierte Daten, die versuchen, in die Datensicht zu wechseln, die folgende Meldung generieren: "Das XML-Dokument ist richtig formatiert, enthält jedoch eine Struktur, die nicht in der Datenansicht angezeigt werden kann."</span><span class="sxs-lookup"><span data-stu-id="cfe6b-154">Although the XML would be considered well formed, if it is not structured data trying to switch to Data view will generate the following message: "Although this document is well formed, it contains structure that Data View cannot display."</span></span>  
  
 <span data-ttu-id="cfe6b-155">In der Datensicht können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="cfe6b-155">In Data view you can:</span></span>  
  
-   <span data-ttu-id="cfe6b-156">Manuell Datentabellen auffüllen</span><span class="sxs-lookup"><span data-stu-id="cfe6b-156">Manually populate data tables</span></span>  
  
-   <span data-ttu-id="cfe6b-157">Vorhandene Datentabellen bearbeiten</span><span class="sxs-lookup"><span data-stu-id="cfe6b-157">Edit existing data tables</span></span>  
  
-   <span data-ttu-id="cfe6b-158">Ein XML-Schema aus einem XML-Dokument generieren</span><span class="sxs-lookup"><span data-stu-id="cfe6b-158">Generate an XML Schema from an XML document</span></span>  
  
## <a name="xml-view"></a><span data-ttu-id="cfe6b-159">XML-Ansicht</span><span class="sxs-lookup"><span data-stu-id="cfe6b-159">XML View</span></span>  
 <span data-ttu-id="cfe6b-160">Die XML-Ansicht bietet einen Editor zum Bearbeiten von Roh-XML sowie darüber hinaus IntelliSense und Farbcodierung.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-160">XML view provides an editor for editing raw XML and provides IntelliSense and color coding.</span></span> <span data-ttu-id="cfe6b-161">Bei der Arbeit an XSD- und XML-Dateien mit zugehörigem Schema steht der Anweisungsabschluss zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-161">Statement completion is available when working on .xsd files and .xml files that have an associated schema.</span></span> <span data-ttu-id="cfe6b-162">Geben \< Sie ein, um ein Tag zu initiieren, und Ihnen wird eine Liste von Elementen angezeigt, die an diesem Speicherort gültig sind.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-162">Type \< to initiate a tag and you will be presented with a list of elements that are valid at that location.</span></span> <span data-ttu-id="cfe6b-163">Nachdem Sie den Elementnamen eingegeben und die LEERTASTE gedrückt haben, wird Ihnen eine Liste mit Attributen vorgeschlagen, die von dem Element unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-163">After you type the element name and press the SPACEBAR, you will be presented with a list of attributes that the element supports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="cfe6b-164">IntelliSense stehen auf der Symbolleiste nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-164">IntelliSense options are not available on the toolbar.</span></span> <span data-ttu-id="cfe6b-165">Wenn Sie im XML-Editor auf die Optionen zugreifen möchten, klicken Sie im Menü **Bearbeiten** auf **IntelliSense**.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-165">When in the XML Editor, to access the options, on the **Edit** menu, click **IntelliSense**.</span></span>  
  
## <a name="showplan-view"></a><span data-ttu-id="cfe6b-166">SHOWPLAN-Sicht</span><span class="sxs-lookup"><span data-stu-id="cfe6b-166">SHOWPLAN view</span></span>  
 <span data-ttu-id="cfe6b-167">Abfragepläne können im XML-Format gespeichert werden, wenn sie mithilfe der Option SET SHOWPLAN_XML ON erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-167">Query plans can be saved in XML format when created using SET SHOWPLAN_XML ON option.</span></span> <span data-ttu-id="cfe6b-168">Doppelklicken Sie auf eine Datei mit der Erweiterung .showplan, um den Abfrageplan zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cfe6b-168">Double-click a file with the .showplan extension to open the query plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe6b-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfe6b-169">See Also</span></span>  
 [<span data-ttu-id="cfe6b-170">Speichern eines Ausführungsplans im XML-Format</span><span class="sxs-lookup"><span data-stu-id="cfe6b-170">Save an Execution Plan in XML Format</span></span>](../performance/save-an-execution-plan-in-xml-format.md)  
  
  
