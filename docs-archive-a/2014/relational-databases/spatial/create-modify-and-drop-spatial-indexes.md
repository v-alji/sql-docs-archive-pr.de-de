---
title: Erstellen, Ändern und Löschen von räumlichen Indizes | Microsoft-Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- indexes [SQL Server], creating
- spatial indexes [SQL Server], dropping
- spatial indexes [SQL Server], creating
- indexes [SQL Server], dropping
- indexes [SQL Server], modifying
- spatial indexes [SQL Server], modifying
ms.assetid: 00c1b927-8ec5-44cf-87c2-c8de59745735
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 88de17e8c487d9a965f2e236edac064dc2fe4c7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609060"
---
# <a name="create-modify-and-drop-spatial-indexes"></a><span data-ttu-id="9973b-102">Erstellen, Ändern und Löschen von räumlichen Indizes</span><span class="sxs-lookup"><span data-stu-id="9973b-102">Create, Modify, and Drop Spatial Indexes</span></span>
  <span data-ttu-id="9973b-103">Mit einem räumlichen Index können bestimmte Vorgänge für eine Spalte des- `geometry` `geography` Datentyps oder-Datentyps (eine *räumliche Spalte*) effizienter durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9973b-103">A spatial index can more efficiently perform certain operations on a column of the `geometry` or `geography` data type (a *spatial column*).</span></span> <span data-ttu-id="9973b-104">Für eine räumliche Spalte können mehrere räumliche Indizes angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9973b-104">More than one spatial index can be specified on a spatial column.</span></span> <span data-ttu-id="9973b-105">Dies ist beispielsweise hilfreich, wenn verschiedene Mosaikparameter in einer Spalte indiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9973b-105">This is useful, for example, for indexing different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="9973b-106">Die Erstellung von räumlichen Indizes unterliegt einigen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="9973b-106">There are a number of restrictions on creating spatial indexes.</span></span> <span data-ttu-id="9973b-107">Weitere Informationen zu den Beschränkungen von räumlichen Indizes finden Sie unter [Erstellen, Ändern und Löschen von räumlichen Indizes](#restrictions) in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="9973b-107">For more information, see [Restrictions on Spatial Indexes](#restrictions) in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9973b-108">Weitere Informationen zur Beziehung zwischen räumlichen Indizes und Partitionen und Dateigruppen finden Sie im Abschnitt mit Hinweisen unter [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9973b-108">For information about the relationship of spatial indexes to partition and to filegroups, see the "Remarks" section in [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
##  <a name="creating-modifying-and-dropping-spatial-indexes"></a><a name="creating"></a> <span data-ttu-id="9973b-109">Erstellen, Ändern und Löschen von räumlichen Indizes</span><span class="sxs-lookup"><span data-stu-id="9973b-109">Creating, Modifying, and Dropping Spatial Indexes</span></span>  
  
###  <a name="to-create-a-spatial-index"></a><a name="create"></a> <span data-ttu-id="9973b-110">So erstellen Sie einen räumlichen Index</span><span class="sxs-lookup"><span data-stu-id="9973b-110">To create a spatial index</span></span>  
 <span data-ttu-id="9973b-111">**So erstellen Sie einen räumlichen Index mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="9973b-111">**To create a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="9973b-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9973b-112">CREATE SPATIAL INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-spatial-index-transact-sql)  
  
 <span data-ttu-id="9973b-113">**So erstellen Sie mit dem Dialogfeld "Neuer Index" in Management Studio einen räumlichen Index**</span><span class="sxs-lookup"><span data-stu-id="9973b-113">**To create a spatial index by using the New Index dialog box in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-management-studio"></a><span data-ttu-id="9973b-114">So erstellen Sie einen räumlichen Index in Management Studio</span><span class="sxs-lookup"><span data-stu-id="9973b-114">To create a spatial index in Management Studio</span></span>  
  
1.  <span data-ttu-id="9973b-115">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="9973b-115">In Object Explorer, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="9973b-116">Erweitern Sie **Datenbanken**und anschließend die Datenbank, die die Tabelle mit dem angegebenen Index enthält, und erweitern Sie anschließend **Tabellen**.</span><span class="sxs-lookup"><span data-stu-id="9973b-116">Expand **Databases**, expand the database that contains the table with the specified index, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="9973b-117">Erweitern Sie die Tabelle, für die Sie den Index erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9973b-117">Expand the table for which you want to create the index.</span></span>  
  
4.  <span data-ttu-id="9973b-118">Klicken Sie mit der rechten Maustaste auf **Indizes** , und wählen Sie **Neuer Index**aus.</span><span class="sxs-lookup"><span data-stu-id="9973b-118">Right-click **Indexes** and select **New Index**.</span></span>  
  
5.  <span data-ttu-id="9973b-119">Geben Sie im Feld **Indexname** einen Namen für den Index ein.</span><span class="sxs-lookup"><span data-stu-id="9973b-119">In the **Index name** field, enter a name for the index.</span></span>  
  
6.  <span data-ttu-id="9973b-120">Wählen Sie in der Dropdownliste **Indextyp** den Eintrag **räumlich**aus.</span><span class="sxs-lookup"><span data-stu-id="9973b-120">In the **Index type** drop-down list, select **Spatial**.</span></span>  
  
7.  <span data-ttu-id="9973b-121">Klicken Sie auf **Hinzufügen**, um die räumliche Spalte anzugeben, die indiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9973b-121">To specify the spatial column that you want to index, click **Add**.</span></span>  
  
8.  <span data-ttu-id="9973b-122">Wählen Sie im Dialogfeld **Spalten auswählen aus** *\<table name>* eine Spalte des Typs oder aus, `geometry` indem Sie `geography` das entsprechende Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9973b-122">In the **Select Columns from** *\<table name>* dialog box, select a column of type `geometry` or `geography` by selecting the corresponding check box.</span></span> <span data-ttu-id="9973b-123">Alle anderen räumlichen Spalten werden daraufhin nicht editierbar.</span><span class="sxs-lookup"><span data-stu-id="9973b-123">Any other spatial columns then become uneditable.</span></span> <span data-ttu-id="9973b-124">Wenn Sie eine andere räumliche Spalte auswählen möchten, müssen Sie zuerst die Auswahl der aktuell ausgewählten Spalte aufheben.</span><span class="sxs-lookup"><span data-stu-id="9973b-124">If you want to select a different spatial column, you must first clear the currently selected column.</span></span> <span data-ttu-id="9973b-125">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9973b-125">When finished, click **OK**.</span></span>  
  
9. <span data-ttu-id="9973b-126">Überprüfen Sie die Spaltenauswahl im Raster **Indexschlüsselspalten** .</span><span class="sxs-lookup"><span data-stu-id="9973b-126">Verify your column selection in the **Index key columns** grid.</span></span>  
  
10. <span data-ttu-id="9973b-127">Klicken Sie im Bereich **Seite auswählen** des Dialogfelds **Indexeigenschaften** auf **räumlich**.</span><span class="sxs-lookup"><span data-stu-id="9973b-127">In the **Select a page** pane of the **Index Properties** dialog box, click **Spatial**.</span></span>  
  
11. <span data-ttu-id="9973b-128">Geben Sie auf der Seite **räumlich** die Werte ein, die Sie für die räumlichen Eigenschaften des Index verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9973b-128">On the **Spatial** page, specify the values that you want to use for the spatial properties of the index.</span></span>  
  
     <span data-ttu-id="9973b-129">Wenn Sie einen Index für eine `geometry` Typspalte erstellen, müssen Sie die Koordinaten **( *`X-min`* , *`Y-min`* )** und **( *`X-max`* , *`Y-max`* )** des umgebenden Felds angeben.</span><span class="sxs-lookup"><span data-stu-id="9973b-129">When creating an index on a `geometry` type column, you must specify the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="9973b-130">Bei einem Index für eine `geography` Typspalte werden die Felder für das umgebende Feld schreibgeschützt, nachdem Sie das Mosaik Schema für das **Geografieraster** angegeben haben, da das Geografieraster-Mosaik kein Begrenzungsfeld verwendet.</span><span class="sxs-lookup"><span data-stu-id="9973b-130">For an index on a `geography` type column, the bounding-box fields become read-only after you specify the **Geography grid** tessellation scheme, because geography grid tessellation does not use a bounding box.</span></span>  
  
     <span data-ttu-id="9973b-131">Optional können Sie benutzerdefinierte Werte für das Feld **Zellen pro Objekt** und für die Rasterdichte auf jeder Ebene des Mosaikschemas angeben.</span><span class="sxs-lookup"><span data-stu-id="9973b-131">Optionally, you can specify nondefault values for the **Cells Per Object** field and for the grid density at any level of the tessellation scheme.</span></span> <span data-ttu-id="9973b-132">Die Standardanzahl von Zellen pro Objekt ist 16 für [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] oder 8 für [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] oder höher, und die Standardrasterdichte ist **Mittel** für [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9973b-132">The default number of cells per object is 16 for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] or 8 for [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] or higher, and the default grid density is **Medium** for [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span>  
  
     <span data-ttu-id="9973b-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]können Sie GEOMETRY_AUTO_GRID oder GEOGRAPHY_AUTO_GRID für das Mosaikschema auswählen.</span><span class="sxs-lookup"><span data-stu-id="9973b-133">You can select GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID for tessellation scheme in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9973b-134">Wenn GEOMETRY_AUTO_GRID oder GEOGRAPHY_AUTO_GRID ausgewählt wird, sind die Rasterdichteoptionen für Ebene 1, Ebene 2, Ebene 3 und Ebene 4 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9973b-134">When GEOMETRY_AUTO_GRID or GEOGRAPHY_AUTO_GRID is selected, then Level 1, Level 2, Level 3, and Level 4 grid density options are disabled.</span></span>  
  
     <span data-ttu-id="9973b-135">Weitere Informationen zu diesen Eigenschaften finden Sie unter [Indexeigenschaften (F1-Hilfe)](../indexes/index-properties-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="9973b-135">For more information about these properties, see [Index Properties F1 Help](../indexes/index-properties-f1-help.md).</span></span>  
  
12. <span data-ttu-id="9973b-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9973b-136">Click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9973b-137">Um einen weiteren räumlichen Index für die gleiche oder eine andere räumliche Spalte zu erstellen, wiederholen Sie die gerade beschriebenen Schritte.</span><span class="sxs-lookup"><span data-stu-id="9973b-137">To create another spatial index on the same or a different spatial column, repeat the preceding steps.</span></span>  
  
  
 <span data-ttu-id="9973b-138">**So erstellen Sie mit dem Tabellen-Designer in Management Studio einen räumlichen Index**</span><span class="sxs-lookup"><span data-stu-id="9973b-138">**To create a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-create-a-spatial-index-in-table-designer"></a><span data-ttu-id="9973b-139">So erstellen Sie einen räumlichen Index im Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="9973b-139">To create a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="9973b-140">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle, für die Sie einen räumlichen Index erstellen möchten, und klicken Sie anschließend auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="9973b-140">In Object Explorer, right-click the table for which you want to create a spatial index, and then click **Design**.</span></span>  
  
     <span data-ttu-id="9973b-141">Die Tabelle wird im Tabellen-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9973b-141">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="9973b-142">Wählen Sie eine `geometry`- oder `geography`-Spalte für den Index aus.</span><span class="sxs-lookup"><span data-stu-id="9973b-142">Select a `geometry` or `geography` column for the index.</span></span>  
  
3.  <span data-ttu-id="9973b-143">Klicken Sie im Menü **Tabellen-Designer** auf **räumlicher Index**.</span><span class="sxs-lookup"><span data-stu-id="9973b-143">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
4.  <span data-ttu-id="9973b-144">Klicken Sie im Dialogfeld **räumliche Indizes** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9973b-144">In the **Spatial Indexes** dialog box, click **Add**.</span></span>  
  
5.  <span data-ttu-id="9973b-145">Wählen Sie den neuen Index aus der Liste **Ausgewählter räumlicher Index** aus, und legen Sie im Raster rechts die Eigenschaften für den räumlichen Index fest.</span><span class="sxs-lookup"><span data-stu-id="9973b-145">Select the new index in the **Selected Spatial Index** list, and in the grid to the right, set the properties for the spatial index.</span></span> <span data-ttu-id="9973b-146">Informationen zu den Eigenschaften finden Sie unter [Dialogfeld 'Räumliche Indizes' &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9973b-146">For information about the properties, see [Spatial Indexes Dialog Box &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
  
###  <a name="to-alter-a-spatial-index"></a><a name="alter"></a> <span data-ttu-id="9973b-147">So ändern Sie einen räumlichen Index</span><span class="sxs-lookup"><span data-stu-id="9973b-147">To alter a spatial index</span></span>  
  
-   [<span data-ttu-id="9973b-148">ALTER INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9973b-148">ALTER INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-index-transact-sql)  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="9973b-149">Zum Ändern von Optionen, die einem bestimmten räumlichen Index eigen sind, beispielsweise BOUNDING_BOX oder GRID, können Sie entweder eine CREATE SPATIAL INDEX-Anweisung mit der Angabe DROP_EXISTING = ON verwenden, oder Sie löschen den räumlichen Index und erstellen einen neuen räumlichen Index.</span><span class="sxs-lookup"><span data-stu-id="9973b-149">To change options that are specific to a spatial index, such as BOUNDING_BOX or GRID, you can either use a CREATE SPATIAL INDEX statement that specifies DROP_EXISTING = ON, or drop the spatial index and create a new one.</span></span> <span data-ttu-id="9973b-150">Für ein Beispiel gehen Sie unter [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9973b-150">For an example, see [CREATE SPATIAL INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-spatial-index-transact-sql).</span></span>  
  
-   [<span data-ttu-id="9973b-151">Ändern eines Indexes</span><span class="sxs-lookup"><span data-stu-id="9973b-151">Modify an Index</span></span>](../indexes/modify-an-index.md)  
  
-   [<span data-ttu-id="9973b-152">Verschieben eines vorhandenen Indexes in eine andere Dateigruppe</span><span class="sxs-lookup"><span data-stu-id="9973b-152">Move an Existing Index to a Different Filegroup</span></span>](../indexes/move-an-existing-index-to-a-different-filegroup.md)  
  
  
###  <a name="to-drop-a-spatial-index"></a><a name="drop"></a> <span data-ttu-id="9973b-153">So löschen Sie einen räumlichen Index</span><span class="sxs-lookup"><span data-stu-id="9973b-153">To drop a spatial index</span></span>  
 <span data-ttu-id="9973b-154">**So löschen Sie einen räumlichen Index mit Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="9973b-154">**To drop a spatial index by using Transact-SQL**</span></span>  
 [<span data-ttu-id="9973b-155">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9973b-155">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 <span data-ttu-id="9973b-156">**So löschen Sie einen Index mit Management Studio**</span><span class="sxs-lookup"><span data-stu-id="9973b-156">**To drop an index by using Management Studio**</span></span>  
 [<span data-ttu-id="9973b-157">Index löschen</span><span class="sxs-lookup"><span data-stu-id="9973b-157">Delete an Index</span></span>](../indexes/delete-an-index.md)  
  
 <span data-ttu-id="9973b-158">**So löschen Sie mit dem Tabellen-Designer in Management Studio einen räumlichen Index**</span><span class="sxs-lookup"><span data-stu-id="9973b-158">**To drop a spatial index by using Table Designer in Management Studio**</span></span>  
 ##### <a name="to-drop-a-spatial-index-in-table-designer"></a><span data-ttu-id="9973b-159">So löschen Sie einen räumlichen Index im Tabellen-Designer</span><span class="sxs-lookup"><span data-stu-id="9973b-159">To drop a spatial index in Table Designer</span></span>  
  
1.  <span data-ttu-id="9973b-160">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf die Tabelle mit dem räumlichen Index, den Sie löschen möchten, und klicken Sie anschließend auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="9973b-160">In Object Explorer, right-click the table with the spatial index you want to delete and click **Design**.</span></span>  
  
     <span data-ttu-id="9973b-161">Die Tabelle wird im Tabellen-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9973b-161">The table opens in Table Designer.</span></span>  
  
2.  <span data-ttu-id="9973b-162">Klicken Sie im Menü **Tabellen-Designer** auf **räumlicher Index**.</span><span class="sxs-lookup"><span data-stu-id="9973b-162">On the **Table Designer** menu, click **Spatial Index**.</span></span>  
  
     <span data-ttu-id="9973b-163">Das Dialogfeld **räumlicher Index** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9973b-163">The **Spatial Index** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="9973b-164">Klicken Sie in der Spalte **Ausgewählter räumlicher Index** auf den Index, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="9973b-164">Click the index you want to delete in the **Selected Spatial Index** column.</span></span>  
  
4.  <span data-ttu-id="9973b-165">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="9973b-165">Click **Delete**.</span></span>  
  
  
##  <a name="restrictions-on-spatial-indexes"></a><a name="restrictions"></a> <span data-ttu-id="9973b-166">Erstellen, Ändern und Löschen von räumlichen Indizes</span><span class="sxs-lookup"><span data-stu-id="9973b-166">Restrictions on Spatial Indexes</span></span>  
 <span data-ttu-id="9973b-167">Ein räumlicher Index kann nur für eine Spalte des Typs `geometry` oder `geography` erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9973b-167">A spatial index can be created only on a column of type `geometry` or `geography`.</span></span>  
  
### <a name="table-and-view-restrictions"></a><span data-ttu-id="9973b-168">Einschränkungen für Tabellen und Sichten</span><span class="sxs-lookup"><span data-stu-id="9973b-168">Table and View Restrictions</span></span>  
 <span data-ttu-id="9973b-169">Räumliche Indizes können nur für eine Tabelle definiert werden, die über einen Primärschlüssel verfügt.</span><span class="sxs-lookup"><span data-stu-id="9973b-169">Spatial indexes can be defined only on a table that has a primary key.</span></span> <span data-ttu-id="9973b-170">Die maximale Anzahl von Primärschlüsselspalten in einer Tabelle beträgt 15.</span><span class="sxs-lookup"><span data-stu-id="9973b-170">The maximum number of primary key columns on the table is 15.</span></span>  
  
 <span data-ttu-id="9973b-171">Die maximal zulässige Größe der Indexschlüsseldatensätze beträgt 895 Byte.</span><span class="sxs-lookup"><span data-stu-id="9973b-171">The maximum size of index key records is 895 bytes.</span></span> <span data-ttu-id="9973b-172">Eine Überschreitung dieser Größe verursacht ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="9973b-172">Larger sizes raise an error.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9973b-173">Primärschlüsselmetadaten können nicht geändert werden, während ein räumlicher Index für eine Tabelle definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9973b-173">Primary key metadata cannot be changed while a spatial index is defined on a table.</span></span>  
  
 <span data-ttu-id="9973b-174">Räumliche Indizes können nicht für indizierte Sichten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9973b-174">Spatial indexes cannot be specified on indexed views.</span></span>  
  
### <a name="multiple-spatial-index-restrictions"></a><span data-ttu-id="9973b-175">Einschränkungen für mehrere räumliche Indizes</span><span class="sxs-lookup"><span data-stu-id="9973b-175">Multiple Spatial Index Restrictions</span></span>  
 <span data-ttu-id="9973b-176">Sie können bis zu 249 räumliche Indizes für beliebige räumliche Spalten in einer unterstützten Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="9973b-176">You can create up to 249 spatial indexes on any of the spatial columns in a supported table.</span></span> <span data-ttu-id="9973b-177">Die Erstellung mehrerer räumlicher Indizes für dieselben räumlichen Spalten kann sinnvoll sein, beispielsweise um verschiedene Mosaikparameter in einer einzelnen Spalte zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="9973b-177">Creating more than one spatial index on the same spatial column can be useful, for example, to index different tessellation parameters in a single column.</span></span>  
  
 <span data-ttu-id="9973b-178">Sie können jeweils nur einen räumlichen Index erstellen.</span><span class="sxs-lookup"><span data-stu-id="9973b-178">You can create only one spatial index at a time.</span></span>  
  
### <a name="spatial-indexes-and-process-parallelism"></a><span data-ttu-id="9973b-179">Räumliche Indizes und Prozessparallelität</span><span class="sxs-lookup"><span data-stu-id="9973b-179">Spatial Indexes and Process Parallelism</span></span>  
 <span data-ttu-id="9973b-180">Bei der Indexerstellung kann die verfügbare Prozessparallelität genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="9973b-180">An index build can use available process parallelism.</span></span>  
  
### <a name="version-restrictions"></a><span data-ttu-id="9973b-181">Versionseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="9973b-181">Version Restrictions</span></span>  
 <span data-ttu-id="9973b-182">Räumliche Mosaike, die mit [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] eingeführt wurden, können nicht in [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] oder [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)]repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="9973b-182">Spatial tessellations introduced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] cannot be replicated to [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="9973b-183">Sie müssen räumliche Mosaike von [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] oder [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] für räumliche Indizes für die Abwärtskompatibilität mit [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] - oder [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] -Datenbanken verwenden.</span><span class="sxs-lookup"><span data-stu-id="9973b-183">You must use [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] spatial tessellations for spatial indexes when backward compatibility with [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] or [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] databases is a requirement.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="9973b-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9973b-184">See Also</span></span>  
 [<span data-ttu-id="9973b-185">Übersicht über räumliche Indizes</span><span class="sxs-lookup"><span data-stu-id="9973b-185">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
  
  
