---
title: Verbindungs-Manager-Editor für mehrere Flatfiles (Seite Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.columns.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: ad0cb668-0df2-4d4e-9a20-d20692a0b67a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5a7f4936f0722754b414076820eda7dcf2dc8dc5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609297"
---
# <a name="multiple-flat-files-connection-manager-editor-columns-page"></a><span data-ttu-id="b53bc-102">Verbindungs-Manager-Editor für mehrere Flatfiles (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="b53bc-102">Multiple Flat Files Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="b53bc-103">Verwenden Sie den Knoten **Spalten** im Dialogfeld **Verbindungs-Manager-Editor für mehrere Flatfiles** , um die Zeilen- und Spalteninformationen anzugeben und eine Vorschau der ersten ausgewählten Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b53bc-103">Use the **Columns** node of the **Multiple Flat Files Connection Manager Editor** dialog box to specify the row and column information, and to preview the first selected file.</span></span>  
  
 <span data-ttu-id="b53bc-104">Weitere Informationen zum Verbindungs-Manager für mehrere Flatfiles finden Sie unter [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b53bc-104">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="b53bc-105">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="b53bc-105">Static Options</span></span>  
 <span data-ttu-id="b53bc-106">**Name des Verbindungs-Managers**</span><span class="sxs-lookup"><span data-stu-id="b53bc-106">**Connection manager name**</span></span>  
 <span data-ttu-id="b53bc-107">Geben Sie einen eindeutigen Namen für die Verbindung für mehrere Flatfiles im Workflow an.</span><span class="sxs-lookup"><span data-stu-id="b53bc-107">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="b53bc-108">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b53bc-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b53bc-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="b53bc-109">**Description**</span></span>  
 <span data-ttu-id="b53bc-110">Beschreiben Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="b53bc-110">Describe the connection.</span></span> <span data-ttu-id="b53bc-111">Es ist eine bewährte Methode, die Verbindung zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und einfacher zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="b53bc-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="b53bc-112">Flatfileformat (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="b53bc-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="b53bc-113">Format = Mit Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="b53bc-113">Format = Delimited</span></span>  
 <span data-ttu-id="b53bc-114">**Zeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="b53bc-114">**Row delimiter**</span></span>  
 <span data-ttu-id="b53bc-115">Wählen Sie aus der Liste verfügbarer Zeilentrennzeichen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="b53bc-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="b53bc-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b53bc-116">Value</span></span>|<span data-ttu-id="b53bc-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b53bc-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b53bc-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-118">**{CR}{LF}**</span></span>|<span data-ttu-id="b53bc-119">Als Trennzeichen für Zeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="b53bc-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="b53bc-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-120">**{CR}**</span></span>|<span data-ttu-id="b53bc-121">Als Trennzeichen für Zeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="b53bc-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="b53bc-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-122">**{LF}**</span></span>|<span data-ttu-id="b53bc-123">Als Trennzeichen für Zeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="b53bc-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="b53bc-124">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-124">**Semicolon {;}**</span></span>|<span data-ttu-id="b53bc-125">Als Trennzeichen für Zeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="b53bc-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="b53bc-126">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-126">**Colon {:}**</span></span>|<span data-ttu-id="b53bc-127">Als Trennzeichen für Zeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="b53bc-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="b53bc-128">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-128">**Comma {,}**</span></span>|<span data-ttu-id="b53bc-129">Als Trennzeichen für Zeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="b53bc-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="b53bc-130">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-130">**Tab {t}**</span></span>|<span data-ttu-id="b53bc-131">Als Trennzeichen für Zeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="b53bc-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="b53bc-132">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="b53bc-133">Als Trennzeichen für Zeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="b53bc-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="b53bc-134">**Spaltentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="b53bc-134">**Column delimiter**</span></span>  
 <span data-ttu-id="b53bc-135">Wählen Sie aus der Liste verfügbarer Spaltentrennzeichen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="b53bc-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="b53bc-136">Wert</span><span class="sxs-lookup"><span data-stu-id="b53bc-136">Value</span></span>|<span data-ttu-id="b53bc-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b53bc-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b53bc-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-138">**{CR}{LF}**</span></span>|<span data-ttu-id="b53bc-139">Als Trennzeichen für Spalten dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="b53bc-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="b53bc-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-140">**{CR}**</span></span>|<span data-ttu-id="b53bc-141">Als Trennzeichen für Spalten dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="b53bc-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="b53bc-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-142">**{LF}**</span></span>|<span data-ttu-id="b53bc-143">Als Trennzeichen für Spalten dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="b53bc-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="b53bc-144">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-144">**Semicolon {;}**</span></span>|<span data-ttu-id="b53bc-145">Als Trennzeichen für Spalten dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="b53bc-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="b53bc-146">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-146">**Colon {:}**</span></span>|<span data-ttu-id="b53bc-147">Als Trennzeichen für Spalten dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="b53bc-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="b53bc-148">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-148">**Comma {,}**</span></span>|<span data-ttu-id="b53bc-149">Als Trennzeichen für Spalten dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="b53bc-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="b53bc-150">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-150">**Tab {t}**</span></span>|<span data-ttu-id="b53bc-151">Als Trennzeichen für Spalten dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="b53bc-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="b53bc-152">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="b53bc-153">Als Trennzeichen für Spalten dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="b53bc-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="b53bc-154">**Spalten zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="b53bc-154">**Reset Columns**</span></span>  
 <span data-ttu-id="b53bc-155">Entfernt alle bis auf die ursprünglichen Spalten, wenn Sie auf **Spalten zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="b53bc-155">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="b53bc-156">Format = Feste Breite</span><span class="sxs-lookup"><span data-stu-id="b53bc-156">Format = Fixed Width</span></span>  
 <span data-ttu-id="b53bc-157">**Schriftart**</span><span class="sxs-lookup"><span data-stu-id="b53bc-157">**Font**</span></span>  
 <span data-ttu-id="b53bc-158">Wählen Sie die Schriftart aus, in der die Vorschaudaten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b53bc-158">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="b53bc-159">**Quelldatenspalten**</span><span class="sxs-lookup"><span data-stu-id="b53bc-159">**Source data columns**</span></span>  
 <span data-ttu-id="b53bc-160">Passen Sie die Zeilenbreite an, indem Sie die vertikale Zeilenmarkierungslinie verschieben, und passen Sie die Spaltenbreite an, indem Sie auf das Lineal am oberen Rand des Vorschaufensters klicken.</span><span class="sxs-lookup"><span data-stu-id="b53bc-160">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="b53bc-161">**Zeilenbreite**</span><span class="sxs-lookup"><span data-stu-id="b53bc-161">**Row width**</span></span>  
 <span data-ttu-id="b53bc-162">Geben Sie erst die Länge der Zeile an, bevor Sie einzelnen Spalten Trennzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b53bc-162">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="b53bc-163">Sie können auch die vertikale Linie im Vorschaufenster verschieben, um das Zeilenende zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="b53bc-163">Or, drag the vertical line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="b53bc-164">Der Wert der Zeilenbreite wird automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="b53bc-164">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="b53bc-165">**Spalten zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="b53bc-165">**Reset Columns**</span></span>  
 <span data-ttu-id="b53bc-166">Entfernt alle bis auf die ursprünglichen Spalten, wenn Sie auf **Spalten zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="b53bc-166">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="b53bc-167">Format = Rechter Flatterrand</span><span class="sxs-lookup"><span data-stu-id="b53bc-167">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b53bc-168">Bei Dateien mit rechtem Flatterrand haben die Spalten mit Ausnahme der letzten Spalte eine feste Breite.</span><span class="sxs-lookup"><span data-stu-id="b53bc-168">Ragged right files are those in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="b53bc-169">Die Trennung der letzten Spalte erfolgt mit einem Zeilentrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="b53bc-169">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="b53bc-170">**Schriftart**</span><span class="sxs-lookup"><span data-stu-id="b53bc-170">**Font**</span></span>  
 <span data-ttu-id="b53bc-171">Wählen Sie die Schriftart aus, in der die Vorschaudaten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b53bc-171">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="b53bc-172">**Quelldatenspalten**</span><span class="sxs-lookup"><span data-stu-id="b53bc-172">**Source data columns**</span></span>  
 <span data-ttu-id="b53bc-173">Passen Sie die Zeilenbreite an, indem Sie die vertikale Zeilenmarkierungslinie verschieben, und passen Sie die Spaltenbreite an, indem Sie auf das Lineal am oberen Rand des Vorschaufensters klicken.</span><span class="sxs-lookup"><span data-stu-id="b53bc-173">Adjust the width of the row by sliding the vertical row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="b53bc-174">**Zeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="b53bc-174">**Row delimiter**</span></span>  
 <span data-ttu-id="b53bc-175">Wählen Sie aus der Liste verfügbarer Zeilentrennzeichen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="b53bc-175">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="b53bc-176">Wert</span><span class="sxs-lookup"><span data-stu-id="b53bc-176">Value</span></span>|<span data-ttu-id="b53bc-177">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b53bc-177">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b53bc-178">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-178">**{CR}{LF}**</span></span>|<span data-ttu-id="b53bc-179">Als Trennzeichen für Zeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="b53bc-179">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="b53bc-180">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-180">**{CR}**</span></span>|<span data-ttu-id="b53bc-181">Als Trennzeichen für Zeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="b53bc-181">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="b53bc-182">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-182">**{LF}**</span></span>|<span data-ttu-id="b53bc-183">Als Trennzeichen für Zeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="b53bc-183">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="b53bc-184">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-184">**Semicolon {;}**</span></span>|<span data-ttu-id="b53bc-185">Als Trennzeichen für Zeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="b53bc-185">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="b53bc-186">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-186">**Colon {:}**</span></span>|<span data-ttu-id="b53bc-187">Als Trennzeichen für Zeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="b53bc-187">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="b53bc-188">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-188">**Comma {,}**</span></span>|<span data-ttu-id="b53bc-189">Als Trennzeichen für Zeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="b53bc-189">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="b53bc-190">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-190">**Tab {t}**</span></span>|<span data-ttu-id="b53bc-191">Als Trennzeichen für Zeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="b53bc-191">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="b53bc-192">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="b53bc-192">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="b53bc-193">Als Trennzeichen für Zeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="b53bc-193">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="b53bc-194">**Spalten zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="b53bc-194">**Reset Columns**</span></span>  
 <span data-ttu-id="b53bc-195">Entfernt alle bis auf die ursprünglichen Spalten, wenn Sie auf **Spalten zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="b53bc-195">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b53bc-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b53bc-196">See Also</span></span>  
 <span data-ttu-id="b53bc-197">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b53bc-197">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b53bc-198">[Verbindungs-Manager-Editor für mehrere Flatfiles &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="b53bc-198">[Multiple Flat Files Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="b53bc-199">[Verbindungs-Manager-Editor für mehrere Flatfiles &#40;Seite "Erweitert"&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="b53bc-199">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="b53bc-200">Verbindungs-Manager-Editor für mehrere Flatfiles &#40;Seite „Vorschau“&#41;</span><span class="sxs-lookup"><span data-stu-id="b53bc-200">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
