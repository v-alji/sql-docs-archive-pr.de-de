---
title: Optionen für die Anforderung für Profil für NULL-Verhältnis der Spalte (Datenprofilerstellungs-Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 157ef8e4-fd23-4f81-8194-eebf74e9fd86
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e47c09a9a19eae4aed21c0c518430bc19a45648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617234"
---
# <a name="column-null-ratio-profile-request-options-data-profiling-task"></a><span data-ttu-id="c3c73-102">Optionen für die Anforderung für Profil für NULL-Verhältnis der Spalte (Datenprofilerstellungs-Task)</span><span class="sxs-lookup"><span data-stu-id="c3c73-102">Column Null Ratio Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="c3c73-103">Verwenden Sie den Bereich **Anforderungseigenschaften** der Seite **Profilanforderungen** , um die Optionen für das im Anforderungsbereich ausgewählte **Profil für NULL-Verhältnis der Spalte** festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c3c73-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Null Ratio Request** selected in the requests pane.</span></span> <span data-ttu-id="c3c73-104">Ein Profil für das NULL-Verhältnis der Spalte dokumentiert den Prozentsatz der NULL-Werte in der ausgewählten Spalte.</span><span class="sxs-lookup"><span data-stu-id="c3c73-104">A Column Null Ratio profile reports the percentage of null values in the selected column.</span></span> <span data-ttu-id="c3c73-105">Dieses Profil hilft Ihnen, Probleme mit den Daten zu identifizieren, z. B. ein unerwartet hohes Verhältnis an NULL-Werten in einer Spalte.</span><span class="sxs-lookup"><span data-stu-id="c3c73-105">This profile can help you identify problems in your data such as an unexpectedly high ratio of null values in a column.</span></span> <span data-ttu-id="c3c73-106">Ein Profil für das NULL-Verhältnis einer Spalte kann beispielsweise ein Profil für eine Spalte für die Postleitzahl erstellen und einen nicht zulässigen hohen Prozentsatz an fehlenden Postleitzahlen erkennen.</span><span class="sxs-lookup"><span data-stu-id="c3c73-106">For example, a Column Null Ratio profile can profile a ZIP Code/Postal Code column and discover an unacceptably high percentage of missing postal codes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3c73-107">Die in diesem Thema beschriebenen Optionen werden auf der Seite **Profilanforderungen** im **Editor für den Datenprofilerstellungs-Task**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3c73-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="c3c73-108">Weitere Informationen zu dieser Seite des Editors finden Sie unter [Editor für den Datenprofilerstellungs-Task &#40;Seite „Profilanforderungen“&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="c3c73-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="c3c73-109">Weitere Informationen zum Verwenden des Datenprofilerstellungs-Tasks finden Sie unter [Einrichten von Datenprofilerstellungs-Tasks](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="c3c73-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="c3c73-110">Weitere Informationen zum Verwenden des Datenprofil-Viewers zum Analysieren der Ausgabe des Datenprofilerstellungs-Tasks finden Sie unter [Datenprofil-Viewer](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="c3c73-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="c3c73-111">Optionen für Anforderungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="c3c73-111">Request Properties Options</span></span>  
 <span data-ttu-id="c3c73-112">Für eine **Anforderung für NULL-Verhältnis der Spalte**zeigt der Bereich **Anforderungseigenschaften** die folgenden Gruppen von Optionen an:</span><span class="sxs-lookup"><span data-stu-id="c3c73-112">For a **Column Null Ratio Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="c3c73-113">**Daten**, die die Optionen **TableOrView** und **Spalte** enthalten</span><span class="sxs-lookup"><span data-stu-id="c3c73-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="c3c73-114">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="c3c73-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="c3c73-115">Datenoptionen</span><span class="sxs-lookup"><span data-stu-id="c3c73-115">Data Options</span></span>  
 <span data-ttu-id="c3c73-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="c3c73-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="c3c73-117">Wählen Sie den vorhandenen [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager aus, der den .NET-Datenanbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) verwendet, um eine Verbindung zur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank herzustellen, die die Tabelle oder Sicht enthält, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3c73-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the.NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="c3c73-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="c3c73-118">**TableOrView**</span></span>  
 <span data-ttu-id="c3c73-119">Wählen Sie die vorhandene Tabelle oder die Sicht aus, die die Spalte enthält, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3c73-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="c3c73-120">Weitere Informationen finden Sie im Abschnitt "TableorView-Optionen" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="c3c73-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="c3c73-121">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c3c73-121">**Column**</span></span>  
 <span data-ttu-id="c3c73-122">Wählen Sie die vorhandene Spalte aus, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3c73-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="c3c73-123">Wählen Sie **(\*)** aus, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3c73-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="c3c73-124">Weitere Informationen finden Sie im Abschnitt "Spaltenoptionen" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="c3c73-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="c3c73-125">TableOrView-Optionen</span><span class="sxs-lookup"><span data-stu-id="c3c73-125">TableOrView Options</span></span>  
 <span data-ttu-id="c3c73-126">**Schema**</span><span class="sxs-lookup"><span data-stu-id="c3c73-126">**Schema**</span></span>  
 <span data-ttu-id="c3c73-127">Gibt das Schema an, zu dem die ausgewählte Tabelle gehört.</span><span class="sxs-lookup"><span data-stu-id="c3c73-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="c3c73-128">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c3c73-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="c3c73-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="c3c73-129">**Table**</span></span>  
 <span data-ttu-id="c3c73-130">Zeigt den Namen der ausgewählten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="c3c73-130">Displays the name of the selected table.</span></span> <span data-ttu-id="c3c73-131">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c3c73-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="c3c73-132">Spaltenoptionen</span><span class="sxs-lookup"><span data-stu-id="c3c73-132">Column Options</span></span>  
 <span data-ttu-id="c3c73-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="c3c73-133">**IsWildCard**</span></span>  
 <span data-ttu-id="c3c73-134">Gibt an, ob der Platzhalter **(\*)** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="c3c73-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="c3c73-135">Diese Option wird auf **TRUE** festgelegt, wenn Sie **(\*)** ausgewählt haben, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3c73-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="c3c73-136">Die Option wird auf **False** festgelegt, wenn Sie eine einzelne Spalte ausgewählt haben, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c3c73-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="c3c73-137">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c3c73-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="c3c73-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="c3c73-138">**ColumnName**</span></span>  
 <span data-ttu-id="c3c73-139">Zeigt den Namen der ausgewählten Spalte an.</span><span class="sxs-lookup"><span data-stu-id="c3c73-139">Displays the name of the selected column.</span></span> <span data-ttu-id="c3c73-140">Diese Option ist leer, wenn Sie **(\*)** ausgewählt haben, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c3c73-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="c3c73-141">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c3c73-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="c3c73-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="c3c73-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="c3c73-143">Diese Option gilt nicht für das Profil für NULL-Verhältnis für Spalten.</span><span class="sxs-lookup"><span data-stu-id="c3c73-143">This option does not apply to the Column Null Ratio Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="c3c73-144">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="c3c73-144">General Options</span></span>  
 <span data-ttu-id="c3c73-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="c3c73-145">**RequestID**</span></span>  
 <span data-ttu-id="c3c73-146">Geben Sie einen beschreibenden Namen ein, um diese Profilanforderung zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c3c73-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="c3c73-147">In der Regel müssen Sie den automatisch generierten Wert nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c3c73-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c73-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3c73-148">See Also</span></span>  
 <span data-ttu-id="c3c73-149">[Editor für den Datenprofilerstellungs-Task &#40;Seite "Allgemein"&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c3c73-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="c3c73-150">Schnellprofilformular für eine einzelne Tabelle &#40;Datenprofilerstellungs-Task&#41;</span><span class="sxs-lookup"><span data-stu-id="c3c73-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
