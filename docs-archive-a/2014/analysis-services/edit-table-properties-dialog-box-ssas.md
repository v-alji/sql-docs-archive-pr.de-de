---
title: Tabellen Eigenschaften bearbeiten (Dialog Feld) (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.edittablepropdb.f1
ms.assetid: 8d913e83-7246-44cc-8fc7-31729023c0d8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6664d244f5f653610b37bd628abdb2263e015c0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621239"
---
# <a name="edit-table-properties-dialog-box-ssas"></a><span data-ttu-id="27b8b-102">Tabelleneigenschaften bearbeiten (Dialogfeld) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="27b8b-102">Edit Table Properties Dialog Box (SSAS)</span></span>
  <span data-ttu-id="27b8b-103">Im Dialogfeld **Tabelleneigenschaften bearbeiten** können Sie die Eigenschaften von Tabellen anzeigen und ändern, die mit dem Tabellenimport-Assistenten in den Modell-Designer importiert werden.</span><span class="sxs-lookup"><span data-stu-id="27b8b-103">The **Edit Table Properties** dialog box enables you to view and modify the properties of tables that are imported into the model designer by using the Table Import Wizard.</span></span> <span data-ttu-id="27b8b-104">Um das Dialogfeld zu öffnen, wählen Sie im Modell-Designer eine Tabelle aus, und klicken Sie auf das Menü **Tabelle** und anschließend auf **Tabelleneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="27b8b-104">To access this dialog box, in the model designer, select a table, then click the **Table** menu, and then click **Table Properties**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="27b8b-105">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="27b8b-105">UI element list</span></span>  
 <span data-ttu-id="27b8b-106">Die Optionen dieses Dialogfelds variieren, je nachdem, ob Daten ursprünglich durch Auswahl von Tabellen aus einer Liste oder mithilfe einer SQL-Abfrage importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="27b8b-106">The options for this dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span>  
  
## <a name="table-preview-mode"></a><span data-ttu-id="27b8b-107">Tabellenvorschaumodus</span><span class="sxs-lookup"><span data-stu-id="27b8b-107">Table Preview Mode</span></span>  
 <span data-ttu-id="27b8b-108">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="27b8b-108">**Table name**</span></span>  
 <span data-ttu-id="27b8b-109">Zeigt den Namen der Datentabelle im Modell an.</span><span class="sxs-lookup"><span data-stu-id="27b8b-109">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27b8b-110">Der Name kann hier nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="27b8b-110">You cannot edit the name here.</span></span> <span data-ttu-id="27b8b-111">Sie können den Namen der Tabelle jedoch ändern, indem Sie im unteren Bereich des Modell-Designers mit der rechten Maustaste auf die Tabellenregisterkarte klicken.</span><span class="sxs-lookup"><span data-stu-id="27b8b-111">However, you can change the name of the table by right-clicking the table tab at the bottom of the model designer.</span></span>  
  
 <span data-ttu-id="27b8b-112">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="27b8b-112">**Connection name**</span></span>  
 <span data-ttu-id="27b8b-113">Zeigt den Namen der aktuell verwendeten Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="27b8b-113">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="27b8b-114">**Quellname**</span><span class="sxs-lookup"><span data-stu-id="27b8b-114">**Source name**</span></span>  
 <span data-ttu-id="27b8b-115">Mit dieser Option können Sie die Tabelle anzeigen oder ändern, aus der die Daten abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="27b8b-115">Display or change the table from which the data is obtained.</span></span>  
  
 <span data-ttu-id="27b8b-116">Wenn Sie die Quelle in eine Tabelle ändern, die andere Spalten als die aktuelle Tabelle enthält, wird eine entsprechende Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="27b8b-116">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="27b8b-117">Sie müssen dann die Spalten auswählen, die Sie in die aktuelle Tabelle einfügen möchten, und auf **Speichern**klicken.</span><span class="sxs-lookup"><span data-stu-id="27b8b-117">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="27b8b-118">Sie können die gesamte Tabelle ersetzen, indem Sie das Kontrollkästchen links von der Tabelle aktivieren.</span><span class="sxs-lookup"><span data-stu-id="27b8b-118">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27b8b-119">Wenn Sie die Datenquelle einer Tabelle ändern, ersetzen Sie praktisch den Inhalt der aktuellen Tabelle durch den Inhalt der neuen Quelltabelle.</span><span class="sxs-lookup"><span data-stu-id="27b8b-119">When you change the data source of a table, you essentially replace the contents of the current table with the contents of the new source table.</span></span>  
  
 <span data-ttu-id="27b8b-120">**Spaltennamen aus**</span><span class="sxs-lookup"><span data-stu-id="27b8b-120">**Column names from**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="27b8b-121">**Quelle**</span><span class="sxs-lookup"><span data-stu-id="27b8b-121">**Source**</span></span>|<span data-ttu-id="27b8b-122">Aktivieren Sie diese Option, um die aktuellen Spaltennamen durch die Spaltennamen aus der ausgewählten Quelltabelle zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-122">Select this option to replace the current column names with the column names from the selected source table.</span></span>|  
|<span data-ttu-id="27b8b-123">**Modell**</span><span class="sxs-lookup"><span data-stu-id="27b8b-123">**Model**</span></span>|<span data-ttu-id="27b8b-124">Aktivieren Sie diese Option, um die aktuellen Spaltennamen zu verwenden, wie sie im Modell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="27b8b-124">Select this option to use the current column names as they exist in the model.</span></span>|  
  
 <span data-ttu-id="27b8b-125">**Vorschau aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="27b8b-125">**Refresh preview**</span></span>  
 <span data-ttu-id="27b8b-126">Klicken Sie auf diese Option, um die Spalten der Daten in der momentan ausgewählten Quelltabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-126">Click to view the columns of data in the currently selected source table.</span></span>  
  
 <span data-ttu-id="27b8b-127">**Wechseln zu**</span><span class="sxs-lookup"><span data-stu-id="27b8b-127">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="27b8b-128">**Tabellenvorschau**</span><span class="sxs-lookup"><span data-stu-id="27b8b-128">**Table preview**</span></span>|<span data-ttu-id="27b8b-129">Wählen Sie diese Option aus, um die ausgewählte Tabelle und eine beschränkte Anzahl von Datenzeilen in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-129">Select this option to preview the selected table and a limited number of rows of data.</span></span>|  
|<span data-ttu-id="27b8b-130">**Abfrage-Editor**</span><span class="sxs-lookup"><span data-stu-id="27b8b-130">**Query editor**</span></span>|<span data-ttu-id="27b8b-131">Wählen Sie diese Option aus, um die Abfrage für die ausgewählte Datenquelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-131">Select this option to view the query against the selected data source.</span></span> <span data-ttu-id="27b8b-132">Diese Option ist nicht für alle Datenquellen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="27b8b-132">This option is not available for all data sources.</span></span>|  
  
 <span data-ttu-id="27b8b-133">**Kontrollkästchen in der Spaltenüberschrift**</span><span class="sxs-lookup"><span data-stu-id="27b8b-133">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="27b8b-134">Aktivieren Sie das Kontrollkästchen, um die Spalte in den Datenimport einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-134">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="27b8b-135">Deaktivieren Sie das Kontrollkästchen, um die Spalte aus dem Datenimport zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-135">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="27b8b-136">**Schaltfläche mit Abwärtspfeil in der Spaltenüberschrift**</span><span class="sxs-lookup"><span data-stu-id="27b8b-136">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="27b8b-137">Filtern Sie Daten in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="27b8b-137">Filter data in the column.</span></span>  
  
 <span data-ttu-id="27b8b-138">**Zeilen Filter löschen**</span><span class="sxs-lookup"><span data-stu-id="27b8b-138">**Clear row filters**</span></span>  
 <span data-ttu-id="27b8b-139">Klicken Sie auf diese Option, um alle angewendeten Filter zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-139">Click to remove any filters that have been applied.</span></span>  
  
 <span data-ttu-id="27b8b-140">**OK**</span><span class="sxs-lookup"><span data-stu-id="27b8b-140">**OK**</span></span>  
 <span data-ttu-id="27b8b-141">Klicken Sie auf diese Option, um alle vorgenommenen Änderungen zu übernehmen, auch das Ersetzen der Spalten.</span><span class="sxs-lookup"><span data-stu-id="27b8b-141">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="query-design-mode"></a><span data-ttu-id="27b8b-142">Abfrageentwurfsmodus</span><span class="sxs-lookup"><span data-stu-id="27b8b-142">Query Design Mode</span></span>  
 <span data-ttu-id="27b8b-143">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="27b8b-143">**Table name**</span></span>  
 <span data-ttu-id="27b8b-144">Zeigt den Namen der Datentabelle im Modell an.</span><span class="sxs-lookup"><span data-stu-id="27b8b-144">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27b8b-145">Sie können den Namen hier nicht bearbeiten. Sie können den Namen der Tabelle jedoch ändern, indem Sie im unteren Bereich des Designers mit der rechten Maustaste auf die Tabellenregisterkarte klicken.</span><span class="sxs-lookup"><span data-stu-id="27b8b-145">You cannot edit the name here; however, you can change the name of the table by right-clicking the table tab at the bottom of the designer.</span></span>  
  
 <span data-ttu-id="27b8b-146">**Verbindungsname**</span><span class="sxs-lookup"><span data-stu-id="27b8b-146">**Connection name**</span></span>  
 <span data-ttu-id="27b8b-147">Zeigt den Namen der aktuell verwendeten Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="27b8b-147">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="27b8b-148">**Wechseln zu**</span><span class="sxs-lookup"><span data-stu-id="27b8b-148">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="27b8b-149">**Tabellenvorschau**</span><span class="sxs-lookup"><span data-stu-id="27b8b-149">**Table preview**</span></span>|<span data-ttu-id="27b8b-150">Wählen Sie diese Option Liste aus, um die ausgewählte Tabelle und einige Zeilen der Daten in der Vorschau anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-150">Select this option to preview the selected table and a few rows of data.</span></span>|  
|<span data-ttu-id="27b8b-151">**Abfrage-Editor**</span><span class="sxs-lookup"><span data-stu-id="27b8b-151">**Query editor**</span></span>|<span data-ttu-id="27b8b-152">Aktivieren Sie diese Option, um die Abfrage anzuzeigen, die für die ausgewählte Datenquelle ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27b8b-152">Select this option to view the query that will be issued against the selected data source.</span></span>|  
  
 <span data-ttu-id="27b8b-153">**SQL-Anweisung**</span><span class="sxs-lookup"><span data-stu-id="27b8b-153">**Sql statement**</span></span>  
 <span data-ttu-id="27b8b-154">Zeigt die SQL-Anweisung an, die für die aktuelle Datenquelle ausgegeben wird, um Zeilen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-154">Displays the SQL statement that is issued against the current data source to retrieve rows.</span></span> <span data-ttu-id="27b8b-155">Standardmäßig werden alle Zeilen abgerufen. Sie können jedoch auch eine Teilmenge der Zeilen abrufen, indem Sie entweder einen Filter entwerfen oder die SQL-Anweisung manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="27b8b-155">By default, all rows are retrieved, but you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="27b8b-156">**Überprüfen**</span><span class="sxs-lookup"><span data-stu-id="27b8b-156">**Validate**</span></span>  
 <span data-ttu-id="27b8b-157">Klicken Sie auf diese Option, um sicherzustellen, dass die Anweisung für die ausgewählte Datenquelle und den Anbieter syntaktisch korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="27b8b-157">Click to verify that the statement is syntactically correct for the selected data source and provider.</span></span>  
  
 <span data-ttu-id="27b8b-158">**Design**</span><span class="sxs-lookup"><span data-stu-id="27b8b-158">**Design**</span></span>  
 <span data-ttu-id="27b8b-159">Klicken Sie auf diese Option, um einen visuellen Abfrage-Designer zu öffnen und eine Abfrageanweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="27b8b-159">Click to open a visual query designer and build a query statement.</span></span> <span data-ttu-id="27b8b-160">Drücken Sie im Designer die F1-TASTE, um Informationen zum Verwenden des Designers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="27b8b-160">For information about how to use the designer, press F1 from the designer.</span></span>  
  
 <span data-ttu-id="27b8b-161">**OK**</span><span class="sxs-lookup"><span data-stu-id="27b8b-161">**OK**</span></span>  
 <span data-ttu-id="27b8b-162">Klicken Sie auf diese Option, um alle vorgenommenen Änderungen zu übernehmen, auch das Ersetzen der Spalten.</span><span class="sxs-lookup"><span data-stu-id="27b8b-162">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b8b-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27b8b-163">See Also</span></span>  
 [<span data-ttu-id="27b8b-164">Tabellen und Spalten &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="27b8b-164">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
