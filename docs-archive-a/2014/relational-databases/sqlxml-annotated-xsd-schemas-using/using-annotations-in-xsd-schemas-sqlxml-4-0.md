---
title: Verwenden von Anmerkungen in XSD-Schemas (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, about annotated XSD schemas
- annotations [SQLXML]
- relationships [SQLXML]
- relationships [SQLXML], hierarchical relationships
- hierarchical relationships [SQLXML]
- mapping schema [SQLXML], scenarios for using
ms.assetid: 78f318a4-7a36-473b-9852-a4bae6940ce5
author: rothja
ms.author: jroth
ms.openlocfilehash: e2be94aa5815593d7a5a2e0c00bcd8849e81484e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617896"
---
# <a name="using-annotations-in-xsd-schemas-sqlxml-40"></a><span data-ttu-id="e8ef2-102">Verwenden von Anmerkungen in XSD-Schemas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e8ef2-102">Using Annotations in XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="e8ef2-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0 unterstützt die XSD-Schemasprache Anmerkungen auf ähnliche Weise wie die in der XDR-Schemasprache (XML-Data Reduced) eingeführten Anmerkungen.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports annotations in a manner similar to the annotations introduced in the XML-Data Reduced (XDR) schema language.</span></span> <span data-ttu-id="e8ef2-104">Es gibt weitere in XSD eingeführte Anmerkungen, die in XDR nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-104">There are additional annotations introduced in XSD that are not supported in XDR.</span></span>  
  
 <span data-ttu-id="e8ef2-105">Diese Anmerkungen können innerhalb des XSD-Schemas verwendet werden, um Zuordnungen von XML zu relationalen Daten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-105">These annotations can be used within the XSD schema to specify XML-to-relational mapping.</span></span> <span data-ttu-id="e8ef2-106">Dazu gehört die Zuordnung von Elementen und Attributen im XSD-Schema zu Tabellen (Sichten) und Spalten in den Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-106">This includes mapping between elements and attributes in the XSD schema to tables (views) and columns in the databases.</span></span>  
  
 <span data-ttu-id="e8ef2-107">Wenn Sie die Anmerkungen nicht angeben, wird die Standardzuordnung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-107">If you do not specify the annotations, default mapping takes place.</span></span> <span data-ttu-id="e8ef2-108">Standardmäßig wird ein XSD-Element mit einem komplexen Typ einem Tabellennamen (Sichtnamen) in der angegebenen Datenbank zugeordnet, und ein Element oder Attribut mit einem einfachen Typ wird der Spalte mit demselben Namen wie das Element oder Attribut zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-108">By default, an XSD element with a complex type maps to a table (view) name in the specified database, and an element or attribute with a simple type maps to the column with the same name as the element or attribute.</span></span>  
  
 <span data-ttu-id="e8ef2-109">Diese Anmerkungen können auch zur Angabe der hierarchischen Beziehungen in XML verwendet werden, wodurch die Beziehungen in der Datenbank dargestellt werden, da ein XSD-Schema einfach eine XML-Sicht relationaler Daten ist.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-109">These annotations can also be used to specify the hierarchical relationships in XML-thus representing the relationships in the database, because an XSD schema is simply an XML view of relational data.</span></span>  
  
 <span data-ttu-id="e8ef2-110">Dieser Abschnitt enthält Beschreibungen der Anmerkungen, die Sie mit XSD-Schemas verwenden können, sowie Anwendungsbeispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-110">This section provides descriptions of the annotations you can use with XSD schemas and examples of their usage.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e8ef2-111">Alle Beispiele in diesem Abschnitt geben einfache Xpath-Abfragen für das mit Anmerkungen versehene XSD-Schema an, das in dem jeweiligen Beispiel beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-111">All the examples in this section specify simple XPath queries against the annotated XSD schema described in each example.</span></span> <span data-ttu-id="e8ef2-112">Kenntnisse der XPath-Sprache werden vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-112">Familiarity with the XPath language is assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8ef2-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e8ef2-113">In This Section</span></span>  
 [<span data-ttu-id="e8ef2-114">XSD-Anmerkungen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-114">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](xsd-annotations-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-115">Enthält eine Liste der Anmerkungen, die Sie mit XSD-Schemas verwenden können, ihre Beschreibungen und die entsprechenden Anmerkungen für XDR.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-115">Lists the annotations you can use with XSD schemas, their descriptions, and the equivalent annotations for XDR.</span></span>  
  
 [<span data-ttu-id="e8ef2-116">Standard Zuordnung von XSD-Elementen und-Attributen zu Tabellen und Spalten &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-116">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-117">Erläutert die Standardzuordnung und enthält Beispiele für Tasks, die im Zusammenhang mit der Standardzuordnung stehen.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-117">Explains default mapping and provides examples of tasks related to default mapping.</span></span>  
  
 [<span data-ttu-id="e8ef2-118">Explizite Zuordnung von XSD-Elementen und-Attributen zu Tabellen und Spalten &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-118">Explicit Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](explicit-mapping-xsd-elements-and-attributes-to-tables-and-columns.md)  
 <span data-ttu-id="e8ef2-119">Erklärt die explizite Zuordnung mit der `sql:relation`-Anmerkung und der `sql:field`-Anmerkung anhand von Beispielen.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-119">Explains explicit mapping with the `sql:relation` and `sql:field` annotations, and provides examples.</span></span>  
  
 [<span data-ttu-id="e8ef2-120">Angeben von Beziehungen mithilfe von ' SQL: Relationship ' &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-120">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-121">Beschreibt die `sql:relationship`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-121">Describes and provides examples of the `sql:relationship` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-122">Angeben des SQL: inverse-Attributs für SQL: Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-122">Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-123">Beschreibt die `sql:inverse`-Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-123">Describes the `sql:inverse` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-124">Erstellen konstanter Elemente mithilfe von SQL: is-constant &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-124">Creating Constant Elements Using sql:is-constant &#40;SQLXML 4.0&#41;</span></span>](creating-constant-elements-using-sql-is-constant-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-125">Beschreibt die `sql:is-constant`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-125">Describes and provides examples of the `sql:is-constant` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-126">Ausschließen von Schema Elementen aus dem resultierenden XML-Dokument mithilfe von SQL: zugeordnet &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-126">Excluding Schema Elements from the Resulting XML Document Using sql:mapped &#40;SQLXML 4.0&#41;</span></span>](excluding-schema-elements-from-the-xml-document-using-sql-mapped.md)  
 <span data-ttu-id="e8ef2-127">Beschreibt die `sql:mapped`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-127">Describes and provides examples of the `sql:mapped` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-128">Filtern von Werten mit ' SQL: limit-field ' und ' SQL: limit-value ' &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-128">Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="e8ef2-129">Beschreibt die `sql:limit-field`-Anmerkung und die `sql:limit-value`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-129">Describes and provides examples of the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 [<span data-ttu-id="e8ef2-130">Identifizieren von Schlüssel Spalten mithilfe von SQL: key-fields &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-130">Identifying Key Columns Using sql:key-fields &#40;SQLXML 4.0&#41;</span></span>](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-131">Beschreibt die `sql:key-fields`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-131">Describes and provides examples of the `sql:key-fields` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-132">Angeben eines Ziel Namespace mit dem targetNamespace-Attribut &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-132">Specifying a Target Namespace Using the targetNamespace Attribute &#40;SQLXML 4.0&#41;</span></span>](specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-133">Beschreibt Beispiele für das **targetNamespace** -Attribut und stellt Beispiele bereit.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-133">Describes and provides examples of the **targetNamespace** attribute.</span></span>  
  
 [<span data-ttu-id="e8ef2-134">Erstellen gültiger Attribute vom Typ ID, IDREF und IDREFS mithilfe von SQL: Prefix &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-134">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix &#40;SQLXML 4.0&#41;</span></span>](creating-valid-id-idref-and-idrefs-type-attributes-using-sql-prefix-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-135">Beschreibt die `sql:prefix`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-135">Describes and provides examples of the `sql:prefix` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-136">Datentyp Umwandlungen und die SQL: datatype-Anmerkung &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-136">Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;</span></span>](data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-137">Beschreibt die `sql:datatype`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-137">Describes and provides examples of the `sql:datatype` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-138">Zuordnung von XSD-Datentypen zu XPath-Datentypen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-138">Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-139">Enthält eine Tabelle, in der die Datentypen XSD, XDR und Xpath verglichen werden, und listet die relevanten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Konvertierungen auf.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-139">Provides a table that compares XSD, XDR, and XPath datatypes and lists the relevant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conversions.</span></span>  
  
 [<span data-ttu-id="e8ef2-140">Erstellen von CDATA-Abschnitten mit SQL: use-cdata &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-140">Creating CDATA Sections Using sql:use-cdata &#40;SQLXML 4.0&#41;</span></span>](creating-cdata-sections-using-sql-use-cdata-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-141">Beschreibt die `sql:use-data`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-141">Describes and provides examples of the `sql:use-data` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-142">Anfordern von URL-verweisen auf BLOB-Daten mithilfe von SQL: encode &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-142">Requesting URL References to BLOB Data Using sql:encode &#40;SQLXML 4.0&#41;</span></span>](requesting-url-references-to-blob-data-using-sql-encode-sqlxml-4-0.md)  
 <span data-ttu-id="e8ef2-143">Beschreibt die `sql:encode`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-143">Describes and provides examples of the `sql:encode` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-144">Abrufen von nicht verbrauchten Daten mithilfe von ' SQL: overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-144">Retrieving Unconsumed Data Using the sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="e8ef2-145">Beschreibt die `sql:overflow-field`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-145">Describes and provides examples of the `sql:overflow-field` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-146">Ausblenden von Elementen und Attributen mit sql:hide</span><span class="sxs-lookup"><span data-stu-id="e8ef2-146">Hiding Elements and Attributes by Using sql:hide</span></span>](hiding-elements-and-attributes-by-using-sql-hide.md)  
 <span data-ttu-id="e8ef2-147">Beschreibt die `sql:hide`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-147">Describes and provides examples of the `sql:hide` annotation.</span></span>  
  
 [<span data-ttu-id="e8ef2-148">Verwenden der Anmerkungen 'sql:identity' und 'sql:guid'</span><span class="sxs-lookup"><span data-stu-id="e8ef2-148">Using the sql:identity and sql:guid Annotations</span></span>](using-the-sql-identity-and-sql-guid-annotations.md)  
 <span data-ttu-id="e8ef2-149">Beschreibt die `sql:identity`-Anmerkung und die `sql:guid`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-149">Describes and provides examples of the `sql:identity` and `sql:guid` annotations.</span></span>  
  
 [<span data-ttu-id="e8ef2-150">Angeben der Tiefe von rekursiven Beziehungen mit 'sql:max-depth'</span><span class="sxs-lookup"><span data-stu-id="e8ef2-150">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>](specifying-depth-in-recursive-relationships-by-using-sql-max-depth.md)  
 <span data-ttu-id="e8ef2-151">Beschreibt die `sql:max-depth`-Anmerkung und gibt Beispiele.</span><span class="sxs-lookup"><span data-stu-id="e8ef2-151">Describes and provides examples of the `sql:max-depth` annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ef2-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8ef2-152">See Also</span></span>  
 [<span data-ttu-id="e8ef2-153">Überlegungen zur Schema Sicherheit mit Anmerkungen &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e8ef2-153">Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md)  
  
  
