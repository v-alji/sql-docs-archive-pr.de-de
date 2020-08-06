---
title: Vergleichen von typisiertem XML mit nicht typisiertem XML | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- parameters [XML in SQL Server]
- facets [XML in SQL Server]
- xml data type [SQL Server], columns
- untyped XML
- xml data type [SQL Server], typed xml
- XML [SQL Server], typed
- variables [XML in SQL Server], creating
- xml data type [SQL Server], untyped xml
- columns [XML in SQL Server], creating
- typed XML
- document mode processing [SQL Server]
- XML [SQL Server], untyped
- xml data type [SQL Server], parameters
ms.assetid: 4bc50af9-2f7d-49df-bb01-854d080c72c7
author: rothja
ms.author: jroth
ms.openlocfilehash: fae9ca930bd8741a1332b61c8272f2133590483e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697617"
---
# <a name="compare-typed-xml-to-untyped-xml"></a><span data-ttu-id="0ee12-102">Vergleichen von typisiertem XML mit nicht typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="0ee12-102">Compare Typed XML to Untyped XML</span></span>
  <span data-ttu-id="0ee12-103">Sie können Variablen, Parameter und Spalten des `xml`-Datentyps erstellen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-103">You can create variables, parameters, and columns of the `xml` type.</span></span> <span data-ttu-id="0ee12-104">Optional können Sie eine Auflistung von XML-Schemas mit einer Variablen, einem Parameter oder einer Spalte vom Typ `xml` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-104">You can optionally associate a collection of XML schemas with a variable, parameter, or column of `xml` type.</span></span> <span data-ttu-id="0ee12-105">In diesem Fall wird die `xml` Instanz des-Datentyps als *typisiert*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0ee12-105">In this case, the `xml` data type instance is called *typed*.</span></span> <span data-ttu-id="0ee12-106">Anderenfalls wird die XML-Instanz als *nicht typisiert*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0ee12-106">Otherwise, the XML instance is called *untyped*.</span></span>  
  
## <a name="well-formed-xml-and-the-xml-data-type"></a><span data-ttu-id="0ee12-107">Wohlgeformtes XML und der xml-Datentyp</span><span class="sxs-lookup"><span data-stu-id="0ee12-107">Well-formed XML and the xml Data Type</span></span>  
 <span data-ttu-id="0ee12-108">Der `xml`-Datentyp implementiert den im ISO-Standard definierten `xml`-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="0ee12-108">The `xml` data type implements the ISO standard `xml` data type.</span></span> <span data-ttu-id="0ee12-109">Deshalb ermöglicht er das Speichern sowohl von wohlgeformten XML-Dokumenten der Version 1.0 als auch von so genannten XML-Inhaltsfragmenten mit Textknoten und einer beliebigen Anzahl von Elementen auf der obersten Ebene in einer nicht typisierten XML-Spalte.</span><span class="sxs-lookup"><span data-stu-id="0ee12-109">Therefore, it can store well-formed XML version 1.0 documents and also so-called XML content fragments with text nodes and an arbitrary number of top-level elements in an untyped XML column.</span></span> <span data-ttu-id="0ee12-110">Das System überprüft, ob die Daten wohlgeformt sind (wobei es nicht erforderlich ist, dass die Spalte an XML-Schemas gebunden ist) und weist alle Daten zurück, die in diesem erweiterten Sinne nicht wohlgeformt sind.</span><span class="sxs-lookup"><span data-stu-id="0ee12-110">The system checks that the data is well-formed, does not require the column to be bound to XML schemas, and rejects data that is not well-formed in the extended sense.</span></span> <span data-ttu-id="0ee12-111">Dies gilt auch für nicht typisierte XML-Variablen und -Parameter.</span><span class="sxs-lookup"><span data-stu-id="0ee12-111">This is true also of untyped XML variables and parameters.</span></span>  
  
## <a name="xml-schemas"></a><span data-ttu-id="0ee12-112">XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="0ee12-112">XML Schemas</span></span>  
 <span data-ttu-id="0ee12-113">Ein XML-Schema stellt Folgendes bereit:</span><span class="sxs-lookup"><span data-stu-id="0ee12-113">An XML schema provides the following:</span></span>  
  
-   <span data-ttu-id="0ee12-114">**Überprüfungseinschränkungen.**</span><span class="sxs-lookup"><span data-stu-id="0ee12-114">**Validation constraints.**</span></span> <span data-ttu-id="0ee12-115">Bei jeder Zuweisung oder Änderung einer typisierten xml-Instanz überprüft SQL Server die Instanz.</span><span class="sxs-lookup"><span data-stu-id="0ee12-115">Whenever a typed xml instance is assigned to or modified, SQL Server validates the instance.</span></span>  
  
-   <span data-ttu-id="0ee12-116">**Datentypinformationen.**</span><span class="sxs-lookup"><span data-stu-id="0ee12-116">**Data type information.**</span></span> <span data-ttu-id="0ee12-117">Schemas stellen Informationen zu den Typen von Attributen und Elementen in der `xml`-Datentypinstanz bereit.</span><span class="sxs-lookup"><span data-stu-id="0ee12-117">Schemas provide information about the types of attributes and elements in the `xml` data type instance.</span></span> <span data-ttu-id="0ee12-118">Die Typinformationen stellen den in der Instanz enthaltenen Werten genauere operationale Semantik zur Verfügung als dies bei untypisiertem `xml` möglich ist.</span><span class="sxs-lookup"><span data-stu-id="0ee12-118">The type information provides more precise operational semantics to the values contained in the instance than is possible with untyped `xml`.</span></span> <span data-ttu-id="0ee12-119">Dezimale arithmetische Operationen können z. B. für einen Dezimalwert, nicht jedoch für einen Zeichenfolgenwert ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ee12-119">For example, decimal arithmetic operations can be performed on a decimal value, but not on a string value.</span></span> <span data-ttu-id="0ee12-120">Aus diesem Grund ist die Speicherung typisierten XMLs erheblich kompakter als bei nicht typisiertem XML.</span><span class="sxs-lookup"><span data-stu-id="0ee12-120">Because of this, typed XML storage can be made significantly more compact than untyped XML.</span></span>  
  
## <a name="choosing-typed-or-untyped-xml"></a><span data-ttu-id="0ee12-121">Auswählen zwischen typisiertem oder nicht typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="0ee12-121">Choosing Typed or Untyped XML</span></span>  
 <span data-ttu-id="0ee12-122">Verwenden Sie den nicht typisierten `xml`-Datentyp in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="0ee12-122">Use untyped `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="0ee12-123">Sie verfügen über kein Schema für Ihre XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="0ee12-123">You do not have a schema for your XML data.</span></span>  
  
-   <span data-ttu-id="0ee12-124">Sie verfügen zwar über Schemas, wollen jedoch die Gültigkeit der Daten nicht durch den Server überprüfen lassen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-124">You have schemas, but you do not want the server to validate the data.</span></span> <span data-ttu-id="0ee12-125">Dies ist manchmal der Fall, wenn eine Anwendung eine clientseitige Gültigkeitsprüfung vor dem Speichern der Daten auf dem Server durchführt oder gemäß dem Schema ungültige XML-Daten temporär speichert oder Schemakomponenten verwendet, die vom Server nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0ee12-125">This is sometimes the case when an application performs client-side validation before storing the data at the server, or temporarily stores XML data that is invalid according to the schema, or uses schema components that are not supported at the server.</span></span>  
  
 <span data-ttu-id="0ee12-126">Verwenden Sie den typisierten- `xml` Datentyp in den folgenden Situationen:</span><span class="sxs-lookup"><span data-stu-id="0ee12-126">Use typed `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="0ee12-127">Sie verfügen über Schemas für Ihre XML-Daten und wollen, dass der Server anhand der XML-Schemas die Gültigkeit Ihrer XML-Daten überprüft.</span><span class="sxs-lookup"><span data-stu-id="0ee12-127">You have schemas for your XML data and you want the server to validate your XML data according to the XML schemas.</span></span>  
  
-   <span data-ttu-id="0ee12-128">Sie möchten Speicherungs- und Abfrageoptimierungen nutzen, die auf den Typinformationen basieren.</span><span class="sxs-lookup"><span data-stu-id="0ee12-128">You want to take advantage of storage and query optimizations based on type information.</span></span>  
  
-   <span data-ttu-id="0ee12-129">Sie möchten beim Kompilieren Ihrer Abfragen einen größeren Nutzen aus den Typinformationen ziehen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-129">You want to take better advantage of type information during compilation of your queries.</span></span>  
  
 <span data-ttu-id="0ee12-130">Typisierte XML-Spalten, -Parameter und -Variablen können XML-Dokumente oder -Inhalte speichern.</span><span class="sxs-lookup"><span data-stu-id="0ee12-130">Typed XML columns, parameters, and variables can store XML documents or content.</span></span> <span data-ttu-id="0ee12-131">Allerdings müssen Sie zum Zeitpunkt der Deklaration durch ein Flag angeben, ob Sie ein Dokument oder einen Inhalt speichern.</span><span class="sxs-lookup"><span data-stu-id="0ee12-131">However, you have to specify with a flag whether you are storing a document or content at the time of declaration.</span></span> <span data-ttu-id="0ee12-132">Außerdem müssen Sie die Auflistung der XML-Schemas bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-132">Additionally, you have to provide the collection of XML schemas.</span></span> <span data-ttu-id="0ee12-133">Geben Sie DOCUMENT an, wenn jede XML-Instanz genau ein Element auf der obersten Ebene aufweist.</span><span class="sxs-lookup"><span data-stu-id="0ee12-133">Specify DOCUMENT if each XML instance has exactly one top-level element.</span></span> <span data-ttu-id="0ee12-134">Verwenden Sie ansonsten CONTENT.</span><span class="sxs-lookup"><span data-stu-id="0ee12-134">Otherwise, use CONTENT.</span></span> <span data-ttu-id="0ee12-135">Der Abfragecompiler verwendet das DOCUMENT-Flag bei den Typüberprüfungen während der Abfragekompilierung, um Singleton-Elemente auf der obersten Ebene abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="0ee12-135">The query compiler uses the DOCUMENT flag in type checks during query compilation to infer singleton top-level elements.</span></span>  
  
## <a name="creating-typed-xml"></a><span data-ttu-id="0ee12-136">Erstellen von typisiertem XML</span><span class="sxs-lookup"><span data-stu-id="0ee12-136">Creating Typed XML</span></span>  
 <span data-ttu-id="0ee12-137">Bevor Sie typisierte `xml` Variablen, Parameter oder Spalten erstellen können, müssen Sie die XML-Schema Auflistung zunächst mithilfe von [CREATE XML Schema Collection &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql)registrieren.</span><span class="sxs-lookup"><span data-stu-id="0ee12-137">Before you can create typed `xml` variables, parameters, or columns, you must first register the XML schema collection by using [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span> <span data-ttu-id="0ee12-138">Anschließend können Sie der XML-Schemaauflistung Variablen, Parameter oder Spalten des `xml`-Datentyps zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-138">You can then associate the XML schema collection with variables, parameters, or columns of the `xml` data type.</span></span>  
  
 <span data-ttu-id="0ee12-139">Im folgenden Beispiel wird eine zweiteilige Benennungskonvention zum Angeben des Namens der XML-Schemaauflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ee12-139">In the following examples, a two-part naming convention is used for specifying the XML schema collection name.</span></span> <span data-ttu-id="0ee12-140">Der erste Teil ist der Schemaname, der zweite Teil der Name der XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="0ee12-140">The first part is the schema name, and the second part is the XML schema collection name.</span></span>  
  
### <a name="example-associating-a-schema-collection-with-an-xml-type-variable"></a><span data-ttu-id="0ee12-141">Beispiel: Verknüpfen einer Schemasammlung mit einer XML-Variable</span><span class="sxs-lookup"><span data-stu-id="0ee12-141">Example: Associating a Schema Collection with an xml Type Variable</span></span>  
 <span data-ttu-id="0ee12-142">Im folgenden Beispiel wird eine `xml` Typvariable erstellt und ihr eine Schema Auflistung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0ee12-142">The following example creates an`xml` type variable and associates a schema collection with it.</span></span> <span data-ttu-id="0ee12-143">Die im Beispiel angegebene Schemaauflistung wurde bereits in die **AdventureWorks** -Datenbank importiert.</span><span class="sxs-lookup"><span data-stu-id="0ee12-143">The schema collection specified in the example is already imported in the **AdventureWorks** database.</span></span>  
  
```  
DECLARE @x xml (Production.ProductDescriptionSchemaCollection);   
```  
  
### <a name="example-specifying-a-schema-for-an-xml-type-column"></a><span data-ttu-id="0ee12-144">Beispiel: Angeben eines Schemas für eine XML-Spalte</span><span class="sxs-lookup"><span data-stu-id="0ee12-144">Example: Specifying a Schema for an xml Type Column</span></span>  
 <span data-ttu-id="0ee12-145">Im folgenden Beispiel wird eine Tabelle mit einer Spalte vom Typ `xml` erstellt und ein Schema für die Spalte angegeben:</span><span class="sxs-lookup"><span data-stu-id="0ee12-145">The following example creates a table with an `xml` type column and specifies a schema for the column:</span></span>  
  
```  
CREATE TABLE T1(  
 Col1 int,   
 Col2 xml (Production.ProductDescriptionSchemaCollection)) ;  
```  
  
### <a name="example-passing-an-xml-type-parameter-to-a-stored-procedure"></a><span data-ttu-id="0ee12-146">Beispiel: Übergeben eines XML-Parameters an eine gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="0ee12-146">Example: Passing an xml Type Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="0ee12-147">Im folgenden Beispiel wird ein Parameter vom Typ `xml` an eine gespeicherte Prozedur übergeben und ein Schema für die Variable angegeben:</span><span class="sxs-lookup"><span data-stu-id="0ee12-147">The following example passes an `xml` type parameter to a stored procedure and specifies a schema for the variable:</span></span>  
  
```  
CREATE PROCEDURE SampleProc   
  @ProdDescription xml (Production.ProductDescriptionSchemaCollection)   
AS   
...  
```  
  
 <span data-ttu-id="0ee12-148">Beachten Sie hinsichtlich der XML-Schemaauflistung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0ee12-148">Note the following about the XML schema collection:</span></span>  
  
-   <span data-ttu-id="0ee12-149">Eine XML-Schemaauflistung ist nur in der Datenbank verfügbar, in der sie mit [Erstellen einer XML-Schemaauflistung](/sql/t-sql/statements/create-xml-schema-collection-transact-sql)registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="0ee12-149">An XML schema collection is available only in the database in which it was registered by using [Creating an XML Schema Collection](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span>  
  
-   <span data-ttu-id="0ee12-150">Wenn Sie die Umwandlung aus einer Zeichenfolge in einen typisierten `xml`-Datentyp vornehmen, führt die Analyse außerdem die Überprüfung und Typisierung basierend auf den XML-Schemanamespaces in der angegebenen Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="0ee12-150">If you cast from a string to a typed `xml` data type, the parsing also performs validation and typing, based on the XML schema namespaces in the collection specified.</span></span>  
  
-   <span data-ttu-id="0ee12-151">Sie können einen typisierten `xml`-Datentyp in einen nicht typisierten `xml`-Datentyp umwandeln und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="0ee12-151">You can cast from a typed `xml` data type to an untyped `xml` data type, and vice versa.</span></span>  
  
 <span data-ttu-id="0ee12-152">Weitere Informationen zu anderen Methoden zum Generieren von XML in SQL Server finden Sie unter [Erstellen von Instanzen der XML-Daten](create-instances-of-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="0ee12-152">For more information about other ways to generate XML in SQL Server, see [Create Instances of XML Data](create-instances-of-xml-data.md).</span></span> <span data-ttu-id="0ee12-153">Nachdem das XML generiert wurde, kann es einer Variablen vom Datentyp `xml` zugewiesen oder in Spalten vom Typ `xml` für die weitere Verarbeitung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0ee12-153">After XML is generated, it can be assigned either to an `xml` data type variable or stored in `xml` type columns for additional processing.</span></span>  
  
 <span data-ttu-id="0ee12-154">In der Datentyphierarchie nimmt der `xml`-Datentyp einen Platz unter `sql_variant` und benutzerdefinierten Typen ein, steht jedoch über allen integrierten Typen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-154">In the data type hierarchy, the `xml` data type appears below `sql_variant` and user-defined types, but above any of the built-in types.</span></span>  
  
### <a name="example-specifying-facets-to-constrain-a-typed-xml-column"></a><span data-ttu-id="0ee12-155">Beispiel: Angeben von Facets zum Einschränken einer typisierten XML-Spalte</span><span class="sxs-lookup"><span data-stu-id="0ee12-155">Example: Specifying Facets to Constrain a Typed xml Column</span></span>  
 <span data-ttu-id="0ee12-156">Typisierte `xml`-Spalten können so eingeschränkt werden, dass nur einzelne Elemente der obersten Ebene für jede darin gespeicherte Instanz zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="0ee12-156">For typed `xml` columns, you can constrain the column to allow only single, top-level elements for each instance stored in it.</span></span> <span data-ttu-id="0ee12-157">Sie geben zu diesem Zweck beim Erstellen der Tabelle den optionalen `DOCUMENT` -Facet an, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="0ee12-157">You do this by specifying the optional `DOCUMENT` facet when a table is created, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml   
   (DOCUMENT Production.ProductDescriptionSchemaCollection));  
GO  
DROP TABLE T;  
GO  
```  
  
 <span data-ttu-id="0ee12-158">Standardmäßig werden Instanzen, die in der typisierten `xml`-Spalte gespeichert werden, als XML-Inhalt und nicht als XML-Dokumente gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0ee12-158">By default, instances stored in the typed `xml` column are stored as XML content and not as XML documents.</span></span> <span data-ttu-id="0ee12-159">Folgendes wird auf diese Weise ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="0ee12-159">This allows for the following:</span></span>  
  
-   <span data-ttu-id="0ee12-160">Null oder zahlreiche Elemente der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="0ee12-160">Zero or many top-level elements</span></span>  
  
-   <span data-ttu-id="0ee12-161">Textknoten in Elementen der obersten Ebene</span><span class="sxs-lookup"><span data-stu-id="0ee12-161">Text nodes in top-level elements</span></span>  
  
 <span data-ttu-id="0ee12-162">Sie können dieses Verhalten auch explizit festlegen, indem Sie, wie im folgenden Beispiel dargestellt, das `CONTENT` -Facet hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="0ee12-162">You can also explicitly specify this behavior by adding `CONTENT` facet, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml(CONTENT Production.ProductDescriptionSchemaCollection));  
GO -- Default  
```  
  
 <span data-ttu-id="0ee12-163">Beachten Sie, dass Sie die optionalen DOCUMENT/CONTENT-Facets immer angeben können, wenn Sie den `xml`-Typ definieren (typisiertes xml).</span><span class="sxs-lookup"><span data-stu-id="0ee12-163">Note that you can specify the optional DOCUMENT/CONTENT facets anywhere you define `xml` type (typed xml).</span></span> <span data-ttu-id="0ee12-164">Wenn Sie eine typisierte `xml`-Variable erstellen, können Sie z. B. das DOCUMENT/CONTENT-Facet, wie im folgenden Beispiel gezeigt, hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="0ee12-164">For example, when you create a typed `xml` variable, you can add the DOCUMENT/CONTENT facet, as shown in the following:</span></span>  
  
```  
declare @x xml (DOCUMENT Production.ProductDescriptionSchemaCollection);  
```  
  
## <a name="document-type-definition-dtd"></a><span data-ttu-id="0ee12-165">Dokumenttypdefinition (DTD)</span><span class="sxs-lookup"><span data-stu-id="0ee12-165">Document Type Definition (DTD)</span></span>  
 <span data-ttu-id="0ee12-166">Die Spalten, Variablen und Parameter des `xml`-Datentyps können mithilfe eines XML-Schemas typisiert werden, jedoch nicht mithilfe von DTD.</span><span class="sxs-lookup"><span data-stu-id="0ee12-166">The `xml` data type columns, variables, and parameters can be typed by using XML schema, but not by using DTD.</span></span> <span data-ttu-id="0ee12-167">Allerdings kann Inline-DTD sowohl für nicht typisiertes als auch für typisiertes XML verwendet werden, um Standardwerte bereitzustellen und um Entitätsverweise durch ihre erweiterte Form zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0ee12-167">However, inline DTD can be used for both untyped and typed XML to supply default values and to replace entity references with their expanded form.</span></span>  
  
 <span data-ttu-id="0ee12-168">Mithilfe von Drittanbieter-Tools können Sie DTDs in XML-Schemadokumente konvertieren und die XML-Schemas in die Datenbank laden.</span><span class="sxs-lookup"><span data-stu-id="0ee12-168">You can convert DTDs to XML schema documents by using third-party tools, and load the XML schemas into the database.</span></span>  
  
## <a name="upgrading-typed-xml-from-sql-server-2005"></a><span data-ttu-id="0ee12-169">Aktualisieren von typisiertem XML aus SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="0ee12-169">Upgrading Typed XML from SQL Server 2005</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="0ee12-170">wurde die XML-Schemaunterstützung erweitert, beispielsweise um die Unterstützung für die lax-Überprüfung, verbesserte Behundlung von Instanzdaten des Typs **xs:date**, **xs:time** und **xs:dateTime** instance data, und added support for list und union types.</span><span class="sxs-lookup"><span data-stu-id="0ee12-170">made several extensions to the XML Schema support, including support for lax validation, improved handling of **xs:date**, **xs:time** and **xs:dateTime** instance data, and added support for list and union types.</span></span> <span data-ttu-id="0ee12-171">In den meisten Fällen beeinflussen die Änderungen die Aktualisierung nicht.</span><span class="sxs-lookup"><span data-stu-id="0ee12-171">In most cases the changes do not affect the upgrade experience.</span></span> <span data-ttu-id="0ee12-172">Wenn Sie jedoch eine XML-Schemaauflistung in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] verwendeten, die Werte des Typs **xs:date**, **xs:time**oder **xs:dateTime** (oder einen Untertyp davon) zuließ, dann werden die folgenden Aktualisierungsschritte ausgeführt, wenn Sie die [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] -Datenbank an eine spätere Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]anfügen:</span><span class="sxs-lookup"><span data-stu-id="0ee12-172">However if you used an XML Schema collection in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] that allowed values of type **xs:date**, **xs:time**, or **xs:dateTime** (or any subtype) then the following upgrade steps occur when you attach your [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database to a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="0ee12-173">Für jede XML-Spalte, die mit einer XML-Schemaauflistung typisiert ist, die Elemente oder Attribute vom Typ **xs:anyType**, **xs:anySimpleType**, **xs:date** oder eines Untertyps davon, **xs:time** oder eines Untertyps davon oder **xs:dateTime** oder eines Untertyps davon enthält bzw. Elemente oder Attribute vom Typ union oder list sind, die einen dieser Typen enthalten, wird folgender Vorgang ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="0ee12-173">For every XML column, that is typed with an XML Schema Collection that contains elements or attributes that are typed as either **xs:anyType**, **xs:anySimpleType**, **xs:date** or any of its subtypes, **xs:time** or any subtype thereof, or **xs:dateTime** or any of its subtypes, or are union or list types containing any of these types the following occurs:</span></span>  
  
    1.  <span data-ttu-id="0ee12-174">Alle XML-Indizes der Spalte werden deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0ee12-174">All XML indices on the column will be disabled.</span></span>  
  
    2.  <span data-ttu-id="0ee12-175">Alle [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] -Werte werden weiterhin in der Z-Zeitzone dargestellt, weil sie in die Z-Zeitzone normalisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0ee12-175">All [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] values will continue to be represented in the Z timezone, because they have been normalized to the Z timezone.</span></span>  
  
    3.  <span data-ttu-id="0ee12-176">Alle Werte des Typs **xs:date** oder **xs:dateTime** , die kleiner sind als der 1. Januar im Jahr 1, führen zu einem Laufzeitfehler, wenn der Index erneut erstellt wird oder wenn eine XQuery-Anweisung oder eine XML-DML-Anweisung für den XML-Datentyp ausgeführt wird, der diesen Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="0ee12-176">Any **xs:date** or **xs:dateTime** values that are smaller than January 1st of year 1 will lead to a runtime error when the index gets rebuild or an XQuery or XML-DML statements gets executed against the XML data type containing that value.</span></span>  
  
2.  <span data-ttu-id="0ee12-177">Alle negativen Jahresangaben in **xs:date** - oder **xs:dateTime** -Facets oder in Standardwerten einer XML-Schemaauflistung werden automatisch durch den kleinsten für den Basistyp **xs:date** oder **xs:dateTime** zulässigen Wert ersetzt (beispielsweise 0001-01-01T00:00:00.0000000Z für **xs:dateTime**).</span><span class="sxs-lookup"><span data-stu-id="0ee12-177">Any negative years in **xs:date** or **xs:dateTime** facets or default values in an XML Schema collection will automatically be updated to the smallest value allowed by the base **xs:date** or **xs:dateTime** type (e.g., 0001-01-01T00:00:00.0000000Z for **xs:dateTime**).</span></span>  
  
 <span data-ttu-id="0ee12-178">Beachten Sie, dass Sie den gesamten XML-Datentyp weiterhin mit einer einfachen SQL-SELECT-Anweisung abrufen können, selbst wenn er negative Jahresangaben enthält.</span><span class="sxs-lookup"><span data-stu-id="0ee12-178">Note that you can still use a simple SQL select statement to retrieve the whole XML data type, even if it contains negative years.</span></span> <span data-ttu-id="0ee12-179">Es wird empfohlen, dass Sie die negativen Jahresangaben durch eine Jahresangabe ersetzen, die im neuen unterstützten Bereich liegt, oder den Typ des Elements oder Attributs in **xs:string**ändern.</span><span class="sxs-lookup"><span data-stu-id="0ee12-179">It is recommended that you replace negative years with a year within the newly supported range or change the type of the element or attribute to **xs:string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee12-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ee12-180">See Also</span></span>  
 <span data-ttu-id="0ee12-181">[Erstellen von Instanzen der XML-Daten](create-instances-of-xml-data.md) </span><span class="sxs-lookup"><span data-stu-id="0ee12-181">[Create Instances of XML Data](create-instances-of-xml-data.md) </span></span>  
 <span data-ttu-id="0ee12-182">[XML-Datentypmethoden](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="0ee12-182">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="0ee12-183">[XML DML &#40;Data Modification Language&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="0ee12-183">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="0ee12-184">XML-Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0ee12-184">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
