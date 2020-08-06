---
title: 'Datentyp Umwandlungen und die SQL: datatype-Anmerkung (SQLXML 4,0) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- type attribute
- sql:datatype
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- xsd:type
- datatype annotation
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XSD schemas [SQLXML], mapping data types
ms.assetid: db192105-e8aa-4392-b812-9d727918c005
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f1b0af93e3b596d74bc107ab6947b9855a2cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617903"
---
# <a name="data-type-coercions-and-the-sqldatatype-annotation-sqlxml-40"></a><span data-ttu-id="99c01-102">Datentypumwandlungen und die sql:datatype-Anmerkung (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="99c01-102">Data Type Coercions and the sql:datatype Annotation (SQLXML 4.0)</span></span>
  <span data-ttu-id="99c01-103">In einem XSD-Schema gibt das `xsd:type`-Attribut den XSD-Datentyp eines Elements oder Attributs an.</span><span class="sxs-lookup"><span data-stu-id="99c01-103">In an XSD schema, the `xsd:type` attribute specifies the XSD data type of an element or attribute.</span></span> <span data-ttu-id="99c01-104">Wenn Daten anhand eines XSD-Schemas aus der Datenbank extrahiert werden, wird der angegebene Datentyp zur Formatierung der Daten verwendet.</span><span class="sxs-lookup"><span data-stu-id="99c01-104">When an XSD schema is used to extract data from the database, the data type specified is used to format the data.</span></span>  
  
 <span data-ttu-id="99c01-105">Darüber hinaus können Sie neben dem XSD-Typ in einem Schema auch über die `sql:datatype`-Anmerkung einen Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp angeben.</span><span class="sxs-lookup"><span data-stu-id="99c01-105">In addition to specifying an XSD type in a schema, you can also specify a Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type by using the `sql:datatype` annotation.</span></span> <span data-ttu-id="99c01-106">Die Attribute `xsd:type` und `sql:datatype` steuern die Zuordnung zwischen XSD-Datentypen und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="99c01-106">The `xsd:type` and `sql:datatype` attributes control the mapping between XSD data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
## <a name="xsdtype-attribute"></a><span data-ttu-id="99c01-107">xsd:type-Attribut</span><span class="sxs-lookup"><span data-stu-id="99c01-107">xsd:type Attribute</span></span>  
 <span data-ttu-id="99c01-108">Sie können das `xsd:type`-Attribut verwenden, um den XML-Datentyp eines Attributs oder Elements anzugeben, das einer Spalte zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="99c01-108">You can use the `xsd:type` attribute to specify the XML data type of an attribute or element that maps to a column.</span></span> <span data-ttu-id="99c01-109">`xsd:type` wirkt sich auf das vom Server zurückgegebene Dokument sowie auf die ausgeführte XPath-Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="99c01-109">The `xsd:type` affects the document that is returned from the server and also the XPath query that is executed.</span></span> <span data-ttu-id="99c01-110">Wenn eine XPath-Abfrage für ein Zuordnungsschema ausgeführt wird, das `xsd:type` enthält, verwendet XPath den angegebenen Datentyp beim Verarbeiten der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="99c01-110">When an XPath query is executed against a mapping schema that contains `xsd:type`, XPath uses the specified data type when it processes the query.</span></span> <span data-ttu-id="99c01-111">Weitere Informationen zur Verwendung von XPath `xsd:type` finden Sie unter [Mapping von XSD-Datentypen zu XPath-Datentypen &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="99c01-111">For more information about how XPath uses `xsd:type`, see [Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="99c01-112">In einem zurückgegebenen Dokument werden alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen in Zeichenfolgendarstellungen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="99c01-112">In a returned document, all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types are converted into string representations.</span></span> <span data-ttu-id="99c01-113">Einige Datentypen erfordern zusätzliche Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="99c01-113">Some data types require additional conversions.</span></span> <span data-ttu-id="99c01-114">In der folgenden Tabelle sind die Konvertierungen für verschiedene `xsd:type`-Werte aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="99c01-114">The following table lists the conversions that are used for various `xsd:type` values.</span></span>  
  
|<span data-ttu-id="99c01-115">XSD-Datentyp</span><span class="sxs-lookup"><span data-stu-id="99c01-115">XSD data type</span></span>|<span data-ttu-id="99c01-116">SQL Server-Konvertierung</span><span class="sxs-lookup"><span data-stu-id="99c01-116">SQL Server conversion</span></span>|  
|-------------------|---------------------------|  
|<span data-ttu-id="99c01-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="99c01-117">Boolean</span></span>|<span data-ttu-id="99c01-118">CONVERT(bit, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="99c01-118">CONVERT(bit, COLUMN)</span></span>|  
|<span data-ttu-id="99c01-119">Date</span><span class="sxs-lookup"><span data-stu-id="99c01-119">Date</span></span>|<span data-ttu-id="99c01-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span><span class="sxs-lookup"><span data-stu-id="99c01-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span></span>|  
|<span data-ttu-id="99c01-121">Decimal</span><span class="sxs-lookup"><span data-stu-id="99c01-121">decimal</span></span>|<span data-ttu-id="99c01-122">CONVERT(money, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="99c01-122">CONVERT(money, COLUMN)</span></span>|  
|<span data-ttu-id="99c01-123">id/idref/idrefs</span><span class="sxs-lookup"><span data-stu-id="99c01-123">id/idref/idrefs</span></span>|<span data-ttu-id="99c01-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="99c01-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="99c01-125">nmtoken/nmtokens</span><span class="sxs-lookup"><span data-stu-id="99c01-125">nmtoken/nmtokens</span></span>|<span data-ttu-id="99c01-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="99c01-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="99c01-127">Time</span><span class="sxs-lookup"><span data-stu-id="99c01-127">Time</span></span>|<span data-ttu-id="99c01-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span><span class="sxs-lookup"><span data-stu-id="99c01-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span></span>|  
|<span data-ttu-id="99c01-129">Alle anderen</span><span class="sxs-lookup"><span data-stu-id="99c01-129">All others</span></span>|<span data-ttu-id="99c01-130">Keine zusätzliche Konvertierung</span><span class="sxs-lookup"><span data-stu-id="99c01-130">No additional conversion</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="99c01-131">Einige von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurückgegebene Werte sind möglicherweise nicht mit den über `xsd:type` angegebenen XML-Datentypen kompatibel. Das liegt entweder daran, dass keine Konvertierung möglich ist (zum Beispiel die Konvertierung von XYZ in einen `decimal`-Datentyp) oder daran, dass der Wert den Bereich dieses Datentyps überschreitet (zum Beispiel bei der Konvertierung von -100000 in einen `UnsignedShort`-XSD-Typ).</span><span class="sxs-lookup"><span data-stu-id="99c01-131">Some of the values returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not be compatible with the XML data types that are specified by using `xsd:type`, either because the conversion is not possible (for example, converting "XYZ" to a `decimal` data type) or because the value exceeds the range of that data type (for example, -100000 converted to an `UnsignedShort` XSD type).</span></span> <span data-ttu-id="99c01-132">Inkompatible Typkonvertierungen führen möglicherweise zu ungültigen XML-Dokumenten oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlern.</span><span class="sxs-lookup"><span data-stu-id="99c01-132">Incompatible type conversions might result in XML documents that are not valid, or in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] errors.</span></span>  
  
## <a name="mapping-from-sql-server-data-types-to-xsd-data-types"></a><span data-ttu-id="99c01-133">Zuordnen von SQL Server-Datentypen zu XSD-Datentypen</span><span class="sxs-lookup"><span data-stu-id="99c01-133">Mapping from SQL Server Data Types to XSD Data Types</span></span>  
 <span data-ttu-id="99c01-134">In der folgenden Tabelle wird eine offensichtliche Zuordnung zwischen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen und XSD-Datentypen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="99c01-134">The following table shows an obvious mapping from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types to XSD data types.</span></span> <span data-ttu-id="99c01-135">Wenn Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Typ kennen, können Sie dieser Tabelle den entsprechenden XSD-Typ für das XSD-Schema entnehmen.</span><span class="sxs-lookup"><span data-stu-id="99c01-135">If you know the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type, this table provides the corresponding XSD type that you can specify in the XSD schema.</span></span>  
  
|<span data-ttu-id="99c01-136">SQL Server-Datentyp</span><span class="sxs-lookup"><span data-stu-id="99c01-136">SQL Server data type</span></span>|<span data-ttu-id="99c01-137">XSD-Datentyp</span><span class="sxs-lookup"><span data-stu-id="99c01-137">XSD data type</span></span>|  
|--------------------------|-------------------|  
|`bigint`|`long`|  
|`binary`|`base64Binary`|  
|`bit`|`boolean`|  
|`char`|`string`|  
|`datetime`|`dateTime`|  
|`decimal`|`decimal`|  
|`float`|`double`|  
|`image`|`base64Binary`|  
|`int`|`int`|  
|`money`|`decimal`|  
|`nchar`|`string`|  
|`ntext`|`string`|  
|`nvarchar`|`string`|  
|`numeric`|`decimal`|  
|`real`|`float`|  
|`smalldatetime`|`dateTime`|  
|`smallint`|`short`|  
|`smallmoney`|`decimal`|  
|`sql_variant`|`string`|  
|`sysname`|`string`|  
|`text`|`string`|  
|`timestamp`|`dateTime`|  
|`tinyint`|`unsignedByte`|  
|`varbinary`|`base64Binary`|  
|`varchar`|`string`|  
|`uniqueidentifier`|`string`|  
  
## <a name="sqldatatype-annotation"></a><span data-ttu-id="99c01-138">sql:datatype-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="99c01-138">sql:datatype Annotation</span></span>  
 <span data-ttu-id="99c01-139">Die `sql:datatype`-Anmerkung wird verwendet, um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp anzugeben. Diese Anmerkung ist obligatorisch, wenn:</span><span class="sxs-lookup"><span data-stu-id="99c01-139">The `sql:datatype` annotation is used to specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type; this annotation must be specified when:</span></span>  
  
-   <span data-ttu-id="99c01-140">Sie sind Massen laden in eine `dateTime` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Spalte aus einem XSD- `dateTime` ,- `date` oder- `time` Typ.</span><span class="sxs-lookup"><span data-stu-id="99c01-140">You are bulk loading into a `dateTime`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column from an XSD `dateTime`, `date`, or `time` type.</span></span> <span data-ttu-id="99c01-141">In diesem Fall müssen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Spaltendatentyp mit `sql:datatype="dateTime"` angeben.</span><span class="sxs-lookup"><span data-stu-id="99c01-141">In this case, you must identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column data type by using `sql:datatype="dateTime"`.</span></span> <span data-ttu-id="99c01-142">Diese Regel gilt auch für Updategrams.</span><span class="sxs-lookup"><span data-stu-id="99c01-142">This rule also applies to updategrams.</span></span>  
  
-   <span data-ttu-id="99c01-143">Sie sind Massen laden in eine Spalte vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` Typ, und der XSD-Wert ist eine GUID mit geschweiften Klammern ({und}).</span><span class="sxs-lookup"><span data-stu-id="99c01-143">You are bulk loading into a column of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type and the XSD value is a GUID that includes braces ({ and }).</span></span> <span data-ttu-id="99c01-144">Wenn Sie `sql:datatype="uniqueidentifier"` angeben, werden die Klammern vor dem Einfügen in die Spalte aus dem Wert entfernt.</span><span class="sxs-lookup"><span data-stu-id="99c01-144">When you specify `sql:datatype="uniqueidentifier"`, the braces are removed from the value before it is inserted in the column.</span></span> <span data-ttu-id="99c01-145">Wird `sql:datatype` nicht angegeben, wird der Wert einschließlich Klammern gesendet, und der Einfüge- oder Updatevorgang erzeugt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="99c01-145">If `sql:datatype` is not specified, the value is sent with the braces, and the insert or update fails.</span></span>  
  
-   <span data-ttu-id="99c01-146">Der XML-Datentyp `base64Binary` ist verschiedenen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen (`binary`, `image` oder `varbinary`) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="99c01-146">The XML data type `base64Binary` maps to various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types (`binary`, `image`, or `varbinary`).</span></span> <span data-ttu-id="99c01-147">Um den XML-Datentyp `base64Binary`einem bestimmten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp zuzuordnen, verwenden Sie die `sql:datatype`-Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="99c01-147">To map the XML data type `base64Binary` to a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, use the `sql:datatype` annotation.</span></span> <span data-ttu-id="99c01-148">Diese Anmerkung gibt den expliziten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp der Spalte an, der das Attribut zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="99c01-148">This annotation specifies the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the column to which the attribute maps.</span></span> <span data-ttu-id="99c01-149">Dies ist nützlich, wenn Daten in der Datenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="99c01-149">This is useful when data is being stored in the databases.</span></span> <span data-ttu-id="99c01-150">Durch Angeben der `sql:datatype`-Anmerkung können Sie den expliziten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp identifizieren.</span><span class="sxs-lookup"><span data-stu-id="99c01-150">By specifying the `sql:datatype` annotation, you can identify the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="99c01-151">Es wird im Allgemeinen empfohlen, `sql:datatype` im Schema anzugeben.</span><span class="sxs-lookup"><span data-stu-id="99c01-151">It is generally recommended that you specify `sql:datatype` in the schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="99c01-152">Beispiele</span><span class="sxs-lookup"><span data-stu-id="99c01-152">Examples</span></span>  
 <span data-ttu-id="99c01-153">Es müssen bestimmte Anforderungen erfüllt sein, damit aus den folgenden Beispielen funktionierende Beispiele erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="99c01-153">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="99c01-154">Weitere Informationen finden Sie unter [Anforderungen zum Ausführen von SQLXML-Beispielen](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="99c01-154">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-xsdtype"></a><span data-ttu-id="99c01-155">A.</span><span class="sxs-lookup"><span data-stu-id="99c01-155">A.</span></span> <span data-ttu-id="99c01-156">Angeben von "xsd:type"</span><span class="sxs-lookup"><span data-stu-id="99c01-156">Specifying xsd:type</span></span>  
 <span data-ttu-id="99c01-157">Dieses Beispiel zeigt, wie sich ein über das `date`-Attribut im Schema angegebener `xsd:type` XSD-Typ auf das daraus resultierende XML-Dokument auswirkt.</span><span class="sxs-lookup"><span data-stu-id="99c01-157">This example shows how an XSD `date` type that is specified by using the `xsd:type` attribute in the schema affects the resulting XML document.</span></span> <span data-ttu-id="99c01-158">Das Schema stellt eine XML-Ansicht der Tabelle Sales.SalesOrderHeader in der AdventureWorks-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="99c01-158">The schema provides an XML view of the Sales.SalesOrderHeader table in the AdventureWorks database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader">  
     <xsd:complexType>  
       <xsd:attribute name="SalesOrderID" type="xsd:string" />   
       <xsd:attribute name="CustomerID"   type="xsd:string" />   
       <xsd:attribute name="OrderDate"    type="xsd:date" />   
       <xsd:attribute name="DueDate"  />   
       <xsd:attribute name="ShipDate"  type="xsd:time" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="99c01-159">In diesem XSD-Schema gibt es drei Attribute, die einen Datumswert von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="99c01-159">In this XSD schema, there are three attributes that return a date value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="99c01-160">Wenn das Schema:</span><span class="sxs-lookup"><span data-stu-id="99c01-160">When the schema:</span></span>  
  
-   <span data-ttu-id="99c01-161">Gibt `xsd:type=date` für das **OrderDate** -Attribut an, dass der Datums Teil des Werts, der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für das **OrderDate** -Attribut zurückgegeben wird, angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="99c01-161">Specifies `xsd:type=date` on the **OrderDate** attribute, the date part of the value returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **OrderDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="99c01-162">Gibt für `xsd:type=time` das **ShipDate** -Attribut an, dass der Uhrzeit Teil des Werts, der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für das **ShipDate** -Attribut zurückgegeben wird, angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="99c01-162">Specifies `xsd:type=time` on the **ShipDate** attribute, the time part of the value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **ShipDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="99c01-163">Gibt `xsd:type` für das **DueDate** -Attribut nicht an, dass derselbe Wert, der von zurückgegeben wird, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="99c01-163">Does not specify `xsd:type` on the **DueDate** attribute, the same value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is displayed.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="99c01-164">So testen Sie eine XPath-Beispiel Abfrage für das Schema</span><span class="sxs-lookup"><span data-stu-id="99c01-164">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="99c01-165">Kopieren Sie den oben stehenden Schemacode, und fügen Sie ihn in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="99c01-165">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="99c01-166">Speichern Sie die Datei unter dem Dateinamen xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="99c01-166">Save the file as xsdType.xml.</span></span>  
  
2.  <span data-ttu-id="99c01-167">Kopieren Sie die folgende Vorlage, und fügen Sie sie in eine Textdatei ein.</span><span class="sxs-lookup"><span data-stu-id="99c01-167">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="99c01-168">Speichern Sie die Datei unter dem Namen xsdTypeT.xml im gleichen Verzeichnis wie sdType.xml.</span><span class="sxs-lookup"><span data-stu-id="99c01-168">Save the file as xsdTypeT.xml in the same directory where you saved xsdType.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="xsdType.xml">  
        /Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="99c01-169">Der für das Zuordnungsschema (xsdType.xml) angegebene Verzeichnispfad bezieht sich auf das Verzeichnis, in dem die Vorlage gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="99c01-169">The directory path specified for the mapping schema (xsdType.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="99c01-170">Es kann auch ein absoluter Pfad angegeben werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="99c01-170">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\xsdType.xml"  
    ```  
  
3.  <span data-ttu-id="99c01-171">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99c01-171">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="99c01-172">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="99c01-172">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="99c01-173">Im Folgenden wird ein Teil des Resultsets aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="99c01-173">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43659"   
         CustomerID="676"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
  <Order SalesOrderID="43660"   
         CustomerID="117"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
 ...  
</ROOT>  
```  
  
 <span data-ttu-id="99c01-174">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="99c01-174">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader">  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="CustomerID"  />  
    <AttributeType name="OrderDate" dt:type="date" />  
    <AttributeType name="DueDate" />  
    <AttributeType name="ShipDate" dt:type="time" />  
  
    <attribute type="SalesOrderID" sql:field="OrderID" />  
    <attribute type="CustomerID" sql:field="CustomerID" />  
    <attribute type="OrderDate" sql:field="OrderDate" />  
    <attribute type="DueDate" sql:field="DueDate" />  
    <attribute type="ShipDate" sql:field="ShipDate" />  
</ElementType>  
</Schema>  
```  
  
### <a name="b-specifying-sql-data-type-using-sqldatatype"></a><span data-ttu-id="99c01-175">B.</span><span class="sxs-lookup"><span data-stu-id="99c01-175">B.</span></span> <span data-ttu-id="99c01-176">Angeben des SQL-Datentyps mit "sql:datatype"</span><span class="sxs-lookup"><span data-stu-id="99c01-176">Specifying SQL data type using sql:datatype</span></span>  
 <span data-ttu-id="99c01-177">Ein funktionierendes Beispiel finden Sie unter Beispiel G in [XML Bulk Load examples &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="99c01-177">For a working sample, see Example G in [XML Bulk Load Examples &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span></span> <span data-ttu-id="99c01-178">In diesem Beispiel wird ein GUID-Wert, der "{" und "}" enthält, massengeladen.</span><span class="sxs-lookup"><span data-stu-id="99c01-178">In this example, a GUID value including "{" and "}" is bulk loaded.</span></span> <span data-ttu-id="99c01-179">Das Schema in diesem Beispiel gibt `sql:datatype` an, um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp als `uniqueidentifier` zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="99c01-179">The schema in this example specifies `sql:datatype` to identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as `uniqueidentifier`.</span></span> <span data-ttu-id="99c01-180">Dieses Beispiel veranschaulicht, wann `sql:datatype` im Schema angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="99c01-180">This example illustrate when `sql:datatype` must be specified in the schema.</span></span>  
  
  
