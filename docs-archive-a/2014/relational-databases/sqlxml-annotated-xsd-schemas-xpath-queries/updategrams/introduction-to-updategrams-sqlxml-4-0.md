---
title: Einführung in Update grams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
ms.openlocfilehash: eb2f29d7f5d86d28254dacb9c55cceb9b4c72d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700857"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a><span data-ttu-id="fc1c3-102">Einführung in Updategrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fc1c3-102">Introduction to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="fc1c3-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Mithilfe eines Update grams oder der OPENXML-Funktion können Sie eine Datenbank in aus einem vorhandenen XML-Dokument ändern (einfügen, aktualisieren oder löschen) [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fc1c3-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="fc1c3-104">Die OPENXML-Funktion ändert eine Datenbank durch Aufteilen des vorhandenen XML-Dokuments und Bereitstellen eines Rowsets, das an eine INSERT-, UPDATE- oder DELETE-Anweisung übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-104">The OPENXML function modifies a database by shredding the existing XML document and providing a rowset that can be passed to an INSERT, UPDATE, or DELETE statement.</span></span> <span data-ttu-id="fc1c3-105">Mit OPENXML werden Operationen direkt für die Datenbanktabellen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-105">With OPENXML, operations are performed directly against the database tables.</span></span> <span data-ttu-id="fc1c3-106">Daher eignet sich OPENXML besonders gut, wenn Rowsetanbieter, wie Tabellen, als Quelle auftreten können.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-106">Therefore, OPENXML is most appropriate wherever rowset providers, such as a table, can appear as a source.</span></span>  
  
 <span data-ttu-id="fc1c3-107">Wie mit OPENXML können Sie mit einem Updategram Daten in der Datenbank einfügen, aktualisieren oder löschen. Ein Updategram wird jedoch für die XML-Sichten verwendet, die vom XSD-Schema (oder einem XDR-Schema) bereitgestellt werden. So werden beispielsweise die Updates auf die vom Zuordnungsschema bereitgestellte XML-Sicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-107">Like OPENXML, an updategram allows you to insert, update, or delete data in the database; however, an updategram works against the XML views provided by the annotated XSD (or an XDR) schema; for example, the updates are applied to the XML view provided by the mapping schema.</span></span> <span data-ttu-id="fc1c3-108">Das Zuordnungsschema enthält die erforderlichen Informationen zum Zuordnen von XML-Elementen und -Attributen zu den entsprechenden Datenbanktabellen und -spalten.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-108">The mapping schema, in turn, has the necessary information to map XML elements and attributes to the corresponding database tables and columns.</span></span> <span data-ttu-id="fc1c3-109">Das Updategram verwendet diese Zuordnungsinformationen zum Aktualisieren der Datenbanktabellen und -spalten.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-109">The updategram uses this mapping information to update the database tables and columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc1c3-110">Diese Dokumentation setzt voraus, dass Sie mit Vorlagen und der Unterstützung von Zuordnungsschemas in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-110">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fc1c3-111">Weitere Informationen finden Sie unter [Einführung in XSD-Schemas mit Anmerkungen &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="fc1c3-111">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="fc1c3-112">Informationen zu Legacy Anwendungen, die XDR verwenden, finden Sie unter mit Anmerkungen versehene [XDR-Schemas &#40;in SQLXML 4,0&#41;veraltet ](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="fc1c3-112">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="required-namespaces-in-the-updategram"></a><span data-ttu-id="fc1c3-113">Erforderliche Namespaces im Updategram</span><span class="sxs-lookup"><span data-stu-id="fc1c3-113">Required Namespaces in the Updategram</span></span>  
 <span data-ttu-id="fc1c3-114">Die Schlüsselwörter in einem Update Gram, z **\<sync>** . b **\<before>** ., und **\<after>** , sind im- `urn:schemas-microsoft-com:xml-updategram` Namespace vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-114">The keywords in an updategram, such as **\<sync>**, **\<before>**, and **\<after>**, exist in the `urn:schemas-microsoft-com:xml-updategram` namespace.</span></span> <span data-ttu-id="fc1c3-115">Sie können ein beliebiges Namespacepräfix verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-115">The namespace prefix that you use is arbitrary.</span></span> <span data-ttu-id="fc1c3-116">In dieser Dokumentation gibt das Präfix `updg` den Namespace `updategram` an.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-116">In this documentation, the `updg` prefix denotes the `updategram` namespace.</span></span>  
  
## <a name="reviewing-syntax"></a><span data-ttu-id="fc1c3-117">Überprüfen der Syntax</span><span class="sxs-lookup"><span data-stu-id="fc1c3-117">Reviewing Syntax</span></span>  
 <span data-ttu-id="fc1c3-118">Ein Update Gram ist eine Vorlage mit **\<sync>** -, **\<before>** -und-Blöcken, die **\<after>** die Syntax des Update grams bilden.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-118">An updategram is a template with **\<sync>**, **\<before>**, and **\<after>** blocks that form the syntax of the updategram.</span></span> <span data-ttu-id="fc1c3-119">Der folgende Code zeigt diese Syntax in ihrer einfachsten Form:</span><span class="sxs-lookup"><span data-stu-id="fc1c3-119">The following code shows this syntax in its simplest form:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="fc1c3-120">In den folgenden Definitionen werden die Rollen der einzelnen Blöcke beschrieben:</span><span class="sxs-lookup"><span data-stu-id="fc1c3-120">The following definitions describe the role of each of these blocks:</span></span>  
  
 **\<before>**  
 <span data-ttu-id="fc1c3-121">Identifiziert den vorhandenen Status (auch als "Vorher-Status" bezeichnet) der Datensatzinstanz.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-121">Identifies the existing state (also called "the before state") of the record instance.</span></span>  
  
 **\<after>**  
 <span data-ttu-id="fc1c3-122">Identifiziert den neuen Status, in den Daten geändert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-122">Identifies the new state to which data is to be changed.</span></span>  
  
 **\<sync>**  
 <span data-ttu-id="fc1c3-123">Enthält die **\<before>** -und- **\<after>** Blöcke.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-123">Contains the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="fc1c3-124">Ein **\<sync>** -Block kann mehr als einen Satz von **\<before>** -und- **\<after>** Blöcken enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-124">A **\<sync>** block can contain more than one set of **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="fc1c3-125">Wenn mehr als ein Satz von **\<before>** -und- **\<after>** Blöcken vorhanden ist, müssen diese Blöcke (auch wenn Sie leer sind) als Paare angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-125">If there is more than one set of **\<before>** and **\<after>** blocks, these blocks (even if they are empty) must be specified as pairs.</span></span> <span data-ttu-id="fc1c3-126">Außerdem kann ein Update Gram mehr als einen **\<sync>** Block enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-126">Furthermore, an updategram can have more than one **\<sync>** block.</span></span> <span data-ttu-id="fc1c3-127">Jeder **\<sync>** Block ist eine Einheit der Transaktion (was bedeutet, dass entweder alles im **\<sync>** Block ausgeführt wird oder nichts ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="fc1c3-127">Each **\<sync>** block is one unit of transaction (which means that either everything in the **\<sync>** block is done or nothing is done).</span></span> <span data-ttu-id="fc1c3-128">Wenn Sie mehrere- **\<sync>** Blöcke in einem Update Gram angeben, wirkt sich der Ausfall eines **\<sync>** Blocks nicht auf die anderen- **\<sync>** Blöcke aus.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-128">If you specify multiple **\<sync>** blocks in an updategram, the failure of one **\<sync>** block does not affect the other **\<sync>** blocks.</span></span>  
  
 <span data-ttu-id="fc1c3-129">Ob ein Update Gram eine Daten Satz Instanz löscht, einfügt oder aktualisiert, hängt vom Inhalt der **\<before>** -und- **\<after>** Blöcke ab:</span><span class="sxs-lookup"><span data-stu-id="fc1c3-129">Whether an updategram deletes, inserts, or updates a record instance depends on the contents of the **\<before>** and **\<after>** blocks:</span></span>  
  
-   <span data-ttu-id="fc1c3-130">Wenn eine Daten Satz Instanz nur im- **\<before>** Block ohne entsprechende Instanz im- **\<after>** Block angezeigt wird, führt das Update Gram einen Löschvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-130">If a record instance appears only in the **\<before>** block with no corresponding instance in the **\<after>** block, the updategram performs a delete operation.</span></span>  
  
-   <span data-ttu-id="fc1c3-131">Wenn eine Daten Satz Instanz nur im- **\<after>** Block ohne entsprechende Instanz im-Block angezeigt wird **\<before>** , handelt es sich um einen INSERT-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-131">If a record instance appears only in the **\<after>** block with no corresponding instance in the **\<before>** block, it is an insert operation.</span></span>  
  
-   <span data-ttu-id="fc1c3-132">Wenn eine Daten Satz Instanz im **\<before>** -Block angezeigt wird und über eine entsprechende-Instanz im- **\<after>** Block verfügt, handelt es sich um einen Update Vorgang.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-132">If a record instance appears in the **\<before>** block and has a corresponding instance in the **\<after>** block, it is an update operation.</span></span> <span data-ttu-id="fc1c3-133">In diesem Fall aktualisiert das Update Gram die Daten Satz Instanz auf die Werte, die im-Block angegeben werden **\<after>** .</span><span class="sxs-lookup"><span data-stu-id="fc1c3-133">In this case, the updategram updates the record instance to the values that are specified in the **\<after>** block.</span></span>  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a><span data-ttu-id="fc1c3-134">Angeben eines Zuordnungsschemas im Updategram</span><span class="sxs-lookup"><span data-stu-id="fc1c3-134">Specifying a Mapping Schema in the Updategram</span></span>  
 <span data-ttu-id="fc1c3-135">In einem Updategram kann die von einem Zuordnungsschema (sowohl XSD- als auch XDR-Schemas werden unterstützt) bereitgestellte XML-Abstraktion implizit oder explizit sein (d. h., ein Updategram kann mit angegebenem Zuordnungsschema oder ohne angegebenes Zuordnungsschema verwendet werden).</span><span class="sxs-lookup"><span data-stu-id="fc1c3-135">In an updategram, the XML abstraction that is provided by a mapping schema (both XSD and XDR schemas are supported) can be implicit or explicit (that is, an updategram can work with or without a specified mapping schema).</span></span> <span data-ttu-id="fc1c3-136">Wenn Sie kein Zuordnungs Schema angeben, geht das Update Gram davon aus, dass eine implizite Zuordnung (die Standard Zuordnung) erfolgt, wobei jedes Element im **\<before>** Block oder **\<after>** Block einer Tabelle zugeordnet wird und dass das untergeordnete Element oder Attribut jedes Elements einer Spalte in der Datenbank zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-136">If you do not specify a mapping schema, the updategram assumes an implicit mapping (the default mapping), where each element in the **\<before>** block or **\<after>** block maps to a table and each element's child element or attribute maps to a column in the database.</span></span> <span data-ttu-id="fc1c3-137">Wenn Sie ausdrücklich ein Zuordnungsschema angeben, müssen die Elemente und Attribute im Updategram mit den Elementen und Attributen im Zuordnungsschema übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-137">If you explicitly specify a mapping schema, the elements and attributes in the updategram must match the elements and attributes in the mapping schema.</span></span>  
  
### <a name="implicit-default-mapping"></a><span data-ttu-id="fc1c3-138">Implizite Zuordnung (Standardzuordnung)</span><span class="sxs-lookup"><span data-stu-id="fc1c3-138">Implicit (default) Mapping</span></span>  
 <span data-ttu-id="fc1c3-139">Ein Updategram, das einfache Updates durchführt, benötigt in der Regel kein Zuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-139">In most cases, an updategram that performs simple updates might not require a mapping schema.</span></span> <span data-ttu-id="fc1c3-140">In diesem Fall verwendet das Updategram das Standardzuordnungsschema.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-140">In this case, the updategram relies on the default mapping schema.</span></span>  
  
 <span data-ttu-id="fc1c3-141">Das folgende Updategram zeigt eine implizite Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-141">The following updategram demonstrates implicit mapping.</span></span> <span data-ttu-id="fc1c3-142">In diesem Beispiel fügt das Updategram einen neuen Kunden in die Sales.Customer-Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-142">In this example, the updategram inserts a new customer in the Sales.Customer table.</span></span> <span data-ttu-id="fc1c3-143">Da in diesem Update Gram die implizite Zuordnung verwendet wird, wird das \<Sales.Customer> -Element der Sales. Customer-Tabelle zugeordnet, und die Attribute CustomerID und SalesPersonID werden den entsprechenden Spalten in der Sales. Customer-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-143">Because this updategram uses implicit mapping, the \<Sales.Customer> element maps to the Sales.Customer table, and the CustomerID and SalesPersonID attributes map to the corresponding columns in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a><span data-ttu-id="fc1c3-144">Explizite Zuordnung</span><span class="sxs-lookup"><span data-stu-id="fc1c3-144">Explicit Mapping</span></span>  
 <span data-ttu-id="fc1c3-145">Wenn Sie ein Zuordnungsschema angeben (XSD oder XDR) verwendet das Updategram das Schema um zu bestimmen, welche Datenbanktabellen und -spalten aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-145">If you specify a mapping schema (either XSD or XDR), the updategram uses the schema to determine the database tables and columns that are to be updated.</span></span>  
  
 <span data-ttu-id="fc1c3-146">Wenn das Updategram ein komplexes Update durchführt (z. B. Datensätze auf der Grundlage der im Zuordnungsschema angegebenen Über-/Unterordnungsbeziehung in mehrere Tabellen einfügt), müssen Sie das Zuordnungsschema explizit angeben. Verwenden Sie hierzu das `mapping-schema`-Attribut, für das das Updategram ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-146">If the updategram performs a complex update (for example, inserting records in multiple tables on the basis of the parent-child relationship that is specified in the mapping schema), you must explicitly provide the mapping schema by using the `mapping-schema` attribute against which the updategram executes.</span></span>  
  
 <span data-ttu-id="fc1c3-147">Da ein Updategram eine Vorlage ist, ist der für das Zuordnungsschema im Updategram angegebene Pfad bezieht sich auf den Speicherort der Vorlagendatei (relativ zum Speicherort des Updategrams).</span><span class="sxs-lookup"><span data-stu-id="fc1c3-147">Because an updategram is a template, the path specified for the mapping schema in the updategram is relative to the location of the template file (relative to where the updategram is stored).</span></span> <span data-ttu-id="fc1c3-148">Weitere Informationen finden Sie unter [Angeben eines Mapping-Schemas mit Anmerkungen in einem Update Gram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="fc1c3-148">For more information, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a><span data-ttu-id="fc1c3-149">Elementzentrierte und attributzentrierte Zuordnung in Updategrams</span><span class="sxs-lookup"><span data-stu-id="fc1c3-149">Element-centric and Attribute-centric Mapping in Updategrams</span></span>  
 <span data-ttu-id="fc1c3-150">Bei der Standardzuordnung (wenn im Updategram kein Zuordnungsschema angegeben ist) werden die Updategramelemente Tabellen und die untergeordneten Elemente (bei der elementzentrierten Zuordnung) und die Attribute (bei der attributzentrierten Zuordnung) Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-150">With default mapping (when the mapping schema is not specified in the updategram), the updategram elements map to tables and the  child elements (in the case of element-centric mapping) and the attributes (in the case of attribute-centric mapping) map to columns.</span></span>  
  
### <a name="element-centric-mapping"></a><span data-ttu-id="fc1c3-151">Elementzentrierte Zuordnung</span><span class="sxs-lookup"><span data-stu-id="fc1c3-151">Element-centric Mapping</span></span>  
 <span data-ttu-id="fc1c3-152">Ein Element in einem elementzentrierten Updategram enthält untergeordnete Elemente, die die Eigenschaften des Elements angeben.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-152">In an element-centric updategram, an element contains child elements that denote the properties of the element.</span></span> <span data-ttu-id="fc1c3-153">Ein Beispiel finden Sie im folgenden Updategram.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-153">As an example, refer to the following updategram.</span></span> <span data-ttu-id="fc1c3-154">Das **\<Person.Contact>** -Element enthält die untergeordneten **\<FirstName>** **\<LastName>** Elemente und.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-154">The **\<Person.Contact>** element contains the **\<FirstName>** and **\<LastName>** child elements.</span></span> <span data-ttu-id="fc1c3-155">Diese untergeordneten Elemente sind Eigenschaften des- **\<Person.Contact>** Elements.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-155">These child elements are properties of the **\<Person.Contact>** element.</span></span>  
  
 <span data-ttu-id="fc1c3-156">Da in diesem Update Gram kein Zuordnungs Schema angegeben ist, verwendet das Update Gram die implizite Zuordnung, bei der das **\<Person.Contact>** -Element der Person. Contact-Tabelle zugeordnet wird und die untergeordneten Elemente den Spalten FirstName und LastName zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-156">Because this updategram does not specify a mapping schema, the updategram uses implicit mapping, where the **\<Person.Contact>** element maps to the Person.Contact table and its child elements map to the FirstName and LastName columns.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a><span data-ttu-id="fc1c3-157">Attributzentrierte Zuordnung</span><span class="sxs-lookup"><span data-stu-id="fc1c3-157">Attribute-centric Mapping</span></span>  
 <span data-ttu-id="fc1c3-158">Die Elemente in einer attributzentrierten Zuordnung verfügen über Attribute.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-158">In an attribute-centric mapping, the elements have attributes.</span></span> <span data-ttu-id="fc1c3-159">Im folgenden Updategram wird die attributzentrierte Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-159">The following updategram uses attribute-centric mapping.</span></span> <span data-ttu-id="fc1c3-160">In diesem Beispiel besteht das **\<Person.Contact>** -Element aus den Attributen **FirstName** und **LastName** .</span><span class="sxs-lookup"><span data-stu-id="fc1c3-160">In this example, the **\<Person.Contact>** element consists of the **FirstName** and **LastName** attributes.</span></span> <span data-ttu-id="fc1c3-161">Diese Attribute sind die Eigenschaften des- **\<Person.Contact>** Elements.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-161">These attributes are the properties of the **\<Person.Contact>** element.</span></span> <span data-ttu-id="fc1c3-162">Wie im vorherigen Beispiel ist in diesem Update Gram kein Zuordnungs Schema angegeben. Daher basiert es auf impliziter Zuordnung, um das **\<Person.Contact>** Element der Person. Contact-Tabelle und die Attribute des Elements den entsprechenden Spalten in der Tabelle zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-162">As in the previous example, this updategram specifies no mapping schema, so it relies on implicit mapping to map the **\<Person.Contact>** element to the Person.Contact table and the element's attributes to the respective columns in the table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a><span data-ttu-id="fc1c3-163">Verwenden der elementzentrierten und der attributzentrierten Zuordnung</span><span class="sxs-lookup"><span data-stu-id="fc1c3-163">Using Both Element-centric and Attribute-centric Mapping</span></span>  
 <span data-ttu-id="fc1c3-164">Sie können eine Mischung elementzentrierter und attributzentrierter Zuordnung angeben, wie im folgenden Updategram dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-164">You can specify a mix of element-centric and attribute-centric mapping, as shown in the following updategram.</span></span> <span data-ttu-id="fc1c3-165">Beachten Sie, dass das **\<Person.Contact>** -Element sowohl ein Attribut als auch ein untergeordnetes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-165">Notice that the **\<Person.Contact>** element contains both an attribute and a child element.</span></span> <span data-ttu-id="fc1c3-166">Für dieses Updategram wird die implizite Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-166">Also, this updategram relies on implicit mapping.</span></span> <span data-ttu-id="fc1c3-167">Folglich werden das **FirstName** -Attribut und das untergeordnete- **\<LastName>** Element den entsprechenden Spalten in der Person. Contact-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-167">Thus, the **FirstName** attribute and the **\<LastName>** child element map to corresponding columns in the Person.Contact table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a><span data-ttu-id="fc1c3-168">Verwenden von Zeichen, die in SQL Server gültig sind, in XML jedoch nicht</span><span class="sxs-lookup"><span data-stu-id="fc1c3-168">Working with Characters Valid in SQL Server but Not Valid in XML</span></span>  
 <span data-ttu-id="fc1c3-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dürfen Tabellennamen Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space.</span></span> <span data-ttu-id="fc1c3-170">Dieser Tabellennamentyp ist in XML jedoch nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-170">However, this type of table name is not valid in XML.</span></span>  
  
 <span data-ttu-id="fc1c3-171">Verwenden Sie zum Codieren von Zeichen, die gültige Bezeichner sind [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , aber keine gültigen XML-Bezeichner sind, "__xHHHH \_ \_ " als Codierungs Wert, wobei HHHH für den vierstelligen hexadezimalen UCS-2-Code für das Zeichen in der signifikantesten bidirektionalen Reihenfolge steht.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-171">To encode characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but are not valid XML identifiers, use '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="fc1c3-172">Mit diesem Codierungsschema wird ein Leerzeichen durch x0020 (der vierstellige Hexadezimal Code für ein Leerzeichen) ersetzt; Daher wird der Tabellenname [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] \_ in XML _x005B_Order_x0020_Details_x005D.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-172">Using this encoding scheme, a space character gets replaced with x0020 (the four-digit hexadecimal code for a space character); thus, the table name [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] becomes _x005B_Order_x0020_Details_x005D\_ in XML.</span></span>  
  
 <span data-ttu-id="fc1c3-173">Ebenso müssen Sie möglicherweise dreiteilige Elementnamen angeben, z \<[database].[owner].[table]> . b..</span><span class="sxs-lookup"><span data-stu-id="fc1c3-173">Similarly, you might need to specify three-part element names, such as \<[database].[owner].[table]>.</span></span> <span data-ttu-id="fc1c3-174">Da die Klammer Zeichen ([und]) in XML nicht gültig sind, müssen Sie diese als angeben \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_> , wobei _x005B \_ die Codierung für die linke eckige Klammer ([) und _x005D \_ die Codierung für die rechte eckige Klammer (]) ist.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-174">Because the bracket characters ([ and ]) are not valid in XML, you must specify this as \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_>, where _x005B\_ is the encoding for the left bracket ([) and _x005D\_ is the encoding for the right bracket (]).</span></span>  
  
## <a name="executing-updategrams"></a><span data-ttu-id="fc1c3-175">Ausführen von Updategrams</span><span class="sxs-lookup"><span data-stu-id="fc1c3-175">Executing Updategrams</span></span>  
 <span data-ttu-id="fc1c3-176">Da ein Updategram eine Vorlage ist, gelten alle Verarbeitungsmechanismen einer Vorlage auch für ein Updategram.</span><span class="sxs-lookup"><span data-stu-id="fc1c3-176">Because an updategram is a template, all the processing mechanisms of a template apply to the updategram.</span></span> <span data-ttu-id="fc1c3-177">Zum Ausführen eines Updategrams in SQLXML 4.0 können Sie eine der beiden folgenden Möglichkeiten verwenden:</span><span class="sxs-lookup"><span data-stu-id="fc1c3-177">For SQLXML 4.0, you can execute an updategram in either of the following ways:</span></span>  
  
-   <span data-ttu-id="fc1c3-178">Senden des Updategrams in einem ADO-Befehl</span><span class="sxs-lookup"><span data-stu-id="fc1c3-178">By submitting it in an ADO command.</span></span>  
  
-   <span data-ttu-id="fc1c3-179">Senden des Updategrams in einem OLE DB-Befehl</span><span class="sxs-lookup"><span data-stu-id="fc1c3-179">By submitting it as an OLE DB command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1c3-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc1c3-180">See Also</span></span>  
 [<span data-ttu-id="fc1c3-181">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="fc1c3-181">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
