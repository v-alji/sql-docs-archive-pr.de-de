---
title: Verbindungs-Manager-Editor für Flatfiles (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ffileconnection.general.f1
helpviewer_keywords:
- Flat File Connection Manager Editor
ms.assetid: 77296024-5c1a-4f6a-9665-0b50d45d744c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 478c7bcf56e300b47af93862bf66409a3c94b5f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609357"
---
# <a name="flat-file-connection-manager-editor-general-page"></a><span data-ttu-id="122ea-102">Verbindungs-Manager-Editor für Flatfiles (Seite Allgemein)</span><span class="sxs-lookup"><span data-stu-id="122ea-102">Flat File Connection Manager Editor (General Page)</span></span>
  <span data-ttu-id="122ea-103">Auf der Seite **Allgemein** des Dialogfelds **Verbindungs-Manager-Editor für Flatfiles** wählen Sie eine Datei und ein Dateiformat aus.</span><span class="sxs-lookup"><span data-stu-id="122ea-103">Use the **General** page of the **Flat File Connection Manager Editor** dialog box to select a file and data format.</span></span> <span data-ttu-id="122ea-104">Eine Flatfileverbindung ermöglicht das Herstellen einer Verbindung von einem Paket zu einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="122ea-104">A flat file connection enables a package to connect to a text file.</span></span>  
  
 <span data-ttu-id="122ea-105">Weitere Informationen zum Verbindungs-Manager für Flatfiles finden Sie unter [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="122ea-105">To learn more about the Flat File connection manager, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="122ea-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="122ea-106">Options</span></span>  
 <span data-ttu-id="122ea-107">**Name des Verbindungs-Managers**</span><span class="sxs-lookup"><span data-stu-id="122ea-107">**Connection manager name**</span></span>  
 <span data-ttu-id="122ea-108">Geben Sie einen eindeutigen Namen für die Flatfileverbindung im Workflow an.</span><span class="sxs-lookup"><span data-stu-id="122ea-108">Provide a unique name for the flat file connection in the workflow.</span></span> <span data-ttu-id="122ea-109">Der angegebene Name wird im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="122ea-109">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="122ea-110">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="122ea-110">**Description**</span></span>  
 <span data-ttu-id="122ea-111">Beschreiben Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="122ea-111">Describe the connection.</span></span> <span data-ttu-id="122ea-112">Es ist eine bewährte Methode, die Verbindung zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und einfacher zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="122ea-112">As a best practice, describe the connection in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="122ea-113">**Dateiname**</span><span class="sxs-lookup"><span data-stu-id="122ea-113">**File name**</span></span>  
 <span data-ttu-id="122ea-114">Geben Sie den Pfad und den Dateinamen ein, die für die Flatfileverbindung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="122ea-114">Type the path and file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="122ea-115">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="122ea-115">**Browse**</span></span>  
 <span data-ttu-id="122ea-116">Suchen Sie den Dateinamen, der für die Flatfileverbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="122ea-116">Locate the file name to use in the flat file connection.</span></span>  
  
 <span data-ttu-id="122ea-117">**Gebietsschema**</span><span class="sxs-lookup"><span data-stu-id="122ea-117">**Locale**</span></span>  
 <span data-ttu-id="122ea-118">Gibt das Gebietsschema für die Bereitstellung sprachspezifischer Informationen für das Bestellen sowie für Datums- und Zeitformate an.</span><span class="sxs-lookup"><span data-stu-id="122ea-118">Specify the locale to provide language-specific information for ordering and for date and time formats.</span></span>  
  
 <span data-ttu-id="122ea-119">**Unicode**</span><span class="sxs-lookup"><span data-stu-id="122ea-119">**Unicode**</span></span>  
 <span data-ttu-id="122ea-120">Gibt an, ob Unicode verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="122ea-120">Indicate whether to use Unicode.</span></span> <span data-ttu-id="122ea-121">Wenn Sie Unicode verwenden, können Sie keine Codepage angeben.</span><span class="sxs-lookup"><span data-stu-id="122ea-121">If you use Unicode, you cannot specify a code page.</span></span>  
  
 <span data-ttu-id="122ea-122">**Codepage**</span><span class="sxs-lookup"><span data-stu-id="122ea-122">**Code page**</span></span>  
 <span data-ttu-id="122ea-123">Gibt die Codepage für Nicht-Unicode-Text an.</span><span class="sxs-lookup"><span data-stu-id="122ea-123">Specify the code page for non-Unicode text.</span></span>  
  
 <span data-ttu-id="122ea-124">**Format**</span><span class="sxs-lookup"><span data-stu-id="122ea-124">**Format**</span></span>  
 <span data-ttu-id="122ea-125">Gibt an, ob die Datei Formatierung mit Trennzeichen, fester Breite oder rechtem Flatterrand verwendet.</span><span class="sxs-lookup"><span data-stu-id="122ea-125">Indicate whether the file uses delimited, fixed width, or ragged right formatting.</span></span>  
  
|<span data-ttu-id="122ea-126">Wert</span><span class="sxs-lookup"><span data-stu-id="122ea-126">Value</span></span>|<span data-ttu-id="122ea-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="122ea-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="122ea-128">Durch Trennzeichen getrennt</span><span class="sxs-lookup"><span data-stu-id="122ea-128">Delimited</span></span>|<span data-ttu-id="122ea-129">Die Trennung von Spalten erfolgt durch Trennzeichen. Welche Trennzeichen dies sind, wird auf der Seite **Spalten** angegeben.</span><span class="sxs-lookup"><span data-stu-id="122ea-129">Columns are separated by delimiters, specified on the **Columns** page.</span></span>|  
|<span data-ttu-id="122ea-130">Feste Breite</span><span class="sxs-lookup"><span data-stu-id="122ea-130">Fixed width</span></span>|<span data-ttu-id="122ea-131">Spalten haben eine feste Breite.</span><span class="sxs-lookup"><span data-stu-id="122ea-131">Columns have a fixed width.</span></span>|  
|<span data-ttu-id="122ea-132">Rechter Flatterrand</span><span class="sxs-lookup"><span data-stu-id="122ea-132">Ragged right</span></span>|<span data-ttu-id="122ea-133">Bei Dateien mit rechtem Flatterrand haben die Spalten mit Ausnahme der letzten Spalte eine feste Breite.</span><span class="sxs-lookup"><span data-stu-id="122ea-133">Ragged right files are files in which every column has a fixed width, except for the last column.</span></span> <span data-ttu-id="122ea-134">Die Trennung der letzten Spalte erfolgt mit einem Zeilentrennzeichen.</span><span class="sxs-lookup"><span data-stu-id="122ea-134">It is delimited by the row delimiter.</span></span>|  
  
 <span data-ttu-id="122ea-135">**Textqualifizierer**</span><span class="sxs-lookup"><span data-stu-id="122ea-135">**Text qualifier**</span></span>  
 <span data-ttu-id="122ea-136">Gibt die zu verwendenden Textqualifizierer an.</span><span class="sxs-lookup"><span data-stu-id="122ea-136">Specify the text qualifier to use.</span></span> <span data-ttu-id="122ea-137">So können Sie beispielsweise angeben, dass Textfelder in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="122ea-137">For example, you can specify that text fields are enclosed in quotation marks.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="122ea-138">Nachdem Sie einen Textqualifizierer ausgewählt haben, können Sie die Option **Keine** nicht erneut auswählen.</span><span class="sxs-lookup"><span data-stu-id="122ea-138">After you select a text qualifier, you cannot re-select the **None** option.</span></span> <span data-ttu-id="122ea-139">Geben Sie **Keine** ein, um die Auswahl des Textqualifizierers aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="122ea-139">Type **None** to de-select the text qualifier.</span></span>  
  
 <span data-ttu-id="122ea-140">**Kopfzeilentrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="122ea-140">**Header row delimiter**</span></span>  
 <span data-ttu-id="122ea-141">Wählen Sie aus einer Liste mit Trennzeichen für Kopfzeilen ein Trennzeichen aus, oder geben Sie den Trennzeichentext ein.</span><span class="sxs-lookup"><span data-stu-id="122ea-141">Select from the list of delimiters for header rows, or enter the delimiter text.</span></span>  
  
|<span data-ttu-id="122ea-142">Wert</span><span class="sxs-lookup"><span data-stu-id="122ea-142">Value</span></span>|<span data-ttu-id="122ea-143">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="122ea-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="122ea-144">**{CR}{LF}**</span><span class="sxs-lookup"><span data-stu-id="122ea-144">**{CR}{LF}**</span></span>|<span data-ttu-id="122ea-145">Als Trennzeichen für Kopfzeilen dient ein Wagenrücklauf in Kombination mit einem Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="122ea-145">The header row is delimited by a carriage return-line feed combination.</span></span>|  
|<span data-ttu-id="122ea-146">**{CR}**</span><span class="sxs-lookup"><span data-stu-id="122ea-146">**{CR}**</span></span>|<span data-ttu-id="122ea-147">Als Trennzeichen für Kopfzeilen dient ein Wagenrücklauf.</span><span class="sxs-lookup"><span data-stu-id="122ea-147">The header row is delimited by a carriage return.</span></span>|  
|<span data-ttu-id="122ea-148">**{LF}**</span><span class="sxs-lookup"><span data-stu-id="122ea-148">**{LF}**</span></span>|<span data-ttu-id="122ea-149">Als Trennzeichen für Kopfzeilen dient ein Zeilenvorschub.</span><span class="sxs-lookup"><span data-stu-id="122ea-149">The header row is delimited by a line feed.</span></span>|  
|<span data-ttu-id="122ea-150">**Semikolon {;}**</span><span class="sxs-lookup"><span data-stu-id="122ea-150">**Semicolon {;}**</span></span>|<span data-ttu-id="122ea-151">Als Trennzeichen für Kopfzeilen dient ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="122ea-151">The header row is delimited by a semicolon.</span></span>|  
|<span data-ttu-id="122ea-152">**Doppelpunkt {:}**</span><span class="sxs-lookup"><span data-stu-id="122ea-152">**Colon {:}**</span></span>|<span data-ttu-id="122ea-153">Als Trennzeichen für Kopfzeilen dient ein Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="122ea-153">The header row is delimited by a colon.</span></span>|  
|<span data-ttu-id="122ea-154">**Komma {,}**</span><span class="sxs-lookup"><span data-stu-id="122ea-154">**Comma {,}**</span></span>|<span data-ttu-id="122ea-155">Als Trennzeichen für Kopfzeilen dient ein Komma.</span><span class="sxs-lookup"><span data-stu-id="122ea-155">The header row is delimited by a comma.</span></span>|  
|<span data-ttu-id="122ea-156">**Tabulator {t}**</span><span class="sxs-lookup"><span data-stu-id="122ea-156">**Tab {t}**</span></span>|<span data-ttu-id="122ea-157">Als Trennzeichen für Kopfzeilen dient ein Tabulator.</span><span class="sxs-lookup"><span data-stu-id="122ea-157">The header row is delimited by a tab.</span></span>|  
|<span data-ttu-id="122ea-158">**Senkrechter Strich {&#124;}**</span><span class="sxs-lookup"><span data-stu-id="122ea-158">**Vertical bar {&#124;}**</span></span>|<span data-ttu-id="122ea-159">Als Trennzeichen für Kopfzeilen dient ein senkrechter Strich.</span><span class="sxs-lookup"><span data-stu-id="122ea-159">The header row is delimited by a vertical bar.</span></span>|  
  
 <span data-ttu-id="122ea-160">**Auszulassende Kopfzeilen**</span><span class="sxs-lookup"><span data-stu-id="122ea-160">**Header rows to skip**</span></span>  
 <span data-ttu-id="122ea-161">Gibt an, wie viele Kopfzeilen bzw. erste Datenzeilen ggf. ausgelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="122ea-161">Specify the number of header rows or initial data rows to skip, if any.</span></span>  
  
 <span data-ttu-id="122ea-162">**Spaltennamen in der ersten Datenzeile**</span><span class="sxs-lookup"><span data-stu-id="122ea-162">**Column names in the first data row**</span></span>  
 <span data-ttu-id="122ea-163">Gibt an, ob in der ersten Datenzeile Spaltennamen erwartet werden bzw. bereitzustellen sind.</span><span class="sxs-lookup"><span data-stu-id="122ea-163">Indicate whether to expect or provide column names in the first data row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122ea-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="122ea-164">See Also</span></span>  
 <span data-ttu-id="122ea-165">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="122ea-165">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="122ea-166">[Verbindungs-Manager-Editor für Flatfiles &#40;Seite Spalten&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="122ea-166">[Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md) </span></span>  
 <span data-ttu-id="122ea-167">[Verbindungs-Manager-Editor für Flatfiles &#40;Seite Erweiterte Seite&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="122ea-167">[Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="122ea-168">Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Vorschau“&#41;</span><span class="sxs-lookup"><span data-stu-id="122ea-168">Flat File Connection Manager Editor &#40;Preview Page&#41;</span></span>](../../2014/integration-services/flat-file-connection-manager-editor-preview-page.md)  
  
  
