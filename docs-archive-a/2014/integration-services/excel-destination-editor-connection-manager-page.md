---
title: Ziel-Editor für Excel (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldestadapter.connection.f1
helpviewer_keywords:
- Excel Destination Editor
ms.assetid: fc13f725-963c-488e-91e2-20627133e842
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1556bf713c49aac31f1cc1cd624336f10dbf832f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618811"
---
# <a name="excel-destination-editor-connection-manager-page"></a><span data-ttu-id="4d008-102">Ziel-Editor für Excel (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="4d008-102">Excel Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="4d008-103">Mithilfe der Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für Excel** können Sie Informationen zur Datenquelle angeben und eine Vorschau der Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4d008-103">Use the **Connection Manager** page of the **Excel Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="4d008-104">Das Excel-Ziel lädt Daten in ein Arbeitsblatt oder einen benannten Bereich einer [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] -Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="4d008-104">The Excel destination loads data into a worksheet or a named range in a [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] workbook.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d008-105">Die- `CommandTimeout` Eigenschaft des Excel-Ziels ist nicht im **Ziel-Editor für Excel**verfügbar, kann jedoch mit dem- **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4d008-105">The `CommandTimeout` property of the Excel destination is not available in the **Excel Destination Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="4d008-106">Außerdem sind bestimmte Optionen für schnelles Laden nur in der **Erweiterter Editor**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4d008-106">In addition, certain Fast Load options are available only in the **Advanced Editor**.</span></span> <span data-ttu-id="4d008-107">Weitere Informationen zu diesen Eigenschaften finden Sie im Abschnitt Excel-Ziel von [Excel Custom Properties](data-flow/excel-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4d008-107">For more information on these properties, see the Excel Destination section of [Excel Custom Properties](data-flow/excel-custom-properties.md).</span></span>  
  
 <span data-ttu-id="4d008-108">Weitere Informationen zum Excel-Ziel finden Sie unter [Excel Destination](data-flow/excel-destination.md).</span><span class="sxs-lookup"><span data-stu-id="4d008-108">To learn more about the Excel destination, see [Excel Destination](data-flow/excel-destination.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="4d008-109">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="4d008-109">Static Options</span></span>  
 <span data-ttu-id="4d008-110">**Excel-Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="4d008-110">**Excel connection manager**</span></span>  
 <span data-ttu-id="4d008-111">Wählen Sie einen vorhandenen Excel-Verbindungs-Manager aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="4d008-111">Select an existing Excel connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="4d008-112">**Neu**</span><span class="sxs-lookup"><span data-stu-id="4d008-112">**New**</span></span>  
 <span data-ttu-id="4d008-113">Erstellen Sie mithilfe des Dialogfelds **Excel-Verbindungs-Manager** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="4d008-113">Create a new connection manager by using the **Excel Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="4d008-114">**Datenzugriffsmodus**</span><span class="sxs-lookup"><span data-stu-id="4d008-114">**Data access mode**</span></span>  
 <span data-ttu-id="4d008-115">Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="4d008-115">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="4d008-116">Option</span><span class="sxs-lookup"><span data-stu-id="4d008-116">Option</span></span>|<span data-ttu-id="4d008-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d008-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4d008-118">Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="4d008-118">Table or view</span></span>|<span data-ttu-id="4d008-119">Lädt Daten aus einem Arbeitsblatt oder dem benannten Bereich einer Excel-Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="4d008-119">Loads data into a worksheet or named range in the Excel data source.</span></span>|  
|<span data-ttu-id="4d008-120">Variable für Tabellenname oder Sichtname</span><span class="sxs-lookup"><span data-stu-id="4d008-120">Table name or view name variable</span></span>|<span data-ttu-id="4d008-121">Geben Sie den Namen des Arbeitsblatts oder Bereichs in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="4d008-121">Specify the worksheet or range name in a variable.</span></span><br /><br /> <span data-ttu-id="4d008-122">**Verwandte Informationen**: [Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="4d008-122">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="4d008-123">SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="4d008-123">SQL command</span></span>|<span data-ttu-id="4d008-124">Lädt Daten mithilfe einer SQL-Abfrage in das Excel-Ziel.</span><span class="sxs-lookup"><span data-stu-id="4d008-124">Load data into the Excel destination by using an SQL query.</span></span>|  
  
 <span data-ttu-id="4d008-125">**Name der Excel-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="4d008-125">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="4d008-126">Wählen Sie in der Dropdownliste das Excel-Ziel aus.</span><span class="sxs-lookup"><span data-stu-id="4d008-126">Select the excel destination from the drop-down list.</span></span> <span data-ttu-id="4d008-127">Wenn die Liste leer ist, klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="4d008-127">If the list is empty, click **New**.</span></span>  
  
 <span data-ttu-id="4d008-128">**Neu**</span><span class="sxs-lookup"><span data-stu-id="4d008-128">**New**</span></span>  
 <span data-ttu-id="4d008-129">Klicken Sie auf **Neu** , um das Dialogfeld **Tabelle erstellen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4d008-129">Click **New** to launch the **Create Table** dialog box.</span></span> <span data-ttu-id="4d008-130">Wenn Sie auf **OK**klicken, erstellt das Dialogfeld die Excel-Datei, auf die der **Excel-Verbindungs-Manager** zeigt.</span><span class="sxs-lookup"><span data-stu-id="4d008-130">When you click **OK**, the dialog box creates the excel file that the **Excel Connection Manager** points to.</span></span>  
  
 <span data-ttu-id="4d008-131">**Vorhandene Daten anzeigen**</span><span class="sxs-lookup"><span data-stu-id="4d008-131">**View Existing Data**</span></span>  
 <span data-ttu-id="4d008-132">Zeigen Sie mithilfe des Dialogfelds **Vorschau der Abfrageergebnisse anzeigen** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="4d008-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="4d008-133">In der Vorschau können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4d008-133">Preview can display up to 200 rows.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="4d008-134"> Wenn der ausgewählte **Excel-Verbindungs-Manager** auf eine Excel-Datei zeigt, die nicht vorhanden ist, wird eine Fehlermeldung angezeigt, wenn Sie auf diese Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="4d008-134">If the **Excel connection manager** you selected points to an excel file that does not exist, you will see an error message when you click this button.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="4d008-135">Dynamische Optionen (Datenzugriffsmodus)</span><span class="sxs-lookup"><span data-stu-id="4d008-135">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="4d008-136">Datenzugriffsmodus = Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="4d008-136">Data access mode = Table or view</span></span>  
 <span data-ttu-id="4d008-137">**Name der Excel-Tabelle**</span><span class="sxs-lookup"><span data-stu-id="4d008-137">**Name of the Excel sheet**</span></span>  
 <span data-ttu-id="4d008-138">Wählen Sie in der Liste der in der Datenquelle verfügbaren Objekte den Namen des Arbeitsblatts oder des benannten Bereichs aus.</span><span class="sxs-lookup"><span data-stu-id="4d008-138">Select the name of the worksheet or named range from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="4d008-139">Datenzugriffsmodus = Variable für Tabellenname oder Sichtname</span><span class="sxs-lookup"><span data-stu-id="4d008-139">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="4d008-140">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="4d008-140">**Variable name**</span></span>  
 <span data-ttu-id="4d008-141">Wählen Sie die Variable aus, die den Namen des Arbeitsblatts oder des benannten Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="4d008-141">Select the variable that contains the name of the worksheet or named range.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="4d008-142">Datenzugriffsmodus = SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="4d008-142">Data access mode = SQL command</span></span>  
 <span data-ttu-id="4d008-143">**SQL-Befehlstext**</span><span class="sxs-lookup"><span data-stu-id="4d008-143">**SQL command text**</span></span>  
 <span data-ttu-id="4d008-144">Geben Sie den Text einer SQL-Abfrage ein, und erstellen Sie die Abfrage, indem Sie auf **Abfrage erstellen**klicken. Wahlweise können Sie auch nach der Datei suchen, die den Abfragetext enthält, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="4d008-144">Enter the text of an SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="4d008-145">**Abfrage erstellen**</span><span class="sxs-lookup"><span data-stu-id="4d008-145">**Build Query**</span></span>  
 <span data-ttu-id="4d008-146">Mithilfe des Dialogfelds **Abfrage-Generator** können Sie die SQL-Abfrage visuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d008-146">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="4d008-147">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="4d008-147">**Browse**</span></span>  
 <span data-ttu-id="4d008-148">Mithilfe des Dialogfelds **Öffnen** können Sie nach der Datei suchen, die den Text der SQL-Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="4d008-148">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="4d008-149">**Abfrage analysieren**</span><span class="sxs-lookup"><span data-stu-id="4d008-149">**Parse Query**</span></span>  
 <span data-ttu-id="4d008-150">Überprüft die Syntax des Abfragetexts.</span><span class="sxs-lookup"><span data-stu-id="4d008-150">Verify the syntax of the query text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d008-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d008-151">See Also</span></span>  
 <span data-ttu-id="4d008-152">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4d008-152">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4d008-153">[Ziel-Editor für Excel &#40;Seite "Zuordnungen"&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="4d008-153">[Excel Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/excel-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="4d008-154">[Der Ziel-Editor für Excel &#40;Seite Fehlerausgabe&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="4d008-154">[Excel Destination Editor &#40;Error Output Page&#41;](../../2014/integration-services/excel-destination-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="4d008-155">Schleife durch Excel-Dateien und Tabellen mit einem Foreach-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="4d008-155">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
