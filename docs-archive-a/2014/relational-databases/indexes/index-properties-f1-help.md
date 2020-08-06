---
title: Indexeigenschaften (F1-Hilfe) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- sql12.swb.indexproperties.storage.f1
- sql12.swb.indexproperties.columns.f1
- sql12.swb.indexproperties.partitions.f1
- sql12.swb.indexproperties.general.f1
- sql12.swb.indexproperties.filter.f1
- sql12.swb.indexproperties.options.f1
- sql12.swb.indexproperties.spatial.f1
ms.assetid: 45efd81a-3796-4b04-b0cc-f3deec94c733
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 390a63d21dc72e052017f2d30b061d71de863bc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725722"
---
# <a name="index-properties-f1-help"></a><span data-ttu-id="df607-102">Indexeigenschaften (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="df607-102">Index Properties F1 Help</span></span>
  <span data-ttu-id="df607-103">In den Abschnitten dieses Themas werden verschiedene Indexeigenschaften beschrieben, die in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] -Dialogfeldern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="df607-103">The sections in this topic refer to various index properties that are available by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialogs.</span></span>  
  
 <span data-ttu-id="df607-104">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="df607-104">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="df607-105">Indexeigenschaften auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="df607-105">Index Properties General Page</span></span>](#General)  
  
 [<span data-ttu-id="df607-106">(Index-)spalten auswählen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="df607-106">Select (Index) Columns Dialog Box</span></span>](#Columns)  
  
 [<span data-ttu-id="df607-107">Indexeigenschaften auf der Seite "Speicher"</span><span class="sxs-lookup"><span data-stu-id="df607-107">Index Properties Storage Page</span></span>](#Storage)  
  
 [<span data-ttu-id="df607-108">Indexeigenschaften auf der Seite "Räumlich"</span><span class="sxs-lookup"><span data-stu-id="df607-108">Index Properties Spatial Page</span></span>](#Spatial)  
  
 [<span data-ttu-id="df607-109">Indexeigenschaften auf der Seite "Filter"</span><span class="sxs-lookup"><span data-stu-id="df607-109">Index Properties Filter Page</span></span>](#Filter)  
  
##  <a name="index-properties-general-page"></a><a name="General"></a> <span data-ttu-id="df607-110">Indexeigenschaften auf der Seite "Allgemein"</span><span class="sxs-lookup"><span data-stu-id="df607-110">Index Properties General Page</span></span>  
 <span data-ttu-id="df607-111">Auf der Seite Allgemein können Sie die Indexeigenschaften für die ausgewählte Tabelle oder Sicht anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="df607-111">Use the General page to view or modify index properties for the selected table or view.</span></span> <span data-ttu-id="df607-112">Die Optionen für jede Seite ändern sich möglicherweise abhängig vom ausgewählten Indextyp.</span><span class="sxs-lookup"><span data-stu-id="df607-112">The options for each page may change based on the type of index selected.</span></span>  
  
 <span data-ttu-id="df607-113">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="df607-113">**Table name**</span></span>  
 <span data-ttu-id="df607-114">Zeigt den Namen der Tabelle oder Sicht an, für die der Index erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="df607-114">Displays the name of the table or view that the index was created on.</span></span> <span data-ttu-id="df607-115">Dieses Feld ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="df607-115">This field is read-only.</span></span> <span data-ttu-id="df607-116">Um eine andere Tabelle auszuwählen, schließen Sie die Seite Indexeigenschaften, wählen Sie die richtige Tabelle aus, und öffnen Sie die Seite Indexeigenschaften erneut.</span><span class="sxs-lookup"><span data-stu-id="df607-116">To select a different table, close the Index Properties page, select the correct table, and then open the Index Properties page again.</span></span>  
  
 <span data-ttu-id="df607-117">Räumliche Indizes können nicht für indizierte Sichten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="df607-117">Spatial indexes cannot be specified on indexed views.</span></span> <span data-ttu-id="df607-118">Räumliche Indizes können nur für eine Tabelle definiert werden, die einen Primärschlüssel aufweist.</span><span class="sxs-lookup"><span data-stu-id="df607-118">Spatial indexes can be defined only for a table that has a primary key.</span></span> <span data-ttu-id="df607-119">Die maximale Anzahl von Primärschlüsselspalten in einer Tabelle beträgt 15.</span><span class="sxs-lookup"><span data-stu-id="df607-119">The maximum number of primary key columns on the table is 15.</span></span> <span data-ttu-id="df607-120">Die kombinierte Größe pro Zeile der Primärschlüsselspalten ist auf maximal 895 Bytes beschränkt.</span><span class="sxs-lookup"><span data-stu-id="df607-120">The combined per-row size of the primary-key columns is limited to a maximum of 895 bytes.</span></span>  
  
 <span data-ttu-id="df607-121">**Indexname**</span><span class="sxs-lookup"><span data-stu-id="df607-121">**Index name**</span></span>  
 <span data-ttu-id="df607-122">Zeigt den Namen des Indexes an.</span><span class="sxs-lookup"><span data-stu-id="df607-122">Displays the name of the index.</span></span> <span data-ttu-id="df607-123">Dieses Feld ist bei einem vorhandenen Index schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="df607-123">This field is read-only for an existing index.</span></span> <span data-ttu-id="df607-124">Wenn ein neuer Index erstellt wird, geben Sie den Namen des Indexes an.</span><span class="sxs-lookup"><span data-stu-id="df607-124">When creating a new index, type the name of the index.</span></span>  
  
 <span data-ttu-id="df607-125">**Indextyp**</span><span class="sxs-lookup"><span data-stu-id="df607-125">**Index type**</span></span>  
 <span data-ttu-id="df607-126">Gibt den Indextyp an.</span><span class="sxs-lookup"><span data-stu-id="df607-126">Indicates the type of index.</span></span> <span data-ttu-id="df607-127">Gibt bei neuen Indizes den Indextyp an, der beim Öffnen des Dialogfelds ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="df607-127">For new indexes, indicates the type of index selected when opening the dialog box.</span></span> <span data-ttu-id="df607-128">Indizes können folgende Typen aufweisen: **Gruppiert**, **Nicht gruppiert**, **Primäre XML**, **Sekundäre XML**, **Räumlich**, **Gruppierter Columnstore** oder **Nicht gruppierter Columnstore**.</span><span class="sxs-lookup"><span data-stu-id="df607-128">Indexes can be: **Clustered**, **Nonclustered**, **Primary XML**, **Secondary XML**, **Spatial**, **Clustered columnstore**, or **Nonclustered Columnstore**.</span></span>  
  
 <span data-ttu-id="df607-129">**Hinweis** Es ist nur ein gruppierter Index pro Tabelle zulässig.</span><span class="sxs-lookup"><span data-stu-id="df607-129">**Note** Only one clustered index is allowed for each table.</span></span> <span data-ttu-id="df607-130">Pro Tabelle ist nur ein speicheroptimierter xVelocity-columnstore-Index zulässig.</span><span class="sxs-lookup"><span data-stu-id="df607-130">Only one xVelocity memory optimized columnstore index is allowed for each table.</span></span>  
  
 <span data-ttu-id="df607-131">**Eindeutig**</span><span class="sxs-lookup"><span data-stu-id="df607-131">**Unique**</span></span>  
 <span data-ttu-id="df607-132">Durch Aktivierung dieses Kontrollkästchens wird der Index zu einem eindeutigen Index gemacht.</span><span class="sxs-lookup"><span data-stu-id="df607-132">Selecting this check box makes the index unique.</span></span> <span data-ttu-id="df607-133">Zwei Zeilen mit demselben Wert sind dann nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="df607-133">No two rows are permitted to have the same index value.</span></span> <span data-ttu-id="df607-134">Standardmäßig ist dieses Kontrollkästchen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="df607-134">By default, this check box is cleared.</span></span> <span data-ttu-id="df607-135">Wenn beim Ändern eines vorhandenen Indexes zwei Zeilen denselben Wert aufweisen, schlägt die Indexerstellung fehl.</span><span class="sxs-lookup"><span data-stu-id="df607-135">When modifying an existing index, index creation will fail if two rows have the same value.</span></span> <span data-ttu-id="df607-136">In Spalten, in denen NULL-Werte zulässig sind, ist bei einem eindeutigen Index ein NULL-Wert zulässig.</span><span class="sxs-lookup"><span data-stu-id="df607-136">For columns where NULL is permitted, a unique index permits one NULL value.</span></span>  
  
 <span data-ttu-id="df607-137">Wenn Sie im Feld **Indextyp** die Option **Räumlich** auswählen, ist das Kontrollkästchen **Eindeutig** abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="df607-137">If you select **Spatial** in the **Index type** field, the **Unique** check box is dimmed.</span></span>  
  
 <span data-ttu-id="df607-138">**Indexschlüsselspalten**</span><span class="sxs-lookup"><span data-stu-id="df607-138">**Index key columns**</span></span>  
 <span data-ttu-id="df607-139">Fügt die gewünschten Spalten dem Raster **Indexschlüsselspalten** hinzu.</span><span class="sxs-lookup"><span data-stu-id="df607-139">Add the desired columns to the **Index key columns** grid.</span></span> <span data-ttu-id="df607-140">Wenn mehr als eine Spalte hinzugefügt wird, müssen die Spalten in der gewünschten Reihenfolge aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="df607-140">When more than one column is added, the columns must be listed in the order desired.</span></span> <span data-ttu-id="df607-141">Die Spaltenreihenfolge in einem Index kann einen großen Einfluss auf die Leistung des Indexes haben.</span><span class="sxs-lookup"><span data-stu-id="df607-141">The column order in an index can have a great impact on the index performance.</span></span>  
  
 <span data-ttu-id="df607-142">Es können nicht mehr als 16 Spalten an einem einzelnen zusammengesetzten Index beteiligt sein.</span><span class="sxs-lookup"><span data-stu-id="df607-142">No more than 16 columns can participate in a single composite index.</span></span> <span data-ttu-id="df607-143">Im Fall von mehr als 16 Spalten finden Sie weitere Informationen am Ende dieses Themas unter "Eingeschlossene Spalten".</span><span class="sxs-lookup"><span data-stu-id="df607-143">For greater than 16 columns, see included columns at the end of this topic.</span></span>  
  
 <span data-ttu-id="df607-144">Ein räumlicher Index kann nur für eine einzelne Spalte definiert werden, die einen räumlichen Datentyp aufweist (eine *räumliche Spalte*).</span><span class="sxs-lookup"><span data-stu-id="df607-144">A spatial index can be defined only on a single column that contains a spatial data type (a *spatial column*).</span></span>  
  
 <span data-ttu-id="df607-145">**Name**</span><span class="sxs-lookup"><span data-stu-id="df607-145">**Name**</span></span>  
 <span data-ttu-id="df607-146">Zeigt den Namen der Spalte an, die am Indexschlüssel beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="df607-146">Displays the name of the column that participates in the index key.</span></span>  
  
 <span data-ttu-id="df607-147">**Sortierreihenfolge**</span><span class="sxs-lookup"><span data-stu-id="df607-147">**Sort Order**</span></span>  
 <span data-ttu-id="df607-148">Gibt die Sortierreihenfolge der ausgewählten Indexspalte an, entweder **Aufsteigend** oder **Absteigend**.</span><span class="sxs-lookup"><span data-stu-id="df607-148">Specifies the sort direction of the selected index column, either **Ascending** or **Descending**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df607-149">Wenn der Indextyp **Primär-XML** oder **Räumlich**ist, wird diese Spalte nicht in der Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="df607-149">If the index type is **Primary XML** or **Spatial**, this column does not appear in the table.</span></span>  
  
 <span data-ttu-id="df607-150">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="df607-150">**Data Type**</span></span>  
 <span data-ttu-id="df607-151">Zeigt die Datentypinformationen an.</span><span class="sxs-lookup"><span data-stu-id="df607-151">Displays the data type information.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df607-152">Wenn die Tabellenspalte eine berechnete Spalte ist, wird unter **Datentyp** "berechnete Spalte" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df607-152">If the table column is a computed column, **Data type** displays "computed column."</span></span>  
  
 <span data-ttu-id="df607-153">**Größe**</span><span class="sxs-lookup"><span data-stu-id="df607-153">**Size**</span></span>  
 <span data-ttu-id="df607-154">Zeigt die maximale Anzahl von Bytes an, die für das Speichern der Spaltendatentypen benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="df607-154">Displays the maximum number of bytes required to store the column data type.</span></span> <span data-ttu-id="df607-155">Zeigt eine Null (0) für eine räumliche oder XML-Spalte an.</span><span class="sxs-lookup"><span data-stu-id="df607-155">Displays zero (0) for a spatial or XML column.</span></span>  
  
 <span data-ttu-id="df607-156">**Identität**</span><span class="sxs-lookup"><span data-stu-id="df607-156">**Identity**</span></span>  
 <span data-ttu-id="df607-157">Zeigt an, ob die am Indexschlüssel beteiligte Spalte eine Identitätsspalte ist.</span><span class="sxs-lookup"><span data-stu-id="df607-157">Displays whether the column participating in the index key is an identity column.</span></span>  
  
 <span data-ttu-id="df607-158">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="df607-158">**Allow NULLs**</span></span>  
 <span data-ttu-id="df607-159">Zeigt an, ob in der am Indexschlüssel beteiligten Spalte NULL-Werte in der Tabellen- oder Sichtspalte gespeichert werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="df607-159">Displays whether the column participating in the index key allows NULL values to be stored in the table or view column.</span></span>  
  
 <span data-ttu-id="df607-160">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="df607-160">**Add**</span></span>  
 <span data-ttu-id="df607-161">Fügt dem Indexschlüssel eine Spalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="df607-161">Adds a column to the index key.</span></span> <span data-ttu-id="df607-162">Wählen Sie im Dialogfeld **Spalten auswählen aus** *\<table name>* Tabellenspalten aus. Dieses Dialogfeld wird angezeigt, wenn Sie auf **Hinzufügen** klicken.</span><span class="sxs-lookup"><span data-stu-id="df607-162">Select table columns from the **Select Columns from** *\<table name>* dialog box that appears when you click **Add**.</span></span> <span data-ttu-id="df607-163">Wenn Sie eine Spalte ausgewählt haben, ist diese Schaltfläche bei einem räumlichen Index abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="df607-163">For a spatial index, after you select one column, this button is dimmed.</span></span>  
  
 <span data-ttu-id="df607-164">**Remove**</span><span class="sxs-lookup"><span data-stu-id="df607-164">**Remove**</span></span>  
 <span data-ttu-id="df607-165">Entfernt die ausgewählte Spalte aus der Beteiligung am Indexschlüssel.</span><span class="sxs-lookup"><span data-stu-id="df607-165">Removes the selected column from participation in the index key.</span></span>  
  
 <span data-ttu-id="df607-166">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="df607-166">**Move Up**</span></span>  
 <span data-ttu-id="df607-167">Verschiebt die ausgewählte Spalte im Indexschlüsselraster nach oben.</span><span class="sxs-lookup"><span data-stu-id="df607-167">Moves the selected column up in the index key grid.</span></span>  
  
 <span data-ttu-id="df607-168">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="df607-168">**Move Down**</span></span>  
 <span data-ttu-id="df607-169">Verschiebt die ausgewählte Spalte im Indexschlüsselraster nach unten.</span><span class="sxs-lookup"><span data-stu-id="df607-169">Moves the selected column down in the index key grid.</span></span>  
  
 <span data-ttu-id="df607-170">**columnstore-Spalten**</span><span class="sxs-lookup"><span data-stu-id="df607-170">**Columnstore columns**</span></span>  
 <span data-ttu-id="df607-171">Klicken Sie auf **Hinzufügen** , um Spalten für den columnstore-Index auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="df607-171">Click **Add** to select columns for the columnstore index.</span></span> <span data-ttu-id="df607-172">Einschränkungen für einen Columnstore-Index finden Sie unter [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="df607-172">For limitations on a columnstore index, see [CREATE COLUMNSTORE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-columnstore-index-transact-sql).</span></span>  
  
 <span data-ttu-id="df607-173">**Eingeschlossene Spalten**</span><span class="sxs-lookup"><span data-stu-id="df607-173">**Included columns**</span></span>  
 <span data-ttu-id="df607-174">Nimmt Nichtschlüsselspalten in den nicht gruppierten Index auf.</span><span class="sxs-lookup"><span data-stu-id="df607-174">Include nonkey columns in the nonclustered index.</span></span> <span data-ttu-id="df607-175">Mit dieser Option können Sie die aktuellen Indexgrenzwerte hinsichtlich der Gesamtgröße eines Indexschlüssels und der maximalen Anzahl der Spalten in einem Indexschlüssel umgehen, indem Sie Spalten auf Blattebene eines nicht gruppierten Indexes als Nichtschlüsselspalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="df607-175">This option allows you to bypass the current index limits on the total size of an index key and the maximum number of columns participating in an index key by adding columns as nonkey columns in the leaf level of the nonclustered index.</span></span> <span data-ttu-id="df607-176">Weitere Informationen finden Sie unter [Erstellen von Indizes mit eingeschlossenen Spalten](create-indexes-with-included-columns.md).</span><span class="sxs-lookup"><span data-stu-id="df607-176">For more information, see [Create Indexes with Included Columns](create-indexes-with-included-columns.md)</span></span>  
  
##  <a name="select-index-columns-dialog-box"></a><a name="Columns"></a> <span data-ttu-id="df607-177">(Index-)spalten auswählen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="df607-177">Select (Index) Columns Dialog Box</span></span>  
 <span data-ttu-id="df607-178">Mithilfe dieser Seite können Sie der Seite **Indexeigenschaften, Allgemein** beim Erstellen oder Ändern eines Indexes Spalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="df607-178">Use this page to add columns to the **Index Properties General** page when creating or modifying an index.</span></span>  
  
 <span data-ttu-id="df607-179">**Kontrollkästchen**</span><span class="sxs-lookup"><span data-stu-id="df607-179">**Check box**</span></span>  
 <span data-ttu-id="df607-180">Aktivieren Sie diese Option, um Spalten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="df607-180">Select to add columns.</span></span>  
  
 <span data-ttu-id="df607-181">**Name**</span><span class="sxs-lookup"><span data-stu-id="df607-181">**Name**</span></span>  
 <span data-ttu-id="df607-182">Name der Spalte.</span><span class="sxs-lookup"><span data-stu-id="df607-182">Name of the column.</span></span>  
  
 <span data-ttu-id="df607-183">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="df607-183">**Data Type**</span></span>  
 <span data-ttu-id="df607-184">Der Datentyp der Spalte.</span><span class="sxs-lookup"><span data-stu-id="df607-184">The data type of the column.</span></span>  
  
 <span data-ttu-id="df607-185">**Byte**</span><span class="sxs-lookup"><span data-stu-id="df607-185">**Bytes**</span></span>  
 <span data-ttu-id="df607-186">Die Größe der Spalte in Bytes.</span><span class="sxs-lookup"><span data-stu-id="df607-186">The size of the column in bytes.</span></span>  
  
 <span data-ttu-id="df607-187">**Identität**</span><span class="sxs-lookup"><span data-stu-id="df607-187">**Identity**</span></span>  
 <span data-ttu-id="df607-188">Zeigt bei Identitätsspalten **Ja** an. Wenn die Spalte keine Identitätsspalte ist, wird **Nein** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df607-188">Displays **Yes** for identity columns, and **No** when the column is not an identity column.</span></span>  
  
 <span data-ttu-id="df607-189">**NULL-Werte zulassen**</span><span class="sxs-lookup"><span data-stu-id="df607-189">**Allow Nulls**</span></span>  
 <span data-ttu-id="df607-190">Zeigt **Ja** an, wenn die Tabellendefinition für die Spalte NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="df607-190">Displays **Yes** when the table definition allows null values for the column.</span></span> <span data-ttu-id="df607-191">Zeigt **Nein** an, wenn die Tabellendefinition für die Spalte keine NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="df607-191">Displays **No** when the table definition does not allow nulls for the column.</span></span>  
  
##  <a name="storage-page-options"></a><a name="Storage"></a> <span data-ttu-id="df607-192">Optionen auf der Seite "Speicher"</span><span class="sxs-lookup"><span data-stu-id="df607-192">Storage Page Options</span></span>  
 <span data-ttu-id="df607-193">Auf dieser Seite können Sie Dateigruppen- bzw. Partitionsschemaeigenschaften für den ausgewählten Index anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="df607-193">Use this page to view or modify filegroup or partition scheme properties for the selected index.</span></span> <span data-ttu-id="df607-194">Zeigt nur Optionen in Zusammenhang mit dem Indextyp an.</span><span class="sxs-lookup"><span data-stu-id="df607-194">Only shows options related to the type of index.</span></span>  
  
 <span data-ttu-id="df607-195">**Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="df607-195">**Filegroup**</span></span>  
 <span data-ttu-id="df607-196">Speichert den Index in der angegebenen Dateigruppe.</span><span class="sxs-lookup"><span data-stu-id="df607-196">Stores the index in the specified filegroup.</span></span> <span data-ttu-id="df607-197">Diese Liste enthält nur Standarddateigruppen (ROW).</span><span class="sxs-lookup"><span data-stu-id="df607-197">The list only displays standard (row) filegroups.</span></span> <span data-ttu-id="df607-198">Die Standardauswahl in der Liste ist die PRIMARY-Dateigruppe der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="df607-198">The default list selection is the PRIMARY filegroup of the database.</span></span> <span data-ttu-id="df607-199">Weitere Informationen finden Sie unter [Datenbankdateien und Dateigruppen](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="df607-199">For more information, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
 <span data-ttu-id="df607-200">**FILESTREAM-Dateigruppe**</span><span class="sxs-lookup"><span data-stu-id="df607-200">**Filestream filegroup**</span></span>  
 <span data-ttu-id="df607-201">Gibt die Dateigruppe für FILESTREAM-Daten an.</span><span class="sxs-lookup"><span data-stu-id="df607-201">Specifies the filegroup for FILESTREAM data.</span></span> <span data-ttu-id="df607-202">Diese Liste zeigt nur FILESTREAM-Dateigruppen an.</span><span class="sxs-lookup"><span data-stu-id="df607-202">This list displays only FILESTREAM filegroups.</span></span> <span data-ttu-id="df607-203">Die Standardlistenauswahl ist die Dateigruppe PRIMARY FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="df607-203">The default list selection is the PRIMARY FILESTREAM filegroup.</span></span> <span data-ttu-id="df607-204">Weitere Informationen finden Sie unter [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="df607-204">For more information, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
 <span data-ttu-id="df607-205">**Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="df607-205">**Partition scheme**</span></span>  
 <span data-ttu-id="df607-206">Speichert den Index in einem Partitionsschema.</span><span class="sxs-lookup"><span data-stu-id="df607-206">Stores the index in a partition scheme.</span></span> <span data-ttu-id="df607-207">Wenn Sie auf **Partitionsschema** klicken, wird das unten stehende Raster aktiviert.</span><span class="sxs-lookup"><span data-stu-id="df607-207">Clicking **Partition Scheme** enables the grid below.</span></span> <span data-ttu-id="df607-208">Die Standardlistenauswahl ist das für das Speichern der Tabellendaten verwendete Partitionsschema.</span><span class="sxs-lookup"><span data-stu-id="df607-208">The default list selection is the partition scheme that is used for storing the table data.</span></span> <span data-ttu-id="df607-209">Bei Auswahl eines anderen Partitionsschemas in der Liste werden die im Raster angezeigten Informationen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="df607-209">When you select a different partition scheme in the list, the information in the grid is updated.</span></span> <span data-ttu-id="df607-210">Weitere Informationen finden Sie unter [partitionierte Tabellen und Indizes](../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="df607-210">For more information, see [Partitioned Tables and Indexes](../partitions/partitioned-tables-and-indexes.md).</span></span>  
  
 <span data-ttu-id="df607-211">Die Option Partitionsschema ist nicht verfügbar, wenn in der Datenbank keine Partitionsschemas vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="df607-211">The partition scheme option is unavailable if there are no partition schemes in the database.</span></span>  
  
 <span data-ttu-id="df607-212">**Dateidatenstrom-Partitionsschema**</span><span class="sxs-lookup"><span data-stu-id="df607-212">**Filestream partition scheme**</span></span>  
 <span data-ttu-id="df607-213">Gibt das Partitionsschema für FILESTREAM-Daten an.</span><span class="sxs-lookup"><span data-stu-id="df607-213">Specifies the partition scheme for FILESTREAM data.</span></span> <span data-ttu-id="df607-214">Das Partitionsschema muss mit dem Schema symmetrisch sein, das in der Option **Partitionsschema** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="df607-214">The partition scheme must be symmetric with the scheme that is specified in the **Partition scheme** option.</span></span>  
  
 <span data-ttu-id="df607-215">Wenn die Tabelle nicht partitioniert ist, ist das Feld leer.</span><span class="sxs-lookup"><span data-stu-id="df607-215">If the table is not partitioned, the field is blank.</span></span>  
  
 <span data-ttu-id="df607-216">**Partitionsschemaparameter**</span><span class="sxs-lookup"><span data-stu-id="df607-216">**Partition Scheme Parameter**</span></span>  
 <span data-ttu-id="df607-217">Zeigt den Namen der Spalte an, die Teil des Partitionsschemas ist.</span><span class="sxs-lookup"><span data-stu-id="df607-217">Displays the name of the column that participates in the partition scheme.</span></span>  
  
 <span data-ttu-id="df607-218">**Tabellenspalte**</span><span class="sxs-lookup"><span data-stu-id="df607-218">**Table Column**</span></span>  
 <span data-ttu-id="df607-219">Wählt die Tabelle oder Sicht aus, die dem Partitionsschema zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="df607-219">Select the table or view to map to the partition scheme.</span></span>  
  
 <span data-ttu-id="df607-220">**Datentyp der Spalte**</span><span class="sxs-lookup"><span data-stu-id="df607-220">**Column Data Type**</span></span>  
 <span data-ttu-id="df607-221">Zeigt Datentypinformationen zu der Spalte an.</span><span class="sxs-lookup"><span data-stu-id="df607-221">Displays data type information about the column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df607-222">Wenn die Tabellenspalte eine berechnete Spalte ist, wird unter **Spaltendatentyp** „berechnete Spalte“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df607-222">If the table column is a computed column, **Column Data Type** displays "computed column."</span></span>  
  
 <span data-ttu-id="df607-223">**Onlineverarbeitung von DML-Anweisungen während der Indexverschiebung zulassen**</span><span class="sxs-lookup"><span data-stu-id="df607-223">**Allow online processing of DML statements while moving the index**</span></span>  
 <span data-ttu-id="df607-224">Ermöglicht Benutzern während des Indexvorgangs den Zugriff auf die zugrunde liegenden Tabellen- bzw. gruppierten Indexdaten und zugehörigen nicht gruppierten Indizes.</span><span class="sxs-lookup"><span data-stu-id="df607-224">Allows users to access the underlying table or clustered index data and any associated nonclustered indexes during the index operation.</span></span> <span data-ttu-id="df607-225">Weitere Informationen finden Sie unter [Ausführen von Onlineindexvorgängen](perform-index-operations-online.md) .</span><span class="sxs-lookup"><span data-stu-id="df607-225">For more information, see [Perform Index Operations Online](perform-index-operations-online.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df607-226">Diese Option ist für XML-Indizes nicht verfügbar. Das gilt auch, wenn der Index ein deaktivierter gruppierter Index ist.</span><span class="sxs-lookup"><span data-stu-id="df607-226">This option is not available for XML indexes, or if the index is a disabled clustered index.</span></span>  
  
 <span data-ttu-id="df607-227">**Maximalen Grad an Parallelität festlegen**</span><span class="sxs-lookup"><span data-stu-id="df607-227">**Set maximum degree of parallelism**</span></span>  
 <span data-ttu-id="df607-228">Begrenzt die Anzahl der bei der Ausführung paralleler Pläne einzusetzenden Prozessoren.</span><span class="sxs-lookup"><span data-stu-id="df607-228">Limits the number of processors to use during parallel plan execution.</span></span> <span data-ttu-id="df607-229">Der Standardwert ist 0; bei diesem Wert wird die tatsächliche Anzahl der verfügbaren CPUs verwendet.</span><span class="sxs-lookup"><span data-stu-id="df607-229">The default value, 0, uses the actual number of available CPUs.</span></span> <span data-ttu-id="df607-230">Wenn Sie den Wert auf 1 setzen, wird die Ausführung paralleler Pläne unterdrückt; bei einem Wert von größer als 1 wird die maximale Anzahl der bei der Ausführung einer einzelnen Abfrage zu verwendenden Prozessoren begrenzt.</span><span class="sxs-lookup"><span data-stu-id="df607-230">Setting the value to 1 suppresses parallel plan generation; setting the value to a number greater than 1 restricts the maximum number of processors used by a single query execution.</span></span> <span data-ttu-id="df607-231">Diese Option ist nur verfügbar, wenn sich das Dialogfeld im Status **Neu organisieren** oder **Neu erstellen** befindet.</span><span class="sxs-lookup"><span data-stu-id="df607-231">This option only becomes available if the dialog box is in the **Rebuild** or **Recreate** state.</span></span> <span data-ttu-id="df607-232">Weitere Informationen finden Sie unter [Festlegen der 'Max. Grad an Parallelität'-Option auf optimale Leistung](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span><span class="sxs-lookup"><span data-stu-id="df607-232">For more information, see [Set the Max Degree of Parallelism Option for Optimal Performance](../policy-based-management/set-the-max-degree-of-parallelism-option-for-optimal-performance.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="df607-233">Wird ein Wert angegeben, der über der Anzahl der verfügbaren CPUs liegt, wird die tatsächliche Anzahl der CPUs verwendet.</span><span class="sxs-lookup"><span data-stu-id="df607-233">If a value greater than the number of available CPUs is specified, the actual number of available CPUs is used.</span></span>  
  
##  <a name="spatial-page-index-options"></a><a name="Spatial"></a> <span data-ttu-id="df607-234">Indexoptionen auf der Seite "Räumlich"</span><span class="sxs-lookup"><span data-stu-id="df607-234">Spatial Page Index Options</span></span>  
 <span data-ttu-id="df607-235">Auf der Seite **Räumlich** können Sie die Werte der räumlichen Eigenschaften anzeigen oder angeben.</span><span class="sxs-lookup"><span data-stu-id="df607-235">Use the **Spatial** page to view or specify the values of the spatial properties.</span></span> <span data-ttu-id="df607-236">Weitere Informationen finden Sie unter [Räumliche Daten &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="df607-236">For more information, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
### <a name="bounding-box"></a><span data-ttu-id="df607-237">Umgebendes Feld</span><span class="sxs-lookup"><span data-stu-id="df607-237">Bounding Box</span></span>  
 <span data-ttu-id="df607-238">Das *umgebende Feld* ist der Umkreis des Rasters der höchsten Ebene einer geometrischen Ebene.</span><span class="sxs-lookup"><span data-stu-id="df607-238">The *bounding box* is the perimeter of the top-level grid of a geometric plane.</span></span> <span data-ttu-id="df607-239">Die Parameter für das umgebende Feld sind nur im Geometrierastermosaik vorhanden.</span><span class="sxs-lookup"><span data-stu-id="df607-239">The bounding-box parameters exist only in the geometry grid tessellation.</span></span> <span data-ttu-id="df607-240">Diese Parameter sind nicht verfügbar, wenn das **Mosaikschema** auf **Geografieraster**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="df607-240">These parameters are unavailable if the **Tessellation Scheme** is **Geography grid**.</span></span>  
  
 <span data-ttu-id="df607-241">Der Bereich zeigt die Koordinaten **( *`X-min`* , *`Y-min`* )** und **( *`X-max`* , *`Y-max`* )** des umgebenden Felds an.</span><span class="sxs-lookup"><span data-stu-id="df607-241">The panel displays the **(*`X-min`*,*`Y-min`*)** and **(*`X-max`*,*`Y-max`*)** coordinates of the bounding box.</span></span> <span data-ttu-id="df607-242">Es gibt keine Standardkoordinatenwerte.</span><span class="sxs-lookup"><span data-stu-id="df607-242">There are no default coordinate values.</span></span> <span data-ttu-id="df607-243">Daher müssen Sie die Koordinatenwerte angeben, wenn Sie einen neuen räumlichen Index für eine Spalte vom Typ `geometry` erstellen.</span><span class="sxs-lookup"><span data-stu-id="df607-243">Therefore, when you are creating a new spatial index on a `geometry` type column, you must specify the coordinate values.</span></span>  
  
 `X-min`  
 <span data-ttu-id="df607-244">Die X-Koordinate der unteren linken Ecke des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="df607-244">The X-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `Y-min`  
 <span data-ttu-id="df607-245">Die Y-Koordinate der unteren linken Ecke des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="df607-245">The Y-coordinate of the lower-left corner of the bounding box.</span></span>  
  
 `X-max`  
 <span data-ttu-id="df607-246">Die X-Koordinate der oberen rechten Ecke des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="df607-246">The X-coordinate of the upper-right corner of the bounding box.</span></span>  
  
 `Y-max`  
 <span data-ttu-id="df607-247">Die Y-Koordinate der oberen rechten Ecke des umgebenden Felds.</span><span class="sxs-lookup"><span data-stu-id="df607-247">The Y-coordinate of upper-right corner of the bounding box.</span></span>  
  
### <a name="general"></a><span data-ttu-id="df607-248">Allgemein</span><span class="sxs-lookup"><span data-stu-id="df607-248">General</span></span>  
 <span data-ttu-id="df607-249">**Mosaikschema**</span><span class="sxs-lookup"><span data-stu-id="df607-249">**Tessellation Scheme**</span></span>  
 <span data-ttu-id="df607-250">Gibt das Mosaikschema für den Index an.</span><span class="sxs-lookup"><span data-stu-id="df607-250">Indicates the tessellation scheme of the index.</span></span> <span data-ttu-id="df607-251">Folgende Mosaikschemas werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="df607-251">The supported tessellation schemes are as follows.</span></span>  
  
 <span data-ttu-id="df607-252">**Geometrieraster**</span><span class="sxs-lookup"><span data-stu-id="df607-252">**Geometry grid**</span></span>  
 <span data-ttu-id="df607-253">Gibt das Mosaikschema für das Geometrieraster an, das für eine Spalte mit dem Datentyp `geometry` gilt.</span><span class="sxs-lookup"><span data-stu-id="df607-253">Specifies the geometry grid tessellation scheme, which applies to a column of the `geometry` data type.</span></span>  
  
 <span data-ttu-id="df607-254">**Automatisches Geometrieraster**</span><span class="sxs-lookup"><span data-stu-id="df607-254">**Geometry Auto grid**</span></span>  
 <span data-ttu-id="df607-255">Diese Option wird für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aktiviert, wenn der Datenbank-Kompatibilitätsgrad auf 110 oder höher festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="df607-255">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="df607-256">**Geografieraster**</span><span class="sxs-lookup"><span data-stu-id="df607-256">**Geography grid**</span></span>  
 <span data-ttu-id="df607-257">Gibt das Mosaikschema für das Geografieraster an, das für eine Spalte mit dem Datentyp **geography** gilt.</span><span class="sxs-lookup"><span data-stu-id="df607-257">Specifies the geography grid tessellation scheme, which applies to a column of the **geography** data type.</span></span>  
  
 <span data-ttu-id="df607-258">**Automatisches Geografieraster**</span><span class="sxs-lookup"><span data-stu-id="df607-258">**Geography Auto grid**</span></span>  
 <span data-ttu-id="df607-259">Diese Option wird für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aktiviert, wenn der Datenbank-Kompatibilitätsgrad auf 110 oder höher festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="df607-259">This option is enabled for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="df607-260">Informationen darüber, wie in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ein Mosaik implementiert wird, finden Sie unter [Räumliche Daten &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="df607-260">For information about how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] implements tessellation, see [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="df607-261">**Zellen pro Objekt**</span><span class="sxs-lookup"><span data-stu-id="df607-261">**Cells Per Object**</span></span>  
 <span data-ttu-id="df607-262">Gibt die Anzahl von Zellen pro Objekt für das Mosaik an, die für ein einzelnes räumliches Objekt im Index verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="df607-262">Indicates the number of tessellation cells-per-object that can be used for a single spatial object in the index.</span></span> <span data-ttu-id="df607-263">Bei dieser Zahl kann es sich um jede ganze Zahl von 1 bis 8192 handeln.</span><span class="sxs-lookup"><span data-stu-id="df607-263">This number can be any integer between 1 and 8192, inclusive.</span></span> <span data-ttu-id="df607-264">Der Standardwert ist 16. Der Wert lautet 8 für frühere Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , wenn der Datenbank-Kompatibilitätsgrad auf 110 oder höher festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="df607-264">The default is 16, and 8 for earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] when database compatibility level is set to 110 or higher.</span></span>  
  
 <span data-ttu-id="df607-265">Auf höchster Ebene verwendet die Indizierung die Anzahl von Zellen, die zum Bereitstellen eines vollständigen Mosaiks der höchsten Ebene erforderlich sind, wenn ein Objekt mehr Zellen abdeckt, als durch *n*angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="df607-265">At the top level, if an object covers more cells than specified by *n*, the indexing uses as many cells as necessary to provide a complete top-level tessellation.</span></span> <span data-ttu-id="df607-266">In solchen Fällen ist es möglich, dass ein Objekt mehr als die angegebene Anzahl von Zellen erhält.</span><span class="sxs-lookup"><span data-stu-id="df607-266">In such cases, an object might receive more than the specified number of cells.</span></span> <span data-ttu-id="df607-267">Die maximale Anzahl ist dann die Anzahl von Zellen, die von dem Raster der höchsten Ebene generiert wird, welche von der Dichte der **Ebene 1** abhängt.</span><span class="sxs-lookup"><span data-stu-id="df607-267">In this case, the maximum number is the number of cells generated by the top-level grid, which depends on the **Level 1** density.</span></span>  
  
### <a name="grids"></a><span data-ttu-id="df607-268">Raster</span><span class="sxs-lookup"><span data-stu-id="df607-268">Grids</span></span>  
 <span data-ttu-id="df607-269">In diesem Bereich wird die Dichte des Rasters auf jeder Ebene des Mosaikschemas angezeigt.</span><span class="sxs-lookup"><span data-stu-id="df607-269">This panel shows the density of the grid at each level of the tessellation scheme.</span></span> <span data-ttu-id="df607-270">Die Dichte wird als **Niedrig**, **Mittel**oder **Hoch**angegeben.</span><span class="sxs-lookup"><span data-stu-id="df607-270">Density is specified as **Low**, **Medium**, or **High**.</span></span> <span data-ttu-id="df607-271">Der Standardwert ist **Mittel**.</span><span class="sxs-lookup"><span data-stu-id="df607-271">The default is **Medium**.</span></span> <span data-ttu-id="df607-272">**Niedrig** stellt ein Raster aus 4x4, also 16 Zellen, **Mittel** ein Raster aus 8x8, also 64 Zellen, und **Hoch** ein Raster aus 16x16, also 256 Zellen, dar.</span><span class="sxs-lookup"><span data-stu-id="df607-272">**Low** represents a 4x4 grid (16 cells), **Medium** represents an 8x8 grid (64 cells), and **High** represents a 16x16 grid (256 cells).</span></span> <span data-ttu-id="df607-273">Diese Optionen sind nicht verfügbar, wenn die Mosaikoptionen **Automatisches Geometrieraster** oder **Automatisches Geografieraster** nicht ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="df607-273">These options are not available when the **Geometry Auto grid** or **Geography Auto grid** tessellation options are chosen.</span></span>  
  
 <span data-ttu-id="df607-274">**Ebene 1**</span><span class="sxs-lookup"><span data-stu-id="df607-274">**Level 1**</span></span>  
 <span data-ttu-id="df607-275">Die Dichte des Rasters der obersten (höchsten) Ebene.</span><span class="sxs-lookup"><span data-stu-id="df607-275">The density of the first-level (top) grid.</span></span>  
  
 <span data-ttu-id="df607-276">**Ebene 2**</span><span class="sxs-lookup"><span data-stu-id="df607-276">**Level 2**</span></span>  
 <span data-ttu-id="df607-277">Die Dichte des Rasters der zweiten Ebene.</span><span class="sxs-lookup"><span data-stu-id="df607-277">The density of the second-level grid.</span></span>  
  
 <span data-ttu-id="df607-278">**Ebene 3**</span><span class="sxs-lookup"><span data-stu-id="df607-278">**Level 3**</span></span>  
 <span data-ttu-id="df607-279">Die Dichte des Rasters der dritten Ebene.</span><span class="sxs-lookup"><span data-stu-id="df607-279">The density of the third-level grid.</span></span>  
  
 <span data-ttu-id="df607-280">**Ebene 4**</span><span class="sxs-lookup"><span data-stu-id="df607-280">**Level 4**</span></span>  
 <span data-ttu-id="df607-281">Die Dichte des Rasters der vierten Ebene.</span><span class="sxs-lookup"><span data-stu-id="df607-281">The density of the fourth-level grid.</span></span>  
  
##  <a name="filter-page"></a><a name="Filter"></a> <span data-ttu-id="df607-282">Seite "Filter"</span><span class="sxs-lookup"><span data-stu-id="df607-282">Filter Page</span></span>  
 <span data-ttu-id="df607-283">Auf dieser Seite können Sie das Filterprädikat für einen gefilterten Index eingeben.</span><span class="sxs-lookup"><span data-stu-id="df607-283">Use this page to enter the filter predicate for a filtered index.</span></span> <span data-ttu-id="df607-284">Weitere Informationen finden Sie unter [erstellen gefilterter Indizes](create-filtered-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="df607-284">For more information, see [Create Filtered Indexes](create-filtered-indexes.md).</span></span>  
  
 <span data-ttu-id="df607-285">**Filterausdruck**</span><span class="sxs-lookup"><span data-stu-id="df607-285">**Filter Expression**</span></span>  
 <span data-ttu-id="df607-286">Definiert, welche Datenzeilen in den gefilterten Index eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="df607-286">Defines which data rows to include in the filtered index.</span></span> <span data-ttu-id="df607-287">Zum Beispiel, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span><span class="sxs-lookup"><span data-stu-id="df607-287">For example, `StartDate > '20000101' AND EndDate IS NOT NULL'.`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df607-288">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df607-288">See Also</span></span>  
 <span data-ttu-id="df607-289">[Festlegen von Indexoptionen](set-index-options.md) </span><span class="sxs-lookup"><span data-stu-id="df607-289">[Set Index Options](set-index-options.md) </span></span>  
 <span data-ttu-id="df607-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="df607-290">[INDEXPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/indexproperty-transact-sql) </span></span>  
 [<span data-ttu-id="df607-291">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="df607-291">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
