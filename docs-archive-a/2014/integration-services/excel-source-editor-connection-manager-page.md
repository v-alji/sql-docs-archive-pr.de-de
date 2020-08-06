---
title: Quellen-Editor für Excel (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.excelsourceadapter.connection.f1
helpviewer_keywords:
- Excel Source Editor
ms.assetid: 428e04e0-ad98-45d0-8345-12ec1b67b2eb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3285b5c8b14016b91005af79542e3e2f9b6559b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618795"
---
# <a name="excel-source-editor-connection-manager-page"></a><span data-ttu-id="268a6-102">Quellen-Editor für Excel (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="268a6-102">Excel Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="268a6-103">Mithilfe des Knotens **Verbindungs-Manager** im Dialogfeld **Quellen-Editor für Excel** können Sie eine [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] -Arbeitsmappe für die Quelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="268a6-103">Use the **Connection Manager** node of the **Excel Source Editor** dialog box to select the [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook for the source to use.</span></span> <span data-ttu-id="268a6-104">Die Excel-Quelle liest Daten aus einem Arbeitsblatt oder dem benannten Bereich einer vorhandenen Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="268a6-104">The Excel source reads data from a worksheet or named range in an existing workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="268a6-105">Die- `CommandTimeout` Eigenschaft der Excel-Quelle ist nicht im **Quellen-Editor für Excel**verfügbar, kann jedoch mit dem- **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="268a6-105">The `CommandTimeout` property of the Excel source is not available in the **Excel Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="268a6-106">Weitere Informationen zu dieser Eigenschaft finden Sie im Abschnitt Excel-Quelle von [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="268a6-106">For more information on this property, see the Excel Source section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="268a6-107">Weitere Informationen zur Excel-Quelle finden Sie unter [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="268a6-107">To learn more about the Excel source, see [Excel Source](data-flow/excel-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="268a6-108">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="268a6-108">Static Options</span></span>  
 <span data-ttu-id="268a6-109">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="268a6-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="268a6-110">Wählen Sie einen vorhandenen Excel-Verbindungs-Manager aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="268a6-110">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="268a6-111">**Neu**</span><span class="sxs-lookup"><span data-stu-id="268a6-111">**New**</span></span>  
 <span data-ttu-id="268a6-112">Erstellen Sie mithilfe des Dialogfelds **Excel-Verbindungs-Manager** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="268a6-112">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="268a6-113">**Datenzugriffsmodus**</span><span class="sxs-lookup"><span data-stu-id="268a6-113">**Data access mode**</span></span>  
 <span data-ttu-id="268a6-114">Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="268a6-114">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="268a6-115">Wert</span><span class="sxs-lookup"><span data-stu-id="268a6-115">Value</span></span>|<span data-ttu-id="268a6-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="268a6-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="268a6-117">Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="268a6-117">Table or view</span></span>|<span data-ttu-id="268a6-118">Ruft Daten aus einem Arbeitsblatt oder dem benannten Bereich einer Excel-Datei ab.</span><span class="sxs-lookup"><span data-stu-id="268a6-118">Retrieve data from a worksheet or named range in the Excel file.</span></span>|  
|<span data-ttu-id="268a6-119">Variable für Tabellenname oder Sichtname</span><span class="sxs-lookup"><span data-stu-id="268a6-119">Table name or view name variable</span></span>|<span data-ttu-id="268a6-120">Geben Sie den Namen des Arbeitsblatts oder Bereichs in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="268a6-120">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="268a6-121">**Verwandte Informationen**: [Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="268a6-121">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="268a6-122">SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="268a6-122">SQL command</span></span>|<span data-ttu-id="268a6-123">Ruft mithilfe einer SQL-Abfrage Daten aus einer Excel-Datei ab.</span><span class="sxs-lookup"><span data-stu-id="268a6-123">Retrieve data from the Excel file by using a SQL query.</span></span> <span data-ttu-id="268a6-124">Informationen zur Abfragesyntax finden Sie unter [Excel Source](data-flow/excel-source.md).</span><span class="sxs-lookup"><span data-stu-id="268a6-124">For information about query syntax, see [Excel Source](data-flow/excel-source.md).</span></span>|  
|<span data-ttu-id="268a6-125">SQL-Befehl aus Variable</span><span class="sxs-lookup"><span data-stu-id="268a6-125">SQL command from variable</span></span>|<span data-ttu-id="268a6-126">Gibt den SQL-Abfragetext in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="268a6-126">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="268a6-127">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="268a6-127">**Preview**</span></span>  
 <span data-ttu-id="268a6-128">Zeigen Sie mithilfe des Dialogfelds **Datenansicht** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="268a6-128">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="268a6-129">In der Vorschau können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="268a6-129">Preview can display up to 200 rows.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="268a6-130">Dynamische Optionen (Datenzugriffsmodus)</span><span class="sxs-lookup"><span data-stu-id="268a6-130">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="268a6-131">Datenzugriffsmodus = Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="268a6-131">Data access mode = Table or view</span></span>  
 <span data-ttu-id="268a6-132">**Name der Excel-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="268a6-132">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="268a6-133">Wählen Sie in der Liste der in der Excel-Arbeitsmappe verfügbaren Objekte den Namen des Arbeitsblatts oder des benannten Bereichs aus.</span><span class="sxs-lookup"><span data-stu-id="268a6-133">Select the name of the worksheet or named range from a list of those available in the Excel workbook.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="268a6-134">Datenzugriffsmodus = Variable für Tabellenname oder Sichtname</span><span class="sxs-lookup"><span data-stu-id="268a6-134">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="268a6-135">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="268a6-135">**Variable name**</span></span>  
 <span data-ttu-id="268a6-136">Wählen Sie die Variable aus, die den Namen des Arbeitsblatts oder des benannten Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="268a6-136">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="268a6-137">Datenzugriffsmodus = SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="268a6-137">Data access mode = SQL command</span></span>  
 <span data-ttu-id="268a6-138">**SQL-Befehlstext**</span><span class="sxs-lookup"><span data-stu-id="268a6-138">**SQL command text**</span></span>  
 <span data-ttu-id="268a6-139">Geben Sie den Text der SQL-Abfrage ein, und erstellen Sie die Abfrage, indem Sie auf **Abfrage erstellen**klicken. Wahlweise können Sie auch nach der Datei mit dem Abfragetext suchen, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="268a6-139">Enter the text of a SQL query, build the query by clicking **Build Query**, or browse to the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="268a6-140">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="268a6-140">**Parameters**</span></span>  
 <span data-ttu-id="268a6-141">Wenn Sie eine parametrisierte Abfrage eingeben und im Abfragetext ?</span><span class="sxs-lookup"><span data-stu-id="268a6-141">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="268a6-142">als Parameterplatzhalter verwenden, können Sie den Paketvariablen mithilfe des Dialogfelds **Abfrageparameter festlegen** Abfrageeingabeparameter zuordnen.</span><span class="sxs-lookup"><span data-stu-id="268a6-142">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="268a6-143">**Abfrage erstellen**</span><span class="sxs-lookup"><span data-stu-id="268a6-143">**Build query**</span></span>  
 <span data-ttu-id="268a6-144">Mithilfe des Dialogfelds **Abfrage-Generator** können Sie die SQL-Abfrage visuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="268a6-144">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="268a6-145">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="268a6-145">**Browse**</span></span>  
 <span data-ttu-id="268a6-146">Mithilfe des Dialogfelds **Öffnen** können Sie nach der Datei suchen, die den Text der SQL-Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="268a6-146">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="268a6-147">**Abfrage analysieren**</span><span class="sxs-lookup"><span data-stu-id="268a6-147">**Parse query**</span></span>  
 <span data-ttu-id="268a6-148">Überprüft die Syntax des Abfragetexts.</span><span class="sxs-lookup"><span data-stu-id="268a6-148">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="268a6-149">Datenzugriffsmodus = SQL-Befehl aus Variable</span><span class="sxs-lookup"><span data-stu-id="268a6-149">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="268a6-150">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="268a6-150">**Variable name**</span></span>  
 <span data-ttu-id="268a6-151">Wählen Sie die Variable aus, die den Text für die SQL-Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="268a6-151">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268a6-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="268a6-152">See Also</span></span>  
 <span data-ttu-id="268a6-153">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="268a6-153">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="268a6-154">[Der Quellen-Editor für Excel &#40;Spalten&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="268a6-154">[Excel Source Editor &#40;Columns Page&#41;](../../2014/integration-services/excel-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="268a6-155">[Quellen-Editor für Excel &#40;Seite Fehlerausgabe&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="268a6-155">[Excel Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="268a6-156">[Excel-Verbindungs-Manager](connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="268a6-156">[Excel Connection Manager](connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="268a6-157">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="268a6-157">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
