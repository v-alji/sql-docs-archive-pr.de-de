---
title: Erteilen von Berechtigungen für eine XML-Schemaauflistung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- granting permissions [SQL Server], XML schema collections
- ALTER permission
ms.assetid: ffbb829c-3b8f-4e5d-97d9-ab4059aab0db
author: rothja
ms.author: jroth
ms.openlocfilehash: 2dc6384acb2f079245c80923e683ebe2c03d2562
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696522"
---
# <a name="grant-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="6c983-102">Erteilen von Berechtigungen für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-102">Grant Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="6c983-103">Sie können Berechtigungen zum Erstellen von XML-Schemaauflistungen sowie Berechtigungen für ein XML-Schemaauflistungsobjekt erteilen.</span><span class="sxs-lookup"><span data-stu-id="6c983-103">You can grant permissions to create an XML schema collection and also grant permissions on an XML schema collection object.</span></span>  
  
## <a name="granting-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="6c983-104">Berechtigung zum Erstellen einer XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-104">Granting Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="6c983-105">Zum Erstellen einer XML-Schemaauflistung sind die folgenden Berechtigungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6c983-105">To create an XML schema collection, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="6c983-106">Der Prinzipal benötigt die CREATE XML SCHEMA COLLECTION-Berechtigung auf Datenbankebene.</span><span class="sxs-lookup"><span data-stu-id="6c983-106">The principal requires CREATE XML SCHEMA COLLECTION permission at the database-level.</span></span>  
  
-   <span data-ttu-id="6c983-107">Da die XML-Schemaauflistungen relationale Schemas als Bereiche besitzen, muss der Prinzipal außerdem die ALTER-Berechtigung für das relationale Schema besitzen.</span><span class="sxs-lookup"><span data-stu-id="6c983-107">Because the XML schema collections are relational schema-scoped, the principal must also have ALTER permission on the relational schema.</span></span>  
  
 <span data-ttu-id="6c983-108">Mithilfe der folgenden Berechtigungen kann ein Prinzipal eine XML-Schemaauflistung in einem relationalen Schema in einer Datenbank auf einem Server erstellen:</span><span class="sxs-lookup"><span data-stu-id="6c983-108">The following permissions let a principal create an XML schema collection in a relational schema in a database on a server:</span></span>  
  
-   <span data-ttu-id="6c983-109">CONTROL-Berechtigung auf dem Server</span><span class="sxs-lookup"><span data-stu-id="6c983-109">CONTROL permission on the server</span></span>  
  
-   <span data-ttu-id="6c983-110">ALTER ANY DATABASE-Berechtigung auf dem Server</span><span class="sxs-lookup"><span data-stu-id="6c983-110">ALTER ANY DATABASE permission on the server</span></span>  
  
-   <span data-ttu-id="6c983-111">ALTER-Berechtigung für die Datenbank</span><span class="sxs-lookup"><span data-stu-id="6c983-111">ALTER permission on the database</span></span>  
  
-   <span data-ttu-id="6c983-112">CONTROL-Berechtigung in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="6c983-112">CONTROL permission in the database</span></span>  
  
-   <span data-ttu-id="6c983-113">ALTER ANY SCHEMA-Berechtigung und CREATE XML SCHEMA COLLECTION-Berechtigung in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="6c983-113">ALTER ANY SCHEMA permission and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
-   <span data-ttu-id="6c983-114">ALTER- oder CONTROL-Berechtigung für das relationale Schema und CREATE XML SCHEMA COLLECTION-Berechtigung in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="6c983-114">ALTER or CONTROL permission on the relational schema and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
 <span data-ttu-id="6c983-115">Die letztgenannten Berechtigungen werden im folgenden Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="6c983-115">This last method of permissions is used in the following example.</span></span>  
  
 <span data-ttu-id="6c983-116">Der Besitzer des relationalen Schemas wird zum Besitzer der XML-Schemaauflistung, die in diesem Schema erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6c983-116">The owner of the relational schema becomes the owner of the XML schema collection created in that schema.</span></span> <span data-ttu-id="6c983-117">Dieser Besitzer besitzt die vollständige Kontrolle über die XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="6c983-117">This owner then has full control over the XML schema collection.</span></span> <span data-ttu-id="6c983-118">Aus diesem Grund kann dieser Besitzer die XML-Schemaauflistung ändern, eine xml-Spalte typisieren oder die XML-Schemaauflistung löschen.</span><span class="sxs-lookup"><span data-stu-id="6c983-118">Therefore, this owner can modify the XML schema collection, type an xml column, or drop the XML schema collection.</span></span>  
  
## <a name="granting-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="6c983-119">Erteilen von Berechtigungen für ein XML-Schemaauflistungsobjekt</span><span class="sxs-lookup"><span data-stu-id="6c983-119">Granting Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="6c983-120">Die folgenden Berechtigungen sind für die XML-Schemaauflistung zulässig:</span><span class="sxs-lookup"><span data-stu-id="6c983-120">The following permissions are allowed on the XML schema collection:</span></span>  
  
-   <span data-ttu-id="6c983-121">Die ALTER-Berechtigung ist erforderlich, wenn der Inhalt einer vorhandenen XML-Schemaauflistung mithilfe der ALTER XML SCHEMA COLLECTION-Anweisung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6c983-121">The ALTER permission is required when modifying contents of an existing XML schema collection by using the ALTER XML SCHEMA COLLECTION statement.</span></span>  
  
-   <span data-ttu-id="6c983-122">Mit der CONTROL-Berechtigung kann ein Benutzer beliebige Vorgänge mit der XML-Schemaauflistung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6c983-122">The CONTROL permission lets a user perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="6c983-123">Die TAKE OWNERSHIP-Berechtigung ist zum Übertragen des Besitzes der XML-Schemaauflistung von einem Prinzipal an einen anderen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6c983-123">The TAKE OWNERSHIP permission is required to transfer ownership of the XML schema collection from one principal to another.</span></span>  
  
-   <span data-ttu-id="6c983-124">Mit der REFERENCES-Berechtigung wird der Prinzipal dazu autorisiert, mithilfe der XML-Schemaauflistung Spalten des `xml`-Typs in Tabellen und Sichten sowie Parametern zu typisieren oder einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="6c983-124">The REFERENCES permission authorizes the principal to use the XML schema collection to type or constrain `xml` type columns, in tables and views and parameters.</span></span> <span data-ttu-id="6c983-125">Die REFERENCES-Berechtigung ist auch erforderlich, wenn eine XML-Schemaauflistung auf eine andere verweist.</span><span class="sxs-lookup"><span data-stu-id="6c983-125">The REFERENCES permission is also required when one XML schema collection refers to another.</span></span>  
  
-   <span data-ttu-id="6c983-126">Die VIEW DEFINITION-Berechtigung ermöglicht dem Prinzipal das Abfragen des Inhalts einer XML-Schemaauflistung mithilfe von XML_SCHEMA_NAMESPACE oder Katalogsichten, wenn dieser Prinzipal auch eine der ALTER-, REFERENCES- oder CONTROL-Berechtigungen für die Auflistung besitzt.</span><span class="sxs-lookup"><span data-stu-id="6c983-126">The VIEW DEFINITION permission allows the principal to query the contents of an XML schema collection either through XML_SCHEMA_NAMESPACE or through the catalog views, provided this principal also has one of the ALTER, REFERENCES, or CONTROL permissions on the collection.</span></span>  
  
-   <span data-ttu-id="6c983-127">Die EXECUTE-Berechtigung ist zum Überprüfen von Werten erforderlich, die vom Prinzipal für die XML-Schemaauflistung eingefügt oder aktualisiert werden, durch die Spalten, Variablen und Parameter vom Typ `xml` typisiert oder einschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="6c983-127">The EXECUTE permission is required to validate values inserted or updated by the principal against the XML schema collection that is typing or constraining the `xml` type columns, variables, and parameters.</span></span> <span data-ttu-id="6c983-128">Sie benötigen diese Berechtigung auch, wenn Sie das in diesen Spalten und Variablen gespeicherte XML abfragen.</span><span class="sxs-lookup"><span data-stu-id="6c983-128">You also need this permission when you are querying the XML stored in these columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6c983-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6c983-129">Examples</span></span>  
 <span data-ttu-id="6c983-130">Die Szenarien in den folgenden Beispielen veranschaulichen, wie XML-Schemaberechtigungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6c983-130">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="6c983-131">Jedes dieser Beispiele erstellt die erforderliche Testdatenbank, die relationalen Schemas und Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="6c983-131">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="6c983-132">Diesen Anmeldenamen werden die erforderlichen Berechtigungen für XML-Schemaauflistungen erteilt.</span><span class="sxs-lookup"><span data-stu-id="6c983-132">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="6c983-133">Jedes der Beispiele führt am Ende den erforderlichen Cleanup aus.</span><span class="sxs-lookup"><span data-stu-id="6c983-133">Each example does the necessary clean up at the end.</span></span>  
  
### <a name="a-granting-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="6c983-134">A.</span><span class="sxs-lookup"><span data-stu-id="6c983-134">A.</span></span> <span data-ttu-id="6c983-135">Erteilen der Berechtigungen zum Erstellen einer XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-135">Granting permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="6c983-136">Im folgenden Beispiel wird gezeigt, wie Berechtigungen erteilt werden, damit ein Prinzipal eine XML-Schemaauflistung erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="6c983-136">The following example shows how to grant permissions so that a principal can create an XML schema collection.</span></span> <span data-ttu-id="6c983-137">Dieses Beispiel erstellt eine Beispieldatenbank und den Testbenutzer `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="6c983-137">The example creates a sample database and a test user, `TestLogin1`.</span></span> <span data-ttu-id="6c983-138">`TestLogin1` wird anschließend die `ALTER` -Berechtigung für das relationale Schema und die `CREATE XML SCHEMA COLLECTION` -Berechtigung für die Datenbank erteilt.</span><span class="sxs-lookup"><span data-stu-id="6c983-138">`TestLogin1` is then given `ALTER` permission on the relational schema and given `CREATE XML SCHEMA COLLECTION` permission on the database.</span></span> <span data-ttu-id="6c983-139">Mit diesen Berechtigungen kann `TestLogin1` erfolgreich eine XML-Beispielschemaauflistung erstellen.</span><span class="sxs-lookup"><span data-stu-id="6c983-139">With these permissions, `TestLogin1` succeeds in creating a sample XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Execute CREATE XML SCHEMA COLLECTION.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="root" type="xsd:byte"/>  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-granting-permission-to-use-an-existing-xml-schema-collection"></a><span data-ttu-id="6c983-140">B.</span><span class="sxs-lookup"><span data-stu-id="6c983-140">B.</span></span> <span data-ttu-id="6c983-141">Erteilen der Berechtigungen zum Verwenden einer vorhandenen XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-141">Granting permission to use an existing XML schema collection</span></span>  
 <span data-ttu-id="6c983-142">Das folgende Beispiel veranschaulicht das Berechtigungsmodell für die XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="6c983-142">The following example further shows the permission model for the XML schema collection.</span></span> <span data-ttu-id="6c983-143">Es veranschaulicht die verschiedenen Berechtigungen, die zum Erstellen und Verwenden der XML-Schemaauflistung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6c983-143">The example shows how different permissions are required to create and use the XML schema collection.</span></span>  
  
 <span data-ttu-id="6c983-144">Das Beispiel erstellt eine Testdatenbank und den Anmeldenamen `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="6c983-144">The example creates a test database and a login, `TestLogin1`.</span></span> <span data-ttu-id="6c983-145">`TestLogin1` erstellt eine XML-Schemaauflistung in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6c983-145">`TestLogin1` creates an XML schema collection in the database.</span></span> <span data-ttu-id="6c983-146">Der Anmeldename erstellt anschließend eine Tabelle und verwendet die XML-Schemaauflistung zum Erstellen einer typisierten xml-Spalte.</span><span class="sxs-lookup"><span data-stu-id="6c983-146">The login then creates a table and uses the XML schema collection to create a typed xml column.</span></span> <span data-ttu-id="6c983-147">Der Benutzer fügt anschließend Daten ein und fragt diese ab.</span><span class="sxs-lookup"><span data-stu-id="6c983-147">The user then inserts data and queries it.</span></span> <span data-ttu-id="6c983-148">Für diese verschiedenen Schritte sind die jeweiligen Schemaberechtigungen wie im Code gezeigt erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6c983-148">All these steps require the necessary schema permissions, as shown in the code.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Create a table by using the collection to type an XML column.   
--TestLogin1 must have permission to create a table.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also must have REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- Now user can create a table and use the XML schema collection to create   
-- a typed XML column.  
SETUSER 'TestLogin1'  
GO  
CREATE TABLE MyTestTable (xmlCol xml (dbo.myTestSchemaCollection))  
GO  
-- To insert data in the table, the user needs EXECUTE permission on the XML schema collection.  
-- GRANT EXECUTE permission to TestLogin2 on the xml schema collection.  
SETUSER  
GO  
GRANT EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- TestLogin1 does not own the dbo schema. This user must have INSERT permission.  
GRANT INSERT TO TestLogin1  
GO  
-- Now the user can insert data into the table.  
SETUSER 'TestLogin1'  
GO  
INSERT INTO MyTestTable VALUES('  
<telephone xmlns="http://schemas.adventure-works.com/Additional/ContactInfo">111-1111</telephone>  
')  
GO  
-- To query the table, TestLogin1 must have permissions: SELECT on the table and EXECUTE on the XML schema collection.  
SETUSER  
GO  
GRANT SELECT TO TestLogin1  
GO  
-- TestLogin1 already has EXECUTE permission on the schema (granted before inserting a record in the table).  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- To show that the user must have EXECUTE permission to query, revoke the  
-- previously granted permission and return the query.  
SETUSER  
GO  
REVOKE EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection to TestLogin1  
Go  
-- Now TestLogin1 cannot execute the query.  
SETUSER 'TestLogin1'  
GO  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="c-granting-alter-permission-on-an-xml-schema-collection"></a><span data-ttu-id="6c983-149">C.</span><span class="sxs-lookup"><span data-stu-id="6c983-149">C.</span></span> <span data-ttu-id="6c983-150">Erteilen der ALTER-Berechtigung für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-150">Granting ALTER permission on an XML schema collection</span></span>  
 <span data-ttu-id="6c983-151">Ein Benutzer benötigt die ALTER-Berechtigung, um eine vorhandene XML-Schemaauflistung in der Datenbank ändern zu können.</span><span class="sxs-lookup"><span data-stu-id="6c983-151">A user must have ALTER permission to modify an existing XML schema collection in the database.</span></span> <span data-ttu-id="6c983-152">Im folgenden Beispiel wird veranschaulicht, wie die `ALTER` -Berechtigung erteilt wird.</span><span class="sxs-lookup"><span data-stu-id="6c983-152">The following example shows how to grant `ALTER` permission.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant ALTER permission to TestLogin1.  
setuser  
GO  
GRANT ALTER ON XML SCHEMA COLLECTION::myTestSchemaCollection TO TestLogin1  
GO  
-- TestLogin1 should be able to add components to the collection.  
SETUSER 'TestLogin1'  
GO  
ALTER XML SCHEMA COLLECTION myTestSchemaCollection ADD '  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns="http://schemas.adventure-works.com/Additional/ContactInfo"   
elementFormDefault="qualified">  
 <xsd:element name="pager" type="xsd:string"/>  
</xsd:schema>  
'  
Go  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="d-granting-take-ownership-permission-on-an-xml-schema-collection"></a><span data-ttu-id="6c983-153">D:</span><span class="sxs-lookup"><span data-stu-id="6c983-153">D.</span></span> <span data-ttu-id="6c983-154">Erteilen der TAKE OWNERSHIP-Berechtigung für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-154">Granting TAKE OWNERSHIP permission on an XML schema collection</span></span>  
 <span data-ttu-id="6c983-155">Im folgenden Beispiel wird veranschaulicht, wie der Besitz des XML-Schemas von einem Benutzer an einen anderen übertragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6c983-155">The following example shows how to transfer XML schema ownership from one user to another.</span></span> <span data-ttu-id="6c983-156">Damit das Beispiel interessanter wird, arbeiten die Benutzer in diesem Beispiel in verschiedenen relationalen Standardschemas.</span><span class="sxs-lookup"><span data-stu-id="6c983-156">To make the example more interesting, the users in this example work in different default relational schemas.</span></span>  
  
 <span data-ttu-id="6c983-157">In diesem Beispiel werden die folgenden Aufgaben ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="6c983-157">This example does the following:</span></span>  
  
-   <span data-ttu-id="6c983-158">Erstellen einer Datenbank mit zwei relationalen Schemas, `dbo` und `myOtherDBSchema`.</span><span class="sxs-lookup"><span data-stu-id="6c983-158">Creates a database with two relational schemas, `dbo` and `myOtherDBSchema`).</span></span>  
  
-   <span data-ttu-id="6c983-159">Erstellen von zwei Benutzern, `TestLogin1` und `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="6c983-159">Creates two users, `TestLogin1` and `TestLogin2`.</span></span> <span data-ttu-id="6c983-160">`TestLogin2` wird Besitzer des relationalen `myOtherDBSchema` -Schemas.</span><span class="sxs-lookup"><span data-stu-id="6c983-160">`TestLogin2` is made the owner of the `myOtherDBSchema` relational schema.</span></span>  
  
-   <span data-ttu-id="6c983-161">`TestLogin1` erstellt eine XML-Schemaauflistung im relationalen `dbo` -Schema.</span><span class="sxs-lookup"><span data-stu-id="6c983-161">`TestLogin1` creates an XML schema collection in the `dbo` relational schema.</span></span>  
  
-   <span data-ttu-id="6c983-162">`TestLogin1` erteilt anschließend `TAKE OWNERSHIP` die `TestLogin2`-Berechtigung für die XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="6c983-162">`TestLogin1` then gives `TAKE OWNERSHIP` permission on the XML schema collection to `TestLogin2`.</span></span>  
  
-   <span data-ttu-id="6c983-163">`TestLogin2` wird zum Besitzer der XML-Schemaauflistung im `myOtherDBSchema`, ohne dass das relationale Schema der XML-Schemaauflistung geändert wird.</span><span class="sxs-lookup"><span data-stu-id="6c983-163">`TestLogin2` becomes the owner of the XML schema collection in `myOtherDBSchema`, without changing the relational schema of the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 with password='SQLSvrPwd1'  
GO  
CREATE LOGIN TestLogin2 with password='SQLSvrPwd2'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
-- Create users in the database. Note TestLogin2's default schema is  
-- myOtherDBSchema.  
CREATE USER TestLogin1  
GO  
CREATE USER TestLogin2 WITH DEFAULT_SCHEMA=myOtherDBSchema  
GO  
-- TestLogin2 will own myOtherDBSchema relational schema.  
ALTER AUTHORIZATION ON SCHEMA::myOtherDBSchema TO TestLogin2  
GO  
  
-- For TestLogin1 to create XML schema collection, the following  
-- permission is required.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- Now TestLogin1 can create an XML schema collection.  
setuser 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
 <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"   
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
 </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Grant TAKE OWNERSHIP to TestLogin2.  
SETUSER  
GO  
GRANT TAKE OWNERSHIP ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Verify the owner. Note the UserName and Principal_id is null.   
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections   
      JOIN sys.schemas   
      ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- TestLogin2 can take ownership now.  
setuser 'TestLogin2'  
GO  
ALTER AUTHORIZATION ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Note that although TestLogin2 is the owner,the XML schema collection   
-- is still in dbo.  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
      sys.schemas.name as RelSchemaName,*   
FROM sys.xml_schema_collections JOIN sys.schemas   
     ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
  
-- TestLogin2 moves the collection from dbo to myOtherDBSchema relational schema.  
-- TestLogin2 already has all necessary permissions.  
-- 1) TestLogin2 owns the destination relational schema so he can alter it.  
-- 2) TestLogin2 owns the XML schema collection (therefore, has CONTROL permission).  
ALTER SCHEMA myOtherDBSchema  
TRANSFER XML SCHEMA COLLECTION::dbo.myTestSchemaCollection  
GO  
  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections JOIN sys.schemas   
       ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
DROP LOGIN TestLogin2  
go   
```  
  
### <a name="e-granting-view-definition-permission-on-an-xml-schema-collection"></a><span data-ttu-id="6c983-164">E.</span><span class="sxs-lookup"><span data-stu-id="6c983-164">E.</span></span> <span data-ttu-id="6c983-165">Erteilen der VIEW DEFINITION-Berechtigung für eine XML-Schemaauflistung</span><span class="sxs-lookup"><span data-stu-id="6c983-165">Granting VIEW DEFINITION permission on an XML schema collection</span></span>  
 <span data-ttu-id="6c983-166">Im folgenden Beispiel wird gezeigt, wie VIEW DEFINITION-Berechtigungen für eine XML-Schemaauflistung erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="6c983-166">The following example shows how to grant VIEW DEFINITION permissions for an XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
IF EXISTS( SELECT * FROM sysdatabases WHERE name='permissionsDB' )  
   DROP DATABASE permissionsDB  
GO  
IF EXISTS( SELECT * FROM sys.sql_logins WHERE name='schemaUser' )  
   DROP LOGIN schemaUser  
GO  
CREATE DATABASE permissionsDB  
GO  
CREATE LOGIN schemaUser WITH PASSWORD='Pass#123',DEFAULT_DATABASE=permissionsDB  
GO  
GRANT CONNECT SQL TO schemaUser  
GO  
USE permissionsDB  
GO  
CREATE USER schemaUser WITH DEFAULT_SCHEMA=dbo  
GO  
CREATE XML SCHEMA COLLECTION MySC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns"  
xmlns:ns="http://ns">  
  
   <simpleType name="ListOfIntegers">  
      <list itemType="integer"/>  
   </simpleType>  
  
   <element name="root" type="ns:ListOfIntegers"/>  
  
   <element name="gRoot" type="gMonth"/>  
  
</schema>  
'  
GO  
-- schemaUser cannot see the contents of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
  
-- Grant schemaUser VIEW DEFINITION and REFERENCES permissions  
-- on the XML schema collection.  
SETUSER  
GO  
GRANT VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
GRANT REFERENCES ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
-- Now schemaUser can see the content of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
-- Revoke schemaUser VIEW DEFINITION permissions  
-- on the XML schema collection.  
SETUSER  
GO  
REVOKE VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC FROM schemaUser  
GO  
-- Now schemaUser cannot see the contents of   
-- the collection.  
setuser 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c983-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c983-167">See Also</span></span>  
 <span data-ttu-id="6c983-168">[XML-Daten &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c983-168">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="6c983-169">[Vergleichen von typisiertem XML mit nicht typisiertem XML](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="6c983-169">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="6c983-170">[XML-Schemaauflistungen &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6c983-170">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="6c983-171">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="6c983-171">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
