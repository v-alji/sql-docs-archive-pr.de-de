---
title: Löschen von Daten mit XML-Update grams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <after> block
- updategrams [SQLXML], deleting data
- <before> block
- mapping-schema attribute
- record deletions [SQLXML]
ms.assetid: 4fb116d7-7652-474a-a567-cb475a20765c
author: rothja
ms.author: jroth
ms.openlocfilehash: d941005c71dc33dd8c4f5c5cc15f645cd0e68177
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620770"
---
# <a name="deleting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="06b00-102">Löschen von Daten mit XML-Updategrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="06b00-102">Deleting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="06b00-103">Ein Update Gram gibt einen Löschvorgang an, wenn eine Daten Satz Instanz im- **\<before>** Block ohne entsprechende Datensätze im-Block angezeigt wird **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="06b00-103">An updategram indicates a delete operation when a record instance appears in the **\<before>** block with no corresponding records in the **\<after>** block.</span></span> <span data-ttu-id="06b00-104">In diesem Fall löscht das Update Gram den Datensatz im- **\<before>** Block aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="06b00-104">In this case, the updategram deletes the record in the **\<before>** block from the database.</span></span>  
  
 <span data-ttu-id="06b00-105">Dies ist das Updategramformat für einen Löschvorgang:</span><span class="sxs-lookup"><span data-stu-id="06b00-105">This is the updategram format for a delete operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   <updg:before>  
       <ElementName />  
      [<ElementName .../>... ]  
   </updg:before>  
    [<updg:after>  
    </updg:after>]  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="06b00-106">Sie können das-Tag weglassen, **\<after>** Wenn das Update Gram nur einen Löschvorgang ausführt.</span><span class="sxs-lookup"><span data-stu-id="06b00-106">You can omit the **\<after>** tag if the updategram is performing only a delete operation.</span></span> <span data-ttu-id="06b00-107">Wenn Sie das optionale-Attribut nicht angeben `mapping-schema` , wird der **\<ElementName>** im Update Gram angegebene einer Datenbanktabelle zugeordnet, und die untergeordneten Elemente oder Attribute werden den Spalten in der Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="06b00-107">If you do not specify the optional `mapping-schema` attribute, the **\<ElementName>** specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
 <span data-ttu-id="06b00-108">Wenn ein im Update Gram angegebenes Element entweder mehr als eine Zeile in der Tabelle oder nicht mit einer Zeile übereinstimmt, gibt das Update Gram einen Fehler zurück und bricht den gesamten **\<sync>** Block ab.</span><span class="sxs-lookup"><span data-stu-id="06b00-108">If an element specified in the updategram either matches more than one row in the table or does not match any row, the updategram returns an error and cancels the entire **\<sync>** block.</span></span> <span data-ttu-id="06b00-109">Nur ein Datensatz kann gleichzeitig von einem Element im Updategram gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="06b00-109">Only one record at a time can be deleted by an element in the updategram.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="06b00-110">Beispiele</span><span class="sxs-lookup"><span data-stu-id="06b00-110">Examples</span></span>  
 <span data-ttu-id="06b00-111">Die Beispiele in diesem Abschnitt verwenden die Standardzuordnung (d. h. es ist kein Zuordnungsschema im Updategram angegeben).</span><span class="sxs-lookup"><span data-stu-id="06b00-111">Examples in this section use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="06b00-112">Weitere Beispiele für Update grams, die Mapping-Schemas verwenden, finden Sie unter [Angeben eines Mappingschemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="06b00-112">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="06b00-113">Wenn Sie in den folgenden Beispielen funktionierende Beispiele erstellen möchten, müssen Sie die unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../../sqlxml/requirements-for-running-sqlxml-examples.md)angegebenen Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="06b00-113">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-deleting-a-record-by-using-an-updategram"></a><span data-ttu-id="06b00-114">A.</span><span class="sxs-lookup"><span data-stu-id="06b00-114">A.</span></span> <span data-ttu-id="06b00-115">Löschen eines Datensatzes mithilfe eines Updategrams</span><span class="sxs-lookup"><span data-stu-id="06b00-115">Deleting a record by using an updategram</span></span>  
 <span data-ttu-id="06b00-116">Die folgenden Updategrams löschen zwei Datensätze aus der Tabelle HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="06b00-116">The following updategrams deletes two records from the HumanResources.Shift table.</span></span>  
  
 <span data-ttu-id="06b00-117">In diesen Beispielen gibt das Updategram kein Zuordnungsschema an.</span><span class="sxs-lookup"><span data-stu-id="06b00-117">In these examples, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="06b00-118">Daher verwendet das Updategram die Standardzuordnung, in der der Elementname einem Tabellennamen, und die Attribute oder untergeordneten Elemente den Spalten in dieser Tabelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="06b00-118">Therefore, the updategram uses default mapping, in which the element name maps to table name and the attributes or subelements map to columns.</span></span>  
  
 <span data-ttu-id="06b00-119">Dieses erste Update Gram ist Attribut zentriert und identifiziert zwei Verschiebungen (Tag-Abend und Abend-Nacht) im- **\<before>** Block.</span><span class="sxs-lookup"><span data-stu-id="06b00-119">This first updategram is attribute-centric and identifies two shifts (Day-Evening and Evening-Night) in the **\<before>** block.</span></span> <span data-ttu-id="06b00-120">Da es keinen entsprechenden Datensatz im-Block gibt, handelt es sich hierbei **\<after>** um einen Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="06b00-120">Because there is no corresponding record in the **\<after>** block, this is a delete operation.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
       <HumanResources.Shift ShiftID="4"  
                        Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift ShiftID="5"  
                        Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:before>  
  <updg:after>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="06b00-121">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="06b00-121">To test the updategram</span></span>  
  
1.  <span data-ttu-id="06b00-122">Vervollständigen Sie Beispiel B ("Einfügen mehrerer Datensätze mithilfe eines Update grams") in das [Einfügen von Daten mit XML-Update grams &#40;SQLXML 4,0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="06b00-122">Complete example B ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
2.  <span data-ttu-id="06b00-123">Kopieren Sie das oben angegebene Update Gram in Editor, und speichern Sie es als Updategram-RemoveShifts.xml im selben Ordner, in dem Sie den Vorgang durchgeführt haben ("Einfügen mehrerer Datensätze mithilfe eines Update grams"), [indem Sie Daten mithilfe von XML-Update grams &#40;SQLXML 4,0&#41;einfügen ](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="06b00-123">Copy the updategram above to Notepad and save it as Updategram-RemoveShifts.xml in the same folder as was used to complete ("Inserting multiple records by using an updategram") in [Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;](inserting-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
3.  <span data-ttu-id="06b00-124">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um das Updategram auszuführen.</span><span class="sxs-lookup"><span data-stu-id="06b00-124">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="06b00-125">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="06b00-125">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b00-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06b00-126">See Also</span></span>  
 [<span data-ttu-id="06b00-127">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="06b00-127">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
