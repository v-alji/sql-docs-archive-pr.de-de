---
title: Einfügen von Daten mit XML-Update grams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- xsi:nil attribute
- unique values
- <after> block
- id attribute
- data insertions [SQLXML]
- nil attribute
- <before> block
- updg:guid attribute
- multiple record insertions
- returnid attribute
- updategrams [SQLXML], inserting data
- updg:at-identity attribute
- invalid characters [SQLXML]
- updg:returnid attribute
- updg:id attribute
- namespaces [SQLXML], updategrams
- IDENTITY-type column
- guid attribute
- record insertion [SQLXML]
- null values [SQLXML]
- at-identity attribute
- xml data type [SQL Server], SQLXML
ms.assetid: 4dc48762-bc12-43fb-b356-ea1b9c1e287e
author: rothja
ms.author: jroth
ms.openlocfilehash: a80f2cb157e59f30ebcbff5c14abba1003de9e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700862"
---
# <a name="inserting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="10724-102">Einfügen von Daten mit XML-Updategrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="10724-102">Inserting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="10724-103">Ein Update Gram zeigt einen Einfügevorgang an, wenn eine Daten Satz Instanz im- **\<after>** Block, jedoch nicht im entsprechenden-Block angezeigt wird **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="10724-103">An updategram indicates an insert operation when a record instance appears in the **\<after>** block but not in the corresponding **\<before>** block.</span></span> <span data-ttu-id="10724-104">In diesem Fall fügt das Update Gram den Datensatz im-Block in **\<after>** die Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="10724-104">In this case, the updategram inserts the record in the **\<after>** block into the database.</span></span>  
  
 <span data-ttu-id="10724-105">Dies ist das Updategramformat für einen Einfügevorgang:</span><span class="sxs-lookup"><span data-stu-id="10724-105">This is the updategram format for an insert operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   [<updg:before>  
   </updg:before>]  
    <updg:after [updg:returnid="x y ...] >  
       <ElementName [updg:id="value"]   
                   [updg:at-identity="x"]   
                   [updg:guid="y"]  
                   attribute="value"   
                   attribute="value"  
                   ...  
       />  
      [<ElementName .../>... ]  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
## <a name="before-block"></a><span data-ttu-id="10724-106">\<before>Baustein</span><span class="sxs-lookup"><span data-stu-id="10724-106">\<before> Block</span></span>  
 <span data-ttu-id="10724-107">Der- **\<before>** Block kann für einen Einfügevorgang ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="10724-107">The **\<before>** block can be omitted for an insert operation.</span></span> <span data-ttu-id="10724-108">Wenn das optionale- `mapping-schema` Attribut nicht angegeben wird, wird der **\<ElementName>** im Update Gram angegebene einer Datenbanktabelle zugeordnet, und die untergeordneten Elemente oder Attribute werden den Spalten in der Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="10724-108">If the optional `mapping-schema` attribute is not specified, the **\<ElementName>** that is specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
## <a name="after-block"></a><span data-ttu-id="10724-109">\<after>Baustein</span><span class="sxs-lookup"><span data-stu-id="10724-109">\<after> Block</span></span>  
 <span data-ttu-id="10724-110">Sie können einen oder mehrere Datensätze im- **\<after>** Block angeben.</span><span class="sxs-lookup"><span data-stu-id="10724-110">You can specify one or more records in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="10724-111">Wenn der- **\<after>** Block keinen Wert für eine bestimmte Spalte bereitstellt, verwendet das Update Gram den Standardwert, der im Schema mit Anmerkungen angegeben ist (sofern ein Schema angegeben wurde).</span><span class="sxs-lookup"><span data-stu-id="10724-111">If the **\<after>** block does not supply a value for a particular column, the updategram uses the default value that is specified in the annotated schema (if a schema has been specified).</span></span> <span data-ttu-id="10724-112">Wenn das Schema keinen Standardwert für die Spalte angibt, gibt das Update Gram keinen expliziten Wert für diese Spalte an und weist stattdessen der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Spalte den Standardwert (falls angegeben) zu.</span><span class="sxs-lookup"><span data-stu-id="10724-112">If the schema does not specify a default value for the column, the updategram does not specify any explicit value to this column and, instead, assigns the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value (if specified) to this column.</span></span> <span data-ttu-id="10724-113">Wenn kein [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Standardwert vorhanden ist, und die Spalte einen NULL-Wert akzeptiert, legt das Updategram den Spaltenwert auf NULL fest.</span><span class="sxs-lookup"><span data-stu-id="10724-113">If there is no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value and the column accepts a NULL value, the updategram sets the column value to NULL.</span></span> <span data-ttu-id="10724-114">Wenn die Spalte weder einen Standardwert besitzt, noch einen NULL-Wert akzeptiert, schlägt der Befehl fehl, und das Updategram gibt einen Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="10724-114">If the column neither has a default value nor accepts a NULL value, the command fails and the updategram returns an error.</span></span> <span data-ttu-id="10724-115">Das optionale `updg:returnid`-Attribut wird verwendet, um den Identitätswert zurückzugeben, der vom System generiert wird, wenn ein Datensatz einer Tabelle mit einer Spalte vom Typ IDENTITY hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="10724-115">The optional `updg:returnid` attribute is used to return the identity value that is generated by the system when a record is added in a table with an IDENTITY-type column.</span></span>  
  
## <a name="updgid-attribute"></a><span data-ttu-id="10724-116">updg:id-Attribut</span><span class="sxs-lookup"><span data-stu-id="10724-116">updg:id Attribute</span></span>  
 <span data-ttu-id="10724-117">Wenn das Updategram nur Datensätze einfügt, erfordert das Updategram das `updg:id`-Attribut nicht.</span><span class="sxs-lookup"><span data-stu-id="10724-117">If the updategram is inserting only records, the updategram does not require the `updg:id` attribute.</span></span> <span data-ttu-id="10724-118">Weitere Informationen zu `updg:id` finden Sie unter [Aktualisieren von Daten mit XML-Update grams &#40;SQLXML 4,0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="10724-118">For more information about `updg:id`, see [Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="updgat-identity-attribute"></a><span data-ttu-id="10724-119">updg:at-identity-Attribut</span><span class="sxs-lookup"><span data-stu-id="10724-119">updg:at-identity Attribute</span></span>  
 <span data-ttu-id="10724-120">Wenn ein Updategram einen Datensatz in eine Tabelle mit einer Spalte vom Typ IDENTITY einfügt, kann das Updategram mithilfe des optionalen `updg:at-identity`-Attributs den vom System zugewiesenen Wert erfassen.</span><span class="sxs-lookup"><span data-stu-id="10724-120">When an updategram inserts a record in a table that has an IDENTITY-type column, the updategram can capture the system assigned value by using the optional `updg:at-identity` attribute.</span></span> <span data-ttu-id="10724-121">Das Updategram kann dann diesen Wert in nachfolgenden Vorgängen verwenden.</span><span class="sxs-lookup"><span data-stu-id="10724-121">The updategram can then use this value in subsequent operations.</span></span> <span data-ttu-id="10724-122">Beim Ausführen des Updategrams können Sie den generierten Identitätswert zurückgeben lassen, indem Sie das `updg:returnid`-Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="10724-122">Upon execution of the updategram, you can return the identity value that is generated by specifying the `updg:returnid` attribute.</span></span>  
  
## <a name="updgguid-attribute"></a><span data-ttu-id="10724-123">updg:guid-Attribut</span><span class="sxs-lookup"><span data-stu-id="10724-123">updg:guid Attribute</span></span>  
 <span data-ttu-id="10724-124">Das `updg:guid`-Attribut ist ein optionales Attribut, das einen global eindeutigen Bezeichner (Globally Unique Identifier, GUID) generiert.</span><span class="sxs-lookup"><span data-stu-id="10724-124">The `updg:guid` attribute is an optional attribute that generates a globally unique identifier.</span></span> <span data-ttu-id="10724-125">Dieser Wert bleibt im Gültigkeitsbereich für den gesamten **\<sync>** Block, in dem er angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="10724-125">This value remains in scope for the entire **\<sync>** block in which it is specified.</span></span> <span data-ttu-id="10724-126">Sie können diesen Wert an beliebiger Stelle im- **\<sync>** Block verwenden.</span><span class="sxs-lookup"><span data-stu-id="10724-126">You can use this value anywhere in the **\<sync>** block.</span></span> <span data-ttu-id="10724-127">Das Attribut ruft die- `NEWGUID()` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Funktion auf, um den eindeutigen Bezeichner zu generieren.</span><span class="sxs-lookup"><span data-stu-id="10724-127">The attribute calls the `NEWGUID()`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] function to generate the unique identifier.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="10724-128">Beispiele</span><span class="sxs-lookup"><span data-stu-id="10724-128">Examples</span></span>  
 <span data-ttu-id="10724-129">Wenn Sie in den folgenden Beispielen funktionierende Beispiele erstellen möchten, müssen Sie die unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../../sqlxml/requirements-for-running-sqlxml-examples.md)angegebenen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="10724-129">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="10724-130">Beachten Sie vor der Verwendung der Update Gram-Beispiele Folgendes:</span><span class="sxs-lookup"><span data-stu-id="10724-130">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="10724-131">Die meisten der Beispiele verwenden die Standardzuordnung (d. h. es ist kein Zuordnungsschema im Updategram angegeben).</span><span class="sxs-lookup"><span data-stu-id="10724-131">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="10724-132">Weitere Beispiele für Update grams, die Mapping-Schemas verwenden, finden Sie unter [Angeben eines Mappingschemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="10724-132">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="10724-133">Die meisten Beispiele verwenden die [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)]-Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="10724-133">Most of the examples use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="10724-134">Alle Updates werden für die Tabellen in dieser Datenbank übernommen.</span><span class="sxs-lookup"><span data-stu-id="10724-134">All the updates are applied to the tables in this database.</span></span>  
  
### <a name="a-inserting-a-record-by-using-an-updategram"></a><span data-ttu-id="10724-135">A.</span><span class="sxs-lookup"><span data-stu-id="10724-135">A.</span></span> <span data-ttu-id="10724-136">Einfügen eines Datensatzes mithilfe eines Updategrams</span><span class="sxs-lookup"><span data-stu-id="10724-136">Inserting a record by using an updategram</span></span>  
 <span data-ttu-id="10724-137">Dieses attributzentrierte Updategram fügt einen Datensatz in die HumanResources.Employee-Tabelle in der [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)]-Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="10724-137">This attribute-centric updategram inserts a record in the HumanResources.Employee table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="10724-138">In diesem Beispiel gibt das Updategram kein Zuordnungsschema an.</span><span class="sxs-lookup"><span data-stu-id="10724-138">In this example, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="10724-139">Daher verwendet das Updategram die Standardzuordnung, in der der Elementname einem Tabellennamen und die untergeordneten Elemente oder Attribute den Spalten in dieser Tabelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="10724-139">Therefore, the updategram uses default mapping, in which the element name maps to a table name and the attributes or child elements map to columns in that table.</span></span>  
  
 <span data-ttu-id="10724-140">Das [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)]-Schema für die HumanResources.Department-Tabelle erzwingt eine NOT NULL-Einschränkung für alle Spalten.</span><span class="sxs-lookup"><span data-stu-id="10724-140">The [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] schema for the HumanResources.Department table imposes a 'not null' restriction on all columns.</span></span> <span data-ttu-id="10724-141">Daher muss das Updategram für alle Spalten angegebene Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="10724-141">Therefore, the updategram must include values specified for all columns.</span></span> <span data-ttu-id="10724-142">DepartmentID ist eine Spalte vom Typ IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="10724-142">The DepartmentID is an IDENTITY-type column.</span></span> <span data-ttu-id="10724-143">Daher werden keine Werte dafür angegeben.</span><span class="sxs-lookup"><span data-stu-id="10724-143">Therefore, no values are specified for it.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name="New Product Research"   
            GroupName="Research and Development"   
            ModifiedDate="2010-08-31"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="10724-144">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="10724-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="10724-145">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-145">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-146">Speichern Sie die Datei unter dem Dateinamen MyUpdategram.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-146">Save the file as MyUpdategram.xml.</span></span>  
  
2.  <span data-ttu-id="10724-147">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-147">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="10724-148">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-148">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="10724-149">In einer elementzentrierten Zuordnung sieht das Updategram aus wie folgt:</span><span class="sxs-lookup"><span data-stu-id="10724-149">In an element-centric mapping, the updategram looks like this:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department>  
            <Name> New Product Research </Name>  
            <GroupName> Research and Development </GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-150">Im gemischten Modus (elementzentriert und attributzentriert) kann ein Element sowohl Attribute als auch Unterelemente aufweisen, wie in diesem Updategram gezeigt:</span><span class="sxs-lookup"><span data-stu-id="10724-150">In a mixed-mode (element-centric and attribute-centric) updategram, an element can have both attributes and subelements, as shown in this updategram:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name=" New Product Research "   
            <GroupName>Research and Development</GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="b-inserting-multiple-records-by-using-an-updategram"></a><span data-ttu-id="10724-151">B.</span><span class="sxs-lookup"><span data-stu-id="10724-151">B.</span></span> <span data-ttu-id="10724-152">Einfügen mehrerer Datensätze mithilfe eines Updategrams</span><span class="sxs-lookup"><span data-stu-id="10724-152">Inserting multiple records by using an updategram</span></span>  
 <span data-ttu-id="10724-153">Dieses Updategram fügt der HumanResources.Shift-Tabelle zwei neue Schichtdatensätze hinzu.</span><span class="sxs-lookup"><span data-stu-id="10724-153">This updategram adds two new shift records to the HumanResources.Shift table.</span></span> <span data-ttu-id="10724-154">Das Update Gram gibt den optionalen Block nicht an **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="10724-154">The updategram does not specify the optional **\<before>** block.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="10724-155">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="10724-155">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="10724-156">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-156">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-157">Speichern Sie die Datei unter dem Dateinamen Updategram-AddShifts.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-157">Save the file as Updategram-AddShifts.xml.</span></span>  
  
2.  <span data-ttu-id="10724-158">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="10724-159">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="10724-160">Eine andere Version dieses Beispiels ist ein Update Gram, das zwei separate **\<after>** Blöcke anstelle eines Blocks verwendet, um die beiden Mitarbeiter einzufügen.</span><span class="sxs-lookup"><span data-stu-id="10724-160">Another version of this example is an updategram that uses two separate **\<after>** blocks instead of one block to insert the two employees.</span></span> <span data-ttu-id="10724-161">Dies ist gültig und kann wie folgt codiert werden:</span><span class="sxs-lookup"><span data-stu-id="10724-161">This is valid and can be encoded as follows:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after >  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="c-working-with-valid-sql-server-characters-that-are-not-valid-in-xml"></a><span data-ttu-id="10724-162">C.</span><span class="sxs-lookup"><span data-stu-id="10724-162">C.</span></span> <span data-ttu-id="10724-163">Arbeiten mit gültigen SQL Server-Zeichen, die in XML nicht gültig sind</span><span class="sxs-lookup"><span data-stu-id="10724-163">Working with valid SQL Server characters that are not valid in XML</span></span>  
 <span data-ttu-id="10724-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] können Tabellennamen Leerzeichen enthalten, wie beispielsweise die Order Details-Tabelle in der Northwind-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="10724-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space, such as the Order Details table in the Northwind database.</span></span> <span data-ttu-id="10724-165">Dies gilt jedoch nicht für XML-Zeichen, die gültige [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Bezeichner sind, aber keine gültigen XML-IDs können mithilfe von "__xHHHH \_ \_ " als Codierungs Wert codiert werden, wobei "HHHH" für den vierstelligen hexadezimalen UCS-2-Code für das Zeichen in der signifikantesten bidirektionalen Reihenfolge steht.</span><span class="sxs-lookup"><span data-stu-id="10724-165">However, this is not valid in XML characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but not valid XML identifiers can be encoded using '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10724-166">Für dieses Beispiel wird die Northwind-Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="10724-166">This example uses the Northwind database.</span></span> <span data-ttu-id="10724-167">Sie können die Northwind-Datenbank mithilfe eines SQL-Skripts installieren, das von dieser [Microsoft](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)-Website heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="10724-167">You can install the Northwind database by using an SQL script available for download from this [Microsoft Web site](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>  
  
 <span data-ttu-id="10724-168">Der Elementname muss in Klammern ([ ]) stehen.</span><span class="sxs-lookup"><span data-stu-id="10724-168">Also, the element name must be enclosed within brackets ([ ]).</span></span> <span data-ttu-id="10724-169">Da die Zeichen [und] in XML nicht gültig sind, müssen Sie Sie als _x005B \_ bzw. _x005D codieren \_ .</span><span class="sxs-lookup"><span data-stu-id="10724-169">Because the characters [and] are not valid in XML, you must encode them as _x005B\_ and _x005D\_, respectively.</span></span> <span data-ttu-id="10724-170">(Falls Sie ein Zuordnungsschema verwenden, können Sie Elementnamen bereitstellen, die keine ungültigen Zeichen wie Leezeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="10724-170">(If you use a mapping schema, you can provide element names that do not contain characters that are not valid, such as white spaces.</span></span> <span data-ttu-id="10724-171">Die erforderliche Zuordnung erfolgt über das Zuordnungsschema, daher müssen Sie diese Zeichen nicht codieren.)</span><span class="sxs-lookup"><span data-stu-id="10724-171">The mapping schema does the necessary mapping; therefore, you do not need to encode for these characters).</span></span>  
  
 <span data-ttu-id="10724-172">Dieses Updategram fügt der Order Details-Tabelle der Northwind-Datenbank einen Datensatz hinzu:</span><span class="sxs-lookup"><span data-stu-id="10724-172">This updategram adds a record to the Order Details table in the Northwind database:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <_x005B_Order_x0020_Details_x005D_ OrderID="1"  
            ProductID="11"  
            UnitPrice="$1.0"  
            Quantity="1"  
            Discount="0.0" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-173">Die UnitPrice-Spalte in der Order Details-Tabelle ist vom Typ `money`.</span><span class="sxs-lookup"><span data-stu-id="10724-173">The UnitPrice column in the Order Details table is of the `money` type.</span></span> <span data-ttu-id="10724-174">Zum Anwenden der geeigneten Typkonvertierung (vom `string`-Typ zum `money`-Typ) muss dem Wert das Dollarzeichen ($) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="10724-174">To apply the appropriate type conversion (from a `string` type to a `money` type), the dollar sign character ($) must be added as part of the value.</span></span> <span data-ttu-id="10724-175">Wenn im Updategram kein Zuordnungsschema angegeben ist, wird das erste Zeichen des `string`-Werts ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="10724-175">If the updategram does not specify a mapping schema, the first character of the `string` value is evaluated.</span></span> <span data-ttu-id="10724-176">Wenn das erste Zeichen ein Dollarzeichen ($) ist, wird die entsprechende Konvertierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="10724-176">If the first character is a dollar sign ($), the appropriate conversion is applied.</span></span>  
  
 <span data-ttu-id="10724-177">Wenn für das Updategram ein Zuordnungsschema angegeben wird, in dem die Spalte als `dt:type="fixed.14.4"` bzw. `sql:datatype="money"` markiert ist, ist das Dollarzeichen ($) nicht erforderlich, und die Konvertierung wird anhand der Zuordnung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10724-177">If the updategram is specified against a mapping schema where the column is appropriately marked as either `dt:type="fixed.14.4"` or `sql:datatype="money"`, the dollar sign ($) is not required and the conversion is handled by the mapping.</span></span> <span data-ttu-id="10724-178">Dies ist die empfohlene Methode, um sicherzustellen, dass die richtige Typkonvertierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="10724-178">This is the recommended way to ensure that the appropriate type conversion occurs.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="10724-179">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="10724-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="10724-180">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-180">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-181">Speichern Sie die Datei unter dem Dateinamen UpdategramSpacesInTableName.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-181">Save the file as UpdategramSpacesInTableName.xml.</span></span>  
  
2.  <span data-ttu-id="10724-182">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-182">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="10724-183">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-183">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-using-the-at-identity-attribute-to-retrieve-the-value-that-has-been-inserted-in-the-identity-type-column"></a><span data-ttu-id="10724-184">D:</span><span class="sxs-lookup"><span data-stu-id="10724-184">D.</span></span> <span data-ttu-id="10724-185">Verwenden des at-identity-Attributs, um den in die Spalte vom Typ IDENTITY eingefügten Wert abzurufen</span><span class="sxs-lookup"><span data-stu-id="10724-185">Using the at-identity attribute to retrieve the value that has been inserted in the IDENTITY-type column</span></span>  
 <span data-ttu-id="10724-186">Das folgende Updategram fügt zwei Datensätze ein: einen in die Sales.SalesOrderHeader-Tabelle und einen in die Sales.SalesOrderDetail-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="10724-186">The following updategram inserts two records: one in the Sales.SalesOrderHeader table and another in the Sales.SalesOrderDetail table.</span></span>  
  
 <span data-ttu-id="10724-187">Zuerst fügt das Updategram der Sales.SalesOrderHeader-Tabelle einen Datensatz hinzu.</span><span class="sxs-lookup"><span data-stu-id="10724-187">First, the updategram adds a record to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="10724-188">In dieser Tabelle ist SalesOrderID eine Spalte vom Typ IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="10724-188">In this table, the SalesOrderID column is an IDENTITY-type column.</span></span> <span data-ttu-id="10724-189">Daher verwendet das Updategram das `at-identity`-Attribut, wenn Sie der Tabelle diesen Datensatz hinzufügen, um den zugeordneten SalesOrderID-Wert als "x" (einen Platzhalterwert) zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="10724-189">Therefore, when you add this record to the table, the updategram uses the `at-identity` attribute to capture the assigned SalesOrderID value as "x" (a placeholder value).</span></span> <span data-ttu-id="10724-190">Der Update Gram gibt dann diese `at-identity` Variable als Wert des SalesOrderID-Attributs im- \<Sales.SalesOrderDetail> Element an.</span><span class="sxs-lookup"><span data-stu-id="10724-190">The updategam then specifies this `at-identity` variable as the value of SalesOrderID attribute in the \<Sales.SalesOrderDetail> element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
   <Sales.SalesOrderHeader updg:at-identity="x"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00001111-2222-3333-4444-556677889900"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
      <Sales.SalesOrderDetail SalesOrderID="x"  
                LineNumber="1"  
                OrderQty="1"  
                ProductID="776"  
                SpecialOfferID="1"  
                UnitPrice="2429.9928"  
                UnitPriceDiscount="0.00"  
                rowguid="aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"  
                ModifiedDate="2001-07-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-191">Wenn Sie den vom `updg:at-identity`-Attribut generierten Identitätswert zurückgeben möchten, können Sie das `updg:returnid`-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="10724-191">If you want to return the identity value that is generated by the `updg:at-identity` attribute, you can use the `updg:returnid` attribute.</span></span> <span data-ttu-id="10724-192">Es folgt ein überarbeitetes Updategram, das diesen Identitätswert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="10724-192">The following is a revised updategram that returns this identity value.</span></span> <span data-ttu-id="10724-193">(Dieses Updategram fügt zwei Order-Datensätze und zwei Order Detail-Datensätze hinzu, um das Beispiel ein bisschen zu komplizieren.)</span><span class="sxs-lookup"><span data-stu-id="10724-193">(This updategram adds two order records and two order detail records, just to make the example a little more complex.)</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync>  
  <updg:before>  
  </updg:before>  
  <updg:after updg:returnid="x y" >  
       <HumanResources.Shift updg:at-identity="x" Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift updg:at-identity="y" Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:after>  
 </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-194">Wenn das Updategram ausgeführt wird, gibt es Ergebnisse wie die folgenden zurück, unter anderem den Identitätswert (den generierten Wert der für Tabellenidentität verwendeten ShiftID-Spalte):</span><span class="sxs-lookup"><span data-stu-id="10724-194">When the updategram is executed, it returns results similar to the following, which includes the identity value (the generated value of the ShiftID column used for table identity) that was generated:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">   
  <returnid>   
    <x>4</x>   
    <y>5</y>   
  </returnid>   
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="10724-195">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="10724-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="10724-196">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-196">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-197">Speichern Sie die Datei unter dem Dateinamen Updategram-returnId.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-197">Save the file as Updategram-returnId.xml.</span></span>  
  
2.  <span data-ttu-id="10724-198">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-198">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="10724-199">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-199">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-the-updgguid-attribute-to-generate-a-unique-value"></a><span data-ttu-id="10724-200">E.</span><span class="sxs-lookup"><span data-stu-id="10724-200">E.</span></span> <span data-ttu-id="10724-201">Verwenden des updg:guid-Attributs, um einen eindeutigen Wert zu generieren</span><span class="sxs-lookup"><span data-stu-id="10724-201">Using the updg:guid attribute to generate a unique value</span></span>  
 <span data-ttu-id="10724-202">In diesem Beispiel fügt das Updategram einen Datensatz in die Tabellen Cust und CustOrder ein.</span><span class="sxs-lookup"><span data-stu-id="10724-202">In this example, the updategram inserts a record in the Cust and CustOrder tables.</span></span> <span data-ttu-id="10724-203">Das Updategram generiert außerdem einen eindeutigen Wert für das CustomerID-Attribut mithilfe des `updg:guid`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="10724-203">Also, the updategram generates a unique value for the CustomerID attribute by using the `updg:guid` attribute.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after updg:returnid="x" >  
      <Cust updg:guid="x" >  
         <CustID>x</CustID>  
         <LastName>Fuller</LastName>  
      </Cust>  
      <CustOrder>  
         <CustID>x</CustID>  
         <OrderID>1</OrderID>  
      </CustOrder>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-204">Das Updategram gibt das `returnid`-Attribut an.</span><span class="sxs-lookup"><span data-stu-id="10724-204">The updategram specifies the `returnid` attribute.</span></span> <span data-ttu-id="10724-205">Als Ergebnis wird der generierte GUID zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="10724-205">As a result, the GUID that is generated is returned:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <returnid>  
    <x>7111BD1A-7F0B-4CEE-B411-260DADFEFA2A</x>   
  </returnid>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="10724-206">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="10724-207">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-207">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-208">Speichern Sie die Datei unter dem Dateinamen Updategram-GenerateGuid.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-208">Save the file as Updategram-GenerateGuid.xml.</span></span>  
  
2.  <span data-ttu-id="10724-209">Erstellen Sie die folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="10724-209">Create these tables:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust (CustID uniqueidentifier, LastName varchar(20))  
    CREATE TABLE CustOrder (CustID uniqueidentifier, OrderID int)  
    ```  
  
3.  <span data-ttu-id="10724-210">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-210">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="10724-211">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-211">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="f-specifying-a-schema-in-an-updategram"></a><span data-ttu-id="10724-212">F.</span><span class="sxs-lookup"><span data-stu-id="10724-212">F.</span></span> <span data-ttu-id="10724-213">Angeben eines Schemas in einem Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-213">Specifying a schema in an updategram</span></span>  
 <span data-ttu-id="10724-214">Das Updategram in diesem Beispiel fügt einen Datensatz in die folgende Tabelle ein:</span><span class="sxs-lookup"><span data-stu-id="10724-214">The updategram in this example inserts a record into the following table:</span></span>  
  
```  
CustOrder(OrderID, EmployeeID, OrderType)  
```  
  
 <span data-ttu-id="10724-215">In diesem Updategram wird ein XSD-Schema angegeben (d. h. es gibt keine Standardzuordnung von Updategramelementen und -attributen).</span><span class="sxs-lookup"><span data-stu-id="10724-215">An XSD schema is specified in this updategram (that is, there is no default mapping of updategram elements and attributes).</span></span> <span data-ttu-id="10724-216">Die erforderliche Zuordnung der Elemente und Attribute zu den Datenbanktabellen und -spalten erfolgt durch das Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="10724-216">The schema provides the necessary mapping of the elements and attributes to the database tables and columns.</span></span>  
  
 <span data-ttu-id="10724-217">Das folgende Schema (CustOrderSchema.xml) beschreibt ein **\<CustOrder>** -Element, das aus den Attributen **OrderID** und Mitarbeiter ID besteht. **EmployeeID**</span><span class="sxs-lookup"><span data-stu-id="10724-217">The following schema (CustOrderSchema.xml) describes a **\<CustOrder>** element that consists of the **OrderID** and **EmployeeID** attributes.</span></span> <span data-ttu-id="10724-218">Um das Schema interessanter zu machen, wird dem Mitarbeiter-ID **-Attribut ein** Standardwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="10724-218">To make the schema more interesting, a default value is assigned to the **EmployeeID** attribute.</span></span> <span data-ttu-id="10724-219">Ein Updategram verwendet den Standardwert eines Attributs nur bei Einfügevorgängen, und auch dann nur, wenn das Updategram kein anderes Attribut angibt.</span><span class="sxs-lookup"><span data-stu-id="10724-219">An updategram uses an attribute's default value only for insert operations, and then only if the updategram does not specify that attribute.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="CustOrder" >  
   <xsd:complexType>  
        <xsd:attribute name="OrderID"     type="xsd:integer" />   
        <xsd:attribute name="EmployeeID"  type="xsd:integer" />  
        <xsd:attribute name="OrderType  " type="xsd:integer" default="1"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="10724-220">Dieses Updategram fügt einen Datensatz in die CustOrder-Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="10724-220">This updategram inserts a record into the CustOrder table.</span></span> <span data-ttu-id="10724-221">Das Updategram gibt nur die Attributwerte für OrderID und EmployeeID an.</span><span class="sxs-lookup"><span data-stu-id="10724-221">The updategram specifies only the OrderID and EmployeeID attribute values.</span></span> <span data-ttu-id="10724-222">Der Attributwert für OrderType wird nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="10724-222">It does not specify the OrderType attribute value.</span></span> <span data-ttu-id="10724-223">Daher verwendet das Updategram den Standardwert des EmployeeID-Attributs, das im vorhergehenden Schema angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="10724-223">Therefore, the updategram uses the default value of the EmployeeID attribute that is specified in the preceding schema.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
             xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync mapping-schema='CustOrderSchema.xml'>  
<updg:after>  
       <CustOrder OrderID="98000" EmployeeID="1" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-224">Weitere Beispiele für Update grams, die ein Mapping-Schema angeben, finden Sie unter [Angeben eines Mapping-Schemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="10724-224">For more examples of updategrams that specify a mapping schema, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="10724-225">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-225">To test the updategram</span></span>  
  
1.  <span data-ttu-id="10724-226">Erstellen Sie diese Tabelle in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="10724-226">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE CustOrder(  
                     OrderID int,   
                     EmployeeID int,   
                     OrderType int)  
    ```  
  
2.  <span data-ttu-id="10724-227">Kopieren Sie das oben stehende Schema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-227">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="10724-228">Speichern Sie die Datei unter dem Dateinamen CustOrderSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-228">Save the file as CustOrderSchema.xml.</span></span>  
  
3.  <span data-ttu-id="10724-229">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-229">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-230">Speichern Sie die Datei als CustOrderUpdategram.xml in demselben Ordner, den Sie im vorherigen Schritt verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="10724-230">Save the file as CustOrderUpdategram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="10724-231">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-231">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="10724-232">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-232">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="10724-233">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="10724-233">This is the equivalent XDR schema:</span></span>  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
 <ElementType name="CustOrder" >  
    <AttributeType name="OrderID" />  
    <AttributeType name="EmployeeID" />  
    <AttributeType name="OrderType" default="1" />  
    <attribute type="OrderID"  />  
    <attribute type="EmployeeID" />  
    <attribute type="OrderType" />  
  </ElementType>  
</Schema>  
```  
  
### <a name="g-using-the-xsinil-attribute-to-insert-null-values-in-a-column"></a><span data-ttu-id="10724-234">G.</span><span class="sxs-lookup"><span data-stu-id="10724-234">G.</span></span> <span data-ttu-id="10724-235">Verwenden des Attributs "xsi:nil", um NULL-Werte in eine Spalte einzufügen</span><span class="sxs-lookup"><span data-stu-id="10724-235">Using the xsi:nil attribute to insert null values in a column</span></span>  
 <span data-ttu-id="10724-236">Zum Einfügen eines NULL-Werts in die entsprechende Spalte der Tabelle können Sie das `xsi:nil`-Attribut in einem Element in einem Updategram angeben.</span><span class="sxs-lookup"><span data-stu-id="10724-236">If you want to insert a null value in the corresponding column in the table, you can specify the `xsi:nil` attribute on an element in an updategram.</span></span> <span data-ttu-id="10724-237">Im entsprechenden XSD-Schema muss auch das XSD-`nillable`-Attribut angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="10724-237">In the corresponding XSD schema, the XSD `nillable` attribute also must be specified.</span></span>  
  
 <span data-ttu-id="10724-238">Das folgende XSD-Schema ist ein Beispiel dafür:</span><span class="sxs-lookup"><span data-stu-id="10724-238">For example, consider this XSD schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="Student" sql:relation="Students">  
  <xsd:complexType>  
    <xsd:all>  
      <xsd:element name="fname" sql:field="first_name"   
                                type="xsd:string"   
                                 nillable="true"/>  
    </xsd:all>  
    <xsd:attribute name="SID"   
                        sql:field="StudentID"  
                        type="xsd:ID"/>      
    <xsd:attribute name="lname"       
                        sql:field="last_name"  
                        type="xsd:string"/>  
    <xsd:attribute name="minitial"    
                        sql:field="middle_initial"   
                        type="xsd:string"/>  
    <xsd:attribute name="years"       
                         sql:field="no_of_years"  
                         type="xsd:integer"/>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="10724-239">Das XSD-Schema gibt **nillable = "true"** für das- **\<fname>** Element an.</span><span class="sxs-lookup"><span data-stu-id="10724-239">The XSD schema specifies **nillable="true"** for the **\<fname>** element.</span></span> <span data-ttu-id="10724-240">Das folgende Updategram verwendet dieses Schema:</span><span class="sxs-lookup"><span data-stu-id="10724-240">The following updategram uses this schema:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
      xmlns:updg="urn:schemas-microsoft-com:xml-updategram"  
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  
<updg:sync mapping-schema='StudentSchema.xml'>  
  <updg:before/>  
  <updg:after>  
    <Student SID="S00004" lname="Elmaci" minitial="" years="2">  
      <fname xsi:nil="true">  
    </fname>  
    </Student>  
  </updg:after>  
</updg:sync>  
  
</ROOT>  
```  
  
 <span data-ttu-id="10724-241">Das Update Gram gibt `xsi:nil` für das- **\<fname>** Element im- **\<after>** Block an.</span><span class="sxs-lookup"><span data-stu-id="10724-241">The updategram specifies `xsi:nil` for the **\<fname>** element in the **\<after>** block.</span></span> <span data-ttu-id="10724-242">Daher wird beim Ausführen dieses Updategrams für die first_name-Spalte in der Tabelle der Wert NULL eingefügt.</span><span class="sxs-lookup"><span data-stu-id="10724-242">Therefore, when this updategram is executed, a value of NULL is inserted for the first_name column in the table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="10724-243">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-243">To test the updategram</span></span>  
  
1.  <span data-ttu-id="10724-244">Erstellen Sie die folgende Tabelle in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="10724-244">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Students (  
       StudentID char(6)NOT NULL ,  
       first_name varchar(50),  
       last_name varchar(50),  
       middle_initial char(1),  
       no_of_years int NULL)  
    GO  
    ```  
  
2.  <span data-ttu-id="10724-245">Kopieren Sie das oben stehende Schema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-245">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="10724-246">Speichern Sie die Datei unter dem Dateinamen StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-246">Save the file as StudentSchema.xml.</span></span>  
  
3.  <span data-ttu-id="10724-247">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-247">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-248">Speichern Sie die Datei als StudentUpdategram.xml in demselben Ordner, den Sie im vorherigen Schritt zum Speichern der Datei StudentSchema.xml verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="10724-248">Save the file as StudentUpdategram.xml in the same folder used in previous step to save StudentSchema.xml.</span></span>  
  
4.  <span data-ttu-id="10724-249">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-249">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="10724-250">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-250">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="h-specifying-namespaces-in-an-updategram"></a><span data-ttu-id="10724-251">H.</span><span class="sxs-lookup"><span data-stu-id="10724-251">H.</span></span> <span data-ttu-id="10724-252">Angeben von Namespaces in einem Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-252">Specifying namespaces in an updategram</span></span>  
 <span data-ttu-id="10724-253">In einem Updategram können Elemente vorhanden sein, die zu einem in demselben Element im Updategram deklarierten Namespace gehören.</span><span class="sxs-lookup"><span data-stu-id="10724-253">In an updategram you can have elements that belong to a namespace declared in the same element in the updategram.</span></span> <span data-ttu-id="10724-254">In diesem Fall muss auch in dem entsprechenden Schema derselbe Namespace deklariert sein, und das Element muss diesem Zielnamespace angehören.</span><span class="sxs-lookup"><span data-stu-id="10724-254">In this case, the corresponding schema must also declare the same namespace and the element must belong to that target namespace.</span></span>  
  
 <span data-ttu-id="10724-255">Im folgenden Update Gram (UpdateGram-ElementHavingNamespace.xml) gehört das-Element z. b **\<Order>** . zu einem Namespace, der im-Element deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="10724-255">For example, in the following updategram (UpdateGram-ElementHavingNamespace.xml), the **\<Order>** element belongs to a namespace declared in the element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema='XSD-ElementHavingNameSpace.xml'>  
    <updg:after>  
       <x:Order  xmlns:x="http://server/xyz/schemas/"  
             updg:at-identity="SalesOrderID"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00009999-8888-7777-6666-554433221100"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-256">In diesem Fall muss auch das Schema den Namespace deklarieren, wie in diesem Schema gezeigt:</span><span class="sxs-lookup"><span data-stu-id="10724-256">In this case, the schema must also declare the namespace as shown in this schema:</span></span>  
  
 <span data-ttu-id="10724-257">Das folgende Schema (XSD-ElementHavingNamespace.xml) zeigt an, wie das entsprechende Element und die entsprechenden Attribute deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="10724-257">The following schema (XSD-ElementHavingNamespace.xml) shows how the corresponding element and attributes must be declared.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns:dt="urn:schemas-microsoft-com:datatypes"   
     xmlns:sql="urn:schemas-microsoft-com:mapping-schema"    
     xmlns:x="http://server/xyz/schemas/"   
     targetNamespace="http://server/xyz/schemas/" >  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="x:Order_type"/>  
  <xsd:complexType name="Order_type">  
    <xsd:attribute name="SalesOrderID"  type="xsd:ID"/>  
    <xsd:attribute name="RevisionNumber" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OrderDate" type="xsd:dateTime"/>  
    <xsd:attribute name="DueDate" type="xsd:dateTime"/>  
    <xsd:attribute name="ShipDate" type="xsd:dateTime"/>  
    <xsd:attribute name="Status" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OnlineOrderFlag" type="xsd:boolean"/>  
    <xsd:attribute name="SalesOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="PurchaseOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="AccountNumber" type="xsd:string"/>  
    <xsd:attribute name="CustomerID" type="xsd:int"/>  
    <xsd:attribute name="ContactID" type="xsd:int"/>  
    <xsd:attribute name="SalesPersonID" type="xsd:int"/>  
    <xsd:attribute name="TerritoryID" type="xsd:int"/>  
    <xsd:attribute name="BillToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipMethodID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardApprovalCode" type="xsd:string"/>  
    <xsd:attribute name="CurrencyRateID" type="xsd:int"/>  
    <xsd:attribute name="SubTotal" type="xsd:decimal"/>  
    <xsd:attribute name="TaxAmt" type="xsd:decimal"/>  
    <xsd:attribute name="Freight" type="xsd:decimal"/>  
    <xsd:attribute name="TotalDue" type="xsd:decimal"/>  
    <xsd:attribute name="Comment" type="xsd:string"/>  
    <xsd:attribute name="rowguid" type="xsd:string"/>  
    <xsd:attribute name="ModifiedDate" type="xsd:dateTime"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="10724-258">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-258">To test the updategram</span></span>  
  
1.  <span data-ttu-id="10724-259">Kopieren Sie das oben stehende Schema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-259">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="10724-260">Speichern Sie die Datei unter dem Dateinamen XSD-ElementHavingNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-260">Save the file as XSD-ElementHavingNamespace.xml.</span></span>  
  
2.  <span data-ttu-id="10724-261">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-261">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-262">Speichern Sie die Datei als Updategram-ElementHavingNamespace.xml in demselben Ordner, den Sie im vorherigen Schritt zum Speichern der Datei XSD-ElementHavingnamespace.xml verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="10724-262">Save the file as Updategram-ElementHavingNamespace.xml in the same folder used to save XSD-ElementHavingnamespace.xml.</span></span>  
  
3.  <span data-ttu-id="10724-263">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-263">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="10724-264">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-264">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="i-inserting-data-into-an-xml-data-type-column"></a><span data-ttu-id="10724-265">I.</span><span class="sxs-lookup"><span data-stu-id="10724-265">I.</span></span> <span data-ttu-id="10724-266">Einfügen von Daten in eine XML-Datentypspalte</span><span class="sxs-lookup"><span data-stu-id="10724-266">Inserting data into an XML data type column</span></span>  
 <span data-ttu-id="10724-267">Der `xml`-Datentyp wurde in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] eingeführt.</span><span class="sxs-lookup"><span data-stu-id="10724-267">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="10724-268">Sie können Updategrams verwenden, um in Spalten vom Typ `xml` gespeicherte Daten einzufügen und zu aktualisieren. Dabei gelten folgende Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="10724-268">You can use updategrams to insert and update data stored in `xml` data type columns with the following provisions:</span></span>  
  
-   <span data-ttu-id="10724-269">Die `xml`-Spalte kann nicht zum Identifizieren einer vorhandenen Zeile verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10724-269">The `xml` column cannot be used for identifying an existing row.</span></span> <span data-ttu-id="10724-270">Deshalb kann sie nicht im `updg:before`-Abschnitt eines Updategrams enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="10724-270">Therefore, it cannot be included in the `updg:before` section of an updategram.</span></span>  
  
-   <span data-ttu-id="10724-271">Namespaces, die sich im Bereich des in die `xml`-Spalte eingefügten XML-Fragments befinden, werden beibehalten, und deren Namespacedeklarationen zu dem obersten Element des eingefügten Fragments hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="10724-271">Namespaces that are in scope of the XML fragment inserted into the `xml` column will be preserved and their namespace declarations are added to the top element of the inserted fragment.</span></span>  
  
 <span data-ttu-id="10724-272">Im folgenden Update Gram (SampleUpdateGram.xml) aktualisiert das-Element z. b **\<Desc>** . die ProductDescription-Spalte in der Production>ProductModel-Tabelle in der- [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] Beispieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="10724-272">For example, in the following updategram (SampleUpdateGram.xml), the **\<Desc>** element updates the ProductDescription column in the Production>productModel table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="10724-273">Das Ergebnis dieses Update grams besteht darin, dass der XML-Inhalt der ProductDescription-Spalte mit dem XML-Inhalt des- **\<Desc>** Elements aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="10724-273">The result of this updategram is that the XML contents of the ProductDescription column are update with the XML contents of the **\<Desc>** element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
       <updg:before>  
<ProductModel ProductModelID="19">  
   <Name>Mountain-100</Name>  
</ProductModel>  
    </updg:before>  
    <updg:after>  
 <ProductModel>  
    <Name>Mountain-100</Name>  
    <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
        <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
              xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
              xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
              xmlns:html="http://www.w3.org/1999/xhtml"   
              xmlns="">  
  <p1:Summary>  
     <html:p>Insert Example</html:p>  
  </p1:Summary>  
  <p1:Manufacturer>  
    <p1:Name>AdventureWorks</p1:Name>  
    <p1:Copyright>2002</p1:Copyright>  
    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
  </p1:Manufacturer>  
  <p1:Features>These are the product highlights.   
    <wm:Warranty>  
       <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
       <wm:Description>parts and labor</wm:Description>  
    </wm:Warranty>  
    <wm:Maintenance>  
       <wm:NoOfYears>10 years</wm:NoOfYears>  
       <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
    </wm:Maintenance>  
    <wf:wheel>High performance wheels.</wf:wheel>  
    <wf:saddle>  
      <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle>  
    <wf:pedal>  
       <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal>  
    <wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter and wall-thickness required of a premium mountain frame. The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame>  
    <wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset>  
   </p1:Features>  
   <p1:Picture>  
      <p1:Angle>front</p1:Angle>  
      <p1:Size>small</p1:Size>  
      <p1:ProductPhotoID>118</p1:ProductPhotoID>  
   </p1:Picture>  
   <p1:Specifications> These are the product specifications.  
     <Material>Almuminum Alloy</Material>  
     <Color>Available in most colors</Color>  
     <ProductLine>Mountain bike</ProductLine>  
     <Style>Unisex</Style>  
     <RiderExperience>Advanced to Professional riders</RiderExperience>  
   </p1:Specifications>  
  </p1:ProductDescription>  
 </Desc>  
      </ProductModel>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="10724-274">Das Updategram verweist auf das folgende XSD-Schema mit Anmerkungen (SampleSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="10724-274">The updategram refers to the following annotated XSD schema (SampleSchema.xml).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
     <xsd:complexType>  
       <xsd:sequence>  
          <xsd:element name="Name" type="xsd:string"></xsd:element>  
          <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
           <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="ProductDescription">  
                 <xsd:complexType>  
                   <xsd:sequence>  
                     <xsd:element name="Summary" type="xsd:anyType">  
                     </xsd:element>  
                   </xsd:sequence>  
                 </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>   
       </xsd:sequence>  
       <xsd:attribute name="ProductModelID" sql:field="ProductModelID"/>  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="10724-275">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="10724-275">To test the updategram</span></span>  
  
1.  <span data-ttu-id="10724-276">Kopieren Sie das oben stehende Schema, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-276">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="10724-277">Speichern Sie die Datei unter dem Dateinamen XSD-SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="10724-277">Save the file as XSD-SampleSchema.xml.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="10724-278">Da Updategrams die Standardzuordnung unterstützen, gibt es keine Möglichkeit, den Anfang und das Ende des `xml`-Datentyps zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="10724-278">Because updategrams support default mapping, there is no way to identify the beginning and ending of the `xml` data type.</span></span> <span data-ttu-id="10724-279">Dies bedeutet, dass beim Einfügen von `xml`-Daten in eine Tabelle und dem Aktualisieren von Tabellen mit xml-Daten ein Zuordnungsschema erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="10724-279">This effectively means that a mapping schema is required when inserting or updating tables with `xml` data type columns.</span></span> <span data-ttu-id="10724-280">Wird kein Schema bereitgestellt, gibt SQLXML einen Fehler zurück und meldet, dass eine der Spalten in der Tabelle fehlt.</span><span class="sxs-lookup"><span data-stu-id="10724-280">When a schema is not provided, SQLXML returns an error indicating that one of the columns is missing from the table.</span></span>  
  
2.  <span data-ttu-id="10724-281">Kopieren Sie das oben stehende Updategram, und fügen Sie es in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="10724-281">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="10724-282">Speichern Sie die Datei als SampleUpdategram.xml in demselben Ordner, den Sie im vorherigen Schritt zum Speichern der Datei SampleSchema.xml verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="10724-282">Save the file as SampleUpdategram.xml in the same folder used to save SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="10724-283">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="10724-283">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="10724-284">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="10724-284">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10724-285">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10724-285">See Also</span></span>  
 [<span data-ttu-id="10724-286">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="10724-286">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
