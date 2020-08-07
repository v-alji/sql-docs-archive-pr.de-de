---
title: Aktualisieren von Daten mit XML-Update grams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREF type attribute [SQLXML]
- before attribute
- <sync> block
- <after> block
- id attribute
- <before> block
- updg:after attribute
- mapping-schema attribute
- IDREFS type attribute [SQLXML]
- updg:id attribute
- multiple record updates
- after attribute
- updategrams [SQLXML], updating data
- updg:before attribute
- record updates [SQLXML]
ms.assetid: 90ef8a33-5ae3-4984-8259-608d2f1d727f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6b019478868b61f293eda824d9b302099728dec4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619737"
---
# <a name="updating-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="571e1-102">Aktualisieren von Daten mit XML-Updategrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="571e1-102">Updating Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="571e1-103">Wenn Sie vorhandene Daten aktualisieren, müssen Sie sowohl den **\<before>** -als auch den- **\<after>** Block angeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-103">When you update existing data, you must specify both the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="571e1-104">Die in den **\<before>** Blöcken und angegebenen Elemente **\<after>** beschreiben die gewünschte Änderung.</span><span class="sxs-lookup"><span data-stu-id="571e1-104">The elements specified in the **\<before>** and **\<after>** blocks describe the desired change.</span></span> <span data-ttu-id="571e1-105">Das Update Gram verwendet die im-Block angegebenen Elemente, **\<before>** um die vorhandenen Datensätze in der Datenbank zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="571e1-105">The updategram uses the element(s) that are specified in the **\<before>** block to identify the existing record(s) in the database.</span></span> <span data-ttu-id="571e1-106">Die entsprechenden Elemente im- **\<after>** Block geben an, wie die Datensätze nach dem Ausführen des Aktualisierungs Vorgangs aussehen sollen.</span><span class="sxs-lookup"><span data-stu-id="571e1-106">The corresponding element(s) in the **\<after>** block indicate how the records should look after executing the update operation.</span></span> <span data-ttu-id="571e1-107">Aus diesen Informationen erstellt das Update Gram eine SQL-Anweisung, die mit dem-Block übereinstimmt **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-107">From this information, the updategram creates an SQL statement that matches the **\<after>** block.</span></span> <span data-ttu-id="571e1-108">Das Updategram verwendet dann diese Anweisung, um die Datenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="571e1-108">The updategram then uses this statement to update the database.</span></span>  
  
 <span data-ttu-id="571e1-109">Dies ist das Updategramformat für einen Updatevorgang:</span><span class="sxs-lookup"><span data-stu-id="571e1-109">This is the updategram format for an update operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
      <ElementName [updg:id="value"] .../>  
      [<ElementName [updg:id="value"] .../> ... ]  
   </updg:before>  
   <updg:after>  
      <ElementName [updg:id="value"] ... />  
      [<ElementName [updg:id="value"] .../> ...]  
   </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 `<updg:before>`  
 <span data-ttu-id="571e1-110">Die Elemente im- **\<before>** Block identifizieren vorhandene Datensätze in den Datenbanktabellen.</span><span class="sxs-lookup"><span data-stu-id="571e1-110">The elements in the **\<before>** block identify existing records in the database tables.</span></span>  
  
 `<updg:after>`  
 <span data-ttu-id="571e1-111">Die Elemente im- **\<after>** Block beschreiben, wie die im-Block angegebenen Datensätze **\<before>** nach dem Anwenden der Updates aussehen sollten.</span><span class="sxs-lookup"><span data-stu-id="571e1-111">The elements in the **\<after>** block describe how the records specified in the **\<before>** block should look after the updates are applied.</span></span>  
  
 <span data-ttu-id="571e1-112">Das `mapping-schema`-Attribut identifiziert das vom Updategram zu verwendende Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="571e1-112">The `mapping-schema` attribute identifies the mapping schema to be used by the updategram.</span></span> <span data-ttu-id="571e1-113">Wenn das Update Gram ein Zuordnungsschema angibt, müssen die in den Blöcken und angegebenen Element-und Attributnamen **\<before>** **\<after>** mit den Namen im Schema identisch sein.</span><span class="sxs-lookup"><span data-stu-id="571e1-113">If the updategram specifies a mapping schema, the element and attribute names specified in the **\<before>** and **\<after>** blocks must match the names in the schema.</span></span> <span data-ttu-id="571e1-114">Das Zuordnungsschema ordnet diese Element- oder Attributnamen der Datenbanktabelle und den Spaltennamen zu.</span><span class="sxs-lookup"><span data-stu-id="571e1-114">The mapping schema maps these element or attribute names to the database table and column names.</span></span>  
  
 <span data-ttu-id="571e1-115">Wenn ein Updategram kein Schema angibt, verwendet das Updategram die Standardzuordnung.</span><span class="sxs-lookup"><span data-stu-id="571e1-115">If an updategram does not specify a schema, the updategam uses default mapping.</span></span> <span data-ttu-id="571e1-116">Bei der Standard Zuordnung wird die, die **\<ElementName>** im Update Gram angegeben ist, der Datenbanktabelle zugeordnet, und die untergeordneten Elemente oder Attribute werden den Daten Bank Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="571e1-116">In default mapping, the **\<ElementName>** specified in the updategram maps to the database table and the child elements or attributes map to the database columns.</span></span>  
  
 <span data-ttu-id="571e1-117">Ein Element im- **\<before>** Block muss mit nur einer Tabellenzeile in der Datenbank identisch sein.</span><span class="sxs-lookup"><span data-stu-id="571e1-117">An element in the **\<before>** block must match with only one table row in the database.</span></span> <span data-ttu-id="571e1-118">Wenn das-Element entweder mit mehreren Tabellenzeilen übereinstimmt oder mit keiner Tabellenzeile übereinstimmt, gibt das Update Gram einen Fehler zurück und bricht den gesamten- **\<sync>** Block ab.</span><span class="sxs-lookup"><span data-stu-id="571e1-118">If the element either matches multiple table rows or does not match any table row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span>  
  
 <span data-ttu-id="571e1-119">Ein Update Gram kann mehrere Blöcke enthalten **\<sync>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-119">An updategram can include multiple **\<sync>** blocks.</span></span> <span data-ttu-id="571e1-120">Jeder **\<sync>** Block wird als Transaktion behandelt.</span><span class="sxs-lookup"><span data-stu-id="571e1-120">Each **\<sync>** block is treated as a transaction.</span></span> <span data-ttu-id="571e1-121">Jeder **\<sync>** Block kann über mehrere **\<before>** -und- **\<after>** Blöcke verfügen.</span><span class="sxs-lookup"><span data-stu-id="571e1-121">Each **\<sync>** block can have multiple **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="571e1-122">Wenn Sie z. b. zwei der vorhandenen Datensätze aktualisieren, können Sie zwei **\<before>** -und- **\<after>** Paare angeben, eine für jeden zu aktualisierenden Datensatz.</span><span class="sxs-lookup"><span data-stu-id="571e1-122">For example, if you are updating two of the existing records, you could specify two **\<before>** and **\<after>** pairs, one for each record being updated.</span></span>  
  
## <a name="using-the-updgid-attribute"></a><span data-ttu-id="571e1-123">Verwenden des updg:id-Attributs</span><span class="sxs-lookup"><span data-stu-id="571e1-123">Using the updg:id Attribute</span></span>  
 <span data-ttu-id="571e1-124">Wenn mehrere Elemente in den **\<before>** -und- **\<after>** Blöcken angegeben werden, verwenden `updg:id` Sie das-Attribut, um Zeilen in den **\<before>** -und-Blöcken zu markieren **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-124">When multiple elements are specified in the **\<before>** and **\<after>** blocks, use the `updg:id` attribute to mark rows in the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="571e1-125">Die Verarbeitungslogik verwendet diese Informationen, um zu bestimmen, welcher Datensatz in den **\<before>** Block Paaren mit welchem Datensatz im Block verwendet wird **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-125">The processing logic uses this information to determine what record in the **\<before>** block pairs with what record in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="571e1-126">Das `updg:id`-Attribut ist nicht notwendig (aber empfohlen), wenn einer der beiden folgenden Fälle zutrifft:</span><span class="sxs-lookup"><span data-stu-id="571e1-126">The `updg:id` attribute is not necessary (although recommended) if either of the following exists:</span></span>  
  
-   <span data-ttu-id="571e1-127">Die Elemente im angegebenen Zuordnungsschema verfügen über das auf ihnen definierte `sql:key-fields`-Attribut.</span><span class="sxs-lookup"><span data-stu-id="571e1-127">The elements in the specified mapping schema have the `sql:key-fields` attribute defined on them.</span></span>  
  
-   <span data-ttu-id="571e1-128">Ein oder mehrere bestimmte Werte sind für das Schlüsselfeld oder die Schlüsselfelder im Updategram angegeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-128">There is one or more specific value supplied for the key field(s) in the updategram.</span></span>  
  
 <span data-ttu-id="571e1-129">Wenn dies der Fall ist, verwendet das Update Gram die Schlüssel Spalten, die in angegeben sind, `sql:key-fields` um die Elemente in den **\<before>** -und-Blöcken zu koppeln **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-129">If either is the case, the updategram uses the key columns that are specified in the `sql:key-fields` to pair the elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="571e1-130">Wenn das Zuordnungsschema keine Schlüsselspalten identifiziert (unter Verwendung von `sql:key-fields`) oder das Updategram einen Schlüsselspaltenwert aktualisiert, müssen Sie `updg:id` angeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-130">If the mapping schema does not identify key columns (by using `sql:key-fields`) or if the updategram is updating a key column value, you must specify `updg:id`.</span></span>  
  
 <span data-ttu-id="571e1-131">Die Datensätze, die in den **\<before>** -und-Blöcken identifiziert werden, **\<after>** müssen sich nicht in derselben Reihenfolge befinden.</span><span class="sxs-lookup"><span data-stu-id="571e1-131">The records that are identified in the **\<before>** and **\<after>** blocks do not have to be in the same order.</span></span> <span data-ttu-id="571e1-132">Das `updg:id` -Attribut erzwingt die Zuordnung zwischen den Elementen, die in den **\<before>** -und-Blöcken angegeben sind **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-132">The `updg:id` attribute forces the association between the elements that are specified in the **\<before>** and **\<after>** blocks.</span></span>  
  
 <span data-ttu-id="571e1-133">Wenn Sie ein Element im **\<before>** -Block und nur ein entsprechendes Element im- **\<after>** Block angeben, ist die Verwendung von `updg:id` nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="571e1-133">If you specify one element in the **\<before>** block and only one corresponding element in the **\<after>** block, using `updg:id` is not necessary.</span></span> <span data-ttu-id="571e1-134">Es wird jedoch empfohlen, `updg:id` trotzdem anzugeben, um Mehrdeutigkeit zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="571e1-134">However, it is recommended that you specify `updg:id` anyway to avoid ambiguity.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="571e1-135">Beispiele</span><span class="sxs-lookup"><span data-stu-id="571e1-135">Examples</span></span>  
 <span data-ttu-id="571e1-136">Bevor Sie die Updategrambeispiele verwenden, beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="571e1-136">Before you use the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="571e1-137">Die meisten der Beispiele verwenden die Standardzuordnung (d. h. es ist kein Zuordnungsschema im Updategram angegeben).</span><span class="sxs-lookup"><span data-stu-id="571e1-137">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="571e1-138">Weitere Beispiele für Update grams, die Mapping-Schemas verwenden, finden Sie unter [Angeben eines Mappingschemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-138">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="571e1-139">Die meisten der Beispiele verwenden die AdventureWorks-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="571e1-139">Most of the examples use the AdventureWorks sample database.</span></span> <span data-ttu-id="571e1-140">Alle Updates werden für die Tabellen in dieser Datenbank übernommen.</span><span class="sxs-lookup"><span data-stu-id="571e1-140">All the updates are applied to the tables in this database.</span></span> <span data-ttu-id="571e1-141">Sie können die AdventureWorks-Datenbank wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="571e1-141">You can restore the AdventureWorks database.</span></span>  
  
### <a name="a-updating-a-record"></a><span data-ttu-id="571e1-142">A.</span><span class="sxs-lookup"><span data-stu-id="571e1-142">A.</span></span> <span data-ttu-id="571e1-143">Aktualisieren eines Datensatzes</span><span class="sxs-lookup"><span data-stu-id="571e1-143">Updating a record</span></span>  
 <span data-ttu-id="571e1-144">Das folgende Updategram aktualisiert den Nachnamen des Mitarbeiters in der Person.Contact-Tabelle in der AdventureWorks-Datenbank zu "Fuller".</span><span class="sxs-lookup"><span data-stu-id="571e1-144">The following updategram updates the employee last name to Fuller in the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="571e1-145">Das Updategram gibt kein Zuordnungsschema an, deswegen verwendet das Updategram die Standardzuordnung.</span><span class="sxs-lookup"><span data-stu-id="571e1-145">The updategram does not specify any mapping schema; therefore, the updategram uses default mapping.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact LastName="Abel-Achong" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="571e1-146">Der Datensatz, der im-Block beschrieben wird, **\<before>** stellt den aktuellen Datensatz in der Datenbank dar.</span><span class="sxs-lookup"><span data-stu-id="571e1-146">The record described in the **\<before>** block represents the current record in the database.</span></span> <span data-ttu-id="571e1-147">Das Update Gram verwendet alle Spaltenwerte, die im-Block angegeben sind **\<before>** , um nach dem Datensatz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="571e1-147">The updategram uses all of the column values specified in the **\<before>** block to search for the record.</span></span> <span data-ttu-id="571e1-148">In diesem Update Gram bietet der- **\<before>** Block nur die ContactID-Spalte. Daher verwendet das Update Gram nur den Wert, um nach dem Datensatz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="571e1-148">In this updategram, the **\<before>** block provides only the ContactID column; therefore, the updategram uses only the value to search for the record.</span></span> <span data-ttu-id="571e1-149">Wenn Sie diesem Block den LastName-Wert hinzufügen würden, würde das Updategram sowohl den ContactID- als auch den LastName-Wert für die Suche verwenden.</span><span class="sxs-lookup"><span data-stu-id="571e1-149">If you were to add the LastName value to this block, the updategram would use both the ContactID and LastName values to search.</span></span>  
  
 <span data-ttu-id="571e1-150">In diesem Update Gram bietet der- **\<after>** Block nur den LastName-Spaltenwert, da dies der einzige Wert ist, der geändert wird.</span><span class="sxs-lookup"><span data-stu-id="571e1-150">In this updategram, the **\<after>** block provides only the LastName column value because this is the only value that is being changed.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="571e1-151">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="571e1-151">To test the updategram</span></span>  
  
1.  <span data-ttu-id="571e1-152">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-152">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="571e1-153">Speichern Sie die Datei unter dem Dateinamen UpdateLastName.xml.</span><span class="sxs-lookup"><span data-stu-id="571e1-153">Save the file as UpdateLastName.xml.</span></span>  
  
2.  <span data-ttu-id="571e1-154">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="571e1-154">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="571e1-155">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-155">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="b-updating-multiple-records-by-using-the-updgid-attribute"></a><span data-ttu-id="571e1-156">B.</span><span class="sxs-lookup"><span data-stu-id="571e1-156">B.</span></span> <span data-ttu-id="571e1-157">Aktualisieren von mehreren Datensätzen mit dem Attribut "updg:id"</span><span class="sxs-lookup"><span data-stu-id="571e1-157">Updating multiple records by using the updg:id attribute</span></span>  
 <span data-ttu-id="571e1-158">In diesem Beispiel führt das Updategram zwei Updates auf die HumanResources.Shift-Tabelle in der AdventureWorks-Datenbank aus:</span><span class="sxs-lookup"><span data-stu-id="571e1-158">In this example, the updategram performs two updates on the HumanResources.Shift table in the AdventureWorks database:</span></span>  
  
-   <span data-ttu-id="571e1-159">Es ändert den Namen der ursprünglichen Tagschicht, die um 7.00 Uhr beginnt, von "Day" in "Early Morning".</span><span class="sxs-lookup"><span data-stu-id="571e1-159">It changes the name of the original day shift that starts at 7:00AM from "Day" to "Early Morning".</span></span>  
  
-   <span data-ttu-id="571e1-160">Es fügt eine neue Schicht namens "Late Morning" ein, die um 10.00 Uhr beginnt.</span><span class="sxs-lookup"><span data-stu-id="571e1-160">It inserts a new shift named "Late Morning" that starts at 10:00AM.</span></span>  
  
 <span data-ttu-id="571e1-161">Im Update Gram `updg:id` erstellt das-Attribut Zuordnungen zwischen Elementen in den **\<before>** -und- **\<after>** Blöcken.</span><span class="sxs-lookup"><span data-stu-id="571e1-161">In the updategram, the `updg:id` attribute creates associations between elements in the **\<before>** and **\<after>** blocks.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift updg:id="x" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift updg:id="y" Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
      <HumanResources.Shift updg:id="x" Name="Early Morning" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="571e1-162">Beachten Sie, wie das- `updg:id` Attribut die erste Instanz des- \<HumanResources.Shift> Elements im- **\<before>** Block mit der zweiten Instanz des- \<HumanResources.Shift> Elements im- **\<after>** Block verbindet.</span><span class="sxs-lookup"><span data-stu-id="571e1-162">Notice how the `updg:id` attribute pairs the first instance of the \<HumanResources.Shift> element in the **\<before>** block with the second instance of the \<HumanResources.Shift> element in the **\<after>** block.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="571e1-163">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="571e1-163">To test the updategram</span></span>  
  
1.  <span data-ttu-id="571e1-164">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-164">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="571e1-165">Speichern Sie die Datei unter dem Dateinamen UpdateMultipleRecords.xml.</span><span class="sxs-lookup"><span data-stu-id="571e1-165">Save the file as UpdateMultipleRecords.xml.</span></span>  
  
2.  <span data-ttu-id="571e1-166">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="571e1-166">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="571e1-167">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-167">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="c-specifying-multiple-before-and-after-blocks"></a><span data-ttu-id="571e1-168">C.</span><span class="sxs-lookup"><span data-stu-id="571e1-168">C.</span></span> <span data-ttu-id="571e1-169">Angeben von mehreren \<before> -und- \<after> Blöcken</span><span class="sxs-lookup"><span data-stu-id="571e1-169">Specifying multiple \<before> and \<after> blocks</span></span>  
 <span data-ttu-id="571e1-170">Um Mehrdeutigkeit zu vermeiden, können Sie das Update Gram in Beispiel B mithilfe mehrerer **\<before>** -und- **\<after>** Block Paare schreiben.</span><span class="sxs-lookup"><span data-stu-id="571e1-170">To avoid ambiguity, you can write the updategram in Example B by using multiple **\<before>** and **\<after>** block pairs.</span></span> <span data-ttu-id="571e1-171">Das Angeben von **\<before>** -Paaren und- **\<after>** Paaren ist eine Möglichkeit, mehrere Updates mit einer minimalen Verwirrung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-171">Specifying **\<before>** and **\<after>** pairs is one way of specifying multiple updates with a minimum of confusion.</span></span> <span data-ttu-id="571e1-172">Außerdem **\<before>** müssen Sie das-Attribut nicht verwenden, wenn jeder der-und- **\<after>** Blöcke höchstens ein-Element angibt `updg:id` .</span><span class="sxs-lookup"><span data-stu-id="571e1-172">Also, if each of the **\<before>** and **\<after>** blocks specify at most one element, you do not have to use the `updg:id` attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="571e1-173">Um ein paar zu bilden, **\<after>** muss das Tag direkt auf das entsprechende **\<before>** Tag folgen.</span><span class="sxs-lookup"><span data-stu-id="571e1-173">To form a pair, the **\<after>** tag must immediately follow its corresponding **\<before>** tag.</span></span>  
  
 <span data-ttu-id="571e1-174">Im folgenden Update Gram aktualisiert das erste und das **\<before>** **\<after>** Paar den Verschiebungs Namen für die Tagesschicht.</span><span class="sxs-lookup"><span data-stu-id="571e1-174">In the following updategram, the first **\<before>** and **\<after>** pair updates the shift name for the day shift.</span></span> <span data-ttu-id="571e1-175">Das zweite Paar fügt einen neuen Schichtdatensatz ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-175">The second pair inserts a new shift record.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1" Name="Day" />  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Early Morning" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <HumanResources.Shift Name="Late Morning"   
                            StartTime="1900-01-01 10:00:00.000"  
                            EndTime="1900-01-01 18:00:00.000"  
                            ModifiedDate="2004-06-01 00:00:00.000"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="571e1-176">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="571e1-176">To test the updategram</span></span>  
  
1.  <span data-ttu-id="571e1-177">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-177">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="571e1-178">Speichern Sie die Datei unter dem Dateinamen UpdateMultipleBeforeAfter.xml.</span><span class="sxs-lookup"><span data-stu-id="571e1-178">Save the file as UpdateMultipleBeforeAfter.xml.</span></span>  
  
2.  <span data-ttu-id="571e1-179">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="571e1-179">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="571e1-180">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-180">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-specifying-multiple-sync-blocks"></a><span data-ttu-id="571e1-181">D:</span><span class="sxs-lookup"><span data-stu-id="571e1-181">D.</span></span> <span data-ttu-id="571e1-182">Angeben mehrerer \<sync> Blöcke</span><span class="sxs-lookup"><span data-stu-id="571e1-182">Specifying multiple \<sync> blocks</span></span>  
 <span data-ttu-id="571e1-183">Sie können mehrere- **\<sync>** Blöcke in einem Update Gram angeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-183">You can specify multiple **\<sync>** blocks in an updategram.</span></span> <span data-ttu-id="571e1-184">Jeder **\<sync>** angegebene Block ist eine unabhängige Transaktion.</span><span class="sxs-lookup"><span data-stu-id="571e1-184">Each **\<sync>** block that is specified is an independent transaction.</span></span>  
  
 <span data-ttu-id="571e1-185">Im folgenden Update Gram aktualisiert der erste **\<sync>** Block einen Datensatz in der Sales. Customer-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="571e1-185">In the following updategram, the first **\<sync>** block updates a record in the Sales.Customer table.</span></span> <span data-ttu-id="571e1-186">Der Einfachheit halber gibt das Updategram nur die erforderlichen Spaltenwerte an, nämlich den Identitätswert (CustomerID) und den zu aktualisierenden Wert (SalesPersonID).</span><span class="sxs-lookup"><span data-stu-id="571e1-186">For the sake of simplicity, the updategram specifies only the required column values; the identity value (CustomerID) and the value being updated (SalesPersonID).</span></span>  
  
 <span data-ttu-id="571e1-187">Der zweite **\<sync>** Block fügt der Sales. SalesOrderHeader-Tabelle zwei Datensätze hinzu.</span><span class="sxs-lookup"><span data-stu-id="571e1-187">The second **\<sync>** block adds two records to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="571e1-188">Für diese Tabelle ist SalesOrderID eine Spalte vom Typ IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="571e1-188">For this table, SalesOrderID is an IDENTITY-type column.</span></span> <span data-ttu-id="571e1-189">Daher gibt das Update Gram den Wert von SalesOrderID nicht in jedem der \<Sales.SalesOrderHeader> Elemente an.</span><span class="sxs-lookup"><span data-stu-id="571e1-189">Therefore, the updategram does not specify the value of SalesOrderID in each of the \<Sales.SalesOrderHeader> elements.</span></span>  
  
 <span data-ttu-id="571e1-190">Das Angeben mehrerer **\<sync>** Blöcke ist nützlich, da der zweite Block **\<sync>** (eine Transaktion) der Sales. SalesOrderHeader-Tabelle keine Datensätze hinzufügen kann. der erste **\<sync>** Block kann weiterhin den Kundendaten Satz in der Sales. Customer-Tabelle aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="571e1-190">Specifying multiple **\<sync>** blocks is useful because if the second **\<sync>** block (a transaction) fails to add records to Sales.SalesOrderHeader table, the first **\<sync>** block can still update the customer record in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
      <Sales.Customer CustomerID="1" SalesPersonID="280" />  
    </updg:before>  
    <updg:after>  
      <Sales.Customer CustomerID="1" SalesPersonID="283" />  
    </updg:after>  
  </updg:sync>  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
   <Sales.SalesOrderHeader   
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="01010101-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-08 00:00:00.000" />  
   <Sales.SalesOrderHeader  
             CustomerID="1"  
             RevisionNumber="1"  
             OrderDate="2004-07-01 00:00:00.000"  
             DueDate="2004-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="1000.0000"  
             TaxAmt="0.0000"  
             Freight="0.0000"  
             rowguid="10101010-2222-3333-4444-556677889900"  
             ModifiedDate="2004-07-09 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="571e1-191">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="571e1-191">To test the updategram</span></span>  
  
1.  <span data-ttu-id="571e1-192">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-192">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="571e1-193">Speichern Sie die Datei unter dem Dateinamen UpdateMultipleSyncs.xml.</span><span class="sxs-lookup"><span data-stu-id="571e1-193">Save the file as UpdateMultipleSyncs.xml.</span></span>  
  
2.  <span data-ttu-id="571e1-194">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="571e1-194">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="571e1-195">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-195">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-a-mapping-schema"></a><span data-ttu-id="571e1-196">E.</span><span class="sxs-lookup"><span data-stu-id="571e1-196">E.</span></span> <span data-ttu-id="571e1-197">Verwenden eines Zuordnungsschemas</span><span class="sxs-lookup"><span data-stu-id="571e1-197">Using a mapping schema</span></span>  
 <span data-ttu-id="571e1-198">In diesem Beispiel gibt das Updategram mithilfe des `mapping-schema`-Attributs ein Zuordnungsschema an.</span><span class="sxs-lookup"><span data-stu-id="571e1-198">In this example, the updategram specifies a mapping schema by using the `mapping-schema` attribute.</span></span> <span data-ttu-id="571e1-199">(Es gibt keine Standardzuordnung, d. h. das Zuordnungsschema bietet die erforderliche Zuordnung der Elemente und Attribute im Updategram zu den Datenbanktabellen und -spalten.)</span><span class="sxs-lookup"><span data-stu-id="571e1-199">(There is no default mapping; that is, the mapping schema provides the necessary mapping of elements and attributes in the updategram to the database tables and columns.)</span></span>  
  
 <span data-ttu-id="571e1-200">Die im Updategram angegebenen Elemente und Attribute verweisen auf die Elemente und Attribute im Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="571e1-200">The elements and attributes specified in the updategram refer to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="571e1-201">Das folgende XSD-Zuordnungs Schema enthält die **\<Customer>** Elemente, und, die **\<Order>** **\<OD>** den Tabellen Sales. Customer, Sales. SalesOrderHeader und Sales. SalesOrderDetail in der-Datenbank zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="571e1-201">The following XSD mapping schema has **\<Customer>**, **\<Order>**, and **\<OD>** elements that map to the Sales.Customer, Sales.SalesOrderHeader, and Sales.SalesOrderDetail tables in the database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustomerOrder"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustomerOrder" >  
           <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OD"   
                             sql:relation="Sales.SalesOrderDetail"  
                             sql:relationship="OrderOD" >  
                 <xsd:complexType>  
                  <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                  <xsd:attribute name="ProductID" type="xsd:integer" />  
                  <xsd:attribute name="UnitPrice" type="xsd:decimal" />  
                  <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  <xsd:attribute name="UnitPriceDiscount" type="xsd:decimal" />   
                 </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
           </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="571e1-202">Dieses Zuordnungsschema (UpdategramMappingSchema.xml) wird im folgenden Updategram angegeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-202">This mapping schema (UpdategramMappingSchema.xml) is specified in the following updategram.</span></span> <span data-ttu-id="571e1-203">Das Updategram fügt in der Sales.SalesOrderDetail-Tabelle ein Auftragselement für einen bestimmten Auftrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="571e1-203">The updategram adds an order detail item in the Sales.SalesOrderDetail table for a specific order.</span></span> <span data-ttu-id="571e1-204">Das Update Gram enthält geschachtelte Elemente: ein **\<OD>** Element, das in einem-Element geschachtelt ist **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-204">The updategram includes nested elements: an **\<OD>** element nested inside an **\<Order>** element.</span></span> <span data-ttu-id="571e1-205">Die Primärschlüssel-Fremdschlüssel-Beziehung zwischen diesen beiden Elementen wird im Zuordnungsschema angegeben.</span><span class="sxs-lookup"><span data-stu-id="571e1-205">The primary key/foreign key relationship between these two elements is specified in the mapping schema.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="UpdategramMappingSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43659" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43659" >  
          <OD ProductID="776" UnitPrice="2329.0000"  
              OrderQty="2" UnitPriceDiscount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="571e1-206">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="571e1-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="571e1-207">Kopieren Sie das oben stehende Zuordnungsschema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-207">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="571e1-208">Speichern Sie die Datei unter dem Dateinamen UpdategramMappingSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="571e1-208">Save the file as UpdategramMappingSchema.xml.</span></span>  
  
2.  <span data-ttu-id="571e1-209">Kopieren Sie die oben stehende Updategramvorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-209">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="571e1-210">Speichern Sie die Datei unter dem Dateinamen UpdateWithMappingSchema.xml im selben Ordner, indem Sie das Zuordnungsschema (UpdategramMappingSchema.xml) gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="571e1-210">Save the file as UpdateWithMappingSchema.xml in the same folder as was used to save the mapping schema (UpdategramMappingSchema.xml).</span></span>  
  
3.  <span data-ttu-id="571e1-211">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="571e1-211">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="571e1-212">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-212">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="571e1-213">Weitere Beispiele für Update grams, die Mapping-Schemas verwenden, finden Sie unter [Angeben eines Mappingschemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-213">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
### <a name="f-using-a-mapping-schema-with-idrefs-attributes"></a><span data-ttu-id="571e1-214">F.</span><span class="sxs-lookup"><span data-stu-id="571e1-214">F.</span></span> <span data-ttu-id="571e1-215">Verwenden eines Zuordnungsschemas mit IDREFS-Attributen</span><span class="sxs-lookup"><span data-stu-id="571e1-215">Using a mapping schema with IDREFS attributes</span></span>  
 <span data-ttu-id="571e1-216">Dieses Beispiel veranschaulicht, wie Updategrams die IDREFS-Attribute im Zuordnungsschema verwenden, um Datensätze in mehreren Tabellen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="571e1-216">This example illustrates how updategrams use the IDREFS attributes in the mapping schema to update records in multiple tables.</span></span> <span data-ttu-id="571e1-217">Nehmen Sie für dieses Beispiel an, dass die Datenbank aus den folgenden Tabellen besteht:</span><span class="sxs-lookup"><span data-stu-id="571e1-217">For this example, assume that the database consists of the following tables:</span></span>  
  
-   <span data-ttu-id="571e1-218">Student(StudentID, LastName)</span><span class="sxs-lookup"><span data-stu-id="571e1-218">Student(StudentID, LastName)</span></span>  
  
-   <span data-ttu-id="571e1-219">Course(CourseID, CourseName)</span><span class="sxs-lookup"><span data-stu-id="571e1-219">Course(CourseID, CourseName)</span></span>  
  
-   <span data-ttu-id="571e1-220">Enrollment(StudentID, CourseID)</span><span class="sxs-lookup"><span data-stu-id="571e1-220">Enrollment(StudentID, CourseID)</span></span>  
  
 <span data-ttu-id="571e1-221">Da ein Student sich in viele Kurse einschreiben kann und an einem Kurs zahlreiche Studenten teilnehmen können, wird die dritte Tabelle, die Enrollment-Tabelle, benötigt, um diese m:n-Beziehung darzustellen.</span><span class="sxs-lookup"><span data-stu-id="571e1-221">Because a student can enroll in many courses and a course can have many students, the third table, the Enrollment table, is required to represent this M:N relationship.</span></span>  
  
 <span data-ttu-id="571e1-222">Das folgende XSD-Mapping-Schema stellt mithilfe der **\<Student>** Elemente, und eine XML-Ansicht der Tabellen bereit **\<Course>** **\<Enrollment>** .</span><span class="sxs-lookup"><span data-stu-id="571e1-222">The following XSD mapping schema provides an XML view of the tables by using the **\<Student>**, **\<Course>**, and **\<Enrollment>** elements.</span></span> <span data-ttu-id="571e1-223">Die **IDREFS** -Attribute im Zuordnungsschema geben die Beziehung zwischen diesen Elementen an.</span><span class="sxs-lookup"><span data-stu-id="571e1-223">The **IDREFS** attributes in the mapping schema specify the relationship between these elements.</span></span> <span data-ttu-id="571e1-224">Das **StudentIDList** -Attribut des- **\<Course>** Elements ist ein Attribut vom Typ **IDREFS** , das auf die StudentID-Spalte in der Registrierungs Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="571e1-224">The **StudentIDList** attribute on the **\<Course>** element is an **IDREFS** type attribute that refers to the StudentID column in the Enrollment table.</span></span> <span data-ttu-id="571e1-225">Entsprechend ist das Attribut " **attribuledin** " für das- **\<Student>** Element ein Attribut vom Typ **IDREFS** , das auf die CourseID-Spalte in der Registrierungs Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="571e1-225">Likewise, the **EnrolledIn** attribute on the **\<Student>** element is an **IDREFS** type attribute that refers to the CourseID column in the Enrollment table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="StudentEnrollment"  
          parent="Student"  
          parent-key="StudentID"  
          child="Enrollment"  
          child-key="StudentID" />  
  
    <sql:relationship name="CourseEnrollment"  
          parent="Course"  
          parent-key="CourseID"  
          child="Enrollment"  
          child-key="CourseID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Course" sql:relation="Course"   
                             sql:key-fields="CourseID" >  
    <xsd:complexType>  
    <xsd:attribute name="CourseID"  type="xsd:string" />   
    <xsd:attribute name="CourseName"   type="xsd:string" />   
    <xsd:attribute name="StudentIDList" sql:relation="Enrollment"  
                 sql:field="StudentID"  
                 sql:relationship="CourseEnrollment"   
                                     type="xsd:IDREFS" />  
  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name="Student" sql:relation="Student" >  
    <xsd:complexType>  
    <xsd:attribute name="StudentID"  type="xsd:string" />   
    <xsd:attribute name="LastName"   type="xsd:string" />   
    <xsd:attribute name="EnrolledIn" sql:relation="Enrollment"  
                 sql:field="CourseID"  
                 sql:relationship="StudentEnrollment"   
                                     type="xsd:IDREFS" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="571e1-226">Jedes Mal, wenn Sie dieses Schema in einem Updategram angeben und einen Datensatz in die Course-Tabelle einfügen, fügt das Updategram einen neuen Kursdatensatz in die Course-Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-226">Whenever you specify this schema in an updategram and insert a record in the Course table, the updategram inserts a new course record in the Course table.</span></span> <span data-ttu-id="571e1-227">Wenn Sie eine oder mehrere neue StudentIDs für das StudentIDList-Attribut angeben, fügt das Updategram ebenfalls einen Datensatz für jeden neuen Studenten in die Enrollment-Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-227">If you specify one or more new student IDs for the StudentIDList attribute, the updategram also inserts a record in the Enrollment table for the each new student.</span></span> <span data-ttu-id="571e1-228">Das Updategram stellt sicher, dass der Enrollment-Tabelle keine Duplikate hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="571e1-228">The updategram ensures that no duplicates are added to the Enrollment table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="571e1-229">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="571e1-229">To test the updategram</span></span>  
  
1.  <span data-ttu-id="571e1-230">Erstellen Sie diese Tabellen in der Datenbank, die im virtuellen Stammverzeichnis angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="571e1-230">Create these tables in the database that is specified in the virtual root:</span></span>  
  
    ```  
    CREATE TABLE Student(StudentID varchar(10) primary key,   
                         LastName varchar(25))  
    CREATE TABLE Course(CourseID varchar(10) primary key,   
                        CourseName varchar(25))  
    CREATE TABLE Enrollment(StudentID varchar(10)   
                                      references Student(StudentID),  
                           CourseID varchar(10)   
                                      references Course(CourseID))  
    ```  
  
2.  <span data-ttu-id="571e1-231">Fügen Sie diese Beispieldaten hinzu:</span><span class="sxs-lookup"><span data-stu-id="571e1-231">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Student VALUES ('S1','Davoli')  
    INSERT INTO Student VALUES ('S2','Fuller')  
  
    INSERT INTO Course VALUES  ('CS101', 'C Programming')  
    INSERT INTO Course VALUES  ('CS102', 'Understanding XML')  
  
    INSERT INTO Enrollment VALUES ('S1', 'CS101')  
    INSERT INTO Enrollment VALUES ('S1', 'CS102')  
    ```  
  
3.  <span data-ttu-id="571e1-232">Kopieren Sie das oben stehende Zuordnungsschema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-232">Copy the mapping schema above and paste it into a text file.</span></span> <span data-ttu-id="571e1-233">Speichern Sie die Datei unter dem Dateinamen SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="571e1-233">Save the file as SampleSchema.xml.</span></span>  
  
4.  <span data-ttu-id="571e1-234">Speichern Sie das Updategram (SampleUpdategram) im selben Ordner, indem Sie das Zuordnungsschema im vorherigen Schritt gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="571e1-234">Save the updategram (SampleUpdategram) in the same folder used to save the mapping schema in the previous step.</span></span> <span data-ttu-id="571e1-235">(Dieses Updategram löscht einen Studenten mit StudentID="1" aus dem Kurs CS102.)</span><span class="sxs-lookup"><span data-stu-id="571e1-235">(This updategram drops a student with StudentID="1" from the CS102 course.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="571e1-236">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="571e1-236">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="571e1-237">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-237">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
6.  <span data-ttu-id="571e1-238">Speichern Sie das Updategram wie in den vorherigen Schritten beschrieben und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="571e1-238">Save and execute the following updategram as described in the previous steps.</span></span> <span data-ttu-id="571e1-239">Das Updategram fügt den Studenten mit StudentID="1" wieder dem Kurs CS102 hinzu, indem der Enrollment-Tabelle ein Datensatz hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="571e1-239">The updategram adds the student with StudentID="1" back into the CS102 course by adding a record in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101" />  
        </updg:before>  
        <updg:after >  
            <Student updg:id="x" StudentID="S1" LastName="Davolio"  
                                 EnrolledIn="CS101 CS102" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
7.  <span data-ttu-id="571e1-240">Speichern Sie das nächste Updategram wie in den vorherigen Schritten beschrieben und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="571e1-240">Save and execute this next updategram as described in the previous steps.</span></span> <span data-ttu-id="571e1-241">Dieses Updategram fügt drei neue Studenten ein und schreibt Sie in den Kurs CS101 ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-241">This updategram inserts three new students and enrolls them in the CS101 course.</span></span> <span data-ttu-id="571e1-242">Wieder fügt die IDREFS-Beziehung Datensätze in der Enrollment-Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="571e1-242">Again, the IDREFS relationship inserts records in the Enrollment table.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleSchema.xml" >  
        <updg:before>  
           <Course updg:id="y" CourseID="CS101"   
                               CourseName="C Programming" />  
        </updg:before>  
        <updg:after >  
           <Student updg:id="x1" StudentID="S3" LastName="Leverling" />  
           <Student updg:id="x2" StudentID="S4" LastName="Pecock" />  
           <Student updg:id="x3" StudentID="S5" LastName="Buchanan" />  
           <Course updg:id="y" CourseID="CS101"  
                               CourseName="C Programming"  
                               StudentIDList="S3 S4 S5" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
 <span data-ttu-id="571e1-243">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="571e1-243">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ElementType name="Enrollment" sql:relation="Enrollment" sql:key-fields="StudentID CourseID">  
    <AttributeType name="StudentID" dt:type="id" />  
    <AttributeType name="CourseID" dt:type="id" />  
  
    <attribute type="StudentID" />  
    <attribute type="CourseID" />  
  </ElementType>  
  <ElementType name="Course" sql:relation="Course" sql:key-fields="CourseID">  
    <AttributeType name="CourseID" dt:type="id" />  
    <AttributeType name="CourseName" />  
  
    <attribute type="CourseID" />  
    <attribute type="CourseName" />  
  
    <AttributeType name="StudentIDList" dt:type="idrefs" />  
    <attribute type="StudentIDList" sql:relation="Enrollment" sql:field="StudentID" >  
        <sql:relationship  
                key-relation="Course"  
                key="CourseID"  
                foreign-relation="Enrollment"  
                foreign-key="CourseID" />  
    </attribute>  
  
  </ElementType>  
  <ElementType name="Student" sql:relation="Student">  
    <AttributeType name="StudentID" dt:type="id" />  
     <AttributeType name="LastName" />  
  
    <attribute type="StudentID" />  
    <attribute type="LastName" />  
  
    <AttributeType name="EnrolledIn" dt:type="idrefs" />  
    <attribute type="EnrolledIn" sql:relation="Enrollment" sql:field="CourseID" >  
        <sql:relationship  
                key-relation="Student"  
                key="StudentID"  
                foreign-relation="Enrollment"  
                foreign-key="StudentID" />  
    </attribute>  
  
    <element type="Enrollment" sql:relation="Enrollment" >  
        <sql:relationship key-relation="Student"  
                          key="StudentID"  
                          foreign-relation="Enrollment"  
                          foreign-key="StudentID" />  
    </element>  
  </ElementType>  
  
</Schema>  
```  
  
 <span data-ttu-id="571e1-244">Weitere Beispiele für Update grams, die Mapping-Schemas verwenden, finden Sie unter [Angeben eines Mappingschemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="571e1-244">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571e1-245">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="571e1-245">See Also</span></span>  
 [<span data-ttu-id="571e1-246">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="571e1-246">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
