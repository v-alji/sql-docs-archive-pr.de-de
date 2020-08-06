---
title: Verweisen auf die integrierte XML-Schemaauflistung (sys) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- sys XML schema collections [SQL Server]
- schema collections [SQL Server], predefined
- predefined XML schema collections [SQL Server]
- XML schema collections [SQL Server], predefined
- built-in XML schema collections [SQL Server]
ms.assetid: 1e118303-5df0-4ee4-bd8d-14ced7544144
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fa30107e1746b33e3f9b8eb1cfa53d1f4d25fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697602"
---
# <a name="reference-the-built-in-xml-schema-collection-sys"></a><span data-ttu-id="fb174-102">Verweisen auf die integrierte XML-Schemaauflistung (sys)</span><span class="sxs-lookup"><span data-stu-id="fb174-102">Reference the Built-in XML Schema Collection (sys)</span></span>
  <span data-ttu-id="fb174-103">Jede Datenbank, die Sie erstellen, besitzt eine vordefinierte **sys** -XML-Schemaauflistung im relationalen **sys** -Schema.</span><span class="sxs-lookup"><span data-stu-id="fb174-103">Every database you create has a predefined **sys** XML schema collection in the **sys** relational schema.</span></span> <span data-ttu-id="fb174-104">Es reserviert diese vordefinierten Schemas, und der Zugriff darauf kann aus einer beliebigen, von einem Benutzer erstellten XML-Schemaauflistung erfolgen.</span><span class="sxs-lookup"><span data-stu-id="fb174-104">It reserves these predefined schemas, and they can be accessed from any other user-created XML schema collection.</span></span> <span data-ttu-id="fb174-105">Die in diesen vordefinierten Schemas verwendeten Präfixe sind in XQuery von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="fb174-105">The prefixes used in these predefined schemas are meaningful in XQuery.</span></span> <span data-ttu-id="fb174-106">Nur **xml** ist ein reserviertes Präfix.</span><span class="sxs-lookup"><span data-stu-id="fb174-106">Only **xml** is a reserved prefix.</span></span>  
  
```  
xml = http://www.w3.org/XML/1998/namespace  
xs = http://www.w3.org/2001/XMLSchema  
xsi = http://www.w3.org/2001/XMLSchema-instance  
fn = http://www.w3.org/2004/07/xpath-functions  
sqltypes = https://schemas.microsoft.com/sqlserver/2004/sqltypes  
xdt = http://www.w3.org/2004/07/xpath-datatypes  
(no prefix) = urn:schemas-microsoft-com:xml-sql  
(no prefix) = https://schemas.microsoft.com/sqlserver/2004/SOAP  
```  
  
 <span data-ttu-id="fb174-107">Beachten Sie, dass der **sqltypes** -Namespace Komponenten enthält, auf die aus jeder beliebigen, von einem Benutzer erstellten XML-Schemaauflistung verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb174-107">Note that the **sqltypes** namespace contains components that can be referenced from any user-created XML schema collection.</span></span> <span data-ttu-id="fb174-108">Sie können das **sqltypes** -Schema von dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?linkid=31850)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="fb174-108">You can download the **sqltypes** schema from this [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=31850).</span></span> <span data-ttu-id="fb174-109">Die folgenden Komponenten sind z. B. integriert:</span><span class="sxs-lookup"><span data-stu-id="fb174-109">The built-in components include the following:</span></span>  
  
-   <span data-ttu-id="fb174-110">XSD-Typen</span><span class="sxs-lookup"><span data-stu-id="fb174-110">XSD types</span></span>  
  
-   <span data-ttu-id="fb174-111">Die XML-Attribute **lang**, **base**und **space**</span><span class="sxs-lookup"><span data-stu-id="fb174-111">XML attributes **lang**, **base**, and **space**</span></span>  
  
-   <span data-ttu-id="fb174-112">Komponenten des **sqltypes** -Namespace</span><span class="sxs-lookup"><span data-stu-id="fb174-112">Components of the **sqltypes** namespace</span></span>  
  
 <span data-ttu-id="fb174-113">Die folgende Abfrage gibt integrierte Komponenten zurück, auf die aus einer von einem Benutzer erstellten XML-Schemaauflistung verwiesen werden kann:</span><span class="sxs-lookup"><span data-stu-id="fb174-113">The following query returns built-in components that can be referenced from a user-created XML schema collection:</span></span>  
  
```  
SELECT C.name, N.name, C.symbol_space_desc from sys.xml_schema_components C join sys.xml_schema_namespaces N  
on ((C.xml_namespace_id = N.xml_namespace_id) AND (C.xml_collection_id = N.xml_collection_id))  
join sys.xml_schema_collections SC  
on SC.xml_collection_id = C.xml_collection_id  
where ((C.xml_collection_id = 1) AND (C.name is not null) AND (C.scoping_xml_component_id is null)   
AND (SC.schema_id = 4))  
GO  
```  
  
 <span data-ttu-id="fb174-114">Im folgenden Beispiel wird veranschaulicht, wie auf diese Komponenten in einem Benutzerschema verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fb174-114">The following example shows how these components are referenced in a user schema.</span></span> <span data-ttu-id="fb174-115">`CREATE XML SCHEMA COLLECTION` erstellt eine XML-Schemasammlung, die auf den im `varchar` -Namespace definierten `sqltypes` -Typ verweist.</span><span class="sxs-lookup"><span data-stu-id="fb174-115">`CREATE XML SCHEMA COLLECTION` creates an XML schema collection that references the `varchar` type defined in the `sqltypes` namespace.</span></span> <span data-ttu-id="fb174-116">Das Beispiel verweist außerdem auf das `lang` -Attribut, das im `xml` -Namespace definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb174-116">The example also references the `lang` attribute that is defined in the `xml` namespace.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema   
   xmlns="http://www.w3.org/2001/XMLSchema"   
   targetNamespace="myNS"  
   xmlns:ns="myNS"  
   xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
   <import namespace="http://www.w3.org/XML/1998/namespace"/>  
   <import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
   <element name="root">  
      <complexType>  
          <sequence>  
             <element name="a" type="string"/>  
             <element name="b" type="string"/>  
             <!-- varchar type is defined in the sys.sys collection and   
                  can be referenced in any user-defined schema -->  
             <element name="c" type="s:varchar"/>  
          </sequence>  
          <attribute name="att" type="int"/>  
          <!-- xml:lang attribute is defined in the sys.sys collection   
               and can be referenced in any user-defined schema -->  
          <attribute ref="xml:lang"/>  
      </complexType>  
    </element>  
 </schema>'  
GO  
 -- Cleanup  
DROP xml schema collection SC   
GO  
```  
  
 <span data-ttu-id="fb174-117">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fb174-117">You should note the following:</span></span>  
  
-   <span data-ttu-id="fb174-118">Sie können keine XML-Schemas mit diesen Namespaces in benutzerdefinierten XML-Schemaauflistungen ändern.</span><span class="sxs-lookup"><span data-stu-id="fb174-118">You cannot modify XML schemas with these namespaces in any user-defined XML schema collection.</span></span> <span data-ttu-id="fb174-119">Die folgende XML-Schemaauflistung verursacht einen Fehler, weil dem geschützten Namespace `sqltypes` eine Komponente hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="fb174-119">For example, the following XML schema collection fails, because it is adding a component to the `sqltypes` protected namespace:</span></span>  
  
    ```  
    CREATE XML SCHEMA COLLECTION SC AS '  
    <schema xmlns="http://www.w3.org/2001/XMLSchema"   
    targetNamespace    
        ="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
          <element name="root" type="string"/>  
    </schema>'  
    GO  
    ```  
  
-   <span data-ttu-id="fb174-120">Sie können die XML-Schemaauflistung `sys` nicht zum Typisieren von Spalten, Variablen oder Parametern von `xml` verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb174-120">You cannot use the `sys` XML schema collection to type `xml` columns, variables, or parameters.</span></span> <span data-ttu-id="fb174-121">So gibt z. B. der folgende Code einen Fehler zurück:</span><span class="sxs-lookup"><span data-stu-id="fb174-121">For example, the following code returns an error:</span></span>  
  
    ```  
    DECLARE @x xml (sys.sys)  
    ```  
  
-   <span data-ttu-id="fb174-122">Die Serialisierung dieser integrierten Schemas wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb174-122">Serialization of these built-in schemas is not supported.</span></span> <span data-ttu-id="fb174-123">So gibt z. B. der folgende Code einen Fehler zurück:</span><span class="sxs-lookup"><span data-stu-id="fb174-123">For example, the following code returns an error:</span></span>  
  
    ```  
    SELECT XML_SCHEMA_NAMESPACE(N'sys',N'sys')  
    GO  
    ```  
  
 <span data-ttu-id="fb174-124">Auch mit dem Code im folgenden Beispiel wird eine XML-Schemaauflistung erstellt, die den `varchar`-Datentyp verwendet, der im `sqltypes`-Namespace definiert wurde:</span><span class="sxs-lookup"><span data-stu-id="fb174-124">The following code is another example in which you create an XML schema collection that uses the `varchar` type defined in the `sqltypes` namespace:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="myNS" xmlns:ns="myNS"  
        xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes">  
   <import     
     namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
      <simpleType name="myType">  
            <restriction base="s:varchar">  
                  <maxLength value="20"/>  
            </restriction>  
      </simpleType>  
      <element name="root" type="ns:myType"/>  
</schema>'  
go  
```  
  
 <span data-ttu-id="fb174-125">Wie das folgende Beispiel zeigt, können Sie eine typisierte `XML`-Variable erstellen, dieser eine XML-Instanz zuweisen und dann überprüfen, ob der Wert des <`root`>-Elementtyps vom Typ `varchar` ist.</span><span class="sxs-lookup"><span data-stu-id="fb174-125">As shown in the following, you can create a typed `XML` variable, assign an XML instance to it, and verify that the value of the <`root`> element type is a `varchar` type.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xmlns="myNS">My data</root>'  
SELECT @var.query('declare namespace sqltypes = "https://schemas.microsoft.com/sqlserver/2004/sqltypes";  
declare namespace ns="myNS";   
data(/ns:root[1]) instance of sqltypes:varchar?')  
GO  
```  
  
 <span data-ttu-id="fb174-126">Der Ausdruck `instance of sqltypes:varchar?`gibt TRUE zurück, weil der Wert des Elements <`root`> einem Typ entspricht, der gemäß dem Schema, das der `@var`-Variablen zugeordnet ist, von **varchar** abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="fb174-126">The `instance of sqltypes:varchar?` expression returns TRUE, because the <`root`> element value is of a type derived from **varchar** according to the schema that is associated with the `@var` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb174-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb174-127">See Also</span></span>  
 [<span data-ttu-id="fb174-128">XML-Schemaauflistungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fb174-128">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
