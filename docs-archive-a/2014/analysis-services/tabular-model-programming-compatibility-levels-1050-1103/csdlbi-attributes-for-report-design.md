---
title: Csdlbi-Attribute für Berichtsentwurf | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 61ba3a27-790e-43bc-b421-e01bf2fdbda6
author: minewiskan
ms.author: owend
ms.openlocfilehash: ee53cb3e4910e988403350bac5c993ef68b5170d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616240"
---
# <a name="csdlbi-attributes-for-report-design"></a><span data-ttu-id="4d405-102">CSDLBI-Attribute für Berichtsentwurf</span><span class="sxs-lookup"><span data-stu-id="4d405-102">CSDLBI Attributes for Report Design</span></span>
  <span data-ttu-id="4d405-103">In diesem Abschnitt werden die Attribute in den Erweiterungen für CSDL für Tabellenmodellierung beschrieben, die sich auf den [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] -Abfrageentwurf auswirken.</span><span class="sxs-lookup"><span data-stu-id="4d405-103">This section describes the attributes in the extensions to CSDL for tabular modeling that affect [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] query design.</span></span>  
  
## <a name="model-attributes"></a><span data-ttu-id="4d405-104">Modellattribute</span><span class="sxs-lookup"><span data-stu-id="4d405-104">Model Attributes</span></span>  
 <span data-ttu-id="4d405-105">Diese Attribute werden für ein Unterelement eines [EntityContainer](https://msdn.microsoft.com/library/bb399169.aspx) -Elements der CSDL definiert.</span><span class="sxs-lookup"><span data-stu-id="4d405-105">These attributes are defined on a sub-element of a CSDL [EntityContainer](https://msdn.microsoft.com/library/bb399169.aspx) element.</span></span>  
  
|<span data-ttu-id="4d405-106">Attributname</span><span class="sxs-lookup"><span data-stu-id="4d405-106">Attribute name</span></span>|<span data-ttu-id="4d405-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4d405-107">Data type</span></span>|<span data-ttu-id="4d405-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d405-108">Description</span></span>|  
|--------------------|---------------|-----------------|  
|<span data-ttu-id="4d405-109">Kultur</span><span class="sxs-lookup"><span data-stu-id="4d405-109">Culture</span></span>|<span data-ttu-id="4d405-110">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-110">Text</span></span>|<span data-ttu-id="4d405-111">Gibt die für Währungsformate verwendete Kultur an.</span><span class="sxs-lookup"><span data-stu-id="4d405-111">Indicates the culture used for currency formats.</span></span> <span data-ttu-id="4d405-112">Wenn keine Angabe erfolgt, wird EN-US verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-112">If omitted, EN-US is used.</span></span>|  
|<span data-ttu-id="4d405-113">IsRightToLeft</span><span class="sxs-lookup"><span data-stu-id="4d405-113">IsRightToLeft</span></span>|<span data-ttu-id="4d405-114">Boolean</span><span class="sxs-lookup"><span data-stu-id="4d405-114">Boolean</span></span>|<span data-ttu-id="4d405-115">Gibt an, ob die Werte von Textfeldern standardmäßig von rechts nach links gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d405-115">Indicates whether the values of text fields should be read right to left by default</span></span>|  
  
## <a name="entity-attributes"></a><span data-ttu-id="4d405-116">Entitätsattribute</span><span class="sxs-lookup"><span data-stu-id="4d405-116">Entity Attributes</span></span>  
 <span data-ttu-id="4d405-117">Diese Attribute werden für ein Unterelement eines EntitySet-Elements oder EntityType-Elements der CSDL definiert.</span><span class="sxs-lookup"><span data-stu-id="4d405-117">These attributes are defined on a sub-element of either a CSDL EntitySet or EntityType element.</span></span>  
  
|<span data-ttu-id="4d405-118">Attributname</span><span class="sxs-lookup"><span data-stu-id="4d405-118">Attribute name</span></span>|<span data-ttu-id="4d405-119">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4d405-119">Data type</span></span>|<span data-ttu-id="4d405-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d405-120">Description</span></span>|  
|--------------------|---------------|-----------------|  
|`ReferenceName`|<span data-ttu-id="4d405-121">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-121">Text</span></span>|<span data-ttu-id="4d405-122">Der Bezeichner, der verwendet wird, um in einer DAX-Abfrage auf diese Entität zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4d405-122">The identifier used to reference this entity in a DAX query.</span></span> <span data-ttu-id="4d405-123">Wenn kein Bezeichner angegeben wird, wird der Name verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-123">If omitted, the name is used.</span></span>|  
|`Caption`|<span data-ttu-id="4d405-124">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-124">Text</span></span>|<span data-ttu-id="4d405-125">Der Anzeigename für die Entität.</span><span class="sxs-lookup"><span data-stu-id="4d405-125">The display name for the entity.</span></span>|  
|`Documentation`|<span data-ttu-id="4d405-126">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-126">Text</span></span>|<span data-ttu-id="4d405-127">Beschreibender Text, der Geschäftskunden die Bedeutung der Daten erläutert.</span><span class="sxs-lookup"><span data-stu-id="4d405-127">Descriptive text to help business users understand the meaning of the data.</span></span>|  
|`Hidden`|<span data-ttu-id="4d405-128">Boolean</span><span class="sxs-lookup"><span data-stu-id="4d405-128">Boolean</span></span>|<span data-ttu-id="4d405-129">Gibt an, ob die Entität angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-129">Indicates whether the entity should be displayed.</span></span> <span data-ttu-id="4d405-130">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="4d405-130">The default is `false`.</span></span>|  
|`CollectionCaption`|<span data-ttu-id="4d405-131">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-131">Text</span></span>|<span data-ttu-id="4d405-132">Der Pluralname für den Verweis auf einen Satz von Instanzen der Entität.</span><span class="sxs-lookup"><span data-stu-id="4d405-132">Plural name for referring to a set of instances of the entity.</span></span> <span data-ttu-id="4d405-133">Wenn der Name nicht angegeben wird, wird das Caption-Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-133">If omitted, the Caption attribute is used.</span></span>|  
|`DisplayKey`|<span data-ttu-id="4d405-134">MemberRef[]</span><span class="sxs-lookup"><span data-stu-id="4d405-134">MemberRef[]</span></span>|<span data-ttu-id="4d405-135">Eine sortierte Felderliste, mit der einem Geschäftskunden eine Entitätsinstanz angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-135">An ordered list of field(s) used to identify an entity instance to a business user.</span></span> <span data-ttu-id="4d405-136">Die Verweise können Instanz- und Navigationseigenschaften einschließen.</span><span class="sxs-lookup"><span data-stu-id="4d405-136">The references can include instance properties and navigation properties.</span></span> <span data-ttu-id="4d405-137">Wenn auf eine Navigationseigenschaft verwiesen wird, wird der `DisplayKey` der Zielentität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d405-137">When a navigation property is referenced, the `DisplayKey` of the target entity is displayed.</span></span> <span data-ttu-id="4d405-138">Wenn der `DisplayKey`-Wert ausgelassen wird, wird das Schlüsselfeld verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-138">If the `DisplayKey` value is omitted, the Key field is used.</span></span>|  
|`DefaultImage`|<span data-ttu-id="4d405-139">MemberRef</span><span class="sxs-lookup"><span data-stu-id="4d405-139">MemberRef</span></span>|<span data-ttu-id="4d405-140">Ein Verweis auf das Feld, das ein Bild enthält, mit dem einem Geschäftskunden visuell eine Entitätsinstanz angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-140">A reference to the field containing an image used to visually identify an entity instance to a business user.</span></span> <span data-ttu-id="4d405-141">Wenn der Verweis nicht angegeben wird, wird das erste Bildfeld in der Entität verwendet (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="4d405-141">If omitted, the first image field in the entity is used, if any.</span></span>|  
|`DefaultDetails`|<span data-ttu-id="4d405-142">MemberRef[]</span><span class="sxs-lookup"><span data-stu-id="4d405-142">MemberRef[]</span></span>|<span data-ttu-id="4d405-143">Eine sortierte Liste von Feldern, die den Standardsatz der Detailinformationen darstellt, die einem Geschäftsbenutzer zu einer Entitätsinstanz angezeigt werden. Wenn die Liste nicht angegeben wird, werden die ersten fünf Felder in der Entität verwendet, wobei die Felder ausgeschlossen werden, auf die bereits von `Key`, `DisplayKey` oder `DefaultImage` verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-143">An ordered list of fields representing the default set of detail information displayed to a business user about an entity instance.If omitted, the first five (5) fields in the entity are used, excluding those already referenced by `Key`, `DisplayKey`, or `DefaultImage`.</span></span>|  
|`SortProperties`|<span data-ttu-id="4d405-144">MemberRef[]</span><span class="sxs-lookup"><span data-stu-id="4d405-144">MemberRef[]</span></span>|<span data-ttu-id="4d405-145">Eine sortierte Liste von Feldern, nach denen die Entitätsinstanzen normalerweise sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="4d405-145">An ordered list of fields by which the entity instances are typically sorted.</span></span> <span data-ttu-id="4d405-146">Wenn Sie einen Sortiervorgang in diesen Feldern ausführen, wird die für jedes Feld angegebene `SortDirection` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-146">When sorting on these fields, the `SortDirection` specified on each field is used.</span></span> <span data-ttu-id="4d405-147">Wenn die Felderliste nicht angegeben wird, werden die `DisplayKey`-Felder verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-147">If omitted, the `DisplayKey` fields are used</span></span>|  
|`DefaultMeasure`|<span data-ttu-id="4d405-148">MemberRef</span><span class="sxs-lookup"><span data-stu-id="4d405-148">MemberRef</span></span>|<span data-ttu-id="4d405-149">Ein Verweis auf ein im Modell definiertes Measure oder auf ein numerisches Feld mit einer standardmäßigen Aggregatfunktion, mit dem angegeben wird, dass das Measure oder Feld für mehrere Instanzen der Entität als Standarddarstellung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-149">A reference to a measure defined in the model, or to a numeric field with a default aggregate function, to indicate that the measure or field should be used as the default representation for multiple instances of the entity.</span></span> <span data-ttu-id="4d405-150">Wenn der Verweis nicht angegeben wird, wird eine Anzahl der Entitätsinstanzen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-150">If omitted, a count of the entity instances is used.</span></span>|  
|`DefaultLocation`|<span data-ttu-id="4d405-151">MemberRef</span><span class="sxs-lookup"><span data-stu-id="4d405-151">MemberRef</span></span>|<span data-ttu-id="4d405-152">Ein Verweis auf ein Feld, dessen Wert den einer Entitätsinstanz zugeordneten Standardort darstellt.</span><span class="sxs-lookup"><span data-stu-id="4d405-152">A reference to a field whose value represents the default location associated with an entity instance.</span></span> <span data-ttu-id="4d405-153">Wenn der Verweis nicht angegeben wird, wird das erste Ortfeld in der Entität verwendet (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="4d405-153">If omitted, the first location field in the entity is used, if any.</span></span>|  
  
## <a name="field-attributes"></a><span data-ttu-id="4d405-154">Feldattribute</span><span class="sxs-lookup"><span data-stu-id="4d405-154">Field Attributes</span></span>  
 <span data-ttu-id="4d405-155">Diese Attribute werden für ein Unterelement einer CSDL-Eigenschaft oder eines [NavigationProperty](https://msdn.microsoft.com/library/bb387104.aspx) -Elements definiert.</span><span class="sxs-lookup"><span data-stu-id="4d405-155">These attributes are defined on a sub-element of a CSDL Property or [NavigationProperty](https://msdn.microsoft.com/library/bb387104.aspx) element.</span></span>  
  
|<span data-ttu-id="4d405-156">Attributname</span><span class="sxs-lookup"><span data-stu-id="4d405-156">Attribute name</span></span>|<span data-ttu-id="4d405-157">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4d405-157">Data type</span></span>|<span data-ttu-id="4d405-158">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d405-158">Description</span></span>|  
|--------------------|---------------|-----------------|  
|`ReferenceName`|<span data-ttu-id="4d405-159">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-159">Text</span></span>|<span data-ttu-id="4d405-160">Der Bezeichner, der verwendet wird, um in einer DAX-Abfrage auf diese Entität zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4d405-160">The identifier used to reference this entity in a DAX query.</span></span> <span data-ttu-id="4d405-161">Wenn der Bezeichner nicht angegeben wird, wird der Feldname verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-161">If omitted, the field name is used.</span></span>|  
|`Caption`|<span data-ttu-id="4d405-162">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-162">Text</span></span>|<span data-ttu-id="4d405-163">Der Anzeigename für die Entität.</span><span class="sxs-lookup"><span data-stu-id="4d405-163">The display name for the entity.</span></span> <span data-ttu-id="4d405-164">Wenn der Wert weggelassen wird, `ReferenceName` wird das Feld verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-164">If omitted, the field's `ReferenceName` is used.</span></span>|  
|`Documentation`|<span data-ttu-id="4d405-165">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-165">Text</span></span>|<span data-ttu-id="4d405-166">Beschreibender Text, der Geschäftskunden die Bedeutung des Felds erläutert.</span><span class="sxs-lookup"><span data-stu-id="4d405-166">Descriptive text to help business users understand the meaning of the field.</span></span>|  
|`Hidden`|<span data-ttu-id="4d405-167">Boolean</span><span class="sxs-lookup"><span data-stu-id="4d405-167">Boolean</span></span>|<span data-ttu-id="4d405-168">Gibt an, ob das Feld angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-168">Indicates whether the field should be displayed.</span></span> <span data-ttu-id="4d405-169">Der Standard ist `false` und bedeutet, dass das Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-169">The default is `false`, meaning the field is displayed.</span></span>|  
|`DisplayFolder`|<span data-ttu-id="4d405-170">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-170">Text</span></span>|<span data-ttu-id="4d405-171">Der Name (vollständiger Pfad) des Ordners, in dem das Feld angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-171">The name (full path) of the folder in which this field is displayed.</span></span> <span data-ttu-id="4d405-172">Wenn der Name nicht angegeben wird, wird das Feld am Modellstamm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d405-172">If omitted, the field is displayed at the model root.</span></span>|  
|`ContextualNameRule`|<span data-ttu-id="4d405-173">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4d405-173">Enum</span></span>|<span data-ttu-id="4d405-174">Ein Wert, der angibt, ob und wie der Eigenschaftsname auf Grundlage des Kontexts geändert werden sollte, in dem er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-174">A value indicating whether and how the property name should be modified based on the context in which it is used.</span></span> <span data-ttu-id="4d405-175">Mögliche Werte: `None`, `Role`, `Merge`.</span><span class="sxs-lookup"><span data-stu-id="4d405-175">Possible values are:  `None`,  `Role`,  `Merge`.</span></span>|  
|`Alignment`|<span data-ttu-id="4d405-176">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4d405-176">Enum</span></span>|<span data-ttu-id="4d405-177">Ein Wert, der angibt, wie die Feldwerte in einer Tabellenpräsentation ausgerichtet werden sollten.</span><span class="sxs-lookup"><span data-stu-id="4d405-177">A value indicating how the field values should be aligned in a tabular presentation.</span></span> <span data-ttu-id="4d405-178">Mögliche Werte `Default`, `Center`, `Left`, `Right`.</span><span class="sxs-lookup"><span data-stu-id="4d405-178">Possible values are `Default`, `Center`, `Left`, `Right`.</span></span> <span data-ttu-id="4d405-179">Wenn der Wert nicht angegeben wird, bestimmt der Standard die Ausrichtung basierend auf dem Datentyp des Felds.</span><span class="sxs-lookup"><span data-stu-id="4d405-179">If omitted, the default determines the alignment based on the field's data type.</span></span>|  
|`FormatString`|<span data-ttu-id="4d405-180">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-180">Text</span></span>|<span data-ttu-id="4d405-181">Eine .NET-Format Zeichenfolge, die angibt, wie der Wert des Felds standardmäßig formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-181">A .NET format string indicating how the field's value should be formatted by default.</span></span> <span data-ttu-id="4d405-182">Wenn die Zeichenfolge nicht angegeben wird, wird das folgende Format angenommen:</span><span class="sxs-lookup"><span data-stu-id="4d405-182">If omitted, the following format is assumed:</span></span><br /><br /> <span data-ttu-id="4d405-183">-DateTime-Felder: Regionales kurzes Datum oder "d"</span><span class="sxs-lookup"><span data-stu-id="4d405-183">-   Datetime fields: regional short date or "d"</span></span><br /><span data-ttu-id="4d405-184">-Gleit Komma Felder und ganzzahlige Felder mit einer Standard Aggregatfunktion: regionale Zahl oder "n"</span><span class="sxs-lookup"><span data-stu-id="4d405-184">-   Floating-point fields and integral fields with a default aggregate function: regional number or "n"</span></span><br /><span data-ttu-id="4d405-185">-Ganze Zahlen ohne Standard Aggregatfunktion: regionale Dezimalzahl oder "d"</span><span class="sxs-lookup"><span data-stu-id="4d405-185">-   Integers with no default aggregate function: regional decimal number or "d"</span></span><br /><br /> <span data-ttu-id="4d405-186">Für alle anderen Feldtypen ist keine Formatzeichenfolge gültig.</span><span class="sxs-lookup"><span data-stu-id="4d405-186">For all other types of fields, no format string applies.</span></span>|  
|`Units`|<span data-ttu-id="4d405-187">Text</span><span class="sxs-lookup"><span data-stu-id="4d405-187">Text</span></span>|<span data-ttu-id="4d405-188">Das Symbol, das für Feldwerte zur Darstellung von Einheiten übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-188">The symbol that is applied to field values to express units.</span></span> <span data-ttu-id="4d405-189">Wenn das Symbol nicht angegeben wird, werden die Einheiten als unbekannt angenommen.</span><span class="sxs-lookup"><span data-stu-id="4d405-189">If omitted, the units are assumed to be unknown.</span></span>|  
|`Width`|<span data-ttu-id="4d405-190">Integer</span><span class="sxs-lookup"><span data-stu-id="4d405-190">Integer</span></span>|<span data-ttu-id="4d405-191">Die bevorzugte Breite in Zeichen, die für die Anzeige der Feldwerte in einer tabellarischen Präsentation reserviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-191">The preferred width in characters that should be reserved for displaying the field's values in a tabular presentation.</span></span> <span data-ttu-id="4d405-192">Wenn der Wert weggelassen wird, basiert eine Standardbreite auf dem Datentyp des Felds.</span><span class="sxs-lookup"><span data-stu-id="4d405-192">If omitted, a default width is based on the field's data type.</span></span>|  
|`SortDirection`|<span data-ttu-id="4d405-193">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4d405-193">Enum</span></span>|<span data-ttu-id="4d405-194">Ein Wert, der angibt, wie die Feldwerte normalerweise sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="4d405-194">A value indicating how the fields values are typically sorted.</span></span> <span data-ttu-id="4d405-195">Mögliche Werte: `Default`, `Ascending`, `Descending`.</span><span class="sxs-lookup"><span data-stu-id="4d405-195">Possible values are `Default`, `Ascending`, `Descending`.</span></span> <span data-ttu-id="4d405-196">Wenn der Wert nicht weggelassen wird, wird eine Sortierrichtung auf Grundlage des Datentyps des Felds zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4d405-196">If omitted, the default value assigns a sort direction is based on the field's data type.</span></span>|  
|`IsRightToLeft`|<span data-ttu-id="4d405-197">Boolean</span><span class="sxs-lookup"><span data-stu-id="4d405-197">Boolean</span></span>|<span data-ttu-id="4d405-198">Gibt an, ob das Feld Text enthält, der von rechts nach links gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-198">Indicates whether the field contains text that should be read right to left.</span></span> <span data-ttu-id="4d405-199">Wenn der Wert nicht angegeben wird, wird die Modelleinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4d405-199">If omitted, the model setting is assumed.</span></span>|  
|`OrderBy`|<span data-ttu-id="4d405-200">MemberRef</span><span class="sxs-lookup"><span data-stu-id="4d405-200">MemberRef</span></span>|<span data-ttu-id="4d405-201">Ein Verweis auf ein anderes Feld innerhalb des Modells, das die Sortierreihenfolge für die Werte dieses Felds definiert.</span><span class="sxs-lookup"><span data-stu-id="4d405-201">A reference to another field within the model that defines the sort order for this field's values.</span></span> <span data-ttu-id="4d405-202">Die Werte für die zwei Felder müssen über eine 1:1-Zuordnung verfügen, da das Sortierverhalten andernfalls nicht definiert wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-202">The values for the two fields must have a 1:1 mapping, or the sort behavior is undefined.</span></span> <span data-ttu-id="4d405-203">Wenn die Werte nicht angegeben werden, wird das Feld auf Grundlage seines eigenen Werts sortiert.</span><span class="sxs-lookup"><span data-stu-id="4d405-203">If omitted, the field is sorted based on its own value.</span></span>|  
|`Contents`|<span data-ttu-id="4d405-204">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4d405-204">Enum</span></span>|<span data-ttu-id="4d405-205">Eine Enumeration, die den Untertyp oder den Inhalt des Felds beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4d405-205">An enumeration describing the subtype or contents of the field.</span></span> <span data-ttu-id="4d405-206">Wenn der Wert weggelassen wird, wird kein bestimmter Untertyp angenommen, es sei denn, der Datentyp des Felds ist binär. in diesem Fall wird ein Bild angenommen.</span><span class="sxs-lookup"><span data-stu-id="4d405-206">If omitted, no particular subtype is assumed, unless the field's data type is Binary, in which case Image is assumed.</span></span> <span data-ttu-id="4d405-207">Eine vollständige Liste der unterstützten Inhaltstypen finden Sie in der AMO-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="4d405-207">For a full list of supported content types, see the AMO documentation.</span></span>|  
|`DefaultAggregateFunction`|<span data-ttu-id="4d405-208">Enumeration</span><span class="sxs-lookup"><span data-stu-id="4d405-208">Enum</span></span>|<span data-ttu-id="4d405-209">Ein Wert, der die Standardfunktion angibt (sofern vorhanden), mit der normalerweise das Feld aggregiert wird.</span><span class="sxs-lookup"><span data-stu-id="4d405-209">A value indicating the default function, if any, typically used to aggregate this field.</span></span> <span data-ttu-id="4d405-210">Mögliche Werte: `None`, `Sum`, `Average`, `Count`, `Min`, `Max`.</span><span class="sxs-lookup"><span data-stu-id="4d405-210">Possible values are `None`, `Sum`, `Average`, `Count`, `Min`, `Max`.</span></span> <span data-ttu-id="4d405-211">Wenn die Werte nicht angegeben werden, wird für numerische Felder `Sum` angenommen bzw. für alle anderen Felder `None`.</span><span class="sxs-lookup"><span data-stu-id="4d405-211">If omitted, `Sum` is assumed for numeric fields, `None` for all other fields.</span></span>|  
|`IsSimpleMeasure`|<span data-ttu-id="4d405-212">Boolean</span><span class="sxs-lookup"><span data-stu-id="4d405-212">Boolean</span></span>|<span data-ttu-id="4d405-213">Gibt an, ob ein Measure lediglich ein einfaches Aggregat eines numerischen Feldes ist.</span><span class="sxs-lookup"><span data-stu-id="4d405-213">Indicates whether a measure is merely a simple aggregate of a numeric field.</span></span> <span data-ttu-id="4d405-214">Solche Aggregate können nach Bedarf in der Abfrage problemlos definiert werden. Daher sollten sie von der Modelldefinition ausgenommen werden, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4d405-214">Such aggregates can be easily defined in the query as needed and therefore should be omitted from the model definition to improve performance.</span></span> <span data-ttu-id="4d405-215">Wenn die Werte nicht angegeben werden, wird `false` angenommen.</span><span class="sxs-lookup"><span data-stu-id="4d405-215">If omitted, `false` is assumed.</span></span>|  
|`Kpi`<br /><br /> `KpiGoal`<br /><br /> `KpiStatus`|<span data-ttu-id="4d405-216">Unterelement</span><span class="sxs-lookup"><span data-stu-id="4d405-216">Subelement</span></span>|<span data-ttu-id="4d405-217">Gibt an, dass das Measureelement als KPI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d405-217">Indicates that the measure element is to be used as a KPI.</span></span> <span data-ttu-id="4d405-218">Das KPI-Unterelement verwendet das KpiGoal-Element und das KpiStauts-Element, um das zugeordnete Anzeigebild zu definieren und Zielbereiche festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4d405-218">The KPI subelement uses the KpiGoal and KpiStauts elements to define the associated display image and target ranges.</span></span>|  
  
  