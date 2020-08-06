---
title: Verbindungs-Manager-Editor für Flatfiles (Seite Spalten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.columns.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 40ce7537-abd0-4973-97fd-6ccb90fddfa0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6ce579f73922d2eaa2c48e98a98f52cd5836f5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609355"
---
# <a name="flat-file-connection-manager-editor-columns-page"></a><span data-ttu-id="bc20c-102">Verbindungs-Manager-Editor für Flatfiles (Seite Spalten)</span><span class="sxs-lookup"><span data-stu-id="bc20c-102">Flat File Connection Manager Editor (Columns Page)</span></span>
  <span data-ttu-id="bc20c-103">Verwenden Sie die Seite **Spalten** im Dialogfeld **Verbindungs-Manager-Editor für Flatfiles** , um die Zeilen- und Spalteninformationen anzugeben und eine Vorschau der Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc20c-103">Use the **Columns** page of the **Flat File Connection Manager Editor** dialog box to specify the row and column information, and to preview the file.</span></span>  
  
 <span data-ttu-id="bc20c-104">Weitere Informationen zum Verbindungs-Manager für Flatfiles finden Sie unter [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="bc20c-104">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="bc20c-105">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="bc20c-105">Static Options</span></span>  
 <span data-ttu-id="bc20c-106">**Name des Verbindungs-Managers**</span><span class="sxs-lookup"><span data-stu-id="bc20c-106">**Connection manager name**</span></span>  
 <span data-ttu-id="bc20c-107">Geben Sie einen eindeutigen Namen für die Flatfile-Verbindung im Workflow an.</span><span class="sxs-lookup"><span data-stu-id="bc20c-107">Provide a unique name for the Flat File connection in the workflow.</span></span> <span data-ttu-id="bc20c-108">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc20c-108">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="bc20c-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="bc20c-109">**Description**</span></span>  
 <span data-ttu-id="bc20c-110">Beschreiben Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="bc20c-110">Describe the connection.</span></span> <span data-ttu-id="bc20c-111">Es ist eine bewährte Methode, die Verbindung zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und einfacher zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="bc20c-111">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
## <a name="flat-file-format-dynamic-options"></a><span data-ttu-id="bc20c-112">Flatfileformat (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="bc20c-112">Flat File Format Dynamic Options</span></span>  
  
### <a name="format--delimited"></a><span data-ttu-id="bc20c-113">Format = Mit Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="bc20c-113">Format = Delimited</span></span>  
 <span data-ttu-id="bc20c-114">**Zeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-114">**Row delimiter**</span></span>  
 <span data-ttu-id="bc20c-115">Wählen Sie aus der Liste verfügbarer Zeilentrennzeichen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="bc20c-115">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="bc20c-116">Wert</span><span class="sxs-lookup"><span data-stu-id="bc20c-116">Value</span></span>|<span data-ttu-id="bc20c-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc20c-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc20c-118">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-118">**{CR}{LF}**</span></span>|<span data-ttu-id="bc20c-119">Als Trennzeichen für Zeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="bc20c-119">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="bc20c-120">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-120">**{CR}**</span></span>|<span data-ttu-id="bc20c-121">Als Trennzeichen für Zeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="bc20c-121">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="bc20c-122">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-122">**{LF}**</span></span>|<span data-ttu-id="bc20c-123">Als Trennzeichen für Zeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="bc20c-123">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="bc20c-124">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-124">**Semicolon {;}**</span></span>|<span data-ttu-id="bc20c-125">Als Trennzeichen für Zeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="bc20c-125">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="bc20c-126">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-126">**Colon {:}**</span></span>|<span data-ttu-id="bc20c-127">Als Trennzeichen für Zeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="bc20c-127">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="bc20c-128">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-128">**Comma {,}**</span></span>|<span data-ttu-id="bc20c-129">Als Trennzeichen für Zeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="bc20c-129">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="bc20c-130">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-130">**Tab {t}**</span></span>|<span data-ttu-id="bc20c-131">Als Trennzeichen für Zeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="bc20c-131">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="bc20c-132">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-132">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="bc20c-133">Als Trennzeichen für Zeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="bc20c-133">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="bc20c-134">**Spaltentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-134">**Column delimiter**</span></span>  
 <span data-ttu-id="bc20c-135">Wählen Sie aus der Liste verfügbarer Spaltentrennzeichen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="bc20c-135">Select from the list of available column delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="bc20c-136">Wert</span><span class="sxs-lookup"><span data-stu-id="bc20c-136">Value</span></span>|<span data-ttu-id="bc20c-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc20c-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc20c-138">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-138">**{CR}{LF}**</span></span>|<span data-ttu-id="bc20c-139">Als Trennzeichen für Spalten dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="bc20c-139">Columns are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="bc20c-140">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-140">**{CR}**</span></span>|<span data-ttu-id="bc20c-141">Als Trennzeichen für Spalten dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="bc20c-141">Columns are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="bc20c-142">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-142">**{LF}**</span></span>|<span data-ttu-id="bc20c-143">Als Trennzeichen für Spalten dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="bc20c-143">Columns are delimited by a line feed.</span></span>|  
|<span data-ttu-id="bc20c-144">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-144">**Semicolon {;}**</span></span>|<span data-ttu-id="bc20c-145">Als Trennzeichen für Spalten dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="bc20c-145">Columns are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="bc20c-146">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-146">**Colon {:}**</span></span>|<span data-ttu-id="bc20c-147">Als Trennzeichen für Spalten dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="bc20c-147">Columns are delimited by a colon.</span></span>|  
|<span data-ttu-id="bc20c-148">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-148">**Comma {,}**</span></span>|<span data-ttu-id="bc20c-149">Als Trennzeichen für Spalten dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="bc20c-149">Columns are delimited by a comma.</span></span>|  
|<span data-ttu-id="bc20c-150">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-150">**Tab {t}**</span></span>|<span data-ttu-id="bc20c-151">Als Trennzeichen für Spalten dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="bc20c-151">Columns are delimited by a tab.</span></span>|  
|<span data-ttu-id="bc20c-152">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-152">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="bc20c-153">Als Trennzeichen für Spalten dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="bc20c-153">Columns are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="bc20c-154">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="bc20c-154">**Refresh**</span></span>  
 <span data-ttu-id="bc20c-155">Zeigt durch Klicken auf **Aktualisieren**an, welche Auswirkung die Änderung der auszulassenden Trennzeichen hat.</span><span class="sxs-lookup"><span data-stu-id="bc20c-155">View the effect of changing the delimiters to skip by clicking **Refresh**.</span></span> <span data-ttu-id="bc20c-156">Diese Schaltfläche wird erst angezeigt, nachdem Sie andere Verbindungsoptionen geändert haben.</span><span class="sxs-lookup"><span data-stu-id="bc20c-156">This button only becomes visible after you have changed other connection options.</span></span>  
  
 <span data-ttu-id="bc20c-157">**Vorschau der Zeilen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-157">**Preview rows**</span></span>  
 <span data-ttu-id="bc20c-158">Zeigt Beispieldaten in der Flatfile an, die entsprechend den von Ihnen ausgewählten Optionen in Spalten und Zeilen unterteilt sind.</span><span class="sxs-lookup"><span data-stu-id="bc20c-158">View sample data in the flat file, divided into columns and rows by using the options selected.</span></span>  
  
 <span data-ttu-id="bc20c-159">**Spalten zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-159">**Reset Columns**</span></span>  
 <span data-ttu-id="bc20c-160">Entfernt alle bis auf die ursprünglichen Spalten, wenn Sie auf **Spalten zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="bc20c-160">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--fixed-width"></a><span data-ttu-id="bc20c-161">Format = Feste Breite</span><span class="sxs-lookup"><span data-stu-id="bc20c-161">Format = Fixed Width</span></span>  
 <span data-ttu-id="bc20c-162">**Schriftart**</span><span class="sxs-lookup"><span data-stu-id="bc20c-162">**Font**</span></span>  
 <span data-ttu-id="bc20c-163">Wählen Sie die Schriftart aus, in der die Vorschaudaten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc20c-163">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="bc20c-164">**Quelldatenspalten**</span><span class="sxs-lookup"><span data-stu-id="bc20c-164">**Source data columns**</span></span>  
 <span data-ttu-id="bc20c-165">Passen Sie die Zeilenbreite an, indem Sie die vertikale rote Zeilenmarkierungslinie verschieben, und passen Sie die Spaltenbreite an, indem Sie auf das Lineal am oberen Rand des Vorschaufensters klicken.</span><span class="sxs-lookup"><span data-stu-id="bc20c-165">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="bc20c-166">**Zeilenbreite**</span><span class="sxs-lookup"><span data-stu-id="bc20c-166">**Row width**</span></span>  
 <span data-ttu-id="bc20c-167">Geben Sie erst die Länge der Zeile an, bevor Sie einzelnen Spalten Trennzeichen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc20c-167">Specify the length of the row before adding delimiters for individual columns.</span></span> <span data-ttu-id="bc20c-168">Sie können auch die vertikale rote Linie im Vorschaufenster verschieben, um das Zeilenende zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="bc20c-168">Or, drag the vertical red line in the preview window to mark the end of the row.</span></span> <span data-ttu-id="bc20c-169">Der Wert der Zeilenbreite wird automatisch aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="bc20c-169">The row width value is automatically updated.</span></span>  
  
 <span data-ttu-id="bc20c-170">**Spalten zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-170">**Reset Columns**</span></span>  
 <span data-ttu-id="bc20c-171">Entfernt alle bis auf die ursprünglichen Spalten, wenn Sie auf **Spalten zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="bc20c-171">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
### <a name="format--ragged-right"></a><span data-ttu-id="bc20c-172">Format = Rechter Flatterrand</span><span class="sxs-lookup"><span data-stu-id="bc20c-172">Format = Ragged Right</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bc20c-173">Bei Dateien mit rechtem Flatterrand haben die Spalten mit Ausnahme der letzten Spalte eine feste Breite.</span><span class="sxs-lookup"><span data-stu-id="bc20c-173">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="bc20c-174">Die Trennung der letzten Spalte erfolgt mit einem Zeilentrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="bc20c-174">It is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="bc20c-175">**Schriftart**</span><span class="sxs-lookup"><span data-stu-id="bc20c-175">**Font**</span></span>  
 <span data-ttu-id="bc20c-176">Wählen Sie die Schriftart aus, in der die Vorschaudaten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc20c-176">Select the font in which to display the preview data.</span></span>  
  
 <span data-ttu-id="bc20c-177">**Quelldatenspalten**</span><span class="sxs-lookup"><span data-stu-id="bc20c-177">**Source data columns**</span></span>  
 <span data-ttu-id="bc20c-178">Passen Sie die Zeilenbreite an, indem Sie die vertikale rote Zeilenmarkierungslinie verschieben, und passen Sie die Spaltenbreite an, indem Sie auf das Lineal am oberen Rand des Vorschaufensters klicken.</span><span class="sxs-lookup"><span data-stu-id="bc20c-178">Adjust the width of the row by sliding the vertical red row marker, and adjust the width of the columns by clicking the ruler at the top of the preview window</span></span>  
  
 <span data-ttu-id="bc20c-179">**Zeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-179">**Row delimiter**</span></span>  
 <span data-ttu-id="bc20c-180">Wählen Sie aus der Liste verfügbarer Zeilentrennzeichen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="bc20c-180">Select from the list of available row delimiters, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="bc20c-181">Wert</span><span class="sxs-lookup"><span data-stu-id="bc20c-181">Value</span></span>|<span data-ttu-id="bc20c-182">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc20c-182">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bc20c-183">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-183">**{CR}{LF}**</span></span>|<span data-ttu-id="bc20c-184">Als Trennzeichen für Zeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="bc20c-184">Rows are delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="bc20c-185">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-185">**{CR}**</span></span>|<span data-ttu-id="bc20c-186">Als Trennzeichen für Zeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="bc20c-186">Rows are delimited by a carriage return.</span></span>|  
|<span data-ttu-id="bc20c-187">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-187">**{LF}**</span></span>|<span data-ttu-id="bc20c-188">Als Trennzeichen für Zeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="bc20c-188">Rows are delimited by a line feed.</span></span>|  
|<span data-ttu-id="bc20c-189">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-189">**Semicolon {;}**</span></span>|<span data-ttu-id="bc20c-190">Als Trennzeichen für Zeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="bc20c-190">Rows are delimited by a semicolon.</span></span>|  
|<span data-ttu-id="bc20c-191">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-191">**Colon {:}**</span></span>|<span data-ttu-id="bc20c-192">Als Trennzeichen für Zeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="bc20c-192">Rows are delimited by a colon.</span></span>|  
|<span data-ttu-id="bc20c-193">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-193">**Comma {,}**</span></span>|<span data-ttu-id="bc20c-194">Als Trennzeichen für Zeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="bc20c-194">Rows are delimited by a comma.</span></span>|  
|<span data-ttu-id="bc20c-195">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-195">**Tab {t}**</span></span>|<span data-ttu-id="bc20c-196">Als Trennzeichen für Zeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="bc20c-196">Rows are delimited by a tab.</span></span>|  
|<span data-ttu-id="bc20c-197">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="bc20c-197">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="bc20c-198">Als Trennzeichen für Zeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="bc20c-198">Rows are delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="bc20c-199">**Spalten zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="bc20c-199">**Reset Columns**</span></span>  
 <span data-ttu-id="bc20c-200">Entfernt alle bis auf die ursprünglichen Spalten, wenn Sie auf **Spalten zurücksetzen**klicken.</span><span class="sxs-lookup"><span data-stu-id="bc20c-200">Remove all but the original columns by clicking **Reset Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc20c-201">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc20c-201">See Also</span></span>  
 <span data-ttu-id="bc20c-202">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bc20c-202">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bc20c-203">[Verbindungs-Manager-Editor für Flatfiles &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="bc20c-203">[Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="bc20c-204">[Verbindungs-Manager-Editor für Flatfiles &#40;Seite Erweiterte Seite&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="bc20c-204">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="bc20c-205">Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Vorschau“&#41;</span><span class="sxs-lookup"><span data-stu-id="bc20c-205">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
