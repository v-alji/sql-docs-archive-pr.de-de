---
title: Einführung in XSD-Schemas mit Anmerkungen (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- mapping schema [SQLXML], about mapping schema
- views [SQLXML]
- valid XSD schemas [SQLXML]
- annotations [SQLXML]
- XSD schemas [SQLXML], creating XML views
- annotated XSD schemas, creating XML views
- minimum XSD schema
- annotated XSD schemas, examples
- XML views [SQLXML]
ms.assetid: 15282db1-65c4-43be-bdb7-e9ef49cb33a2
author: rothja
ms.author: jroth
ms.openlocfilehash: b91be71569daa9e5bf4143be9f652617ba7c5b01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619720"
---
# <a name="introduction-to-annotated-xsd-schemas-sqlxml-40"></a><span data-ttu-id="92a73-102">Einführung in XSD-Schemas mit Anmerkungen (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="92a73-102">Introduction to Annotated XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="92a73-103">Sie können mit der XML-Schemadefinitionssprache (XSD) XML-Sichten von relationalen Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="92a73-103">You can create XML views of relational data by using the XML Schema Definition (XSD) language.</span></span> <span data-ttu-id="92a73-104">Diese Sichten können dann mit XPath (XML Path)-Abfragen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="92a73-104">These views can then be queried by using XML Path language (XPath) queries.</span></span> <span data-ttu-id="92a73-105">Dieser Vorgang gleicht prinzipiell dem Erstellen von Sichten mit CREATE VIEW-Anweisungen und dem Definieren von SQL-Abfragen für diese Sichten.</span><span class="sxs-lookup"><span data-stu-id="92a73-105">This is similar to creating views by using CREATE VIEW statements and then specifying SQL queries against the view.</span></span>  
  
 <span data-ttu-id="92a73-106">Ein XML-Schema beschreibt die Struktur eines XML-Dokuments und beschreibt außerdem die verschiedenen Einschränkungen der Daten im Dokument.</span><span class="sxs-lookup"><span data-stu-id="92a73-106">An XML schema describes the structure of an XML document and also describes the various constraints on the data in the document.</span></span> <span data-ttu-id="92a73-107">Wenn XQuery-Abfragen mit dem XSD-Schema angegeben werden, wird die Struktur des resultierenden XML-Dokuments durch das Schema bestimmt, mit dem die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="92a73-107">When you specify XPath queries against the schema, the structure of the XML document returned is determined by the schema against which the XPath query is executed.</span></span>  
  
 <span data-ttu-id="92a73-108">In einem XSD-Schema **\<xsd:schema>** umschließt das-Element das gesamte Schema; alle Element Deklarationen müssen im- **\<xsd:schema>** Element enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="92a73-108">In an XSD schema, the **\<xsd:schema>** element encloses the entire schema; all element declarations must be contained within the **\<xsd:schema>** element.</span></span> <span data-ttu-id="92a73-109">Sie können Attribute beschreiben, die den Namespace definieren, in dem sich das Schema befindet, und die Namespaces, die im Schema als Eigenschaften des Elements verwendet werden **\<xsd:schema>** .</span><span class="sxs-lookup"><span data-stu-id="92a73-109">You can describe attributes that define the namespace in which the schema resides and the namespaces that are used in the schema as properties of the **\<xsd:schema>** element.</span></span>  
  
 <span data-ttu-id="92a73-110">Ein gültiges XSD-Schema muss das-Element enthalten, das **\<xsd:schema>** wie folgt definiert ist:</span><span class="sxs-lookup"><span data-stu-id="92a73-110">A valid XSD schema must contain the **\<xsd:schema>** element defined as follows:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<!-- additional schema definitions here -->  
</xsd:schema>  
```  
  
 <span data-ttu-id="92a73-111">Das- **\<xsd:schema>** Element wird von der XML-Schema-Namespace Spezifikation unter abgeleitet http://www.w3.org/2001/XMLSchema .</span><span class="sxs-lookup"><span data-stu-id="92a73-111">The **\<xsd:schema>** element is derived from the XML Schema namespace specification at http://www.w3.org/2001/XMLSchema.</span></span>  
  
## <a name="annotations-to-the-xsd-schema"></a><span data-ttu-id="92a73-112">Anmerkungen zum XSD-Schema</span><span class="sxs-lookup"><span data-stu-id="92a73-112">Annotations to the XSD Schema</span></span>  
 <span data-ttu-id="92a73-113">Sie können ein XSD-Schema mit Anmerkungen angeben, welche die Zuordnung zu einer Datenbank beschreiben, die Datenbank abfragen und die Ergebnisse in Form eines XML-Dokuments zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="92a73-113">You can use an XSD schema with annotations that describe the mapping to a database, query the database, and return the results in the form of an XML document.</span></span> <span data-ttu-id="92a73-114">Anmerkungen werden bereitgestellt, um ein XSD-Schema Datenbanktabellen und -spalten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="92a73-114">Annotations are provided to map an XSD schema to database tables and columns.</span></span> <span data-ttu-id="92a73-115">XPath-Abfragen können für die XML-Sicht, die durch das XSD-Schema erstellt wird, angegeben werden, um die Datenbank abzufragen und die Ergebnisse als XML-Dokument zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="92a73-115">XPath queries can be specified against the XML view created by the XSD schema to query the database and obtain results as an XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92a73-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 unterstützt die XSD-Schemasprache die Anmerkungen, die in der XDR-Schemasprache (XML-Data Reduced) mit Anmerkungen in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] eingeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="92a73-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports the annotations introduced with annotated XML-Data Reduced (XDR) schema language in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="92a73-117">XDR-Anmerkungen sind in SQLXML 4.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="92a73-117">Annotated XDR is deprecated in SQLXML 4.0.</span></span>  
  
 <span data-ttu-id="92a73-118">Im Kontext relationaler Datenbanken ist es nützlich, das beliebige XSD-Schema einem relationalen Datenspeicher zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="92a73-118">In the context of the relational database, it is useful to map the arbitrary XSD schema to a relational store.</span></span> <span data-ttu-id="92a73-119">Dies lässt sich beispielsweise erreichen, indem das XSD-Schema mit Anmerkungen versehen wird.</span><span class="sxs-lookup"><span data-stu-id="92a73-119">One way to achieve this is to annotate the XSD schema.</span></span> <span data-ttu-id="92a73-120">Ein XSD-Schema mit Anmerkungen wird als Zuordnungsschema *mapping schema*bezeichnet, das Informationen dazu bereitstellt, wie XML-Daten dem relationalen Speicher zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="92a73-120">An XSD schema with the annotations is referred to as a *mapping schema*, which provides information pertaining to how XML data is to be mapped to the relational store.</span></span> <span data-ttu-id="92a73-121">Ein Zuordnungsschema ist im Grunde eine XML-Sicht der relationalen Daten.</span><span class="sxs-lookup"><span data-stu-id="92a73-121">A mapping schema is, in effect, an XML view of the relational data.</span></span> <span data-ttu-id="92a73-122">Diese Zuordnungen können verwendet werden, um relationale Daten als XML-Dokument abzurufen.</span><span class="sxs-lookup"><span data-stu-id="92a73-122">These mappings can be used to retrieve relational data as an XML document.</span></span>  
  
## <a name="namespace-for-annotations"></a><span data-ttu-id="92a73-123">Namespace für Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="92a73-123">Namespace for Annotations</span></span>  
 <span data-ttu-id="92a73-124">In einem XSD-Schema werden Anmerkungen mithilfe des Namespace **urn: Schemas-Microsoft-com: Mapping-Schema**angegeben.</span><span class="sxs-lookup"><span data-stu-id="92a73-124">In an XSD schema, annotations are specified by using the namespace **urn:schemas-microsoft-com:mapping-schema**.</span></span> <span data-ttu-id="92a73-125">Wie im folgenden Beispiel gezeigt, ist die einfachste Möglichkeit, den Namespace anzugeben, im- **\<xsd:schema>** Tag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="92a73-125">As shown in the following example, the easiest way to specify the namespace is to specify it in the **\<xsd:schema>** tag.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
...  
</xsd:schema>  
```  
  
 <span data-ttu-id="92a73-126">Es kann ein beliebiges Namespacepräfix verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92a73-126">The namespace prefix that is used is arbitrary.</span></span> <span data-ttu-id="92a73-127">In dieser Dokumentation wird das **SQL** -Präfix verwendet, um den Namespace der Anmerkung anzugeben und Anmerkungen in diesem Namespace von denjenigen in anderen Namespaces zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="92a73-127">In this documentation, the **sql** prefix is used to denote the annotation namespace and to distinguish annotations in this namespace from those in other namespaces.</span></span>  
  
## <a name="example-of-an-annotated-xsd-schema"></a><span data-ttu-id="92a73-128">Beispiel eines XSD-Schemas mit Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="92a73-128">Example of an Annotated XSD Schema</span></span>  
 <span data-ttu-id="92a73-129">Im folgenden Beispiel besteht das XSD-Schema aus einem- **\<Person.Contact>** Element.</span><span class="sxs-lookup"><span data-stu-id="92a73-129">In the following example, the XSD schema consists of an **\<Person.Contact>** element.</span></span> <span data-ttu-id="92a73-130">Das- **\<Employee>** Element verfügt über ein **ContactID** -Attribut und untergeordnete **\<FirstName>** - **\<LastName>** Elemente:</span><span class="sxs-lookup"><span data-stu-id="92a73-130">The **\<Employee>** element has a **ContactID** attribute and **\<FirstName>** and **\<LastName>** child elements:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <xsd:element name="Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     type="xsd:string" />   
        <xsd:element name="LName"  
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="92a73-131">Diesem XSD-Schema werden Anmerkungen hinzugefügt, um die darin enthaltenen Elemente und Attribute den entsprechenden Datenbanktabellen und –spalten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="92a73-131">Annotations are added to this XSD schema to map its elements and attributes to the database tables and columns:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID"   
                       sql:field="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="92a73-132">Im Zuordnungs Schema wird das- **\<Contact>** Element mithilfe der-Anmerkung der Person. Contact-Tabelle in der AdventureWorks-Beispieldatenbank zugeordnet `sql:relation` .</span><span class="sxs-lookup"><span data-stu-id="92a73-132">In the mapping schema, the **\<Contact>** element is mapped to the Person.Contact table in the sample AdventureWorks database by using the `sql:relation` annotation.</span></span> <span data-ttu-id="92a73-133">Die Attribute ConID, FName und LName werden mithilfe der `sql:field`-Anmerkungen den Spalten ContactID, FirstName und LastName in der Person.Contact-Tabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="92a73-133">The attributes ConID, FName, and LName are mapped to the ContactID, FirstName, and LastName columns in the Person.Contact table by using the `sql:field` annotations.</span></span>  
  
 <span data-ttu-id="92a73-134">Dieses XSD-Schema mit Anmerkungen stellt die XML-Sicht der relationalen Daten bereit.</span><span class="sxs-lookup"><span data-stu-id="92a73-134">This annotated XSD schema provides the XML view of the relational data.</span></span> <span data-ttu-id="92a73-135">Diese XML-Sicht kann mit der XPath-Sprache abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="92a73-135">This XML view can be queried using the XPath language.</span></span> <span data-ttu-id="92a73-136">Xpath-Abfragen geben als Ergebnis ein XML-Dokument zurück statt eines Rowsets, das von SQL-Abfragen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="92a73-136">An XPath query returns an XML document as a result, instead of the rowset that is returned by SQL queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="92a73-137">Ob im Zuordnungsschema bei relationalen Werten, z. B. Tabellenname und Spaltenname, zwischen Groß-und Kleinschreibung unterschieden wird, hängt davon ab, ob in den Sortiereinstellungen auf dem SQL Server die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="92a73-137">In the mapping schema, case-sensitivity for the specified relational values (such as table name and column name) depends upon if SQL Server is using case-sensitive collation settings.</span></span> <span data-ttu-id="92a73-138">Weitere Informationen finden Sie unter [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="92a73-138">For more information, see [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="92a73-139">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="92a73-139">Other Resources</span></span>  
 <span data-ttu-id="92a73-140">Weitere Informationen zu XSD (XML Schema Definition Language), XPath (XML Path Language) und XSLT (Extensible Stylesheet Language Transformations) finden Sie auf den folgenden Websites:</span><span class="sxs-lookup"><span data-stu-id="92a73-140">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="92a73-141">XML Schema Part 0: Primer, W3C-Empfehlung (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="92a73-141">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="92a73-142">XML-Schema Teil 1: Strukturen, W3C-Empfehlung (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="92a73-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="92a73-143">XML Schema Part 2: Datatypes, W3C-Empfehlung (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="92a73-143">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="92a73-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="92a73-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="92a73-145">XSL-Transformationen (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="92a73-145">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92a73-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92a73-146">See Also</span></span>  
 <span data-ttu-id="92a73-147">[Überlegungen zur Schema Sicherheit mit Anmerkungen &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="92a73-147">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="92a73-148">XDR-Schemas mit Anmerkungen &#40;in SQLXML 4,0 als veraltet markiert&#41;</span><span class="sxs-lookup"><span data-stu-id="92a73-148">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
  
  
