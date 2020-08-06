---
title: Optionen für die Anforderung für Spaltenstatistikprofil (Datenprofilerstellungs-Task) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: 87205984-507a-49f3-b27c-36a0075c234d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9ce5c062a12e38d147f3cef95ea09b4c80f7c256
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617231"
---
# <a name="column-statistics-profile-request-options-data-profiling-task"></a><span data-ttu-id="5b17f-102">Optionen für die Anforderung für Spaltenstatistikprofil (Datenprofilerstellungs-Task)</span><span class="sxs-lookup"><span data-stu-id="5b17f-102">Column Statistics Profile Request Options (Data Profiling Task)</span></span>
  <span data-ttu-id="5b17f-103">Verwenden Sie den Bereich **Anforderungseigenschaften** der Seite **Profilanforderungen** , um die Optionen für die im Anforderungsbereich ausgewählte **Anforderung für Spaltenstatistikprofil** festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5b17f-103">Use the **Request Properties** pane of the **Profile Requests** page to set the options for the **Column Statistics Profile Request** selected in the requests pane.</span></span> <span data-ttu-id="5b17f-104">Ein Spaltenstatistikprofil meldet Statistiken, wie minimale, maximale, durchschnittliche und standardmäßige Abweichung für numerische Spalten und den Mindest- und Höchstwert für `datetime`-Spalten.</span><span class="sxs-lookup"><span data-stu-id="5b17f-104">A Column Statistics profile reports statistics such as minimum, maximum, average, and standard deviation for numeric columns, and minimum and maximum for `datetime` columns.</span></span> <span data-ttu-id="5b17f-105">Dieses Profil hilft Ihnen, Probleme mit den Daten zu identifizieren, z. B. ungültige Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="5b17f-105">This profile can help you identify problems in your data such as invalid dates.</span></span> <span data-ttu-id="5b17f-106">Beispiel: Sie erstellen ein Profil einer Spalte mit historischen Daten und entdecken einen Maximalwert, der in der Zukunft liegt.</span><span class="sxs-lookup"><span data-stu-id="5b17f-106">For example, you profile a column of historical dates and discover a maximum date that is in the future.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b17f-107">Die in diesem Thema beschriebenen Optionen werden auf der Seite **Profilanforderungen** im **Editor für den Datenprofilerstellungs-Task**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b17f-107">The options described in this topic appear on the **Profile Requests page** of the **Data Profiling Task Editor**.</span></span> <span data-ttu-id="5b17f-108">Weitere Informationen zu dieser Seite des Editors finden Sie unter [Editor für den Datenprofilerstellungs-Task &#40;Seite „Profilanforderungen“&#41;](data-profiling-task-editor-profile-requests-page.md).</span><span class="sxs-lookup"><span data-stu-id="5b17f-108">For more information about this page of the editor, see [Data Profiling Task Editor &#40;Profile Requests Page&#41;](data-profiling-task-editor-profile-requests-page.md).</span></span>  
  
 <span data-ttu-id="5b17f-109">Weitere Informationen zum Verwenden des Datenprofilerstellungs-Tasks finden Sie unter [Einrichten von Datenprofilerstellungs-Tasks](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="5b17f-109">For more information about how to use the Data Profiling Task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="5b17f-110">Weitere Informationen zum Verwenden des Datenprofil-Viewers zum Analysieren der Ausgabe des Datenprofilerstellungs-Tasks finden Sie unter [Datenprofil-Viewer](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="5b17f-110">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling Task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
## <a name="request-properties-options"></a><span data-ttu-id="5b17f-111">Optionen für Anforderungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b17f-111">Request Properties Options</span></span>  
 <span data-ttu-id="5b17f-112">Für eine **Anforderung für Spaltenstatistikprofil**zeigt der Bereich **Anforderungseigenschaften** die folgenden Gruppen von Optionen an:</span><span class="sxs-lookup"><span data-stu-id="5b17f-112">For a **Column Statistics Profile Request**, the **Request Properties** pane displays the following groups of options:</span></span>  
  
-   <span data-ttu-id="5b17f-113">**Daten**, die die Optionen **TableOrView** und **Spalte** enthalten</span><span class="sxs-lookup"><span data-stu-id="5b17f-113">**Data**, which includes the **TableOrView** and **Column** options</span></span>  
  
-   <span data-ttu-id="5b17f-114">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="5b17f-114">**General**</span></span>  
  
### <a name="data-options"></a><span data-ttu-id="5b17f-115">Datenoptionen</span><span class="sxs-lookup"><span data-stu-id="5b17f-115">Data Options</span></span>  
 <span data-ttu-id="5b17f-116">**ConnectionManager**</span><span class="sxs-lookup"><span data-stu-id="5b17f-116">**ConnectionManager**</span></span>  
 <span data-ttu-id="5b17f-117">Wählen Sie den vorhandenen [!INCLUDE[vstecado](../../includes/vstecado-md.md)] -Verbindungs-Manager aus, der den .NET-Datenanbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) verwendet, um eine Verbindung zur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank herzustellen, die die Tabelle oder Sicht enthält, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b17f-117">Select the existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the .NET Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SqlClient) to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that contains the table or view to be profiled.</span></span>  
  
 <span data-ttu-id="5b17f-118">**TableOrView**</span><span class="sxs-lookup"><span data-stu-id="5b17f-118">**TableOrView**</span></span>  
 <span data-ttu-id="5b17f-119">Wählen Sie die vorhandene Tabelle oder die Sicht aus, die die Spalte enthält, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b17f-119">Select the existing table or view that contains the column to be profiled.</span></span>  
  
 <span data-ttu-id="5b17f-120">Weitere Informationen finden Sie im Abschnitt "TableorView-Optionen" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="5b17f-120">For more information, see the section, "TableorView Options," in this topic.</span></span>  
  
 <span data-ttu-id="5b17f-121">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="5b17f-121">**Column**</span></span>  
 <span data-ttu-id="5b17f-122">Wählen Sie die vorhandene Spalte aus, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b17f-122">Select the existing column to be profiled.</span></span> <span data-ttu-id="5b17f-123">Wählen Sie **(\*)** aus, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b17f-123">Select **(\*)** to profile all columns.</span></span>  
  
 <span data-ttu-id="5b17f-124">Weitere Informationen finden Sie im Abschnitt "Spaltenoptionen" in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="5b17f-124">For more information, see the section, "Column Options," in this topic.</span></span>  
  
#### <a name="tableorview-options"></a><span data-ttu-id="5b17f-125">TableOrView-Optionen</span><span class="sxs-lookup"><span data-stu-id="5b17f-125">TableOrView Options</span></span>  
 <span data-ttu-id="5b17f-126">**Schema**</span><span class="sxs-lookup"><span data-stu-id="5b17f-126">**Schema**</span></span>  
 <span data-ttu-id="5b17f-127">Gibt das Schema an, zu dem die ausgewählte Tabelle gehört.</span><span class="sxs-lookup"><span data-stu-id="5b17f-127">Specifies the schema to which the selected table belongs.</span></span> <span data-ttu-id="5b17f-128">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="5b17f-128">This option is read-only.</span></span>  
  
 <span data-ttu-id="5b17f-129">**Table**</span><span class="sxs-lookup"><span data-stu-id="5b17f-129">**Table**</span></span>  
 <span data-ttu-id="5b17f-130">Zeigt den Namen der ausgewählten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="5b17f-130">Displays the name of the selected table.</span></span> <span data-ttu-id="5b17f-131">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="5b17f-131">This option is read-only.</span></span>  
  
#### <a name="column-options"></a><span data-ttu-id="5b17f-132">Spaltenoptionen</span><span class="sxs-lookup"><span data-stu-id="5b17f-132">Column Options</span></span>  
 <span data-ttu-id="5b17f-133">**IsWildCard**</span><span class="sxs-lookup"><span data-stu-id="5b17f-133">**IsWildCard**</span></span>  
 <span data-ttu-id="5b17f-134">Gibt an, ob der Platzhalter **(\*)** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b17f-134">Specifies whether the **(\*)** wildcard has been selected.</span></span> <span data-ttu-id="5b17f-135">Diese Option wird auf **TRUE** festgelegt, wenn Sie **(\*)** ausgewählt haben, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b17f-135">This option is set to **True** if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="5b17f-136">Die Option wird auf **False** festgelegt, wenn Sie eine einzelne Spalte ausgewählt haben, für die ein Profil erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b17f-136">It is **False** if you have selected an individual column to be profiled.</span></span> <span data-ttu-id="5b17f-137">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="5b17f-137">This option is read-only.</span></span>  
  
 <span data-ttu-id="5b17f-138">**ColumnName**</span><span class="sxs-lookup"><span data-stu-id="5b17f-138">**ColumnName**</span></span>  
 <span data-ttu-id="5b17f-139">Zeigt den Namen der ausgewählten Spalte an.</span><span class="sxs-lookup"><span data-stu-id="5b17f-139">Displays the name of the selected column.</span></span> <span data-ttu-id="5b17f-140">Diese Option ist leer, wenn Sie **(\*)** ausgewählt haben, um ein Profil für alle Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b17f-140">This option is blank if you have selected **(\*)** to profile all columns.</span></span> <span data-ttu-id="5b17f-141">Diese Option ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="5b17f-141">This option is read-only.</span></span>  
  
 <span data-ttu-id="5b17f-142">**StringCompareOptions**</span><span class="sxs-lookup"><span data-stu-id="5b17f-142">**StringCompareOptions**</span></span>  
 <span data-ttu-id="5b17f-143">Diese Option gilt nicht für das Spaltenstatistikprofil.</span><span class="sxs-lookup"><span data-stu-id="5b17f-143">This option does not apply to the Column Statistics Profile.</span></span>  
  
### <a name="general-options"></a><span data-ttu-id="5b17f-144">Allgemeine Optionen</span><span class="sxs-lookup"><span data-stu-id="5b17f-144">General Options</span></span>  
 <span data-ttu-id="5b17f-145">**RequestID**</span><span class="sxs-lookup"><span data-stu-id="5b17f-145">**RequestID**</span></span>  
 <span data-ttu-id="5b17f-146">Geben Sie einen beschreibenden Namen ein, um diese Profilanforderung zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="5b17f-146">Type a descriptive name to identify this profile request.</span></span> <span data-ttu-id="5b17f-147">In der Regel müssen Sie den automatisch generierten Wert nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="5b17f-147">Typically, you do not have to change the autogenerated value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b17f-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b17f-148">See Also</span></span>  
 <span data-ttu-id="5b17f-149">[Editor für den Datenprofilerstellungs-Task &#40;Seite "Allgemein"&#41;](../general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5b17f-149">[Data Profiling Task Editor &#40;General Page&#41;](../general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="5b17f-150">Schnellprofilformular für eine einzelne Tabelle &#40;Datenprofilerstellungs-Task&#41;</span><span class="sxs-lookup"><span data-stu-id="5b17f-150">Single Table Quick Profile Form &#40;Data Profiling Task&#41;</span></span>](single-table-quick-profile-form-data-profiling-task.md)  
  
  
