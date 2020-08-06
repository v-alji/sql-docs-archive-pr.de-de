---
title: Verbindungs-Manager-Editor für mehrere Flatfiles (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.multifile.general.f1
helpviewer_keywords:
- Multiple Flat Files Connection Manager Editor
ms.assetid: 00129d43-2772-413b-bdf8-ac5de81cf4a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f30a422794723f216d30e05f0750fb1e974e0920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721581"
---
# <a name="multiple-flat-files-connection-manager-editor-general-page"></a><span data-ttu-id="9f21a-102">Verbindungs-Manager-Editor für mehrere Flatfiles (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="9f21a-102">Multiple Flat Files Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="9f21a-103">Um eine Gruppe von Dateien im selben Datenformat auszuwählen und das entsprechende Datenformat anzugeben, verwenden Sie im Dialogfeld **Verbindungs-Manager-Editor für mehrere Flatfiles** die Seite **Allgemein** .</span><span class="sxs-lookup"><span data-stu-id="9f21a-103">Use the **General** page of the **Multiple Flat Files Connection Manager Editor** dialog box to select a group of files that have the same data format, and to specify their data format.</span></span> <span data-ttu-id="9f21a-104">Durch eine Verbindung für mehrere Flatfiles kann von einem Paket eine Verbindung zu einer Gruppe von Textdateien im selben Format hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9f21a-104">A multiple flat files connection enables a package to connect to a group of text files that have the same format.</span></span>  
  
 <span data-ttu-id="9f21a-105">Weitere Informationen zum Verbindungs-Manager für mehrere Flatfiles finden Sie unter [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="9f21a-105">To learn more about the Multiple Flat Files connection manager, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9f21a-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="9f21a-106">Options</span></span>  
 <span data-ttu-id="9f21a-107">**Name des Verbindungs-Managers**</span><span class="sxs-lookup"><span data-stu-id="9f21a-107">**Connection manager name**</span></span>  
 <span data-ttu-id="9f21a-108">Geben Sie einen eindeutigen Namen für die Verbindung für mehrere Flatfiles im Workflow an.</span><span class="sxs-lookup"><span data-stu-id="9f21a-108">Provide a unique name for the Multiple Flat Files connection in the workflow.</span></span> <span data-ttu-id="9f21a-109">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f21a-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="9f21a-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9f21a-110">**Description**</span></span>  
 <span data-ttu-id="9f21a-111">Beschreiben Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="9f21a-111">Describe the connection.</span></span> <span data-ttu-id="9f21a-112">Es ist eine bewährte Methode, die Verbindung zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und einfacher zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="9f21a-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="9f21a-113">**Dateinamen**</span><span class="sxs-lookup"><span data-stu-id="9f21a-113">**File names**</span></span>  
 <span data-ttu-id="9f21a-114">Geben Sie den Pfad und den Dateinamen ein, die für die Verbindung für mehrere Flatfiles verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-114">Type the path and file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="9f21a-115">Verwenden Sie zum Angeben mehrerer Dateien Platzhalterzeichen, wie in „C:\\*.txt“, oder verwenden Sie den senkrechten Strich (|), um die verschiedenen angegebenen Dateinamen voneinander zu trennen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-115">You can specify multiple files by using wildcard characters, as in the example "C:\\*.txt", or by using the vertical pipe character (|) to separate multiple file names.</span></span> <span data-ttu-id="9f21a-116">Alle Dateien müssen dasselbe Datenformat aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-116">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="9f21a-117">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="9f21a-117">**Browse**</span></span>  
 <span data-ttu-id="9f21a-118">Wechseln Sie in das Verzeichnis mit den Dateinamen, die bei der Verbindung für mehrere Flatfiles verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-118">Browse the file names to use in the Multiple Flat Files connection.</span></span> <span data-ttu-id="9f21a-119">Sie können mehrere Dateien auswählen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-119">You can select multiple files.</span></span> <span data-ttu-id="9f21a-120">Alle Dateien müssen dasselbe Datenformat aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-120">All files must have the same data format.</span></span>  
  
 <span data-ttu-id="9f21a-121">**Gebietsschema**</span><span class="sxs-lookup"><span data-stu-id="9f21a-121">**Locale**</span></span>  
 <span data-ttu-id="9f21a-122">Geben Sie den Ort an, um Informationen zu Bestellungen und zur Datums- und Zeitkonvertierung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-122">Specify the location to provide information for ordering and for date and time conversion.</span></span>  
  
 <span data-ttu-id="9f21a-123">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="9f21a-123">**Unicode**</span></span>  
 <span data-ttu-id="9f21a-124">Gibt an, ob Unicode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f21a-124">Indicate whether to use Unicode.</span></span> <span data-ttu-id="9f21a-125">Bei Verwendung von Unicode wird keine Codepage angegeben.</span><span class="sxs-lookup"><span data-stu-id="9f21a-125">Using Unicode precludes specifying a code page.</span></span>  
  
 <span data-ttu-id="9f21a-126">**Codepage**</span><span class="sxs-lookup"><span data-stu-id="9f21a-126">**Code page**</span></span>  
 <span data-ttu-id="9f21a-127">Gibt die Codepage für Nicht-Unicode-Text an.</span><span class="sxs-lookup"><span data-stu-id="9f21a-127">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="9f21a-128">**Format**</span><span class="sxs-lookup"><span data-stu-id="9f21a-128">**Format**</span></span>  
 <span data-ttu-id="9f21a-129">Gibt an, ob die Datei Formatierung mit Trennzeichen, fester Breite oder rechtem Flatterrand verwendet.</span><span class="sxs-lookup"><span data-stu-id="9f21a-129">Indicate whether to use delimited, fixed width, or ragged right formatting.</span></span> <span data-ttu-id="9f21a-130">Alle Dateien müssen dasselbe Datenformat aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9f21a-130">All files must have the same data format.</span></span>  
  
|<span data-ttu-id="9f21a-131">Wert</span><span class="sxs-lookup"><span data-stu-id="9f21a-131">Value</span></span>|<span data-ttu-id="9f21a-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f21a-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9f21a-133">Durch Trennzeichen getrennt</span><span class="sxs-lookup"><span data-stu-id="9f21a-133">Delimited</span></span>|<span data-ttu-id="9f21a-134">Die Trennung von Spalten erfolgt durch Trennzeichen. Welche Trennzeichen dies sind, wird auf der Seite **Spalten** angegeben.</span><span class="sxs-lookup"><span data-stu-id="9f21a-134">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="9f21a-135">Feste Breite</span><span class="sxs-lookup"><span data-stu-id="9f21a-135">Fixed width</span></span>|<span data-ttu-id="9f21a-136">Die Spalten weisen eine feste Breite auf, die auf der Seite **Spalten** durch Ziehen der Markierungslinien angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9f21a-136">Columns have a fixed width, specified by dragging marker lines on the **Columns** page.</span></span>|  
|<span data-ttu-id="9f21a-137">Rechter Flatterrand</span><span class="sxs-lookup"><span data-stu-id="9f21a-137">Ragged right</span></span>|<span data-ttu-id="9f21a-138">Bei Dateien mit rechtem Flatterrand weisen alle Spalten mit Ausnahme der letzten eine feste Breite auf. Die letzte Spalte wird durch das auf der Seite **Spalten** angegebene Zeilentrennzeichen begrenzt.</span><span class="sxs-lookup"><span data-stu-id="9f21a-138">Ragged right files are files in which every column has a fixed width, except for the last column, which is delimited by the row delimiter, specified on the **Columns** page.</span></span>|  
  
 <span data-ttu-id="9f21a-139">**Textqualifizierer**</span><span class="sxs-lookup"><span data-stu-id="9f21a-139">**Text qualifier**</span></span>  
 <span data-ttu-id="9f21a-140">Gibt die zu verwendenden Textqualifizierer an.</span><span class="sxs-lookup"><span data-stu-id="9f21a-140">Specify the text qualifier to use.</span></span> <span data-ttu-id="9f21a-141">Sie können beispielsweise angeben, dass Text in Anführungszeichen eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9f21a-141">For example, you can specify to enclose text with quotation marks.</span></span>  
  
 <span data-ttu-id="9f21a-142">**Kopfzeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="9f21a-142">**Header row delimiter**</span></span>  
 <span data-ttu-id="9f21a-143">Wählen Sie aus einer Liste mit Trennzeichen für Kopfzeilen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="9f21a-143">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="9f21a-144">Wert</span><span class="sxs-lookup"><span data-stu-id="9f21a-144">Value</span></span>|<span data-ttu-id="9f21a-145">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9f21a-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9f21a-146">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-146">**{CR}{LF}**</span></span>|<span data-ttu-id="9f21a-147">Als Trennzeichen für Kopfzeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="9f21a-147">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="9f21a-148">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-148">**{CR}**</span></span>|<span data-ttu-id="9f21a-149">Als Trennzeichen für Kopfzeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="9f21a-149">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="9f21a-150">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-150">**{LF}**</span></span>|<span data-ttu-id="9f21a-151">Als Trennzeichen für Kopfzeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="9f21a-151">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="9f21a-152">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-152">**Semicolon {;}**</span></span>|<span data-ttu-id="9f21a-153">Als Trennzeichen für Kopfzeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="9f21a-153">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="9f21a-154">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-154">**Colon {:}**</span></span>|<span data-ttu-id="9f21a-155">Als Trennzeichen für Kopfzeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="9f21a-155">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="9f21a-156">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-156">**Comma {,}**</span></span>|<span data-ttu-id="9f21a-157">Als Trennzeichen für Kopfzeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="9f21a-157">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="9f21a-158">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-158">**Tab {t}**</span></span>|<span data-ttu-id="9f21a-159">Als Trennzeichen für Kopfzeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="9f21a-159">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="9f21a-160">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="9f21a-160">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="9f21a-161">Als Trennzeichen für Kopfzeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="9f21a-161">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="9f21a-162">**Auszulassende Kopfzeilen**</span><span class="sxs-lookup"><span data-stu-id="9f21a-162">**Header rows to skip**</span></span>  
 <span data-ttu-id="9f21a-163">Geben Sie nach Möglichkeit die Anzahl der auszulassenden Kopfzeilen an.</span><span class="sxs-lookup"><span data-stu-id="9f21a-163">Specify the number of header rows to skip, if any.</span></span>  
  
 <span data-ttu-id="9f21a-164">**Spaltennamen in der ersten Datenzeile**</span><span class="sxs-lookup"><span data-stu-id="9f21a-164">**Column names in the first data row**</span></span>  
 <span data-ttu-id="9f21a-165">Gibt an, ob in der ersten Datenzeile Spaltennamen erwartet werden bzw. bereitzustellen sind.</span><span class="sxs-lookup"><span data-stu-id="9f21a-165">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f21a-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9f21a-166">See Also</span></span>  
 <span data-ttu-id="9f21a-167">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9f21a-167">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="9f21a-168">[Verbindungs-Manager-Editor für mehrere Flatfiles &#40;Seite Spalten&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="9f21a-168">[Multiple Flat Files Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="9f21a-169">[Verbindungs-Manager-Editor für mehrere Flatfiles &#40;Seite "Erweitert"&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="9f21a-169">[Multiple Flat Files Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/multiple-flat-files-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="9f21a-170">Verbindungs-Manager-Editor für mehrere Flatfiles &#40;Seite „Vorschau“&#41;</span><span class="sxs-lookup"><span data-stu-id="9f21a-170">Multiple Flat Files Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/multiple-flat-files-connection-manager-editor-preview-page.md)  
  
  
