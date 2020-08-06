---
title: Exportieren als CSV-Datei (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 68ec746e-8c82-47f5-8c3d-dbe403a441e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 635d5904acf6e616378f5423bfbaf4cf5390fa9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608363"
---
# <a name="exporting-to-a-csv-file-report-builder-and-ssrs"></a><span data-ttu-id="e682d-102">Exportieren als CSV-Datei (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="e682d-102">Exporting to a CSV File (Report Builder and SSRS)</span></span>
  <span data-ttu-id="e682d-103">Die durch Trennzeichen getrennte CSV (Comma-Separated Value)-Renderingerweiterung rendert Berichte als vereinfachte Darstellung der Daten eines Berichts in einem standardisierten Nur-Text-Format, das leicht lesbar und mit anderen Anwendungen austauschbar ist.</span><span class="sxs-lookup"><span data-stu-id="e682d-103">The Comma-Separated Value (CSV) rendering extension renders reports as a flattened representation of data from a report in a standardized, plain-text format that is easily readable and exchangeable with many applications.</span></span>  
  
 <span data-ttu-id="e682d-104">Dabei werden Felder und Zeilen durch ein Trennzeichen getrennt, für das auch ein anderes Zeichen als ein Komma gewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e682d-104">The CSV rendering extension uses a string character delimiter to separate fields and rows, with the string character delimiter configurable to be a character other than a comma.</span></span> <span data-ttu-id="e682d-105">Die erstellte Datei kann in einem Tabellenkalkulationsprogramm wie [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] geöffnet oder als Importformat für andere Programme verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e682d-105">The resulting file can be opened in a spreadsheet program like [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)] or used as an import format for other programs.</span></span> <span data-ttu-id="e682d-106">Der exportierte Bericht wird zu einer CSV-Datei umgewandelt und gibt den MIME-Typ `text/csv` zurück.</span><span class="sxs-lookup"><span data-stu-id="e682d-106">The exported report becomes a .csv file, and returns a MIME type of `text/csv`.</span></span>  
  
 <span data-ttu-id="e682d-107">Wenn Sie in [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)]mit Daten für Diagramme, Datenbalken, Sparklines, Messgeräte oder Indikatoren arbeiten möchten, exportieren Sie den Bericht in eine CSV-Datei, und öffnen Sie diese anschließend in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="e682d-107">If you want to work with data related to charts, data bars, sparklines, gauges, and indicators in [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)], export the report to a CSV file, and then open the file in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="csv-rendering"></a><a name="CSVRendering"></a><span data-ttu-id="e682d-108">CSV-Rendering</span><span class="sxs-lookup"><span data-stu-id="e682d-108">CSV Rendering</span></span>  
 <span data-ttu-id="e682d-109">Ein CSV-Bericht, der mit den Standardeinstellungen gerendert wurde, besitzt folgende Merkmale:</span><span class="sxs-lookup"><span data-stu-id="e682d-109">When rendered using the default settings, a CSV report has the following characteristics:</span></span>  
  
-   <span data-ttu-id="e682d-110">Das standardmäßige Feldtrennzeichen ist ein Komma (,).</span><span class="sxs-lookup"><span data-stu-id="e682d-110">The default field delimiter string is a comma (,).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e682d-111">Sie können das Feldtrennzeichen in ein beliebiges Zeichen (einschließlich TAB) ändern, indem Sie die Geräteinformationseinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="e682d-111">You can change the field delimiter to any character that you want, including TAB, by changing the device information settings.</span></span> <span data-ttu-id="e682d-112">Weitere Informationen finden Sie unter [CSV Device Information Settings](../csv-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e682d-112">For more information, see [CSV Device Information Settings](../csv-device-information-settings.md).</span></span>  
  
-   <span data-ttu-id="e682d-113">Die Daten Satz Trennzeichen-Zeichenfolge ist das Wagen Rücklauf-und Zeilenvorschub Zeichen ( \<cr> \<lf> ).</span><span class="sxs-lookup"><span data-stu-id="e682d-113">The record delimiter string is the carriage return and line feed (\<cr>\<lf>).</span></span>  
  
-   <span data-ttu-id="e682d-114">Als Textqualifizierer-Zeichenfolge dient das Anführungszeichen (").</span><span class="sxs-lookup"><span data-stu-id="e682d-114">The text qualifier string is a quotation mark (").</span></span>  
  
     <span data-ttu-id="e682d-115">Der CSV-Renderer fügt keine Qualifizierer um alle Textzeichenfolgen hinzu.</span><span class="sxs-lookup"><span data-stu-id="e682d-115">The CSV renderer does not add qualifiers around all text strings.</span></span> <span data-ttu-id="e682d-116">Textqualifizierer werden nur hinzugefügt, wenn der Wert das Trennzeichen oder einen Zeilenumbruch enthält.</span><span class="sxs-lookup"><span data-stu-id="e682d-116">Text qualifiers are added only when the value contains the delimiter character or when the value has a line break.</span></span>  
  
-   <span data-ttu-id="e682d-117">Falls der Text eine eingebettete Trennzeichenfolge oder Qualifiziererzeichenfolge enthält, wird der Text in den Textqualifizierer eingeschlossen, und die eingebetteten Qualifiziererzeichenfolgen werden verdoppelt.</span><span class="sxs-lookup"><span data-stu-id="e682d-117">If the text contains an embedded delimiter string or qualifier string, the text qualifier is placed around the text, and the embedded qualifier strings are doubled.</span></span>  
  
-   <span data-ttu-id="e682d-118">Formatierung und Layout werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e682d-118">Formatting and layout are ignored.</span></span>  
  
 <span data-ttu-id="e682d-119">Die folgenden Elemente werden beim Rendern ignoriert:</span><span class="sxs-lookup"><span data-stu-id="e682d-119">The following items are ignored during rendering:</span></span>  
  
-   <span data-ttu-id="e682d-120">Seitenkopf</span><span class="sxs-lookup"><span data-stu-id="e682d-120">Page header</span></span>  
  
-   <span data-ttu-id="e682d-121">Seitenfuß</span><span class="sxs-lookup"><span data-stu-id="e682d-121">Page footer</span></span>  
  
-   <span data-ttu-id="e682d-122">Benutzerdefinierte Berichtselemente</span><span class="sxs-lookup"><span data-stu-id="e682d-122">Custom report items</span></span>  
  
-   <span data-ttu-id="e682d-123">Linie</span><span class="sxs-lookup"><span data-stu-id="e682d-123">Line</span></span>  
  
-   <span data-ttu-id="e682d-124">Image</span><span class="sxs-lookup"><span data-stu-id="e682d-124">Image</span></span>  
  
-   <span data-ttu-id="e682d-125">Rechteck</span><span class="sxs-lookup"><span data-stu-id="e682d-125">Rectangle</span></span>  
  
-   <span data-ttu-id="e682d-126">Automatische Teilergebnisse</span><span class="sxs-lookup"><span data-stu-id="e682d-126">Automatic subtotals</span></span>  
  
 <span data-ttu-id="e682d-127">Die verbleibenden Berichtselemente werden von oben nach unten und dann von links nach rechts sortiert.</span><span class="sxs-lookup"><span data-stu-id="e682d-127">The remaining report items are sorted, from top to bottom, then left to right.</span></span> <span data-ttu-id="e682d-128">Anschließend wird jedes Element in eine Spalte gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-128">Each item is then rendered to a column.</span></span> <span data-ttu-id="e682d-129">Enthält der Bericht geschachtelte Datenelemente, wie Listen oder Tabellen, werden die übergeordneten Elemente in jedem Datensatz wiederholt.</span><span class="sxs-lookup"><span data-stu-id="e682d-129">If the report has nested data items like lists or tables, the parent items are repeated in each record.</span></span>  
  
 <span data-ttu-id="e682d-130">In der folgenden Tabelle wird die Darstellung von Berichtselementen beim Rendern angegeben:</span><span class="sxs-lookup"><span data-stu-id="e682d-130">The following table indicates the appearance of report items when rendered:</span></span>  
  
|<span data-ttu-id="e682d-131">Element</span><span class="sxs-lookup"><span data-stu-id="e682d-131">Item</span></span>|<span data-ttu-id="e682d-132">Renderingverhalten</span><span class="sxs-lookup"><span data-stu-id="e682d-132">Rendering behavior</span></span>|  
|----------|------------------------|  
|<span data-ttu-id="e682d-133">Textfeld</span><span class="sxs-lookup"><span data-stu-id="e682d-133">Text box</span></span>|<span data-ttu-id="e682d-134">Der Inhalt des Textfelds wird gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-134">Renders the contents of the text box.</span></span> <span data-ttu-id="e682d-135">Im Standardmodus werden Elemente auf Grundlage der Formatierungseigenschaften des Elements formatiert.</span><span class="sxs-lookup"><span data-stu-id="e682d-135">In default mode, items are formatted based on the item's formatting properties.</span></span> <span data-ttu-id="e682d-136">Im kompatiblen Modus kann die Formatierung durch die Geräteinformationseinstellungen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e682d-136">In compliant mode, formatting can be changed by device information settings.</span></span> <span data-ttu-id="e682d-137">Weitere Informationen zu den CSV-Renderingmodi finden Sie weiter unten.</span><span class="sxs-lookup"><span data-stu-id="e682d-137">For more information about CSV rendering modes, see below.</span></span>|  
|<span data-ttu-id="e682d-138">Tabelle</span><span class="sxs-lookup"><span data-stu-id="e682d-138">Table</span></span>|<span data-ttu-id="e682d-139">Das Rendering erfolgt durch Erweitern der Tabelle und Erstellen einer Zeile und Spalte für jede Zeile und Spalte auf der untersten Detailebene.</span><span class="sxs-lookup"><span data-stu-id="e682d-139">Renders by expanding the table and creating a row and column for each row and column at the lowest level of detail.</span></span> <span data-ttu-id="e682d-140">Teilergebniszeilen und -spalten weisen keine Zeilen- und Spaltenüberschriften auf.</span><span class="sxs-lookup"><span data-stu-id="e682d-140">Subtotal rows and columns do not have column or row headings.</span></span> <span data-ttu-id="e682d-141">Drillthroughberichte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e682d-141">Drillthrough reports are not supported.</span></span>|  
|<span data-ttu-id="e682d-142">Matrix</span><span class="sxs-lookup"><span data-stu-id="e682d-142">Matrix</span></span>|<span data-ttu-id="e682d-143">Das Rendering erfolgt durch Erweitern der Matrix und Erstellen einer Zeile und Spalte für jede Zeile und Spalte auf der untersten Detailebene.</span><span class="sxs-lookup"><span data-stu-id="e682d-143">Renders by expanding the matrix and creating a row and column for each row and column at the lowest level of detail.</span></span> <span data-ttu-id="e682d-144">Teilergebniszeilen und -spalten weisen keine Zeilen- und Spaltenüberschriften auf.</span><span class="sxs-lookup"><span data-stu-id="e682d-144">Subtotal rows and columns do not have column or row headings.</span></span>|  
|<span data-ttu-id="e682d-145">List</span><span class="sxs-lookup"><span data-stu-id="e682d-145">List</span></span>|<span data-ttu-id="e682d-146">Für jede Detailzeile oder Instanz in der Liste wird ein Datensatz gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-146">Renders a record for each detail row or instance in the list.</span></span>|  
|<span data-ttu-id="e682d-147">Unterbericht</span><span class="sxs-lookup"><span data-stu-id="e682d-147">Subreport</span></span>|<span data-ttu-id="e682d-148">Das übergeordnete Element wird für jede Instanz des Inhalts wiederholt.</span><span class="sxs-lookup"><span data-stu-id="e682d-148">The parent item is repeated for each instance of the contents.</span></span>|  
|<span data-ttu-id="e682d-149">Diagramm</span><span class="sxs-lookup"><span data-stu-id="e682d-149">Chart</span></span>|<span data-ttu-id="e682d-150">Wird gerendert, indem eine Zeile für jeden Diagrammwert und jede Elementbezeichnung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e682d-150">Renders by creating a row for each chart value and member labels.</span></span> <span data-ttu-id="e682d-151">Bezeichnungen aus Reihen und Kategorien in Hierarchien werden vereinfacht und in die Zeile für einen Diagrammwert eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e682d-151">Labels from series and categories in hierarchies are flattened and included in the row for a chart value.</span></span>|  
|<span data-ttu-id="e682d-152">Datenbalken</span><span class="sxs-lookup"><span data-stu-id="e682d-152">Data bar</span></span>|<span data-ttu-id="e682d-153">Wird wie ein Diagramm gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-153">Renders like a chart.</span></span> <span data-ttu-id="e682d-154">Ein Datenbalken enthält normalerweise keine Hierarchien oder Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="e682d-154">Typically, a data bar does not include hierarchies or labels.</span></span>|  
|<span data-ttu-id="e682d-155">Sparkline</span><span class="sxs-lookup"><span data-stu-id="e682d-155">Sparkline</span></span>|<span data-ttu-id="e682d-156">Wird wie ein Diagramm gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-156">Renders like a chart.</span></span> <span data-ttu-id="e682d-157">Eine Sparkline enthält üblicherweise keine Hierarchien oder Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="e682d-157">Typically, a sparkline does not  do not include hierarchies or labels.</span></span>|  
|<span data-ttu-id="e682d-158">Maßstab</span><span class="sxs-lookup"><span data-stu-id="e682d-158">Gauge</span></span>|<span data-ttu-id="e682d-159">Wird als einzelner Datensatz mit dem Minimal- und Maximalwert der linearen Skala, dem Start- und Endwert des Bereichs und dem Wert des Zeigers gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-159">Renders as a single record with the minimum and maximum values of the linear scale, start and end values of the range, and the value of the pointer.</span></span>|  
|<span data-ttu-id="e682d-160">Indikator</span><span class="sxs-lookup"><span data-stu-id="e682d-160">Indicator</span></span>|<span data-ttu-id="e682d-161">Es wird als einzelnes Element mit dem Namen des aktiven Zustands, den verfügbaren Zuständen und dem Datenwert als Attribute gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-161">Renders as a single record with the active state name, available states, and the data value.</span></span>|  
|<span data-ttu-id="e682d-162">Karte</span><span class="sxs-lookup"><span data-stu-id="e682d-162">Map</span></span>|<span data-ttu-id="e682d-163">Rendert eine Zeile mit den Bezeichnungen und Werten der einzelnen Kartenelemente einer Kartenebene.</span><span class="sxs-lookup"><span data-stu-id="e682d-163">Renders a row with the labels and values for each map member of a map layer.</span></span><br /><br /> <span data-ttu-id="e682d-164">Wenn die Karte über mehrere Ebenen verfügt, variieren die Werte in den Zeilen abhängig davon, ob die Kartenebenen die gleichen oder unterschiedliche Kartendatenbereiche verwenden.</span><span class="sxs-lookup"><span data-stu-id="e682d-164">If the map has multiple layers the values in the rows varies depending on whether the map layers use the same or different map data regions.</span></span> <span data-ttu-id="e682d-165">Wenn mehrere Kartenebenen den gleichen Datenbereich verwenden, enthalten die Zeilen Daten aus allen Ebenen.</span><span class="sxs-lookup"><span data-stu-id="e682d-165">If multiple map layers use the same data region, the rows contain data from all layers.</span></span>|  
  
### <a name="hierarchical-and-grouped-data"></a><span data-ttu-id="e682d-166">Hierarchische und gruppierte Daten</span><span class="sxs-lookup"><span data-stu-id="e682d-166">Hierarchical and Grouped Data</span></span>  
 <span data-ttu-id="e682d-167">Hierarchische und gruppierte Daten müssen vereinfacht werden, um im CSV-Format dargestellt zu werden.</span><span class="sxs-lookup"><span data-stu-id="e682d-167">Hierarchical and grouped data must be flattened in order to be represented in the CSV format.</span></span>  
  
 <span data-ttu-id="e682d-168">Die Renderingerweiterung vereinfacht den Bericht zu einer Baumstruktur, die die geschachtelten Gruppen innerhalb des Datenbereichs darstellt.</span><span class="sxs-lookup"><span data-stu-id="e682d-168">The rendering extension flattens the report into a tree structure that represents the nested groups within the data region.</span></span> <span data-ttu-id="e682d-169">So vereinfachen Sie den Bericht:</span><span class="sxs-lookup"><span data-stu-id="e682d-169">To flatten the report:</span></span>  
  
-   <span data-ttu-id="e682d-170">Eine Zeilenhierarchie wird vor einer Spaltenhierarchie vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="e682d-170">A row hierarchy is flattened before a column hierarchy.</span></span>  
  
-   <span data-ttu-id="e682d-171">Spalten werden wie folgt sortiert: Textfelder im Hauptteil von links nach rechts und von oben nach unten, gefolgt von Datenbereichen von links nach rechts und von oben nach unten.</span><span class="sxs-lookup"><span data-stu-id="e682d-171">Columns are ordered as follows: text boxes in body order left-to-right, top-to-bottom followed by data regions ordered left-to-right, top-to-bottom.</span></span>  
  
-   <span data-ttu-id="e682d-172">Innerhalb eines Datenbereichs werden die Spalten wie folgt sortiert: Eckelemente, Zeilenhierarchieelemente, Spaltenhierarchieelemente und Zellen</span><span class="sxs-lookup"><span data-stu-id="e682d-172">Within a data region, the columns are ordered as follows: corner members, row hierarchy members, column hierarchy members, and then cells.</span></span>  
  
-   <span data-ttu-id="e682d-173">Peerdatenbereiche sind Datenbereiche oder dynamische Gruppen, die einen allgemeinen Datenbereich oder einen dynamischen Vorgänger gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="e682d-173">Peer data regions are data regions or dynamic groups that share a common data region or dynamic ancestor.</span></span> <span data-ttu-id="e682d-174">Peerdaten werden durch Verzweigen der vereinfachten Struktur identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e682d-174">Peer data is identified by branching of the flattened tree.</span></span>  
  
 <span data-ttu-id="e682d-175">Weitere Informationen finden Sie unter [Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="e682d-175">For more information, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
 
  
##  <a name="renderer-modes"></a><a name="RenderingModes"></a> <span data-ttu-id="e682d-176">Renderermodi</span><span class="sxs-lookup"><span data-stu-id="e682d-176">Renderer Modes</span></span>  
 <span data-ttu-id="e682d-177">Für die CSV-Renderingerweiterung stehen zwei Modi zur Verfügung. Ein Modus ist für Excel, der andere für Anwendungen von Drittanbietern optimiert, die eine strikte CSV-Kompatibilität mit der CSV-Spezifikation in RFC 4180 erfordern.</span><span class="sxs-lookup"><span data-stu-id="e682d-177">The CSV rendering extension can operate in two modes: one is optimized for Excel and the other is optimized for third-party applications that require strict CSV compliance to the CSV specification in RFC 4180.</span></span> <span data-ttu-id="e682d-178">Je nach verwendetem Modus werden Peerdatenbereiche unterschiedlich behandelt.</span><span class="sxs-lookup"><span data-stu-id="e682d-178">Depending on which mode you use, peer data regions are handled differently.</span></span>  
  
### <a name="default-mode"></a><span data-ttu-id="e682d-179">Standardmodus</span><span class="sxs-lookup"><span data-stu-id="e682d-179">Default Mode</span></span>  
 <span data-ttu-id="e682d-180">Der Standardmodus ist für Excel optimiert.</span><span class="sxs-lookup"><span data-stu-id="e682d-180">The default mode is optimized for Excel.</span></span> <span data-ttu-id="e682d-181">Im Standardmodus wird der Bericht als CSV-Datei mit mehreren Abschnitten gerenderter CSV-Daten gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-181">When rendered in default mode, the report is rendered as a CSV file with multiple sections of CSV-rendered data.</span></span> <span data-ttu-id="e682d-182">Jeder Peerdatenbereich wird durch eine leere Zeile begrenzt.</span><span class="sxs-lookup"><span data-stu-id="e682d-182">Each peer data region is delimited by an empty line.</span></span> <span data-ttu-id="e682d-183">Peerdatenbereiche innerhalb des Berichthauptteils werden als separate Datenblocks innerhalb der CSV-Datei gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-183">Peer data regions within the report body are rendered as separate blocks of data within the CSV file.</span></span> <span data-ttu-id="e682d-184">Das Ergebnis ist eine CSV-Datei mit folgenden Merkmalen:</span><span class="sxs-lookup"><span data-stu-id="e682d-184">The result is a CSV file in which:</span></span>  
  
-   <span data-ttu-id="e682d-185">Einzelne Textfelder innerhalb des Berichthauptteils werden einmal als erster Datenblock innerhalb der CSV-Datei gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-185">Individual text boxes within the report body are rendered once as the first block of data within the CSV file.</span></span>  
  
-   <span data-ttu-id="e682d-186">Jeder Peerdatenbereich der obersten Ebene im Hauptteil des Berichts wird in einem eigenen Datenblock gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-186">Each top-level peer data region in the report body is rendered in its own data block.</span></span>  
  
-   <span data-ttu-id="e682d-187">Geschachtelte Datenbereiche werden diagonal in den gleichen Datenblock gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-187">Nested data regions are rendered diagonally into the same data block.</span></span>  
  
#### <a name="formatting"></a><span data-ttu-id="e682d-188">Formatierung</span><span class="sxs-lookup"><span data-stu-id="e682d-188">Formatting</span></span>  
 <span data-ttu-id="e682d-189">Numerische Werte werden in ihrem formatierten Status gerendert.</span><span class="sxs-lookup"><span data-stu-id="e682d-189">Numeric values are rendered in their formatted state.</span></span> <span data-ttu-id="e682d-190">Excel kann formatierte numerische Werte, wie Währungen, Prozentwerte und Datumsangaben, erkennen und die Zellen beim Importieren einer CSV-Datei entsprechend formatieren.</span><span class="sxs-lookup"><span data-stu-id="e682d-190">Excel can recognize formatted numeric values, such as currency, percentage and date, and format the cells appropriately when importing the CSV file.</span></span>  
  
### <a name="compliant-mode"></a><span data-ttu-id="e682d-191">Kompatibler Modus</span><span class="sxs-lookup"><span data-stu-id="e682d-191">Compliant Mode</span></span>  
 <span data-ttu-id="e682d-192">Der kompatible Modus ist für Anwendungen von Drittanbietern optimiert.</span><span class="sxs-lookup"><span data-stu-id="e682d-192">Compliant mode is optimized for third-party applications.</span></span>  
  
#### <a name="data-regions"></a><span data-ttu-id="e682d-193">Datenbereiche</span><span class="sxs-lookup"><span data-stu-id="e682d-193">Data Regions</span></span>  
 <span data-ttu-id="e682d-194">Nur die erste Textzeile in der Datei enthält die Spaltenkopfzeilen, und jede Zeile verfügt über dieselbe Spaltenanzahl.</span><span class="sxs-lookup"><span data-stu-id="e682d-194">Only the first row of the file contains the column headers and each row has the same number of columns.</span></span>  
  
#### <a name="formatting"></a><span data-ttu-id="e682d-195">Formatierung</span><span class="sxs-lookup"><span data-stu-id="e682d-195">Formatting</span></span>  
 <span data-ttu-id="e682d-196">Die Werte sind unformatiert.</span><span class="sxs-lookup"><span data-stu-id="e682d-196">Values are unformatted.</span></span>  
  
##  <a name="interactivity"></a><a name="Interactivity"></a><span data-ttu-id="e682d-197">Interaktivität</span><span class="sxs-lookup"><span data-stu-id="e682d-197">Interactivity</span></span>  
 <span data-ttu-id="e682d-198">Interaktivität wird von keinem der durch diesen Renderer generierten CSV-Formate unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e682d-198">Interactivity is not supported by either CSV formats generated by this renderer.</span></span> <span data-ttu-id="e682d-199">Die folgenden interaktiven Elemente werden nicht gerendert:</span><span class="sxs-lookup"><span data-stu-id="e682d-199">The following interactive elements are not rendered:</span></span>  
  
-   <span data-ttu-id="e682d-200">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="e682d-200">Hyperlinks</span></span>  
  
-   <span data-ttu-id="e682d-201">Anzeigen oder ausblenden</span><span class="sxs-lookup"><span data-stu-id="e682d-201">Show or Hide</span></span>  
  
-   <span data-ttu-id="e682d-202">Dokumentstruktur</span><span class="sxs-lookup"><span data-stu-id="e682d-202">Document Map</span></span>  
  
-   <span data-ttu-id="e682d-203">Drillthrough oder Links mit Durchklicken</span><span class="sxs-lookup"><span data-stu-id="e682d-203">Drillthrough or clickthrough links</span></span>  
  
-   <span data-ttu-id="e682d-204">Endbenutzersortierung</span><span class="sxs-lookup"><span data-stu-id="e682d-204">End user sort</span></span>  
  
-   <span data-ttu-id="e682d-205">Feste Berichtsköpfe</span><span class="sxs-lookup"><span data-stu-id="e682d-205">Fixes headers</span></span>  
  
-   <span data-ttu-id="e682d-206">Lesezeichen</span><span class="sxs-lookup"><span data-stu-id="e682d-206">Bookmarks</span></span>  
  

  
##  <a name="device-information-settings"></a><a name="DeviceInfo"></a><span data-ttu-id="e682d-207">Geräte Informationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e682d-207">Device Information Settings</span></span>  
 <span data-ttu-id="e682d-208">Sie kännen einige Standardeinstellungen für diesen Renderer ändern, beispielsweise den Modus für das Rendern, die Zeichen, die als Trennzeichen verwendet werden können, und die Zeichen, die als Textqualifizierer für die Standardzeichenfolge verwendet werden können. Ändern Sie dazu die Geräteinformationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="e682d-208">You can change some default settings for this renderer, including which mode to render in, which characters to use as delimiters and which characters to use as the text qualifier default string, by changing the device information settings.</span></span> <span data-ttu-id="e682d-209">Weitere Informationen finden Sie unter [CSV Device Information Settings](../csv-device-information-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e682d-209">For more information, see [CSV Device Information Settings](../csv-device-information-settings.md).</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="e682d-210">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e682d-210">See Also</span></span>  
 <span data-ttu-id="e682d-211">[Paginierung in Reporting Services &#40;Berichts-Generator und SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e682d-211">[Pagination in Reporting Services &#40;Report Builder  and SSRS&#41;](../report-design/pagination-in-reporting-services-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e682d-212">[Renderingverhaltensweisen &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e682d-212">[Rendering Behaviors &#40;Report Builder  and SSRS&#41;](../report-design/rendering-behaviors-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="e682d-213">[Interaktive Funktionalität für verschiedene Berichtsrenderingerweiterungen &#40;Berichts-Generator und SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="e682d-213">[Interactive Functionality for Different Report Rendering Extensions &#40;Report Builder and SSRS&#41;](interactive-functionality-different-report-rendering-extensions.md) </span></span>  
 <span data-ttu-id="e682d-214">[Rendern von Berichts Elementen &#40;Berichts-Generator und SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="e682d-214">[Rendering Report Items &#40;Report Builder and SSRS&#41;](../report-design/rendering-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="e682d-215">Tabellen, Matrizen und Listen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e682d-215">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)  
  
  
