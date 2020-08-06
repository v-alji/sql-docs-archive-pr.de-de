---
title: Dialogfeld 'Räumliche Indizes' (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.spatialindexes
ms.assetid: 4d84239a-68c7-4aa2-8602-2b51dd07260f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e401b7f93a8376b1c6dc0c75ca29cbdc8a39863d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617354"
---
# <a name="spatial-indexes-dialog-box-visual-database-tools"></a><span data-ttu-id="54a28-102">Dialogfeld 'Räumliche Indizes' (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="54a28-102">Spatial Indexes Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="54a28-103">Verwenden Sie das Dialogfeld **Räumliche Indizes** , um Indizes für Spalten des Datentyps **geometry** oder **geography** (*räumliche Spalten*) zu erstellen, denn diese können nicht mithilfe des Dialogfelds **Index/Schlüssel** indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="54a28-103">Use the **Spatial Indexes** dialog box to create indexes for columns of the **geometry** or **geography** data type (*spatial columns*), which cannot be indexed using the **Index/Keys** dialog box.</span></span> <span data-ttu-id="54a28-104">Jede räumliche Spalte kann mehr als einen räumlichen Index aufweisen, jedoch müssen sie einzeln erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="54a28-104">Each spatial column can have more than one spatial index, but they must be created one at a time.</span></span>  
  
 <span data-ttu-id="54a28-105">Weitere Informationen über die Einschränkungen bei der Erstellung von räumlichen Indizes finden Sie unter [Übersicht über räumliche Indizes](../../relational-databases/spatial/spatial-indexes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="54a28-105">For information about restrictions on spatial index creation, see [Spatial Indexes Overview](../../relational-databases/spatial/spatial-indexes-overview.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="54a28-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="54a28-106">Options</span></span>  
 <span data-ttu-id="54a28-107">**Ausgewählter räumlicher Index**</span><span class="sxs-lookup"><span data-stu-id="54a28-107">**Selected Spatial Index**</span></span>  
 <span data-ttu-id="54a28-108">Listet vorhandene räumliche Indizes auf.</span><span class="sxs-lookup"><span data-stu-id="54a28-108">Lists existing spatial indexes.</span></span> <span data-ttu-id="54a28-109">Wählen Sie einen Index aus, um dessen Eigenschaften anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="54a28-109">Select an index to show its properties.</span></span> <span data-ttu-id="54a28-110">Wenn die Liste leer ist, wurden bisher keine räumlichen Indizes für die Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="54a28-110">If the list is empty, no spatial indexes have been defined for the table.</span></span>  
  
 <span data-ttu-id="54a28-111">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="54a28-111">**Add**</span></span>  
 <span data-ttu-id="54a28-112">Erstellt einen neuen räumlichen Index.</span><span class="sxs-lookup"><span data-stu-id="54a28-112">Creates a new spatial index.</span></span>  
  
 <span data-ttu-id="54a28-113">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="54a28-113">**Delete**</span></span>  
 <span data-ttu-id="54a28-114">Löscht den in der Liste **Ausgewählter räumlicher Index** ausgewählten räumlichen Index.</span><span class="sxs-lookup"><span data-stu-id="54a28-114">Deletes the spatial index selected in the **Selected Spatial Index** list.</span></span>  
  
 <span data-ttu-id="54a28-115">**Zellen pro Objekt**</span><span class="sxs-lookup"><span data-stu-id="54a28-115">**Cells Per Object**</span></span>  
 <span data-ttu-id="54a28-116">Gibt die Anzahl von Zellen pro Objekt für das Mosaik an, die für ein einzelnes räumliches Objekt im Index verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="54a28-116">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="54a28-117">Bei dieser Zahl kann es sich um jede ganze Zahl von 1 bis 8192 handeln.</span><span class="sxs-lookup"><span data-stu-id="54a28-117">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="54a28-118">Der Standardwert ist 16.</span><span class="sxs-lookup"><span data-stu-id="54a28-118">The default is 16.</span></span>  
  
 <span data-ttu-id="54a28-119">Wenn ein Objekt mehr Zellen abdeckt, als durch *n*angegeben sind, werden bei der Indizierung so viele Zellen verwendet, wie zum Bereitstellen eines vollständigen Mosaiks der höchsten Ebene erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="54a28-119">If an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="54a28-120">In solchen Fällen ist es möglich, dass ein Objekt mehr als die angegebene Anzahl von Zellen erhält.</span><span class="sxs-lookup"><span data-stu-id="54a28-120">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="54a28-121">Die maximale Anzahl ist dann die Anzahl von Zellen, die von dem Raster der höchsten Ebene generiert wird, welche von der Dichte der **Ebene 1** abhängt.</span><span class="sxs-lookup"><span data-stu-id="54a28-121">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
 <span data-ttu-id="54a28-122">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="54a28-122">**Columns**</span></span>  
 <span data-ttu-id="54a28-123">Gibt den Spaltennamen und die Sortierreihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="54a28-123">Indicates the column name and sort order.</span></span>  
  
 <span data-ttu-id="54a28-124">**IsSpatialIndex**</span><span class="sxs-lookup"><span data-stu-id="54a28-124">**IsSpatialIndex**</span></span>  
 <span data-ttu-id="54a28-125">Gibt an, dass ein räumlicher Index ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-125">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="54a28-126">**Ebene 1**</span><span class="sxs-lookup"><span data-stu-id="54a28-126">**Level 1**</span></span>  
 <span data-ttu-id="54a28-127">Gibt die Dichte des Rasters der obersten (höchsten) Ebene an.</span><span class="sxs-lookup"><span data-stu-id="54a28-127">Indicates the density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="54a28-128">**Ebene 2**</span><span class="sxs-lookup"><span data-stu-id="54a28-128">**Level 2**</span></span>  
 <span data-ttu-id="54a28-129">Gibt die Dichte des Rasters der zweiten Ebene an.</span><span class="sxs-lookup"><span data-stu-id="54a28-129">Indicates the density of the second-level grid.</span></span>  
  
 <span data-ttu-id="54a28-130">**Ebene 3**</span><span class="sxs-lookup"><span data-stu-id="54a28-130">**Level 3**</span></span>  
 <span data-ttu-id="54a28-131">Gibt die Dichte des Rasters der dritten Ebene an.</span><span class="sxs-lookup"><span data-stu-id="54a28-131">Indicates the density of the third-level grid.</span></span>  
  
 <span data-ttu-id="54a28-132">**Ebene 4**</span><span class="sxs-lookup"><span data-stu-id="54a28-132">**Level 4**</span></span>  
 <span data-ttu-id="54a28-133">Gibt die Dichte des Rasters der vierten Ebene an.</span><span class="sxs-lookup"><span data-stu-id="54a28-133">Indicates the density of the fourth-level grid.</span></span>  
  
 <span data-ttu-id="54a28-134">**Mosaikschema**</span><span class="sxs-lookup"><span data-stu-id="54a28-134">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="54a28-135">Gibt das Mosaikschema an:</span><span class="sxs-lookup"><span data-stu-id="54a28-135">Indicates the tessellation scheme:</span></span>  
  
 <span data-ttu-id="54a28-136">**Geometriespaltenoptionen** :</span><span class="sxs-lookup"><span data-stu-id="54a28-136">**Geometry** column options:</span></span>  
  
-   <span data-ttu-id="54a28-137">**Geometrieraster** für eine Geometriespalte</span><span class="sxs-lookup"><span data-stu-id="54a28-137">**Geometry grid** for a geometry column</span></span>  
  
-   <span data-ttu-id="54a28-138">**Geografieraster** für eine Geografiespalte</span><span class="sxs-lookup"><span data-stu-id="54a28-138">**Geography grid** for a geography column</span></span>  
  
 <span data-ttu-id="54a28-139">**Typ**</span><span class="sxs-lookup"><span data-stu-id="54a28-139">**Type**</span></span>  
 <span data-ttu-id="54a28-140">Gibt an, dass ein räumlicher Index ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-140">Indicates that a spatial index is selected.</span></span>  
  
 <span data-ttu-id="54a28-141">**Maximaler X-Wert**</span><span class="sxs-lookup"><span data-stu-id="54a28-141">**X-max**</span></span>  
 <span data-ttu-id="54a28-142">Gibt die X-Koordinate der oberen rechten Ecke des Begrenzungsrahmens an.</span><span class="sxs-lookup"><span data-stu-id="54a28-142">Specifies the x-coordinate of the upper-right corner of the bounding box.</span></span> <span data-ttu-id="54a28-143">Diese Eigenschaft wird abgeblendet, wenn das **Mosaikschema** auf **Geografieraster**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-143">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="54a28-144">**Minimaler X-Wert**</span><span class="sxs-lookup"><span data-stu-id="54a28-144">**X-min**</span></span>  
 <span data-ttu-id="54a28-145">Gibt die X-Koordinate der unteren linken Ecke des umgebenden Felds an.</span><span class="sxs-lookup"><span data-stu-id="54a28-145">Specifies the x-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="54a28-146">Diese Eigenschaft wird abgeblendet, wenn das **Mosaikschema** auf **Geografieraster**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-146">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="54a28-147">**Maximaler Y-Wert**</span><span class="sxs-lookup"><span data-stu-id="54a28-147">**Y-max**</span></span>  
 <span data-ttu-id="54a28-148">Gibt die Y-Koordinate der oberen rechten Ecke des umgebenden Felds an.</span><span class="sxs-lookup"><span data-stu-id="54a28-148">Specifies the y-coordinate of upper-right corner of the bounding box.</span></span> <span data-ttu-id="54a28-149">Diese Eigenschaft wird abgeblendet, wenn das **Mosaikschema** auf **Geografieraster**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-149">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="54a28-150">**Minimaler Y-Wert**</span><span class="sxs-lookup"><span data-stu-id="54a28-150">**Y-min**</span></span>  
 <span data-ttu-id="54a28-151">Gibt die Y-Koordinate der unteren linken Ecke des umgebenden Felds an.</span><span class="sxs-lookup"><span data-stu-id="54a28-151">Specifies the y-coordinate of the lower-left corner of the bounding box.</span></span> <span data-ttu-id="54a28-152">Diese Eigenschaft wird abgeblendet, wenn das **Mosaikschema** auf **Geografieraster**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-152">This property is dimmed if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="54a28-153">**Identität**</span><span class="sxs-lookup"><span data-stu-id="54a28-153">**Identity**</span></span>  
 <span data-ttu-id="54a28-154">Wenn die Kategorie erweitert ist, werden die Eigenschaftenfelder für **Name** und **Beschreibung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54a28-154">When expanded, shows the **Name** and **Description** property fields.</span></span>  
  
 <span data-ttu-id="54a28-155">**(Name)**</span><span class="sxs-lookup"><span data-stu-id="54a28-155">**(Name)**</span></span>  
 <span data-ttu-id="54a28-156">Zeigt den Namen des räumlichen Indexes an.</span><span class="sxs-lookup"><span data-stu-id="54a28-156">Shows the name of the spatial index.</span></span> <span data-ttu-id="54a28-157">Wenn ein neuer Index erstellt wird, erhält dieser einen Standardnamen, der auf der Tabelle im aktiven Fenster des Tabellen-Designers basiert.</span><span class="sxs-lookup"><span data-stu-id="54a28-157">When a new index is created, it is given a default name based on the table in the active window in Table Designer.</span></span> <span data-ttu-id="54a28-158">Sie können den Namen jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="54a28-158">You can change the name at any time.</span></span>  
  
 <span data-ttu-id="54a28-159">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="54a28-159">**Description**</span></span>  
 <span data-ttu-id="54a28-160">Beschreibt den Index.</span><span class="sxs-lookup"><span data-stu-id="54a28-160">Describes the index.</span></span> <span data-ttu-id="54a28-161">Klicken Sie zum Erstellen einer detaillierteren Beschreibung auf **Beschreibung**, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten ( **…** ) rechts neben dem Eigenschaftenfeld.</span><span class="sxs-lookup"><span data-stu-id="54a28-161">To write a more detailed description, click **Description** and then click the ellipsis button (**...**) that appears to the right of the property field.</span></span> <span data-ttu-id="54a28-162">Dadurch wird ein größerer Bereich verfügbar, in den Sie Text eingeben können.</span><span class="sxs-lookup"><span data-stu-id="54a28-162">This provides a larger area in which to write text.</span></span>  
  
 <span data-ttu-id="54a28-163">**Kategorie Tabellen-Designer**</span><span class="sxs-lookup"><span data-stu-id="54a28-163">**Table Designer Category**</span></span>  
 <span data-ttu-id="54a28-164">Wenn die Kategorie erweitert ist, werden Informationen zu den Eigenschaften dieses räumlichen Indexes angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54a28-164">When expanded, shows information about the properties of this spatial index.</span></span>  
  
 <span data-ttu-id="54a28-165">**Füllspezifikation**</span><span class="sxs-lookup"><span data-stu-id="54a28-165">**Fill Specification**</span></span>  
 <span data-ttu-id="54a28-166">Wenn dieses Element erweitert ist, werden Informationen für **Füllfaktor** und **Index mit Leerstellen auffüllen**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54a28-166">When expanded, shows information for **Fill Factor** and **Pad Index**.</span></span>  
  
 <span data-ttu-id="54a28-167">**Füllfaktor**</span><span class="sxs-lookup"><span data-stu-id="54a28-167">**Fill Factor**</span></span>  
 <span data-ttu-id="54a28-168">Geben Sie an, zu welchem Prozentsatz die Indexseite vom System gefüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="54a28-168">Specify what percentage of the index page the system can fill.</span></span> <span data-ttu-id="54a28-169">Wenn eine Seite gefüllt ist, muss beim Hinzufügen neuer Daten die Seite geteilt werden. Dies beeinträchtigt die Leistung.</span><span class="sxs-lookup"><span data-stu-id="54a28-169">When a page is full, if new data is added, the system must split the page, which impairs performance.</span></span>  
  
-   <span data-ttu-id="54a28-170">Ein Wert von 100 bedeutet, dass die Seiten gefüllt werden. Diese Einstellung erfordert den geringsten Aufwand an Speicherplatz, ist aber auch am wenigsten effektiv.</span><span class="sxs-lookup"><span data-stu-id="54a28-170">A value of 100 means the pages will be full; this requires the least amount of storage space but is the least efficient.</span></span> <span data-ttu-id="54a28-171">Diese Einstellung sollte nur verwendet werden, wenn keine Änderungen an den Daten vorgenommen werden, zum Beispiel in einer schreibgeschützten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="54a28-171">This setting should be used only when there will be no changes to the data, for example, on a read-only table.</span></span>  
  
-   <span data-ttu-id="54a28-172">Durch einen niedrigeren Wert bleibt auf den Datenseiten ein größerer Bereich leer. Dadurch müssen die Datenseiten seltener geteilt werden, wenn Indizes größer werden.</span><span class="sxs-lookup"><span data-stu-id="54a28-172">A lower value leaves more empty space on the data pages, which reduces the need to split data pages as indexes grow.</span></span> <span data-ttu-id="54a28-173">Dies erfordert allerdings mehr Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="54a28-173">However, it requires more storage space.</span></span> <span data-ttu-id="54a28-174">Diese Einstellung empfiehlt sich eher, wenn Änderungen an den Daten in der Tabelle vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="54a28-174">This setting is more appropriate when there will be changes to the data in the table.</span></span>  
  
 <span data-ttu-id="54a28-175">**Index mit Leerstellen auffüllen**</span><span class="sxs-lookup"><span data-stu-id="54a28-175">**Pad Index**</span></span>  
 <span data-ttu-id="54a28-176">Stellt Seiten in diesem Index mit dem in **Füllfaktor**angegebenen Prozentsatz leeren Platzes (Auffüllung) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="54a28-176">Provides pages in this index the same percentage of empty space (padding) that is specified in **Fill Factor**.</span></span>  
  
 <span data-ttu-id="54a28-177">**Seitensperren sind zulässig**</span><span class="sxs-lookup"><span data-stu-id="54a28-177">**Page Locks Allowed**</span></span>  
 <span data-ttu-id="54a28-178">Gibt an, ob Sperren auf Seitenebene für diesen Index zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="54a28-178">Specifies whether page-level locking is allowed on this index.</span></span> <span data-ttu-id="54a28-179">Das Zulassen oder Untersagen von Sperren auf Seitenebene wirkt sich auf die Datenbankleistung aus.</span><span class="sxs-lookup"><span data-stu-id="54a28-179">Allowing or disallowing page-level locking affects database performance.</span></span>  
  
 <span data-ttu-id="54a28-180">**Statistiken neu berechnen**</span><span class="sxs-lookup"><span data-stu-id="54a28-180">**Re-compute  Statistics**</span></span>  
 <span data-ttu-id="54a28-181">Gibt an, ob beim Erstellen des Index neue Statistiken berechnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="54a28-181">Specifies whether to compute new statistics when the index is created.</span></span> <span data-ttu-id="54a28-182">Durch erneutes Berechnen von Statistiken wird die Erstellung der Indizes verlangsamt, die Abfrageleistung wird jedoch meist verbessert.</span><span class="sxs-lookup"><span data-stu-id="54a28-182">Recomputing statistics slows the building of indexes but usually improves query performance.</span></span>  
  
 <span data-ttu-id="54a28-183">**Zeilensperren sind zulässig**</span><span class="sxs-lookup"><span data-stu-id="54a28-183">**Row Locks Allowed**</span></span>  
 <span data-ttu-id="54a28-184">Gibt an, ob das Sperren auf Zeilenebene für diesen Index zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="54a28-184">Specifies whether row-level locking is allowed on this index.</span></span> <span data-ttu-id="54a28-185">Das Zulassen oder Untersagen von Sperren auf Zeilenebene wirkt sich auf die Datenbankleistung aus.</span><span class="sxs-lookup"><span data-stu-id="54a28-185">Allowing or disallowing row-level locking affects database performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a28-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54a28-186">See Also</span></span>  
 [<span data-ttu-id="54a28-187">Übersicht über räumliche Indizes</span><span class="sxs-lookup"><span data-stu-id="54a28-187">Spatial Indexes Overview</span></span>](../../relational-databases/spatial/spatial-indexes-overview.md)  
  
  
