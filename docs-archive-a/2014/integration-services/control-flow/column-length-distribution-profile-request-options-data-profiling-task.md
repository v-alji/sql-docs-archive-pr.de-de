---
title: Optionen für Anforderung für Verteilungsprofil für Spaltenlänge (Datenprofilerstellungs-Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 1a4de41f-f38d-40ea-ba1b-6c0ef67ea52a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c0ebb6f1e0a6df2c0e47311f7b8217c5ce6f2df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617236"
---
# <a name="column-length-distribution-profile-request-options-data-profiling-task"></a><span data-ttu-id="daf16-102">Optionen für Anforderung für Verteilungsprofil für Spaltenlänge (Datenprofilerstellungs-Task)</span><span class="sxs-lookup"><span data-stu-id="daf16-102">Column Length Distribution Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="daf16-103">Verwenden Sie den Bereich **Anforderungseigenschaften** der Seite **Profilanforderungen** , um die Optionen für die im Anforderungsbereich ausgewählte **Anforderung für Verteilungsprofil für Spaltenlänge** festzulegen.</span><span class="sxs-lookup"><span data-stu-id="daf16-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Length Distribution Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="daf16-104">Ein Verteilungsprofil für die Spaltenlänge dokumentiert alle eindeutigen Längen von Zeichenfolgenwerten in der ausgewählten Spalte sowie den Prozentsatz der Zeilen in der Tabelle, die jede Länge darstellt.</span><span class="sxs-lookup"><span data-stu-id="daf16-104">A Column Length Distribution profile reports all the distinct lengths of string values in the selected column and the percentage of rows in the table that each length represents.</span></span> <span data-ttu-id="daf16-105">Dieses Profil hilft Ihnen, Probleme mit den Daten zu identifizieren, z. B. ungültige Werte.</span><span class="sxs-lookup"><span data-stu-id="daf16-105">This profile can help you identify problems in your data such as invalid values.</span></span> <span data-ttu-id="daf16-106">Beispiel: Sie erstellen ein Profil einer Spalte mit den Codes der US-amerikanischen Bundesstaaten, die zwei Zeichen lang sind, und entdecken Werte, die länger als zwei Zeichen sind.</span><span class="sxs-lookup"><span data-stu-id="daf16-106">For example, you profile a column of two-character United States state codes and discover values longer than two characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="daf16-107">Die in diesem Thema beschriebenen Optionen werden auf der Seite **Profilanforderungen** im **Editor für den Datenprofilerstellungs-Task**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="daf16-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="daf16-108">Weitere Informationen zu dieser Seite des Editors finden Sie unter [Editor für den Datenprofilerstellungs-Task &#40;Seite „Profilanforderungen“&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="daf16-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="daf16-109">Weitere Informationen zum Verwenden des Datenprofilerstellungs-Tasks finden Sie unter [Einrichten von Datenprofilerstellungs-Tasks](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="daf16-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="daf16-110">Weitere Informationen zum Verwenden des Datenprofil-Viewers zum Analysieren der Ausgabe des Datenprofilerstellungs-Tasks finden Sie unter [Datenprofil-Viewer](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="daf16-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="daf16-111">Optionen für Anforderungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="daf16-111">Request Properties Options</span></span>  
 <span data-ttu-id="daf16-112">Für eine **Anforderung für Verteilungsprofil für Spaltenlänge**zeigt der Bereich **Anforderungseigenschaften** die folgenden Gruppen von Optionen an:</span><span class="sxs-lookup"><span data-stu-id="daf16-112">For a **Column Length Distribution Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="daf16-113">**Daten**, die die Optionen **TableOrView** und **Spalte** enthalten</span><span class="sxs-lookup"><span data-stu-id="daf16-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="daf16-114">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="daf16-114">**General**</span></span>  
  
-   <span data-ttu-id="daf16-115">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="daf16-115">**Options**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="daf16-116">Datenoptionen</span><span class="sxs-lookup"><span data-stu-id="daf16-116">Data Options</span></span>  
 <span data-ttu-id="daf16-117">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="daf16-117">**ConnectionManager**</span></span>  
 <span data-ttu-id="daf16-118">Wählen Sie den vorhandenen [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager aus, der den .NET-Datenanbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) verwendet, um eine Verbindung zur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank herzustellen, die die Tabelle oder Sicht enthält, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="daf16-118">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="daf16-119">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="daf16-119">**TableOrView**</span></span>  
 <span data-ttu-id="daf16-120">Wählen Sie die vorhandene Tabelle oder die Sicht aus, die die Spalte enthält, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="daf16-120">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="daf16-121">Weitere Informationen finden Sie im Abschnitt "TableorView-Optionen" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="daf16-121">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="daf16-122">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="daf16-122">**Column**</span></span>  
 <span data-ttu-id="daf16-123">Wählen Sie die vorhandene Spalte aus, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="daf16-123">Select the existing column to be profiled.</span></span> <span data-ttu-id="daf16-124">Wählen Sie **(\*)** aus, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="daf16-124">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="daf16-125">Weitere Informationen finden Sie im Abschnitt "Spaltenoptionen" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="daf16-125">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="daf16-126">TableOrView-Optionen</span><span class="sxs-lookup"><span data-stu-id="daf16-126">TableOrView Options</span></span>  
 <span data-ttu-id="daf16-127">**Schema**</span><span class="sxs-lookup"><span data-stu-id="daf16-127">**Schema**</span></span>  
 <span data-ttu-id="daf16-128">Gibt das Schema an, zu dem die ausgewählte Tabelle gehört.</span><span class="sxs-lookup"><span data-stu-id="daf16-128">Specify the schema to which the selected table belongs.</span></span> <span data-ttu-id="daf16-129">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="daf16-129">This option is read-only.</span></span>  
  
 <span data-ttu-id="daf16-130">**Table**</span><span class="sxs-lookup"><span data-stu-id="daf16-130">**Table**</span></span>  
 <span data-ttu-id="daf16-131">Zeigt den Namen der ausgewählten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="daf16-131">Displays the name of the selected table.</span></span> <span data-ttu-id="daf16-132">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="daf16-132">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="daf16-133">Spaltenoptionen</span><span class="sxs-lookup"><span data-stu-id="daf16-133">Column Options</span></span>  
 <span data-ttu-id="daf16-134">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="daf16-134">**IsWildCard**</span></span>  
 <span data-ttu-id="daf16-135">Gibt an, ob der Platzhalter **(\*)** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="daf16-135">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="daf16-136">Diese Option wird auf **TRUE** festgelegt, wenn Sie **(\*)** ausgewählt haben, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="daf16-136">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="daf16-137">Die Option wird auf **False** festgelegt, wenn Sie eine einzelne Spalte ausgewählt haben, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="daf16-137">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="daf16-138">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="daf16-138">This option is read-only.</span></span>  
  
 <span data-ttu-id="daf16-139">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="daf16-139">**ColumnName**</span></span>  
 <span data-ttu-id="daf16-140">Zeigt den Namen der ausgewählten Spalte an.</span><span class="sxs-lookup"><span data-stu-id="daf16-140">Displays the name of the selected column.</span></span> <span data-ttu-id="daf16-141">Diese Option ist leer, wenn Sie **(\*)** ausgewählt haben, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="daf16-141">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="daf16-142">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="daf16-142">This option is read-only.</span></span>  
  
 <span data-ttu-id="daf16-143">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="daf16-143">**StringCompareOptions**</span></span>  
 <span data-ttu-id="daf16-144">Diese Option gilt nicht für das Verteilungsprofil für Spaltenlänge.</span><span class="sxs-lookup"><span data-stu-id="daf16-144">This option does not apply to the Column Length Distribution Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="daf16-145">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="daf16-145">General Options</span></span>  
 <span data-ttu-id="daf16-146">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="daf16-146">**RequestID**</span></span>  
 <span data-ttu-id="daf16-147">Geben Sie einen beschreibenden Namen ein, um diese Profilanforderung zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="daf16-147">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="daf16-148">In der Regel müssen Sie den automatisch generierten Wert nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="daf16-148">Typically, you do not have to change the autogenerated value.</span></span>  
  
### <a name="options"></a><span data-ttu-id="daf16-149">Tastatur</span><span class="sxs-lookup"><span data-stu-id="daf16-149">Options</span></span>  
 <span data-ttu-id="daf16-150">**IgnoreLeadingSpaces**</span><span class="sxs-lookup"><span data-stu-id="daf16-150">**IgnoreLeadingSpaces**</span></span>  
 <span data-ttu-id="daf16-151">Geben Sie an, ob führende Leerzeichen ignoriert werden sollen, wenn das Profil Zeichenfolgenwerte vergleicht.</span><span class="sxs-lookup"><span data-stu-id="daf16-151">Indicate whether to ignore leading spaces when the profile compares string values.</span></span> <span data-ttu-id="daf16-152">Der Standardwert für diese Option ist **False**.</span><span class="sxs-lookup"><span data-stu-id="daf16-152">The default value of this option is **False**.</span></span>  
  
 <span data-ttu-id="daf16-153">**IgnoreTrailingSpaces**</span><span class="sxs-lookup"><span data-stu-id="daf16-153">**IgnoreTrailingSpaces**</span></span>  
 <span data-ttu-id="daf16-154">Geben Sie an, ob nachfolgende Leerzeichen ignoriert werden sollen, wenn das Profil Zeichenfolgenwerte vergleicht.</span><span class="sxs-lookup"><span data-stu-id="daf16-154">Indicate whether to ignore trailing spaces when the profile compares string values.</span></span> <span data-ttu-id="daf16-155">Der Standardwert für diese Option ist **True**.</span><span class="sxs-lookup"><span data-stu-id="daf16-155">The default value of this option is **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf16-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daf16-156">See Also</span></span>  
 <span data-ttu-id="daf16-157">[Editor für den Datenprofilerstellungs-Task &#40;Seite "Allgemein"&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="daf16-157">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="daf16-158">Schnellprofilformular für eine einzelne Tabelle &#40;Datenprofilerstellungs-Task&#41;</span><span class="sxs-lookup"><span data-stu-id="daf16-158">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
